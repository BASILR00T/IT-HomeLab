# Network Diagram

```text
Windows 11 Pro Host
        │
        ▼
Microsoft Hyper-V
        │
        ▼
LAB-SW01 — Internal vSwitch
10.10.10.0/24
        │
        ├───────────────┬────────────────
        │               │
        ▼               ▼
LAB-DC01            LAB-CL01
DC01                CL01
10.10.10.10         10.10.10.20
AD DS + DNS         Windows 10 Education
basilroot.local     Domain joined
DNS: 10.10.10.10   DNS: 10.10.10.10

LAB-LNX01 exists as a reserved VM but is not configured yet.
```

## Current Network Characteristics

- Hyper-V switch type: **Internal**
- Subnet: **10.10.10.0/24**
- Gateway: **Not configured**
- DHCP: **Not configured yet**
- Internal DNS: **10.10.10.10**
