

# AI-Driven Accessible Legal Aid Platform
## Project Proposal

Student: Chirag

Roll Number: 2022UCS1524

Program: B.Tech Computer Science Engineering 

Academic Year: 2025–26 

Guide/Supervisor: Dr. Ankush Jain

Institution: netaji subhash university of technology

Date: August 24, 2025

## 1. Executive Summary
This proposal presents a web platform that delivers clear, actionable legal information in India with language inclusion and built‑in accessibility. The system interprets legal queries in plain language, supports Hindi and English, and provides features that enable elderly users and persons with disabilities to access information independently. It includes tools for community organizations to support multiple clients consistently. The aim is to reduce barriers to legal awareness and improve service delivery through an interoperable, reliable, and easy‑to‑use system.

## 2. Problem Analysis
### 2.1 Structural Barriers
- Availability: Legal services are scarce in rural and peri‑urban areas; travel time and cost prevent timely help.  
- Affordability: Per‑session consultation costs are prohibitive for low‑income households.  
- Language: Legal content and processes are primarily in English; many citizens use regional languages.  
- Digital skills: Many citizens and seniors have limited digital literacy and use basic devices or intermittent internet.

### 2.2 Accessibility Gaps
- Visual: Inadequate support for screen readers, insufficient contrast, non‑scalable text.  
- Motor: Poor keyboard navigation, small touch targets, time‑limited interactions.  
- Cognitive: Dense language, jargon, unclear task flows, and error messages that do not guide recovery.  
- Hearing: Lack of transcripts and visual alternatives for audio content.

### 2.3 Service Limitations
- Narrow language coverage; accessibility treated as an add‑on rather than a baseline.  
- Interfaces optimized for professionals rather than laypersons.  
- Urban‑centric models; limited support for intermittent connectivity or offline usage.  
- Limited tools for NGOs and community workers to manage multi‑client workflows.

## 3. Conceptual Foundations
The design draws from:
- Universal Design and WCAG 2.1: Build for the broadest range of abilities from the start.  
- Plain Language Principles: Replace legal jargon with clear, concise explanations and actionable steps.  
- Human‑Centered Design: Iterative testing with representative users (seniors, low literacy, screen reader users).  
- Responsible AI: Confidence scoring, explainability, explicit scope boundaries, and human oversight.  
- Socio‑Technical Systems: Technology embedded in real service ecosystems (NGOs, clinics, help desks) to ensure adoption and impact.

## 4. Solution Overview
### Objectives
- Provide plain‑language guidance with concrete next steps for common legal needs.  
- Ensure accessibility by default and multilingual operation.  
- Equip organizations with case tools to increase reach and consistency.

### Principles
- Clarity over jargon  
- Accessibility by default  
- Accuracy with transparent limitations  
- Actionable outputs prioritized over general information

### Core Capabilities
- Natural language query processing with confidence indicators and alternative pathways when confidence is low.  
- Multilingual operation (Hindi and English initially), with a framework to add regional languages.  
- Accessibility features: screen reader compatibility, keyboard navigation, scalable text, high contrast, voice input/output.  
- Guided flows for frequent needs (e.g., property, benefits, documentation, family matters).  
- Content provenance and last‑review metadata per guidance item.

### Community Features
- Case workspace for NGOs: client notes, follow‑ups, and templated guidance.  
- Offline support for unstable networks; SMS fallbacks for basic phones.  
- Role‑based access for community help desks and supervised devices.

## 5. Architecture and Rationale
### 5.1 System Design Goals
- Reliability: Fast responses, graceful degradation offline, and defensible failure modes.  
- Privacy by Design: Minimal data collection, explicit consent, and transparent storage.  
- Evolvability: Modular components to add languages, flows, and integrations without rework.  
- Interoperability: Standards‑based APIs for future integration with partner systems.

### 5.2 Components
Frontend
- React + TypeScript for predictable UI state and maintainability.  
- Accessible components and semantic HTML as the baseline.  
- PWA for offline caching of UI and non‑sensitive content.

Backend
- Python (Django) REST APIs for clarity, security, and maturity.  
- JWT authentication, rate limiting, input validation, consistent error contracts.  
- Structured logging, request IDs, and correlation for supportability.

Data
- PostgreSQL with normalized schemas for content, sessions, and minimal user data.  
- Encryption at rest for sensitive fields; strict access controls; scheduled backups.  
- Content versioning and audit trail.

AI Layer
- Transformer models adapted for Indian legal contexts with retrieval over a curated knowledge base.  
- Confidence scores; fallback to curated FAQ or connect‑to‑help flow on low confidence.  
- Human‑review loop for content updates and model behavior audits.

Security
- TLS everywhere, secure cookie/session handling, secret rotation.  
- Least privilege IAM, CSP headers, SSRF/XSS/CSRF protections.  
- Data retention policies and user data export/delete workflows.

