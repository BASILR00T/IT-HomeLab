# Network Plan

## Current Lab Network

| Item | Value |
|---|---|
| Hyper-V switch | `LAB-SW01` |
| Switch type | Internal |
| Subnet | `10.10.10.0/24` |
| Gateway | Not configured |
| DNS server | `10.10.10.10` |
| DHCP | Not configured yet |

## Addressing

| System | Hyper-V VM | Hostname | IP | Gateway | DNS |
|---|---|---|---|---|---|
| Domain Controller | `LAB-DC01` | `DC01` | `10.10.10.10` | None | `10.10.10.10` |
| Windows Client | `LAB-CL01` | `CL01` | `10.10.10.20` | None | `10.10.10.10` |
| Linux VM | `LAB-LNX01` | TBD | TBD | TBD | TBD |

## Active Directory Namespace

- AD domain: **`basilroot.local`**
- NetBIOS name: **`BASILROOT`**

## Current Scope

The first milestone uses static addressing on an isolated internal Hyper-V network. Internet routing and DHCP are intentionally outside the current completed scope and will be added only when required by later labs.
