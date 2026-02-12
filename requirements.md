# ArkHealth – Requirements (Kiro Spec)

## Overview
ArkHealth is an AI-powered clinical trial patient matching platform that identifies eligible patients from participating hospitals and clinics and connects them to ongoing clinical trials in a privacy-first, explainable, and workflow-native manner.

This document defines MVP requirements using structured, testable statements following Kiro’s spec-driven format (EARS-style).

---

## 1. Trial Protocol Upload

**User Story**  
As a Sponsor or CRO user, I want to upload a clinical trial protocol so that the system can extract eligibility criteria.

**Acceptance Criteria**
- WHEN a user uploads a protocol file,  
  THE SYSTEM SHALL parse the document and extract inclusion and exclusion criteria.
- WHEN criteria are extracted,  
  THE SYSTEM SHALL display them for review and manual editing.

---

## 2. Site Data Ingestion

**User Story**  
As a Doctor or Site Admin, I want to upload deidentified patient data so that ArkHealth can match patients to trials.

**Acceptance Criteria**
- WHEN a user uploads a patient dataset (CSV),  
  THE SYSTEM SHALL validate the dataset against the required schema.
- WHEN the dataset is valid,  
  THE SYSTEM SHALL ingest the dataset for matching.

---

## 3. Eligibility Matching

**User Story**  
As a CRA, I want ArkHealth to match eligible patients against trials so I can focus my screening effort.

**Acceptance Criteria**
- WHEN patient data and eligibility rules are available,  
  THE SYSTEM SHALL run rule-based and ML-assisted matching.
- WHEN matches are found,  
  THE SYSTEM SHALL assign a confidence score to each candidate.

---

## 4. Evidence Packet Generation

**User Story**  
As a CRA, I want to see why a patient was matched so I can assess the candidate quickly.

**Acceptance Criteria**
- WHEN a candidate is matched,  
  THE SYSTEM SHALL generate evidence snippets showing which criteria are satisfied.
- WHEN evidence is generated,  
  THE SYSTEM SHALL display source fields and timestamps.

---

## 5. CRA Dashboard

**User Story**  
As a CRA, I want a dashboard with ranked candidate lists.

**Acceptance Criteria**
- WHEN candidates are available,  
  THE SYSTEM SHALL display them sorted by confidence score.
- WHEN a CRA updates a candidate status,  
  THE SYSTEM SHALL save the status (New, Reviewed, Shortlisted, Contacted).

---

## 6. Doctor / Site Approval

**User Story**  
As a Doctor, I want to approve or reject contacting a patient.

**Acceptance Criteria**
- WHEN a CRA requests approval,  
  THE SYSTEM SHALL notify the Doctor dashboard.
- WHEN the Doctor approves or rejects,  
  THE SYSTEM SHALL record the decision.

---

## 7. Sponsor / CRO Analytics

**User Story**  
As a Sponsor or CRO, I want to view recruitment metrics.

**Acceptance Criteria**
- WHEN recruitment data changes,  
  THE SYSTEM SHALL update metrics.
- WHEN metrics are updated,  
  THE SYSTEM SHALL display matched, contacted, and enrolled counts.

---

## 8. Patient Engagement (Demo)

**User Story**  
As a Patient, I want to see trial information and give consent.

**Acceptance Criteria**
- WHEN a patient is approved for contact,  
  THE SYSTEM SHALL show trial information.
- WHEN the patient gives consent or declines,  
  THE SYSTEM SHALL record the response.

---

## 9. Non-Functional Requirements

- System shall use only synthetic or deidentified data.
- System shall encrypt data in transit.
- System shall support role-based access control.
- System shall respond to user actions within 2 seconds for MVP.

---

## 10. Out of Scope (Hackathon)

- Real hospital EHR integrations  
- Production regulatory certification  
- Payments or billing

---

## 11. Success Criteria

- Demonstrate end-to-end flow
- Generate ranked candidates
- Show evidence packets
- Display dashboards

---

## 12. Timeline (Hackathon)

Day 1  
- Backend setup  
- Protocol parser  

Day 2  
- Matching engine  
- Dashboards  

Day 3  
- Evidence packets  
- Testing & demo  

---
