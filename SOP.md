# Standard Operating Procedure
## Amuma Development Manual: Engineering Workflows, Clinical Boundaries & Regulatory Protocols for the Amuma Pre-Clinical Triage PWA

---

### Revision History

| Version | Date | Author | Description of Changes |
| :--- | :--- | :--- | :--- |
| **1.0** | October 24, 2026 | John Lloyd D. Canoy | Created Initial SOP |

---

### Abstract
This document serves as the Standard Operating Procedure (SOP) and Development Manual for the **Amuma** Progressive Web App (PWA). It details the mandatory software engineering standards, architectural perimeters, clinical boundaries, and regulatory protocols governing system development, testing, and deployment. Adherence ensures full compliance with statutory data privacy and mental health mandates while delivering secure, resilient pre-clinical triage and guidance appointment workflows.

---

### Table of Contents
- [I. Purpose](#i-purpose)
- [II. Scope](#ii-scope)
  - [II.A. Governed Technical Perimeter](#iia-governed-technical-perimeter)
- [III. Proponents](#iii-proponents)
- [IV. Roles and Responsibilities](#iv-roles-and-responsibilities)
- [V. Procedure](#v-procedure)
  - [V.A. Development & Version Control Workflow](#va-development--version-control-workflow)
  - [V.B. Clinical Safety & Regulatory Guardrails](#vb-clinical-safety--regulatory-guardrails)
  - [V.C. Security, Data Privacy & Encryption Protocols](#vc-security-data-privacy--encryption-protocols)
  - [V.D. Quality Assurance & Testing Procedure](#vd-quality-assurance--testing-procedure)
- [VI. Tools and Equipment](#vi-tools-and-equipment)
  - [VI.A. Tools (Software & Frameworks)](#via-tools-software--frameworks)
  - [VI.B. Equipment (Hardware & Infrastructure)](#vib-equipment-hardware--infrastructure)

---

### I. Purpose
This Standard Operating Procedure (SOP) and Development Manual establishes the mandatory software engineering protocols, security controls, clinical safety boundaries, and quality assurance workflows for developing, maintaining, and deploying Amuma—an AI-driven appointment scheduling, gamified mental fitness, and pre-clinical triage Progressive Web App (PWA) for the University of Science and Technology of Southern Philippines – Cagayan de Oro Campus (USTP-CDO). All proponents and future maintainers must strictly adhere to this manual to ensure full compliance with the Philippine Data Privacy Act of 2012 (RA 10173), the Philippine Mental Health Act (RA 11036), and USTP Guidance and Counseling Services Office clinical confidentiality mandates.

---

### II. Scope
This manual governs the end-to-end decoupled software architecture of the Amuma ecosystem, serving young adults aged 18–24 in Cagayan de Oro City (~106,973 regional cohort; validated across a Cochran sample target of 687 respondents at a 4% margin of error and 15% non-response buffer).

#### II.A. Governed Technical Perimeter
The governed technical perimeter encompasses:
1. **Frontend Client Layer**: Next.js Progressive Web App (PWA) responsive client, offline-cached service workers, student self-care gamification interface, and appointment booking forms.
2. **Backend API Microservices**: Python FastAPI microservice architecture handling intake data pipelines, business logic, and conversational AI buffers.
3. **Data Storage & Security Perimeter**: Relational PostgreSQL database cluster enforcing AES-256 field-level encryption at rest and TLS 1.3 transit encryption.
4. **Clinical Administrative Subsystem**: Registered Guidance Counselor (RGC) portal, intake summary generation engine, and secure A4 printable PDF export pipelines.
5. **Emergency Hotlines Integration**: Static, offline-accessible click-to-call (`tel:` URI) crisis intervention reference module.

---

### III. Proponents
- Canoy, John Lloyd D.
- Arevalo, Zach Alfred M.
- Cinco, John Dave P.
- Jandayan, Carl Bernie A.
- Pimentel, Domvi Ford B.

---

### IV. Roles and Responsibilities

| Name | Role | Responsibilities |
| :--- | :--- | :--- |
| **Canoy, John Lloyd D.** | Team Lead | Project coordination, sprint planning, survey methodology, statistical data analysis, and regulatory liaison. |
| **Arevalo, Zach Alfred M.** | Backend Developer / Software Architect *(BOTTOM/pAPwet)* | Core backend API architecture, database schema design, microservices integration, authentication (JWT), and encryption enforcement. |
| **Cinco, John Dave P.** | Front End | Multilingual AI venting buffer integration, frontend UI development, client-side state handling, and prompt engineering. |
| **Jandayan, Carl Bernie A.** | Lead Researcher | Research protocol formulation, PWA UX design, gamified mental fitness mechanics (Cat Sudoku, streaks), and user testing analysis. |
| **Pimentel, Domvi Ford B.** | Quality Assurance Officer | QA test plan execution, security verification, RBAC authorization auditing, bug tracking, and compliance validation. |

---

### V. Procedure

#### V.A. Development & Version Control Workflow
1. **Branching Strategy**:
   - `main`: Production-ready, stable releases only.
   - `develop`: Primary integration branch for active sprint features.
   - `feature/<feature-name>`: Modular branches for isolated feature development.
2. **Code Review & Pull Requests**:
   - All PRs require at least one peer approval (Team Lead or QA Officer) prior to merge into `develop`.
   - Automated linting and test suites must pass without errors.
3. **Documentation Updates**:
   - Any architectural or API modification must be reflected in the SRS and API documentation.

#### V.B. Clinical Safety & Regulatory Guardrails
1. **Zero Autonomous Clinical Diagnosis**:
   - System prompts and AI outputs must strictly serve non-clinical supportive purposes.
   - Never issue formal medical diagnoses, psychotherapy evaluations, or medication advice.
2. **Emergency Referral Protocol**:
   - Maintain static, offline-cached emergency cards with active click-to-call hotline numbers (CSWD 24/7 Hotline, 911, CUMC Emergency Room).
   - Display unambiguous non-acute disclaimers on intake and venting interfaces.

#### V.C. Security, Data Privacy & Encryption Protocols
1. **Encryption Standards**:
   - **In Transit**: Enforce HTTPS / TLS 1.3 across all communication channels.
   - **At Rest**: Enforce AES-256 encryption for all sensitive personal intake data, counseling notes, and chat buffers.
2. **Role-Based Access Control (RBAC)**:
   - Students may only access their personal profiles, logs, and booking vouchers.
   - Counselors (RGCs) are restricted to their assigned college intake queues.
   - Administrative staff are barred from viewing student clinical narratives.

#### V.D. Quality Assurance & Testing Procedure
1. **Unit & Integration Testing**: Verify backend API routes, token verification, and encryption/decryption routines.
2. **Usability & Offline Testing**: Verify PWA service worker caching, offline fallback screen rendering, and responsive UI scaling.
3. **Security Audits**: Routine vulnerability scans, role escalation tests, and penetration testing on API endpoints.

---

### VI. Tools and Equipment

#### VI.A. Tools (Software & Frameworks)
- **Frontend**: Next.js, React, Tailwind CSS, Service Workers (PWA)
- **Backend & APIs**: Python 3.11+, FastAPI, Uvicorn, Pydantic
- **Database & ORM**: PostgreSQL, SQLAlchemy / Alembic
- **Data Science & Analytics**: Jupyter Notebook, Pandas, NumPy, Seaborn, Matplotlib
- **Security & Cryptography**: PyCryptodome / Cryptography (AES-256), OpenSSL (TLS 1.3), JSON Web Tokens (PyJWT)
- **Version Control & Collaboration**: Git, GitHub, Visual Studio Code

#### VI.B. Equipment (Hardware & Infrastructure)
- **Development Workstations**: Multi-core development PCs / Laptops running Windows 11 / Linux
- **Testing Devices**: Android and iOS mobile smartphones for PWA testing and responsive layout verification
- **Hosting / Server Infrastructure**: Containerized runtime environment (Docker), cloud deployment instance or local test server
- **Networking Equipment**: Secure internet connection with SSL/TLS termination proxies
