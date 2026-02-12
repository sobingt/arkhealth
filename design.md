# ArkHealth — Design Specification (Kiro)

## 1. High‑Level Architecture

ArkHealth is composed of the following layers:

- Frontend — UI dashboards for CRA, Site, Sponsor/CRO, and patient engagement (React)
- Backend API — Serves REST endpoints (FastAPI / Node.js)
- Matching Engine — Combines rule‑based and ML models to score candidates
- Protocol Parser — NLP service that extracts trial criteria
- Database & Storage — PostgreSQL and MongoDB
- Vector Store — FAISS
- Monitoring & Logging — Prometheus, Grafana

---

## 2. Components & Interfaces

### Frontend Routes
/login  
/sponsor/dashboard  
/sponsor/trials/new  
/cra/dashboard  
/cra/candidate/:id  
/site/dashboard  
/patient/engage/:id  

---

## 3. API Endpoints (Draft)

POST /api/trials  
GET /api/trials  
POST /api/sites/{siteId}/patients/upload  
POST /api/trials/{id}/match  
GET /api/trials/{id}/candidates  
GET /api/candidates/{id}/evidence  
POST /api/candidates/{id}/approve  
POST /api/candidates/{id}/reject  

---

## 4. Database Schema

Trial(id, title, protocol_raw, criteria_structured)  
Candidate(id, trial_id, patient_id, confidence_score, status)  
Site(id, name, location)

Patient (MongoDB)
_id, age, conditions, labs, medications

---

## 5. Matching Engine Design

Hybrid model:
- Rule-based eligibility filtering
- Semantic similarity scoring
- Weighted final score

---

## 6. Evidence Packet Structure

candidate_id  
trial_id  
confidence_score  
evidence[]  
timestamps  

---

## 7. Security & Privacy

- Deidentified or synthetic data only  
- TLS encryption  
- Role-based access  
- Audit logs  

---

## 8. Deployment

Docker  
AWS
GitHub Actions  

---

## 9. Testing

Unit tests  
Integration tests  
Acceptance tests  
