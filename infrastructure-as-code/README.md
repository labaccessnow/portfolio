# Infrastructure as Code

Declarative, version-controlled infrastructure — reproducible environments instead of
snowflakes, rebuildable from scratch.

## Stack
- **Provisioning** — Terraform / OpenTofu and Pulumi for cloud and virtualization.
- **Private cloud** — Proxmox + SDN as a programmable substrate (VMs, VLANs, zones).
- **GitOps / CI-CD** — GitHub Actions: a commit triggers validation and a push-to-deploy;
  infrastructure changes go through the same review as application code.
- **State & secrets** — idempotent applies, remote/locked state in shared environments,
  and SOPS-encrypted config kept in git.

## Where the ecosystem is (2024–2026)
This space moved fast. HashiCorp's 2023 **BSL relicense** of Terraform triggered the **OpenTofu**
fork (now a Linux Foundation / **CNCF** project, with its own features like native **state
encryption**); **IBM completed its $6.4B acquisition of HashiCorp** in December 2024. For end-user
teams running their own infrastructure the BSL is largely a non-issue, but it reshaped the tooling
around Terraform — so I track both Terraform and OpenTofu and keep configurations portable rather
than betting a stack on one vendor's license terms.

If it runs here, it is defined in a repository — and can be torn down and rebuilt deterministically.
