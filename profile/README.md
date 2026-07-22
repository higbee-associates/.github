# HACA IT

**Higbee & Associates Consumer Advocacy · Technology & Product Engineering**

We are the IT / engineering team for **HACA** — the consumer advocacy division of [Higbee & Associates](https://www.higbeeassociates.com). Since 2011, HACA has helped clients with debt settlement, collection-lawsuit defense, and rights under the **FDCPA** and **FCRA**. Our team builds and operates the software that makes that work scalable, compliant, and reliable.

This GitHub organization hosts the products and platforms we develop and offer for HACA operations, attorneys, vendors, and related workflows.

---

## Who we support

| Audience | How we help |
| --- | --- |
| **HACA staff & case teams** | Case data, CRM, compliance tooling, and internal APIs |
| **Attorneys & vendors** | Portals for case work, deliverables, and collaboration |
| **Consumers (product surfaces)** | Self-serve / DIY legal-tech experiences and related services |
| **Firm leadership** | Secure, maintainable platforms aligned with legal & compliance requirements |

Parent firm: [higbeeassociates.com](https://www.higbeeassociates.com) · Division: Higbee & Associates Consumer Advocacy (HACA)

---

## What we build

### Attorney Vendor Portal (AVP)
Web app + Laravel API for attorney/vendor workflows, integrated with the HACA Microsoft SQL Server data platform.

- `attorney-vendor-portal-frontend` — Next.js portal  
- `attorney-vendor-portal-backend` — Laravel API (HACA MSSQL)

### HACA data platform
APIs and services that expose and operate on core HACA case/client data.

- `haca_mssql_api` (HAPI) — Laravel API for the HACA MSSQL database  

### Compliance platform
Tools to review sales/call compliance with AI-assisted analysis, CRM, and media pipelines.

- `complaince-ai` — Compliance AI web platform  
- `complaince-ai-agent-service` — FastAPI / LangGraph compliance analysis agent  
- `compliance-crm-frontend` / `compliance-crm-backend` — Compliance CRM  
- `compliance-ai-audio-concatenator` — Audio merge Lambda for multi-segment calls  

### Consumer / legal-tech products
Product surfaces adjacent to HACA consumer advocacy workflows.

- `diy` — DIY legal-tech SaaS (consumer, vendor, attorney, staff roles)  
- Related automation (e.g. CanTheyCollect workflows) as needed  

---

## How we work

- Ship secure, documented software for a regulated legal environment  
- Prefer clear APIs, strong tests, and environment parity (Docker / AWS)  
- Keep secrets out of git; follow each repo’s `SECURITY.md` / contributing guide  
- Use organization defaults from this [`.github`](https://github.com/higbee-associates/.github) repo when a project doesn’t define its own templates  

See [`CONTRIBUTING.md`](./CONTRIBUTING.md) for contribution norms and [`SECURITY.md`](./SECURITY.md) for vulnerability reporting.

---

## Stack (typical)

| Layer | Technologies we commonly use |
| --- | --- |
| Web | Next.js, React, TypeScript |
| APIs | Laravel (PHP), FastAPI (Python) |
| Data | Microsoft SQL Server (HACA), PostgreSQL, Redis |
| Cloud | AWS (ECS, Lambda, S3, ALB, and related services) |
| AI | LangGraph / agent workflows for compliance analysis |

---

## This repository

Organization-wide community health files for **higbee-associates**:

- Issue templates (bug, feature, task)  
- Pull request template  
- Contributing, code of conduct, security, and support defaults  

Repos that define their own `.github/ISSUE_TEMPLATE/` (or other health files) override these defaults.

---

## Links

| | |
| --- | --- |
| Firm | [higbeeassociates.com](https://www.higbeeassociates.com) |
| LinkedIn | [Law Firm of Higbee & Associates](https://www.linkedin.com/company/law-firm-of-higbee-&-associates) |
| Org defaults | [higbee-associates/.github](https://github.com/higbee-associates/.github) |

---

*Built by HACA IT for Higbee & Associates Consumer Advocacy.*
