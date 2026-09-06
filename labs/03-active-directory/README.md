# Active Directory

**Status:** Foundation complete

## Milestone 01 — Active Directory Foundation

### Objective

Build and validate a small Windows domain environment on Microsoft Hyper-V that can support future IT administration and troubleshooting labs.

### Environment

- Hyper-V switch: `LAB-SW01` (Internal)
- Subnet: `10.10.10.0/24`
- Domain Controller: `DC01` / `10.10.10.10`
- Server OS: Windows Server 2022 Datacenter Evaluation
- Domain: `basilroot.local`
- NetBIOS: `BASILROOT`
- Client: `CL01` / `10.10.10.20`
- Client OS: Windows 10 Education
- Client DNS: `10.10.10.10`

### Completed

- Created the Hyper-V internal lab network.
- Built the Windows Server VM and configured static addressing.
- Installed Active Directory Domain Services and DNS.
- Promoted `DC01` as the first Domain Controller for `basilroot.local`.
- Created a domain user account.
- Joined `CL01` to the domain.
- Successfully signed in to the client with a domain user account.

### Validation

The milestone was validated by confirming:

- Active Directory Users and Computers loads the `basilroot.local` domain.
- `CL01` resolves the domain through `DC01` DNS.
- `CL01` successfully joins `basilroot.local`.
- A domain user can authenticate and sign in on `CL01`.

### Current Limitations / Next Steps

- DHCP is not configured yet.
- No gateway is currently configured for the internal lab network.
- `LAB-LNX01` exists but its OS and network configuration are still pending.
- Future labs will expand into OUs, groups, Group Policy, permissions, and troubleshooting scenarios.

This page intentionally documents the working milestone rather than reproducing a step-by-step installation tutorial.
