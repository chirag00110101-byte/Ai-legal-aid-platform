AI-Driven Accessible Legal Aid Platform
An academic, production-style web application to democratize first-level legal assistance in India through natural-language AI, multilingual UX, and accessible design. Developed over two semesters: a functional MVP in Semester 7 and advanced capabilities in Semester 8.

Project Overview
Student: Chirag, Roll No.:2022UCS1524

Program: B.Tech (CSE), Final Year

Academic Year: 2025–26

Guide/Supervisor: Dr. Ankush jain

Institution: netaji subhash university of technology

Motivation: Millions face barriers to legal awareness: complex statutes, English-only resources, cost of consultations, and accessibility gaps for seniors and differently-abled citizens. This project builds an inclusive, AI-backed interface that explains rights and next steps in plain language, starting with India-focused use cases.

Goals and Non-Goals-

Goals (Semester 7 MVP) :
Text-based legal query intake with simple, clear responses
Hindi and English UI with basic language toggles
Accessibility-first UI: keyboard navigation, ARIA, scalable fonts, high-contrast mode
Accounts with saved query history and minimal admin oversight
Deployed MVP with basic logging and testing

Planned (Semester 8):
Voice input/output (STT/TTS)
Document understanding (summarization, key info extraction)
Regional language expansion
Semantic search with vector store for statutes/FAQs
Case intake + lightweight NGO workflow
Security hardening, CI/CD, performance tuning

Non-Goals:
The system does not replace lawyers or provide binding legal advice.
Deep jurisdiction-specific counsel is out of scope for the MVP.

Users and Impact:
Citizens needing plain-language guidance on common issues (property, employment, benefits)
Elderly and low-vision users benefiting from accessible UX and voice
NGO/paralegal workers handling multiple client queries
Help desks at public offices and community centers

Expected impact: wider legal access, a digital accessibility bridge, and a scalable tool NGOs and communities can adopt.

Architecture:
Frontend: React (accessible components, React Router)
Backend: Python (Flask or Django) REST API
Database: PostgreSQL (users, queries, responses, documents)
AI/NLP: Hugging Face Transformers, spaCy (baseline); vector DB (Semester 8)
Search: Keyword (S7), semantic/vector retrieval (S8)
Deployment: Heroku/Railway (S7 MVP), containers + CI/CD (S8)

Repository Structure:
ai-legal-aid-platform/
├── README.md
├── docs/
│   ├── project-proposal.md
│   ├── requirements.md
│   ├── design/
│   │   ├── system-architecture.md
│   │   ├── database-design.md
│   │   └── uml-diagrams/
│   └── reports/
│       └── final-report.md
├── backend/
├── frontend/
├── tests/
└── deployment/


Success Criteria :
Deployed MVP accessible on the web
Typical query response latency under ~3s
WCAG-aligned checks on core flows
Positive feedback from at least 5 pilot users (incl. accessibility needs)
Complete documentation set: SRS, UML/DFD, architecture, test plan, user guide

Getting Started Prerequisites:
Node.js LTS, Python 3.11+, PostgreSQL
Setup (placeholder; will be expanded as code lands)
frontend/: npm install && npm start
backend/: python -m venv venv && pip install -r requirements.txt && flask run
Configure .env for DB connection and API keys

Deployment:
Semester 7: Heroku/Railway MVP
Semester 8: Containerized with CI/CD

Data and Privacy:
Minimal data collection; clear consent prompts
“Not legal advice” disclaimer on all outputs
Audit logging for administrative actions (S8 enhancement)

Quality and Governance:
Branching: main (protected), feature/, fix/
Code style: Prettier (FE), Black + Flake8 (BE)
Tests: Jest/RTL (FE), Pytest (BE)
Accessibility checks: axe-core, manual screen reader passes (NVDA/VoiceOver)
Security: OWASP-aligned checklist (auth, input validation, secret management)
