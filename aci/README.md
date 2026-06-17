# Cisco ACI & Data-Center Fabric

Spine-leaf data-center fabric design, policy, and automation — expressing application
intent (who can talk to whom) instead of hand-plumbing VLANs and ACLs.

## What I work on
- **Logical design** — tenants, VRFs, bridge domains, EPGs, and contracts.
- **Fabric automation** — programmatic configuration through the APIC REST API.
- **Service integration** — wiring compute and L4-L7 services into the fabric.
- **Migration** — moving workloads off traditional three-tier into a spine-leaf fabric.

## Where the platform is (2024–2026)
Cisco is converging data-center operations under **Nexus Dashboard** and the **"Nexus One"**
model, which unifies a single management/policy plane across **both ACI and NX-OS VXLAN EVPN**
fabrics (via Group Policy Objects + Border Gateways). The wider industry has been standardizing on
**open VXLAN/EVPN**, and Cisco's 2024 **Isovalent (eBPF)** acquisition extends that intent model
into cloud-native and container networking. I keep current on both stacks — the ACI policy model I
know well, and the VXLAN-EVPN + Nexus Dashboard direction it's converging toward — so a fabric
design today isn't painted into a corner.

Part of broader data-center and network-security engineering.
