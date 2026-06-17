# Cisco ACI & Data-Center Fabric

Spine-leaf data-center fabric design, policy, and automation — expressing application
intent (which workloads may talk, on which ports) instead of hand-plumbing VLANs and ACLs.

## What I do
- **Logical design** — tenants, VRFs, bridge domains, EPGs/ESGs, and contracts.
- **Fabric automation** — programmatic configuration through the APIC REST API (IaC, not GUI clicks).
- **Service integration** — wiring compute and L4-L7 services into the fabric.
- **Migration** — moving workloads off traditional three-tier into a spine-leaf fabric.

## Best practices I follow
- **Start network-centric, move to app-centric** — don't try to model every contract on day one;
  migrate into EPG/ESG segmentation as you learn the traffic.
- **Disciplined naming + contract hygiene** — reusable filters, scoped contracts, avoid
  permit-any "preferred group" sprawl.
- **Automate the fabric** — APIC API + version control; the GUI is for reading, not building.
- **Operate from Nexus Dashboard** — assurance/insights, not box-by-box CLI.

## Recent direction (dated)
- **Dec 2023 → 2024:** Cisco acquires **Isovalent** (eBPF/Cilium), extending the intent model
  into cloud-native and container networking.
- **2024–2025:** Cisco consolidates data-center ops under **Nexus Dashboard** and the **"Nexus
  One"** model — one management/policy plane across **both ACI and NX-OS VXLAN EVPN** (Group
  Policy Objects + Border Gateways), as the industry standardizes on open **VXLAN/EVPN**.
- **Late 2025 → 2026:** ACI 6.1.x / 6.2 and Nexus Dashboard 4.x carry that convergence forward.

I keep current on both stacks — the ACI policy model I know well, and the VXLAN-EVPN +
Nexus Dashboard direction it's converging toward — so a fabric design today doesn't get stranded.
