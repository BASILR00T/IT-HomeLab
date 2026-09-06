# Windows Client

**Status:** Domain foundation complete

## Current Client

| Item | Value |
|---|---|
| Hyper-V VM | `LAB-CL01` |
| Hostname | `CL01` |
| OS | Windows 10 Education |
| RAM | 4 GB |
| Disk | 40 GB Dynamic VHDX |
| IP | `10.10.10.20` |
| DNS | `10.10.10.10` |
| Domain | `basilroot.local` |

## Completed

- Installed and configured the Windows client.
- Renamed the client to `CL01`.
- Configured static addressing and internal DNS.
- Joined `CL01` to `basilroot.local`.
- Confirmed successful domain-user sign-in.

The client will be reused as the primary target for future Group Policy, permissions, user-support, and troubleshooting scenarios.
