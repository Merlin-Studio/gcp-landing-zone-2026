# GCP Landing Zones in 2026: There's a Better Way

> If you've ever spent weeks designing a GCP landing zone only to spend months fixing it — this is for you.

---

## The Problem Nobody Talks About Honestly

You know how landing zone projects actually go.

You start with a blank page, or a template from a consultancy built for someone else's requirements. You make decisions about folder structure, networking, IAM, security policies — each one seems reasonable in isolation. Then six months in, someone finds that the networking decision you made early on conflicts with a compliance requirement nobody flagged at the start. Or the CMEK configuration looks correct in code but was never actually wired to the service agents. Or the budget alerts were silently failing because a currency code was missing.

None of this is a skills problem. These are **structural problems** — what happens when 16 interconnected decisions get made in isolation, across spreadsheets, Slack threads, and tribal knowledge, without a process that connects them.

A decision in networking affects your security posture. Your security posture shapes your compliance readiness. Your compliance requirements drive encryption and audit logging. Pull one thread and the whole thing moves.

Most tools don't solve this. They give you more Terraform to write and leave the design problem to you.

We built [Merlin Studio](https://site.merlin-studio.cloud) to solve the design problem.

![Merlin: Right-Sized GCP Foundations in 3 Phases — Discover, Design, Generate](images/infographic.png)
*Structured discovery → guided configuration across 16 domains → production-ready FAST output. Right-sized for your actual organization, not a Fortune 500 template.*

---

## Before and After

Here's what the difference looks like in practice:

| Without Merlin | With Merlin |
|---|---|
| Weeks editing YAML and HCL, tracing module dependencies, commenting out what you don't need — hoping nothing breaks downstream | Guided wizard across 16 domains with three modes — Express for smart defaults, Guided for explanations, Expert for full control. No raw code editing. |
| One-size-fits-all enterprise template. A 15-VM shop gets the same 8-folder hierarchy and hub-and-spoke network as a Fortune 500 bank. | Discovery-driven profiles — Simple, Standard, or Advanced — calibrated defaults for hierarchy, IAM, networking, and security that match your actual organization. |
| Compliance mapped in spreadsheets. Manual checklists for SOC 2, HIPAA, FedRAMP. Controls verified during audits — not during design. | Select your frameworks and Merlin applies 370+ field-level compliance upgrades automatically — CMEK, VPC-SC, DLP, data residency — all traceable to their regulatory source. |
| Security validation happens after deployment. Broad IAM roles, missing org policies, and encryption gaps discovered in the first audit — or the first breach. | Six validation layers run before you deploy — architecture scorecard, operational readiness, cross-section consistency, HCL syntax, parser checks, and Checkov static analysis. |

---

## Your Profile Is Determined by Your Answers

The most important thing Merlin does early is right-size your architecture. Answer the discovery questions honestly — team size, compliance requirements, connectivity needs, data sensitivity — and Merlin calibrates the right complexity level for you. No manual selection, no guessing.

![Merlin profile cards — Simple (1-2 hours), Standard (4-8 hours), Advanced (1-2 weeks)](images/profiles.png)
*Three profiles, each with calibrated defaults. Your discovery answers determine which one fits — you don't have to choose blindly.*

**Simple** — single team, cloud-native workloads, no regulatory requirements. Two folders, standalone networking, secure defaults. Done in 1–2 hours. If this is you, don't add complexity you don't need.

**Standard** — multiple teams or environments, compliance requirements (SOC 2, ISO, PCI, HIPAA), hub-and-spoke networking, optional hybrid connectivity. Where most production deployments land. Plan 4–8 hours.

**Advanced** — complex multi-BU structure, strict compliance (FedRAMP, NIST 800-53, GDPR), Interconnect, VPC Service Controls, CMEK encryption, policy-as-code. 1–2 weeks — and that's appropriate, because the decisions genuinely require that care.

---

## Discovery First — Everything Else Follows

Before any configuration begins, Merlin walks you through 7 categories of structured questions. This is not a form — it's the foundation that every downstream decision depends on.

![Merlin Cloud Foundation Discovery — Business Profile, step 1 of 7](images/msp-BusinessProfile.png)
*Each question includes context and examples so stakeholders can contribute without deep GCP expertise. No blank-page requirements gathering.*

The 7 categories cover Business Profile, Identity & Billing, Technical Profile, Compliance & Security, Infrastructure Requirements, Workload Profile, and Preferences. Every answer feeds into the profile recommendation and into the configuration defaults that follow.

Skipping or rushing this step is the root cause of the inconsistencies that lead to costly rework. A compliance requirement missed in discovery doesn't show up until it forces a redesign of networking and folder hierarchy simultaneously.

---

## Configuration That Actually Guides You

Once discovery is complete, Merlin walks you through all 16 technical domains. Three modes let you control depth per section:

![Merlin Discovery Complete — Simple profile recommended, with Express / Guided / Expert mode selector](images/msp-DiscoveryComplete-1.png)
*Profile is set from your discovery answers. Then choose your working mode — Express accepts smart defaults in one click, Guided explains each recommendation, Expert exposes every Terraform variable.*

- **Express** — pre-filled defaults based on your discovery answers and profile. One click per section. About 30% of Guided mode time. Right for sections where defaults fit your context.
- **Guided** — each setting shows Merlin's recommendation with an explanation of why. Accept or override with full context on trade-offs. The default for most production deployments.
- **Expert** — every field expanded, Terraform variable names visible alongside each setting. Advanced options exposed: VPC peering, custom DNS, MTU, flow logs. Built for architects who need full control.

Switch modes freely between domains — use Express for naming and preferences, Expert for networking and IAM. You never lose your work.

---

## Compliance Wired In — Not Added Later

This is where most approaches fail. Compliance isn't a checklist you apply at the end — it's a set of architectural constraints that affect decisions across every domain. Merlin applies compliance framework controls before configuration, so your output is compliant from the start.

![Merlin Compliance Configuration — FedRAMP selected, Data Access Logs enabled with SOC2/FedRAMP/NIST/SOX badges](images/msp-ComplianceSecurity.png)
*Every setting shows which regulatory frameworks require it. Select FedRAMP and CMEK, VPC Service Controls, specific audit retention, and locked org policies are applied automatically — all traceable to their regulatory source.*

Select FedRAMP and Merlin enforces CMEK, VPC Service Controls, specific audit log retention, and locked org policies. Select HIPAA and it enforces PHI access controls and encryption requirements. Select PCI-DSS and it enforces network segmentation and cardholder data environment isolation. Eleven frameworks supported: CIS, SOC 2, ISO 27001, HIPAA, PCI-DSS v4.0, FedRAMP, NIST 800-53, SOX, GDPR, NIS2, EUCS.

No spreadsheets. No manual checklists. No gaps discovered during an audit.

---

## One Click. Everything You Need to Deploy.

When your design is complete, generation takes seconds.

![Merlin Generated Artifacts — 63 files across org-setup, project-factory, VPC-SC, CMEK stages with inline YAML preview](images/gen-results-2.png)
*63 files covering all FAST stages — browse and preview every artifact before downloading. Hand the output directly to your infrastructure team or feed it into CI/CD.*

The output package includes FAST YAML datasets for all Google Cloud Foundation Fabric stages (org-setup, networking, security, project-factory, VPC Service Controls, CMEK), or classic Terraform `.tfvars` if you prefer. Plus architecture diagrams, a full README, a CMEK wiring guide with post-deployment `gcloud` commands, and scorecards.

![Merlin Security and Architecture Scorecards — 100/100 Checkov, 89/100 Architecture, 17 checks passed, 2 failed with explanations](images/gen-results-1.png)
*Six validation layers run before you deploy. Every check is explained — not just flagged. You know exactly what to fix before a single resource is created.*

The architecture scorecard runs 26+ weighted checks across IP planning, multi-region readiness, GKE configuration, hybrid connectivity, naming, IAM, encryption, org policies, and logging. The security scan runs Checkov static analysis plus manual GCP-specific checks. Every failure has an explanation and a fix.

The diagrams come from your actual configuration — not generic templates:

![Merlin Architecture Diagrams — Resource Hierarchy, Network Topology, IAM Identity from Mermaid](images/msp-diagrams-1.png)
*Resource hierarchy, network topology, and IAM identity — generated automatically from your design.*

---

## Requirements Change. Merlin Handles That.

Every configuration is saved and versioned. When requirements shift — and they always do — update your inputs and regenerate. Terraform, documentation, architecture diagrams, and scorecards all stay in sync. You can create multiple versions of the same landing zone and compare diffs. You never lose previous work.

---

## Going Deeper

- **Healthcare, fintech, insurance** → [GCP Landing Zone for Regulated Industries](../gcp-landing-zone-regulated/) — HIPAA, PCI-DSS, SOC 2
- **Government** → GCP Landing Zone for Government — FedRAMP and NIS2/GDPR *(coming soon)*
- **Startups** → GCP Cloud for Startups — fast to production *(coming soon)*

---

## Try It — Two Weeks Free

See what your landing zone should look like before you write a single line of Terraform.

→ **[Request free preview access](https://site.merlin-studio.cloud/#preview-form)**

*Free two-week preview · No credit card required*

---

© 2026 Merlin Studio. Licensed under [CC BY-ND 4.0](https://creativecommons.org/licenses/by-nd/4.0/).
