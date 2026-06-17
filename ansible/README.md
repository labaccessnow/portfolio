# Ansible

Idempotent provisioning and configuration management for network and compute —
environments rebuilt from a repository, not hand-assembled.

## Patterns I use
- **One role, many machines** — a single reusable role provisions multiple VM types from
  per-host variables (Windows DC, Linux, network appliances) on Proxmox.
- **Unattended bring-up** — automated OS install, Active Directory promotion, and serial-driven
  setup of appliances with no API on day zero.
- **Network device config** — `cisco.ios` / `community.*` collections against live gear.

## Best practices I follow
- **Idempotent + check-mode first** — a dry run before any apply; re-running converges, never duplicates.
- **Secrets out of the repo** — SOPS-encrypted; nothing changes unless explicitly requested.
- **Execution environments** — containerized, version-pinned dependency bundles so dev, CI, and
  the controller run identical automation.
- **CI hygiene** — lint + molecule/test before merge.

## Recent timeline
- **2022:** Event-Driven Ansible developer preview.
- **2023 (AAP 2.4):** Event-Driven Ansible reaches GA — rulebooks react to events.
- **Sep 30, 2024 (AAP 2.5):** unified control plane combining **Automation Execution** (playbooks)
  and **Automation Decisions** (**Event-Driven Ansible**); execution environments standardized.
- **Fall 2025 (AAP 2.6):** continued consolidation of the platform.

The shift is from scheduled runs toward **event-driven remediation** — rulebooks triggered by
webhooks / ITSM / observability. My provisioning work fits that model: pinned collections,
reproducible environments, and a clear path to event-driven actions.

## Reference
**[ise-demo-enclave](https://github.com/labaccessnow/ise-demo-enclave)** — one role builds both a
Windows Domain Controller and a Cisco ISE node, fully unattended, end to end.
