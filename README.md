# IT HomeLab

A hands-on IT home lab built to strengthen my practical IT support, Windows administration, networking, virtualization, and troubleshooting skills while preparing for entry-level IT Support / Help Desk roles.

This repository documents what I build, the issues I intentionally simulate, how I troubleshoot them, and how I verify each solution.

> **Build → Break → Troubleshoot → Fix → Verify → Document**

## Goals

- Refresh and apply core IT support fundamentals.
- Build confidence troubleshooting Windows, hardware, network, and user-access issues.
- Practice Windows Server and Active Directory administration in a small-business-style environment.
- Develop clear technical documentation and ticket-writing habits.
- Prepare for CompTIA A+ and entry-level IT Support / Help Desk work.
- Build a public portfolio of practical, reproducible IT labs.

## Lab Platform

The primary virtualization platform is **Microsoft Hyper-V** running on a Windows 10 host.

### Initial Architecture

```text
Windows 10 Host
└── Hyper-V
    ├── LAB-DC01
    │   └── Windows Server
    │       ├── Active Directory Domain Services
    │       ├── DNS
    │       └── DHCP (planned)
    │
    ├── LAB-CL01
    │   └── Windows 10 Client
    │       └── Domain-joined workstation
    │
    └── LAB-LNX01
        └── Ubuntu
            └── Linux and networking practice
```

The environment will expand only when a lab requires it.

## Repository Structure

```text
IT-HomeLab/
├── README.md
├── docs/
│   ├── architecture.md
│   ├── environment.md
│   └── network-plan.md
├── labs/
│   ├── 01-hyper-v/
│   ├── 02-windows-server/
│   ├── 03-active-directory/
│   ├── 04-dns-dhcp/
│   ├── 05-windows-client/
│   ├── 06-group-policy/
│   ├── 07-file-permissions/
│   ├── 08-network-troubleshooting/
│   ├── 09-windows-troubleshooting/
│   └── 10-linux/
├── scenarios/
│   ├── account-locked/
│   ├── dns-failure/
│   ├── domain-login-failure/
│   ├── gpo-not-applying/
│   ├── no-network-connectivity/
│   └── shared-folder-access/
├── screenshots/
├── templates/
│   ├── lab-template.md
│   └── troubleshooting-template.md
└── media/
    └── linkedin/
        └── templates/
```

## Planned Labs

### Hyper-V & Virtualization
- Enable and validate Hyper-V.
- Create and document virtual switches.
- Build and manage VMs.
- Configure checkpoints appropriately.
- Document VM resource allocation and networking.

### Windows Server
- Install and configure Windows Server.
- Configure server naming and static addressing.
- Install server roles.
- Practice basic server administration.

### Active Directory
- Build a domain controller.
- Create Organizational Units, users, and groups.
- Join Windows clients to the domain.
- Practice account lifecycle and access support.
- Troubleshoot login and domain issues.

### DNS & DHCP
- Configure internal DNS.
- Configure DHCP scopes and leases.
- Simulate name-resolution failures.
- Troubleshoot address-assignment problems.

### Windows Client Support
- Windows installation, drivers, updates, and recovery.
- Local accounts and permissions.
- Device Manager and Event Viewer.
- Storage, performance, startup, and display troubleshooting.
- Printer installation and common printing issues.

### Group Policy
- Create and link basic GPOs.
- Validate policy application.
- Troubleshoot GPO processing issues.

### File & NTFS Permissions
- Shared folders.
- Share vs NTFS permissions.
- Group-based access.
- Missing-access troubleshooting.

### Networking
- IP addressing, subnetting, gateway, DNS, DHCP, MAC, and VLAN fundamentals.
- `ipconfig`, `ping`, `tracert`, `nslookup`, `netstat`.
- Simulated connectivity and DNS failures.

### Linux
- Basic Ubuntu administration.
- Users, permissions, services, networking, and CLI troubleshooting.

## Documentation Standard

Every completed lab or scenario should include:

1. **Scenario** — What is being built or what issue is being simulated.
2. **Objective** — What the lab is intended to prove or practice.
3. **Environment** — Systems, VMs, OS versions, network, and services involved.
4. **Symptoms / Initial State** — What is observed before troubleshooting.
5. **Troubleshooting Process** — Steps taken and the reason for each step.
6. **Root Cause** — Confirmed cause when applicable.
7. **Resolution** — The confirmed fix.
8. **Verification** — Evidence that the system now works as expected.
9. **Evidence** — Screenshots, commands, logs, or configuration outputs.
10. **Key Takeaway** — What was learned.

## Progress

| Area | Status |
|---|---|
| Repository foundation | 🟡 In progress |
| Hyper-V foundation | ⬜ Planned |
| Windows Server | ⬜ Planned |
| Active Directory | ⬜ Planned |
| DNS / DHCP | ⬜ Planned |
| Windows Client | ⬜ Planned |
| Group Policy | ⬜ Planned |
| File Permissions | ⬜ Planned |
| Network Troubleshooting | ⬜ Planned |
| Windows Troubleshooting | ⬜ Planned |
| Linux | ⬜ Planned |

## Background

I am an Associate of Science in Computer and Information Technology candidate at Jubail Industrial College. I am building this lab to turn my academic foundation into consistent, documented practical skill.

## Contact

**Basil Albarazi**  
LinkedIn: https://www.linkedin.com/in/basil-albarazi/
