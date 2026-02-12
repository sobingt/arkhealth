# ArkHealth — Design Specification (Kiro)

## 1. High-Level Architecture

ArkHealth is composed of the following layers:

- **Frontend** — UI dashboards for CRA, Site, Sponsor/CRO, and patient engagement (React).
- **Backend API** — Serves REST endpoints (FastAPI / Node.js).
- **Matching Engine** — Combines rule-based and ML models to score candidates.
- **Protocol Parser** — NLP service that extracts trial criteria.
- **Database & Storage** — Structured (Postgres) and document (Mongo) stores.
- **Vector Store** — FAISS or lightweight vector index for similarity scoring.
- **Monitoring & Logging** — Prometheus, Grafana, Sentry.

---

## 2. Components & Interfaces

### 2.1 Frontend Components

| Component | Description | Key Routes |
|-----------|-------------|------------|
| Landing / Auth | Login & signup | `/login` |
| Sponsor Dashboard | Trial metrics & analytics | `/sponsor/dashboard` |
| Trial Setup | Upload protocols | `/sponsor/trials/new` |
| CRA Dashboard | Candidate lists | `/cra/dashboard` |
| Candidate Detail | Evidence packet view | `/cra/candidate/:id` |
| Site Dashboard | Approvals | `/site/dashboard` |
| Patient Screen (Demo) | Consent UI | `/patient/engage/:id` |

---

## 3. API Endpoints (Draft)

**Sponsor / CRO**
