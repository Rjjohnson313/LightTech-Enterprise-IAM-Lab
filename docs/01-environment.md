# 01 — Lab Environment and Scope

## Infrastructure

- **Hypervisor:** VirtualBox; isolated NAT Network `LT-IAM-NET` (`10.10.10.0/24`).
- **Domain Controller:** `LT-DC01` — Windows Server 2025 — `10.10.10.3`.
- **Workstation:** `RJTEST01` — Windows 11 Pro — `10.10.10.4`.
- **Directory:** `lab.lighttech.internal`; NetBIOS `LIGHTTECH`.
- **Cloud identity:** Okta; on-premise AD Agent installed and connected.

AD DS/DNS readiness and workstation domain join were verified during setup. A prior workstation secure-channel/trust issue was repaired before completing the identity scenarios.

## Test identities and groups

| Identity | Lab purpose |
|---|---|
| `finance.user` | Finance department user |
| `hr.user` | Human Resources department user |
| Honey H. Wells (`hwells`) | Joiner → Mover → Leaver scenario |
| `it.admin`, `it.helpdesk` | Additional directory personas |

All group names use the **`LT-` prefix**, including `LT-Finance-Users`, `LT-HR-Users`, `LT-IT-Administrators`, and `LT-IT-Helpdesk`.

## Boundaries

- Synthetic lab identities, no production data.
- Okta bookmark portals use a placeholder URL to demonstrate group-based access assignment and tile visibility.
- FrostID is a demo SAML SP.
- No M365 tenant, real HRIS, automated access certification, or privileged-access-management platform was integrated.

See [architecture](../architecture/README.md).
