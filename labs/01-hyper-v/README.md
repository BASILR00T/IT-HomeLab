# Hyper-V Foundation

**Status:** Foundation complete

## Completed

- Microsoft Hyper-V enabled and in use on the Windows 11 Pro host.
- Internal virtual switch created: `LAB-SW01`.
- Lab subnet established: `10.10.10.0/24`.
- `LAB-DC01` and `LAB-CL01` created and connected to the internal lab network.
- `LAB-LNX01` reserved for a later Linux lab.

## Current Scope

The first milestone uses an isolated internal Hyper-V network with static addressing. Gateway routing and DHCP are not configured yet.

See `../../docs/architecture.md` and `../../docs/network-plan.md` for the current verified design.
