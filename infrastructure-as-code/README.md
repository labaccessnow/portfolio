# Infrastructure as Code

Declarative, version-controlled infrastructure — reproducible environments instead of
snowflakes, rebuildable from scratch.

## Stack
- **Provisioning** — Terraform / OpenTofu and Pulumi for cloud and virtualization.
- **Private cloud** — Proxmox + SDN as a programmable substrate (VMs, VLANs, zones).
- **GitOps / CI-CD** — GitHub Actions: a commit triggers validation and a push-to-deploy.

## Best practices I follow
- **Remote, locked state** — never local state in a shared environment; encrypt it at rest.
- **Plan in CI** — every change runs `plan` + static analysis + (where it fits) cost estimation
  before apply, reviewed like application code.
- **Policy-as-code** — guardrails (OPA / Sentinel-style) instead of tribal knowledge.
- **Drift detection** — reconcile reality against the repo on a schedule; the repo is the truth.
- **Stay portable** — modules and provider abstractions over single-vendor lock-in.

## Recent timeline (the license shake-up, dated)
- **Aug 10, 2023:** HashiCorp relicenses Terraform from MPL to the **BSL**.
- **Aug–Sep 2023:** the community forks it (OpenTF → **OpenTofu**), moved under the **Linux Foundation**.
- **Jan 2024:** OpenTofu **1.6 GA** (drop-in fork); later **1.7** adds native **state encryption**.
- **Apr 24, 2024:** IBM announces a **$6.4B acquisition of HashiCorp**.
- **Feb 27, 2025:** the IBM/HashiCorp deal **closes** after regulatory review.
- **2025:** OpenTofu joins the **CNCF**; large orgs migrate.

For teams running their own infrastructure the BSL is largely a non-issue, but it reshaped the
tooling — so I track both Terraform and OpenTofu and keep configs portable rather than betting a
stack on one vendor's license terms. If it runs here, it's defined in a repo and rebuildable from scratch.
