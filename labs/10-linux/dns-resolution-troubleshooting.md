# Ubuntu DNS Resolution Troubleshooting

## Problem

`LAB-LNX01` could reach the domain controller by IP address, but initially could not resolve the Active Directory domain name.

Observed behavior:

```text
ping 10.10.10.10
```

worked successfully, while:

```text
ping basilroot.local
```

returned:

```text
Name or service not known
```

This showed that basic IP connectivity between Ubuntu and `DC01` was working, but hostname resolution was not.

## Environment

| Item | Value |
|---|---|
| Linux VM | `LAB-LNX01` |
| Hostname | `LNX01` |
| OS | Ubuntu 24.04.1 Desktop |
| IP | `10.10.10.30` |
| DNS server | `10.10.10.10` |
| Domain Controller | `DC01` |
| DC IP | `10.10.10.10` |
| AD domain | `basilroot.local` |

## Troubleshooting

### 1. Verify basic network connectivity

```bash
ping 10.10.10.10
```

Result: successful.

This confirmed that the VM could reach the domain controller over the lab network.

### 2. Query the DNS server directly

```bash
nslookup basilroot.local 10.10.10.10
```

Result:

```text
Name:    basilroot.local
Address: 10.10.10.10
```

This confirmed that the DNS service on `DC01` was responding correctly and contained a valid record for `basilroot.local`.

### 3. Verify Ubuntu DNS configuration

```bash
resolvectl status
```

Confirmed:

```text
Current DNS Server: 10.10.10.10
DNS Servers: 10.10.10.10
```

So the configured DNS server was correct.

### 4. Inspect the local resolver

```bash
cat /etc/resolv.conf
```

The system was using the `systemd-resolved` local stub resolver:

```text
nameserver 127.0.0.53
search .
```

This is normal on Ubuntu, but it means applications normally query `systemd-resolved` first instead of contacting `10.10.10.10` directly.

### 5. Test the system resolver

```bash
resolvectl query basilroot.local
```

Initially returned:

```text
No appropriate name servers or networks for name found
```

## Cause

The Active Directory domain uses the `.local` suffix.

On Linux systems using `systemd-resolved`, `.local` is treated specially because it is normally reserved for multicast DNS (mDNS). As a result, a normal resolver request for `basilroot.local` was not automatically being routed to the Active Directory DNS server, even though direct DNS queries to `10.10.10.10` worked.

This explains why:

- IP connectivity worked.
- Direct `nslookup` against `10.10.10.10` worked.
- Normal hostname resolution initially failed.

## Resolution

A routing domain was assigned to the Ubuntu network interface so that requests for `basilroot.local` would be sent through the configured DNS path:

```bash
sudo resolvectl domain eth0 "basilroot.local"
```

The resolver was then tested again:

```bash
resolvectl query basilroot.local
```

Result:

```text
basilroot.local: 10.10.10.10
```

The hostname-resolution issue was subsequently confirmed resolved.

## Key Takeaway

When Linux can reach an Active Directory DNS server by IP and direct `nslookup` queries succeed, but normal resolution of a `.local` domain fails, the problem may be caused by Linux resolver behavior around `.local` and mDNS rather than by the DNS server itself.

The troubleshooting sequence used here was:

```text
Verify IP connectivity
→ Test DNS directly
→ Confirm configured DNS server
→ Inspect systemd-resolved
→ Identify .local resolver conflict
→ Route the AD domain through the correct interface
→ Verify name resolution
```
