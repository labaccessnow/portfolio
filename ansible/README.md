# Ansible

Idempotent provisioning and configuration management for network and compute —
environments rebuilt from a repository, not hand-assembled.

## Patterns I use
- **One role, many machines** — a single reusable role provisions multiple VM types from
  per-host variables (Windows DC, Linux, network appliances) on Proxmox.
- **Unattended bring-up** — automated OS install, Active Directory promotion, and serial-driven
  setup of appliances that have no API on day zero.
- **Safe by default** — nothing changes unless explicitly requested; secrets stay out of the
  repo (SOPS-encrypted).
- **Network device config** — `cisco.ios` / `community.*` collections against live gear.

## Where the platform is (2024–2026)
**Ansible Automation Platform 2.5** unified execution (playbooks) and **Automation Decisions**
(**Event-Driven Ansible**) in one control plane — rulebooks react to webhooks/ITSM/observability
events and remediate automatically, moving network ops from scheduled runs toward event-driven.
**Execution environments** (containerized, versioned dependency bundles) are now the standard unit
of portability across dev, CI, and the controller. My provisioning work fits that model directly:
pinned collections, reproducible environments, and a clear path to event-driven remediation.

## Reference
**[ise-demo-enclave](https://github.com/labaccessnow/ise-demo-enclave)** — one role builds both a
Windows Domain Controller and a Cisco ISE node, fully unattended, end to end.
