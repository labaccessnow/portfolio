# Identity Services Engine (ISE) & Zero-Trust NAC

Cisco Identity Services Engine as the policy decision point of a Zero-Trust network —
every user and device continuously identified, profiled, and authorized before it
reaches the network, wired or wireless. Maps directly to the CISA Zero Trust pillars
(identity, device, network/segmentation).

## What I do
- **Policy architecture** — authorization policy sets structured by trust tier
  (executives / employees / contractors / guests / IoT), downloadable ACLs, dynamic
  VLAN and SGT assignment.
- **802.1X / EAP-TLS** — certificate-based onboarding against Active Directory and an
  internal CA, MAB fallback for headless/IoT, profiling and posture for compliance.
- **TACACS+ device administration** — role-based command authorization for the estate.
- **Wired + wireless NADs** — Catalyst switches and Catalyst 9800 WLCs as RADIUS clients,
  with CoA so access can be revoked the moment a session goes bad.

## Best practices I follow
- **Phase the rollout**: Monitor Mode → Low-Impact → Closed Mode, so 802.1X never
  black-holes production before policy is proven.
- **EAP-TLS over PEAP/MSCHAP** — certificates, not passwords, as the default.
- **Distributed deployment** — dedicated PAN / MnT / PSN personas; size PSNs for the
  endpoint count and keep two for HA.
- **Revocation is non-negotiable** — CoA wired in so a quarantine action is immediate.
- **Certificate hygiene** — internal CA, automated renewal, no self-signed in production.

## Recent timeline
- **3.3 — Jul 10, 2023:** TLS 1.3 for EAP-TLS.
- **3.4 — Aug 5, 2024:** native Duo identity sync, AD domain-controller prioritization
  with automatic failover, pxGrid Direct (URL Pusher), multiple ACI connectors.
- **3.5 — Sep 18, 2025:** SNMPv3 endpoint profiling for non-authenticating IoT
  (printers, cameras, building automation) and a cloud Multi-Factor Classification profiler.

## Reference build
**[ise-demo-enclave](https://github.com/labaccessnow/ise-demo-enclave)** — a self-contained,
fully automated Cisco **ISE 3.4 + Windows Server AD** lab on Proxmox (one Ansible role builds
both nodes; unattended DC, serial-driven ISE setup). Lead engineer on a production ISE /
Zero-Trust deployment across enterprise and federal networks.
