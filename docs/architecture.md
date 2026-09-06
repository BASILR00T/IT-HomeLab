# Home Lab Architecture

## Current Architecture

```text
Windows 11 Pro Host
└── Microsoft Hyper-V
    └── LAB-SW01 (Internal)
        └── 10.10.10.0/24
            ├── LAB-DC01
            │   └── DC01
            │       ├── Windows Server 2022 Datacenter Evaluation
            │       ├── 10.10.10.10
            │       ├── Active Directory Domain Services
            │       └── DNS
            │
            ├── LAB-CL01
            │   └── CL01
            │       ├── Windows 10 Education
            │       ├── 10.10.10.20
            │       ├── DNS: 10.10.10.10
            │       └── Domain: basilroot.local
            │
            └── LAB-LNX01
                └── Reserved VM — OS and network configuration pending
```

## Design Notes

- `LAB-SW01` is an Internal Hyper-V virtual switch.
- The current lab has no configured gateway.
- `DC01` provides DNS for the lab and hosts the `basilroot.local` Active Directory domain.
- `CL01` is a domain-joined Windows client used for administration and troubleshooting scenarios.
- DHCP is planned but not part of the current completed milestone.
- The environment will expand only when a later lab requires additional services or systems.