### 5.3 Data Flow (High‑Level)
1. User asks a question (text or voice).  
2. Request hits API gateway → auth/ratelimit → query processor.  
3. Retrieval over curated legal knowledge base; AI composes plain‑language draft.  
4. Draft passes through policy filters (disclaimer, scope, escalation criteria) and confidence checks.  
5. Response returned with clear next steps and options (save, share, contact).  
6. Anonymous analytics events log usage for improvement (no PII by default).

## 6. Content Governance
- Curation: Knowledge base seeded with official sources and validated summaries.  
- Review: Legal expert review for accuracy; update cadence and change logs.  
- Provenance: Source references and last‑review date surfaced to admins.  
- Scope: Clear “not legal advice” and guidance to seek professional help for complex disputes.  
- Escalation: Pathways to vetted legal aid centers or helplines when needed.

## 7. User Journeys
- Rural citizen: Enters a property question in Hindi → receives steps, documents checklist, and nearest aid contact; can save via SMS.  
- Senior citizen: Uses voice to ask about pension eligibility → hears concise steps and required forms; increases text size for review.  
- Community worker: Opens case workspace; bulk enters client questions; prints simple guides in local language for distribution.

## 8. Implementation Plan
Phase 1: Foundation and Research  
- Recruit test users via partner NGOs; define research ethics and consent.  
- Technical environment setup; security baselines; content seeding.  
- Accessibility‑first UI design; establish design tokens for contrast and scale.

Phase 2: Core Development  
- Auth and onboarding; language toggle; preferences storage.  
- Query processing pipeline; knowledge base retrieval; confidence logic.  
- Initial guided flows; content provenance and admin tools.  
- Accessibility features to WCAG 2.1 AA.

Phase 3: Community and Offline  
- NGO dashboard: cases, notes, templated outputs, follow‑ups.  
- Voice input/output; basic SMS delivery for saved guidance.  
- Offline cache for UI and non‑sensitive guidance.

Phase 4: Testing and Deployment  
- Usability testing with seniors and screen reader users; iterate based on findings.  
- Load and latency tuning; security and privacy checks; backup drills.  
- Production deploy; monitoring, alerts, and support runbooks.

## 9. Assurance and Evaluation
### 9.1 Accessibility Verification
- Manual testing with NVDA and TalkBack; keyboard‑only navigation.  
- Automated checks (axe, pa11y) embedded in CI.  
- Contrast, focus states, and reflow validation at 200% zoom.

### 9.2 Performance Targets
- P50 latency ≤ 1.5s; P95 ≤ 3s under 200 concurrent users.  
- Offline: UI and cached content accessible; queued submissions synced on reconnect.

### 9.3 Privacy and Security
- Data Protection Impact Assessment (DPIA‑style checklist).  
- Secrets management; periodic vulnerability scans; incident response playbook.  
- Minimal analytics with no PII by default; consent banner for optional telemetry.

### 9.4 Outcome Metrics
Adoption and Use
- Monthly active users; first‑time vs returning; language split.  
- Feature usage: voice, accessibility settings, saved guidance.

Effectiveness
- Task success rate for common journeys (find eligibility, identify documents, locate contact).  
- Time‑to‑first‑value (from open to guidance).  
- User comprehension score via brief, optional post‑task checks.

Retention and Impact
- Repeat usage within 30/90 days.  
- NGO throughput (clients assisted per worker per day).  
- Qualitative feedback: clarity, usefulness, next‑step confidence.

## 10. Risk Register and Mitigation
- Misinterpretation risk: Confidence thresholds and explicit “seek expert help” triggers.  
- Accessibility regressions: CI checks, release gates, and periodic audits.  
- Model drift: Scheduled reviews, curated retrieval layer, controlled updates.  
- Connectivity failure: Offline cache and SMS fallback; clear sync indicators.  
- Privacy breach: Minimize data, encrypt sensitive fields, test restores, rotate secrets.

## 11. Resources
Infrastructure
- Git, CI/CD, containerized services (optional), managed Postgres, object storage.  
- Monitoring and alerting dashboards; uptime probes.

Partnerships
- Legal experts for content governance.  
- NGOs for user recruitment, pilots, and field feedback.  
- Accessibility organizations for usability testing.

Documentation
- Architecture and threat model.  
- Runbooks for deployment, rollback, incident response, and backup restore.  
- Admin and content governance manuals.

## 12. Roadmap for Language and Region Expansion
- Language pack model: strings, content bundles, and locale‑specific flows.  
- Community translation review with glossary for legal terms.  
- Regional content variants (state schemes, local offices) with fallback logic.

## 13. Conclusion
This platform takes a practical, evidence‑based approach to legal awareness: plain language, accessibility by default, multilingual support, and reliable performance. It enables citizens to understand options and take next steps, and it provides organizations with tools to serve more people consistently. The architecture supports responsible AI, privacy, and long‑term maintainability, positioning the system for sustainable impact and regional expansion.

## References
1. Indian Constitution: Articles 14, 19, 21  
2. Legal Services Authority Act, 1987  
3. Rights of Persons with Disabilities Act, 2016  
4. Web Content Accessibility Guidelines (WCAG) 2.1  
5. Digital India initiative  
6. National Sample Survey Organization: Access to justice data  
7. UNESCO digital inclusion guidance

