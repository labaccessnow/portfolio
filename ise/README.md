# Identity Services Engine (ISE) & Zero-Trust NAC

Designing and operating Cisco Identity Services Engine as the policy core of a
Zero-Trust network — every user and device is continuously identified, profiled,
and authorized before it reaches the network, wired or wireless.

## What I work on
- **Policy architecture** — authentication / authorization policy sets, downloadable
  ACLs and dynamic VLAN assignment, profiling, and posture.
- **802.1X / EAP-TLS** — certificate-based onboarding against Active Directory and an
  internal CA, with MAB fallback for headless and IoT endpoints.
- **TACACS+ device administration** — role-based command authorization for the network
  estate (ISE remains the one NAC platform that also does TACACS+).
- **Wired + wireless NADs** — Catalyst switches and Catalyst 9800 WLCs as RADIUS clients,
  including CoA / change-of-authorization.
- **Lifecycle & HA** — certificate management, AD/LDAP/MFA integration, distributed deployment.

## Where the platform is (2024–2026)
I track the releases closely. **ISE 3.3/3.4** brought **TLS 1.3 for EAP-TLS**, native **Duo**
identity sync, Active Directory domain-controller prioritization with automatic failover, and
**pxGrid Direct**; **ISE 3.5 (2025)** added **SNMPv3 endpoint profiling** for gear that can't
authenticate (printers, cameras, building automation) and a **cloud Multi-Factor Classification**
profiler. The broader direction is identity-driven Zero Trust spanning wired, wireless, VPN, and
ZTNA — and ISE deployed cloud-side, not just as an appliance.

## Reference build
**[ise-demo-enclave](https://github.com/labaccessnow/ise-demo-enclave)** — a self-contained,
fully automated **Cisco ISE 3.4 + Windows Server AD** lab on Proxmox. One Ansible role provisions
both nodes, the DC promotes unattended (forest + DNS + authoritative NTP), and ISE setup is driven
over serial. Lead engineer for a production ISE / Zero-Trust deployment across enterprise and federal networks.
