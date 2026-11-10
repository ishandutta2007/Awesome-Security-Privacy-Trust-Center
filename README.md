# Awesome-Security-Privacy-Trust-Center

# Awesome Security, Privacy & Trust Center

> A curated list of top Security, Privacy and Trust Center platforms — both SaaS/Hosted commercial solutions and open-source alternatives for publishing compliance posture, answering security questionnaires, and managing trust with customers.
> 🌟 Star this repo if you find it useful! 🌟

---

## 📋 Table of Contents

- [SaaS / Hosted Platforms](#-saas--hosted-platforms)
  - [SafeBase](#safebase)
  - [Conveyor](#conveyor)
  - [Whistic](#whistic)
  - [Vanta Trust Center](#vanta-trust-center)
  - [Drata Trust Center](#drata-trust-center)
  - [OneTrust Trust Center](#onetrust-trust-center)
  - [TrustArc](#trustarc)
- [Open-Source Software](#-open-source-software)
  - [Kodus Trust Center](#kodus-trust-center)
  - [Probo](#probo)
  - [QResponder](#qresponder)
  - [Questionnaire-Responder](#questionnaire-responder)
  - [OpenWatch](#openwatch)
  - [CompliEdge](#compliedge)
  - [evidentia](#evidentia)
- [Comparison at a Glance](#-comparison-at-a-glance)
- [Contributing](#-contributing)

---

## 🟦 SaaS / Hosted Platforms

Commercial, cloud-hosted Security, Privacy and Trust Center platforms. These are not open-source but are included as reference points for feature comparison.

### SafeBase
**Type:** Trust center platform with AI questionnaire automation
SafeBase is a leading commercial trust center platform, providing a public-facing security posture page alongside AI-assisted questionnaire response and document access controls. It is the primary commercial reference for open-source alternatives like Kodus Trust Center [citation:6].

### Conveyor
**Type:** Trust center and security review automation
Conveyor provides a trust center for publishing compliance posture, alongside a security questionnaire automation workflow that helps sales and security teams respond faster to customer inquiries.

### Whistic
**Type:** Vendor security assessment and trust management
Whistic focuses on vendor security assessments and trust management, helping organizations respond to security questionnaires and manage third-party risk from a centralized platform.

### Vanta Trust Center
**Type:** Trust center within compliance automation suite
Vanta's Trust Center extends its compliance automation platform with a public-facing trust page, allowing organizations to showcase SOC 2, ISO 27001, and other certifications alongside security posture information.

### Drata Trust Center
**Type:** Trust center within Drata compliance platform
Drata provides a Trust Center as part of its compliance automation offering, enabling organizations to publish their security posture and certifications without building a separate portal.

### OneTrust Trust Center
**Type:** Privacy-focused trust center within OneTrust suite
OneTrust provides a Trust Center as part of its broader privacy management platform, focused on consent, data mapping, and privacy certifications.

### TrustArc
**Type:** Privacy certification and trust center
TrustArc provides privacy compliance certifications and a trust center for publishing certification status to customers and partners.

---

## 🟩 Open-Source Software

Self-hosted, community-driven Security, Privacy and Trust Center tools. The open-source ecosystem **splits** between **trust center builders** (Kodus Trust Center), **GRC platforms with public compliance pages** (Probo), and **questionnaire automation engines** (QResponder, Questionnaire-Responder).

### Kodus Trust Center
**Stack:** Next.js / TypeScript / Supabase | **License:** Open Source
Kodus Trust Center is a **free, self-hosted, YAML-driven trust center builder** that lets you paste your security program into a single YAML document and instantly expose a polished trust portal [citation:6]. Features include:
- **Public trust center** with theming (light/dark), company logo, hero commitments, metrics, compliance cards, policies, documents, infrastructure, monitoring, updates, FAQs accordion, subprocessors, and contacts [citation:6]
- **Document requests** via modal collecting work email and context, stored in Supabase [citation:6]
- **Admin dashboard** with tabs for requests and YAML editor, GitHub SSO via NextAuth [citation:6]
- **YAML schema** with layout control (sections can be `full`/`half` width or hidden entirely) [citation:6]

Everything lives in your repo or Supabase project, deployable to Vercel, Fly, Render, or any Next.js host [citation:6]. The project explicitly positions itself as "no paid SaaS, no vendor lock-in" [citation:6].
**Best for:** Small to mid-sized teams wanting a self-hosted trust center that can be edited via YAML by sales and security teams, without a commercial subscription.

### Probo
**Stack:** Go / PostgreSQL / GraphQL / Docker | **License:** ISC
Probo is an open-source **Governance, Risk, and Compliance (GRC) platform** with a built-in **Compliance Page** for public trust center publishing [citation:15]. It covers the full GRC lifecycle including risk management, controls, vendor risk, data privacy, access reviews, audit programs, and document approval workflows [citation:15]. The Compliance Page supports public compliance portal publishing, NDA management, certification publishing, and custom domain support [citation:15]. Every entity is accessible via web console, `prb` CLI (44+ command groups), **270+ MCP tools** for AI agent integration, GraphQL API, and an n8n community node [citation:15]. Audit-ready features include policy-based RBAC, immutable audit logs, electronic document sign-off, and evidence chains [citation:15].
**Best for:** Organizations wanting a self-hosted GRC platform that includes a public compliance page alongside full internal compliance management, with strong AI agent accessibility via MCP.

### QResponder
**Stack:** Python / FastAPI / Local-first | **License:** Open Source
QResponder is a **local-first, self-hostable security questionnaire automation** tool that generates grounded, cited answers from your own knowledge base [citation:2]. Key privacy guarantees: connector credentials live in `.env` on the server and are never sent to the browser; connectors run only on explicit `connect`, never during answering; local answering stays zero-egress [citation:2]. Supports OAuth connections to Notion, Google Drive, and Confluence, plus paste-a-token paths [citation:2]. The answering path (Tier-1 → hybrid retrieval + rerank → grounded generation → faithfulness → abstain) never makes external fetches unless you configure a cloud model; with a local model, zero external calls are made [citation:2]. Includes per-run source include/exclude filters and an audit trail recording effective sources used [citation:2].
**Best for:** Security teams wanting questionnaire automation with strict data boundary guarantees, where internal policies never leave the host unless explicitly configured.

### Questionnaire-Responder
**Stack:** Python / SQLite / Streamlit | **License:** Open Source
Questionnaire-Responder turns a vendor security questionnaire spreadsheet into a first-pass draft, **citing your own security docs for every answer and never inventing a control you do not have** [citation:7]. It includes a **documentation gap report** that analyzes unanswered questions to reveal what your policy set does not document — a second product hiding in the NOT_FOUND rows: "find out what you need to write before a customer asks" [citation:7]. Multi-client workspaces keep consultant or vCISO client evidence structurally isolated at the storage layer (separate directories, separate SQLite stores), making cross-workspace contamination structurally impossible [citation:7]. Includes a Streamlit review UI for approving, editing, or rejecting drafted answers with verbatim cited evidence and confidence badges [citation:7].
**Best for:** Consultants and vCISOs answering questionnaires for multiple clients, needing strict workspace isolation and gap analysis to improve documentation.

### OpenWatch
**Stack:** Go / PostgreSQL / React | **License:** Open Source
OpenWatch is a **continuous compliance platform** for Linux fleets under CIS, STIG, NIST 800-53, NIST 800-171, CMMC Level 2, and PCI DSS [citation:8]. While not a trust center per se, it provides the **audit-ready evidence layer** that a trust center depends on: point-in-time queries answering "Were these 200 servers compliant with STIG on January 15th?" in seconds, backed by machine-verifiable evidence exportable as CSV, JSON, PDF, or OSCAL [citation:8]. Connects to servers over SSH, runs the 779-rule Kensa corpus, and keeps posture as a timeline showing what is passing now, what was passing last Tuesday, and what drifted [citation:8]. Deploys as a single Go binary with embedded React UI, requiring PostgreSQL and 4GB RAM [citation:8].
**Best for:** Linux-centric organizations needing continuous compliance evidence for audits that can feed into trust center claims, without proprietary scanning agents.

### CompliEdge
**Stack:** Python / Django / PostgreSQL | **License:** Open Source
CompliEdge is an enterprise-grade **GRC management system** built with Django, covering governance policies, risk management, compliance frameworks with automated checklists, dashboards, and AI-driven risk prediction [citation:5]. It includes multi-role user management (Admin, Manager, Employee, Auditor), workflow management for policy and risk approvals, two-factor authentication, and comprehensive audit logs [citation:5]. While not a public trust center, it provides the internal governance foundation that supports trust center claims.
**Best for:** Organizations wanting a Django-based GRC platform for internal policy and risk management, with the option to build a trust center on top.

### evidentia
**Stack:** Python | **License:** Open Source
evidentia is an open-source GRC tool covering gap analysis, risk statements, evidence collection, web UI, and compliance automation [citation:10]. Search results are limited; verify current maintenance and feature coverage before adoption.
**Best for:** Teams exploring lightweight GRC tooling with evidence collection capabilities.

---

## 📊 Comparison at a Glance

| Software | License | Stack | Public Trust Page | Questionnaire Automation | Self-Hosted | Best For |
|----------|---------|-------|-------------------|--------------------------|-------------|----------|
| **SafeBase** | Proprietary | Cloud | ✅ | ✅ AI | ❌ | Commercial trust center |
| **Vanta Trust Center** | Proprietary | Cloud | ✅ | (Suite) | ❌ | Vanta compliance users |
| **Kodus Trust Center** | Open Source | Next.js/Supabase | ✅ YAML-driven | ❌ | ✅ | Self-hosted trust portal |
| **Probo** | ISC | Go/Postgres | ✅ Compliance Page | ❌ | ✅ | Full GRC + public page |
| **QResponder** | Open Source | Python/FastAPI | ❌ | ✅ Local-first | ✅ | Zero-egress questionnaire |
| **Questionnaire-Responder** | Open Source | Python/SQLite | ❌ | ✅ + Gap report | ✅ | Multi-client consultants |
| **OpenWatch** | Open Source | Go/Postgres | ❌ (Evidence layer) | ❌ | ✅ | Continuous compliance evidence |
| **CompliEdge** | Open Source | Python/Django | ❌ | ❌ | ✅ | Internal GRC foundation |

---

## 🤝 Contributing

Contributions are welcome! If you know of an open-source Security, Privacy or Trust Center tool that should be listed here, please open a pull request with:

- Project name and URL
- Brief description (1–2 sentences)
- Stack and license
- Why it stands out

Please ensure the project is actively maintained (releases within the last 12 months) and genuinely open-source. Note that the open-source ecosystem **splits** between **trust center builders** (Kodus Trust Center, the most direct SafeBase alternative with YAML-driven editing), **GRC platforms with public compliance pages** (Probo, with 270+ MCP tools and full GRC coverage), and **questionnaire automation engines** (QResponder for zero-egress local answering, Questionnaire-Responder for multi-client gap analysis). No single open-source project yet replicates the full breadth of SafeBase or Vanta's trust center with AI questionnaire automation and document access controls, but combinations of Kodus (public page) + Probo (GRC) or QResponder (questionnaire) cover meaningful subsets of the workflow.

---

## 📄 License

This list is released under CC0 1.0 Universal (Public Domain). The software projects listed retain their respective licenses.

---

⭐ **If this list helped you discover a useful tool, please star the repo!** ⭐
