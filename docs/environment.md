# Lab Environment

This document records the verified hardware and software currently used by the IT HomeLab.

## Host

| Item | Value |
|---|---|
| Host OS | Windows 11 Pro |
| Hypervisor | Microsoft Hyper-V |
| CPU | AMD Ryzen 5 5625U with Radeon Graphics |
| RAM | 16 GB |
| VM storage location | `D:` |

## Virtual Machines

| Hyper-V VM | Hostname | OS | Role | RAM | Disk | Status |
|---|---|---|---|---:|---:|---|
| `LAB-DC01` | `DC01` | Windows Server 2022 Datacenter Evaluation | AD DS / DNS | 4 GB | 40 GB Dynamic VHDX | Active |
| `LAB-CL01` | `CL01` | Windows 10 Education | Domain-joined client | 4 GB | 40 GB Dynamic VHDX | Active |
| `LAB-LNX01` | TBD | OS not installed yet | Linux / network testing | TBD | TBD | Reserved / pending |

## Notes

- Virtual processor counts are intentionally not documented yet because they were not explicitly verified.
- DHCP is not configured yet.
- The Linux VM exists in Hyper-V, but its operating system and network configuration are still pending.
