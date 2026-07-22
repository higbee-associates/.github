# HACA IT

**Higbee & Associates Consumer Advocacy · Technology & Product Engineering**

We are the IT / engineering team for **HACA** — the consumer advocacy division of [Higbee & Associates](https://www.higbeeassociates.com). Since 2011, HACA has helped clients with debt settlement, collection-lawsuit defense, and rights under the **FDCPA** and **FCRA**. Our team builds and operates the software that makes that work scalable, compliant, and reliable.

---

## Quick links

<!-- Small logo pills for day-to-day tools (absolute asset URLs so they resolve on the org Overview page). -->

<p>
  <a href="https://status.higbeeassociates.com"><img src="https://raw.githubusercontent.com/higbee-associates/.github/main/profile/assets/myview-icon.svg" alt="" height="18" />&nbsp;<strong>My View</strong></a>
  &nbsp;·&nbsp;
  <a href="https://raven.higbee.law"><img src="https://raw.githubusercontent.com/higbee-associates/.github/main/profile/assets/raven-icon.svg" alt="" height="18" />&nbsp;<strong>Raven</strong></a>
  &nbsp;·&nbsp;
  <a href="https://raven-user-guide.higbee.law"><img src="https://raw.githubusercontent.com/higbee-associates/.github/main/profile/assets/raven-logo.png" alt="" height="18" />&nbsp;<strong>Raven Specs</strong></a>
  &nbsp;·&nbsp;
  <a href="https://owlbert.moxieit.net/doku.php"><img src="https://raw.githubusercontent.com/higbee-associates/.github/main/profile/assets/owlbert-icon.svg" alt="" height="18" />&nbsp;<strong>Org Docs</strong></a>
  &nbsp;·&nbsp;
  <a href="https://raven-api.higbee.law/horizon"><img src="https://raw.githubusercontent.com/higbee-associates/.github/main/profile/assets/horizon-icon.svg" alt="" height="18" />&nbsp;<strong>Raven Horizon</strong></a>
  &nbsp;·&nbsp;
  <a href="https://app.haca-compliance.com"><img src="https://raw.githubusercontent.com/higbee-associates/.github/main/profile/assets/crm-logo.png" alt="" height="18" />&nbsp;<strong>Compliance CRM</strong></a>
  &nbsp;·&nbsp;
  <a href="https://inspector.higbee.law"><img src="https://raw.githubusercontent.com/higbee-associates/.github/main/profile/assets/compliance-ai-icon.png" alt="" height="18" />&nbsp;<strong>Compliance AI</strong></a>
</p>

- [My View](https://status.higbeeassociates.com) — legacy HACA case portal  
- [Raven](https://raven.higbee.law) — attorney / vendor case portal (AVP)  
- [Raven Specs](https://raven-user-guide.higbee.law) — Raven user guide & product docs ([GitHub](https://github.com/higbee-associates/raven-user-guide))  
- [Org Docs (Owlbert)](https://owlbert.moxieit.net/doku.php) — internal wiki / API docs  
- [Raven Horizon](https://raven-api.higbee.law/horizon) — Laravel Horizon (queues / failed jobs)  
- [Compliance CRM](https://app.haca-compliance.com) — compliance CRM app  
- [Compliance AI](https://inspector.higbee.law) — AI compliance inspector  

---

## Production status

Status badges for core platforms (Attorney Vendor Portal, Compliance CRM, Compliance AI). Badges reflect GitHub Actions on `main` / production workflows. Private-repo badges are visible to org members.

| Project | Repository | Prod deploy | Tests |
| --- | --- | --- | --- |
| **Raven (AVP) Frontend** | [`attorney-vendor-portal-frontend`](https://github.com/higbee-associates/attorney-vendor-portal-frontend) | [![Prod deploy](https://github.com/higbee-associates/attorney-vendor-portal-frontend/actions/workflows/deploy-production-west.yml/badge.svg?branch=main)](https://github.com/higbee-associates/attorney-vendor-portal-frontend/actions/workflows/deploy-production-west.yml) | [![Tests](https://github.com/higbee-associates/attorney-vendor-portal-frontend/actions/workflows/test.yml/badge.svg?branch=main)](https://github.com/higbee-associates/attorney-vendor-portal-frontend/actions/workflows/test.yml) |
| **Raven (AVP) Backend** | [`attorney-vendor-portal-backend`](https://github.com/higbee-associates/attorney-vendor-portal-backend) | [![Prod deploy](https://github.com/higbee-associates/attorney-vendor-portal-backend/actions/workflows/deploy-production-west.yml/badge.svg?branch=main)](https://github.com/higbee-associates/attorney-vendor-portal-backend/actions/workflows/deploy-production-west.yml) | [![Tests](https://github.com/higbee-associates/attorney-vendor-portal-backend/actions/workflows/test.yml/badge.svg?branch=main)](https://github.com/higbee-associates/attorney-vendor-portal-backend/actions/workflows/test.yml) |
| **Compliance CRM Frontend** | [`compliance-crm-frontend`](https://github.com/higbee-associates/compliance-crm-frontend) | [![Prod deploy](https://github.com/higbee-associates/compliance-crm-frontend/actions/workflows/deploy.yml/badge.svg?branch=main)](https://github.com/higbee-associates/compliance-crm-frontend/actions/workflows/deploy.yml) | ![Tests](https://img.shields.io/badge/tests-n%2Fa-lightgrey) |
| **Compliance CRM Backend** | [`compliance-crm-backend`](https://github.com/higbee-associates/compliance-crm-backend) | [![Prod deploy](https://github.com/higbee-associates/compliance-crm-backend/actions/workflows/deploy.yml/badge.svg?branch=main)](https://github.com/higbee-associates/compliance-crm-backend/actions/workflows/deploy.yml) | ![Tests](https://img.shields.io/badge/tests-n%2Fa-lightgrey) |
| **Compliance AI App** | [`complaince-ai`](https://github.com/higbee-associates/complaince-ai) | [![Prod deploy](https://github.com/higbee-associates/complaince-ai/actions/workflows/deploy-app-prod.yml/badge.svg?branch=main)](https://github.com/higbee-associates/complaince-ai/actions/workflows/deploy-app-prod.yml) | ![Tests](https://img.shields.io/badge/tests-n%2Fa-lightgrey) |
| **Compliance AI Agent** | [`complaince-ai-agent-service`](https://github.com/higbee-associates/complaince-ai-agent-service) | [![Prod deploy](https://github.com/higbee-associates/complaince-ai-agent-service/actions/workflows/deploy-fastapi-prod.yml/badge.svg?branch=main)](https://github.com/higbee-associates/complaince-ai-agent-service/actions/workflows/deploy-fastapi-prod.yml) | ![Tests](https://img.shields.io/badge/tests-n%2Fa-lightgrey) |

<p>
  <a href="https://github.com/higbee-associates/attorney-vendor-portal-frontend/actions/workflows/deploy-production-west.yml"><img src="https://github.com/higbee-associates/attorney-vendor-portal-frontend/actions/workflows/deploy-production-west.yml/badge.svg?branch=main" alt="AVP FE prod" height="20" /></a>
  <a href="https://github.com/higbee-associates/attorney-vendor-portal-backend/actions/workflows/deploy-production-west.yml"><img src="https://github.com/higbee-associates/attorney-vendor-portal-backend/actions/workflows/deploy-production-west.yml/badge.svg?branch=main" alt="AVP BE prod" height="20" /></a>
  <a href="https://github.com/higbee-associates/compliance-crm-frontend/actions/workflows/deploy.yml"><img src="https://github.com/higbee-associates/compliance-crm-frontend/actions/workflows/deploy.yml/badge.svg?branch=main" alt="CRM FE prod" height="20" /></a>
  <a href="https://github.com/higbee-associates/compliance-crm-backend/actions/workflows/deploy.yml"><img src="https://github.com/higbee-associates/compliance-crm-backend/actions/workflows/deploy.yml/badge.svg?branch=main" alt="CRM BE prod" height="20" /></a>
  <a href="https://github.com/higbee-associates/complaince-ai/actions/workflows/deploy-app-prod.yml"><img src="https://github.com/higbee-associates/complaince-ai/actions/workflows/deploy-app-prod.yml/badge.svg?branch=main" alt="Compliance AI prod" height="20" /></a>
  <a href="https://github.com/higbee-associates/complaince-ai-agent-service/actions/workflows/deploy-fastapi-prod.yml"><img src="https://github.com/higbee-associates/complaince-ai-agent-service/actions/workflows/deploy-fastapi-prod.yml/badge.svg?branch=main" alt="Agent prod" height="20" /></a>
</p>

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

### Attorney Vendor Portal / Raven
Web app + Laravel API for attorney/vendor workflows, integrated with the HACA Microsoft SQL Server data platform.

- [`attorney-vendor-portal-frontend`](https://github.com/higbee-associates/attorney-vendor-portal-frontend) — Next.js portal ([raven.higbee.law](https://raven.higbee.law))  
- [`attorney-vendor-portal-backend`](https://github.com/higbee-associates/attorney-vendor-portal-backend) — Laravel API ([raven-api.higbee.law](https://raven-api.higbee.law))  

### Compliance platform
Tools to review sales/call compliance with AI-assisted analysis and CRM.

- [`complaince-ai`](https://github.com/higbee-associates/complaince-ai) — Compliance AI web platform ([inspector.higbee.law](https://inspector.higbee.law))  
- [`complaince-ai-agent-service`](https://github.com/higbee-associates/complaince-ai-agent-service) — FastAPI / LangGraph compliance analysis agent  
- [`compliance-crm-frontend`](https://github.com/higbee-associates/compliance-crm-frontend) / [`compliance-crm-backend`](https://github.com/higbee-associates/compliance-crm-backend) — Compliance CRM  

---

## How we work

- Ship secure, documented software for a regulated legal environment  
- Prefer clear APIs, strong tests, and environment parity (Docker / AWS)  
- Keep secrets out of git; follow each repo’s security / contributing guide  
- Use organization defaults from this [`.github`](https://github.com/higbee-associates/.github) repo when a project doesn’t define its own templates  

See [`CONTRIBUTING.md`](https://github.com/higbee-associates/.github/blob/main/CONTRIBUTING.md) and [`SECURITY.md`](https://github.com/higbee-associates/.github/blob/main/SECURITY.md).

---

## Links

| | |
| --- | --- |
| Firm | [higbeeassociates.com](https://www.higbeeassociates.com) |
| LinkedIn | [Law Firm of Higbee & Associates](https://www.linkedin.com/company/law-firm-of-higbee-%26-associates) |
| Org defaults | [higbee-associates/.github](https://github.com/higbee-associates/.github) |
| Org docs | [owlbert.moxieit.net](https://owlbert.moxieit.net/doku.php) |

---

*Built by HACA IT for Higbee & Associates Consumer Advocacy.*
