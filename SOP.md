# Standard Operating Procedure
## Amuma Development Manual: Engineering Workflows, Clinical Boundaries & Regulatory Protocols for the Amuma Pre-Clinical Triage PWA

---

### Revision History

| Version | Date | Author | Description of Changes |
| :--- | :--- | :--- | :--- |
| **1.0** | October 24, 2026 | John Lloyd D. Canoy | Created Initial SOP |
| **1.1** | November 5, 2026 | Project Team | Integrated Section V.E Gemini Notebook Prompting Protocol (no code) and updated Section V.A.3 with mandatory peer review and documentation logging requirements. |

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
  - [V.E. Gemini Notebook Prompting Protocol (Manuscript Drafting)](#ve-gemini-notebook-prompting-protocol-manuscript-drafting)
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
3. **Documentation Updates & Revision Logging**:
   - **Architectural & API Alignment**: Any architectural, database schema, or API endpoint modification must be promptly reflected in the Software Requirements Specification (`amuma_srs_specification.md`) and API documentation.
   - **Mandatory Review for SRS & Research Paper Edits**: Any addition, amendment, or revision made to the SRS, research paper manuscript, research protocols (`research-rules.md`), or standard operating procedures must undergo formal peer review and approval by the Team Lead (**Canoy**), Lead Researcher (**Jandayan**), or QA Officer (**Pimentel**) prior to integration.
   - **Documentation Log Tracking**: All modifications across documentation files must be chronologically recorded in the project's documentation log (`DOCUMENTATION_LOG.md`) as well as the respective file's Revision History table. Each log entry must specify:
     - **Date & Time of Edit**: When the modification was performed.
     - **Author / Editor**: Name of the proponent who introduced the changes.
     - **Target File & Section**: Exact document and section modified (e.g., `SRS Section 3.1.2`, `Chapter 1.1`).
     - **Detailed Description of Changes**: Exact summary of what was added, modified, or removed, and the technical or research rationale.
     - **Reviewer Sign-off**: Name of the peer reviewer who verified and approved the changes.

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

#### V.E. Gemini Notebook Prompting Protocol (Manuscript Drafting)

##### 1. Personnel in Charge
- **Lead Prompt Engineer**: **Cinco, John Dave P.** (Prompt design, system instruction envelopes, parameter calibration).
- **Lead Researcher**: **Jandayan, Carl Bernie A.** (Section objectives, literature synthesis, thesis alignment).
- **Integrity & Compliance Reviewer**: **Pimentel, Domvi Ford B.** (Pre-flight audit, similarity check, statutory compliance).
- **Supervisory Approval**: **Canoy, John Lloyd D.** (Team Lead review, final sign-off).

##### 2. Operational Policy & Grounding Mandate
When generating or refining any section of the academic manuscript (e.g., Chapter 1: Introduction, Problem Statement, Objectives) inside a Gemini Notebook environment:
- **Strict Rule Binding**: Every prompt must strictly abide by and anchor to `research-rules.md`. Ungrounded or open-ended prompts without statutory and ethical guardrails are strictly forbidden.
- **Mandatory Statutory Constraints**: Explicitly enforce the Philippine Data Privacy Act of 2012 (RA 10173), the Philippine Mental Health Act (RA 11036), and the Guidance and Counseling Act of 2004 (RA 9258).
- **Clinical Boundaries**: Enforce zero diagnostic claims. Amuma is strictly a pre-clinical triage buffer, gamified self-care motivator, and appointment booking bridge—never an autonomous diagnostic tool, virtual therapist, or crisis dispatcher.
- **Demographic Precision**: Ground all contextual claims in the target cohort of tertiary students and young adults aged 18–24 at USTP-CDO (regional population ~106,973; Cochran sample target $n = 687$ at a 4% margin of error and 15% non-response buffer).
- **Academic Standard**: Enforce APA 7th Edition citations, objective scholarly tone, and past tense for study methodology/results.

##### 3. Step-by-Step Prompting Workflow
1. **Step 1: Set the System Instruction (Master Guardrail Envelope)**
   - Paste the Master System Prompt into the notebook's system instruction field. This permanently binds the model to `research-rules.md` and regulatory statutes for the session.
2. **Step 2: Formulate the Segment-Specific Task Prompt**
   - Provide the specific chapter, section number, structural outline, key themes, and boundary conditions.
3. **Step 3: Run Regulatory & Self-Consistency Audit**
   - Execute the verification prompt on the generated text to check for diagnostic overreach, hallucinated citations, or statutory violations.
4. **Step 4: Plagiarism & CRediT Log**
   - Verify that similarity is under 15% (Turnitin/iThenticate) and record the session details for the paper's mandatory *Acknowledgment of AI Use* disclosure.

---

##### 4. Master Prompt Templates

###### Prompt Template A: Master System Instruction (Guardrail Envelope)
*Paste this into the System Instruction field of the Gemini Notebook session:*

> **SYSTEM INSTRUCTION:**
> 
> You are an expert scientific co-author and academic research assistant for the AMUMA capstone research paper at the University of Science and Technology of Southern Philippines – Cagayan de Oro Campus (USTP-CDO).
> 
> You must strictly abide by the authoritative project rules in `research-rules.md` and the following non-negotiable boundaries:
> 
> 1. **Statutory Guardrails**:
>    - **RA 10173 (Philippine Data Privacy Act of 2012)**: All student interactions, check-ins, and intake summaries are Sensitive Personal Information (SPI). Enforce TLS 1.3 transit encryption and AES-256 storage encryption at rest.
>    - **RA 11036 (Philippine Mental Health Act)**: The system is non-diagnostic. Zero autonomous medical diagnosing, clinical risk scoring, automated crisis intervention dispatch, or psychiatric medication advice.
>    - **RA 9258 (Guidance and Counseling Act of 2004)**: All clinical, diagnostic, and therapeutic authority belongs exclusively to licensed Registered Guidance Counselors (RGCs). Amuma serves solely as a pre-clinical intake briefing bridge.
> 
> 2. **System Definition**:
>    - Always describe Amuma strictly as an *"AI-driven appointment scheduling, gamified mental fitness, and pre-clinical triage Progressive Web App (PWA)"*. Never refer to it as a "virtual therapist", "diagnostic AI", or "autonomous crisis responder".
> 
> 3. **Target Cohort & Empirical Grounding**:
>    - Target Population: Tertiary students and young adults aged 18–24 in Cagayan de Oro City (~106,973 regional cohort).
>    - Study Sample: Cochran formula target of $n = 687$ respondents at a 4% margin of error with a 15% non-response buffer.
>    - Setting: University of Science and Technology of Southern Philippines – Cagayan de Oro Campus (USTP-CDO).
> 
> 4. **Writing Style & Integrity**:
>    - Style: APA 7th Edition in-text citation format.
>    - Tone: Objective, rigorous, formal academic voice. Use past tense for procedures conducted and present tense for established literature truths.
>    - Authenticity: Never hallucinate or fabricate citations, author names, or empirical statistics.

---

###### Prompt Template B: Chapter 1, Section 1.1 (Background of the Study) Prompt
*Paste this into the user prompt field when generating Section 1.1:*

> **USER PROMPT:**
> 
> **Task**: Draft Section 1.1 (*Background of the Study*) for Chapter 1 of the AMUMA capstone research manuscript.
> 
> **Required Section Outline**:
> 1. **The Mental Health Landscape & Institutional Bottleneck**: Discuss the rising mental health challenges and help-seeking friction among Filipino tertiary students (specifically young adults aged 18–24), highlighting stigma, unfavorable counselor-to-student ratios, and guidance intake bottlenecks at USTP-CDO.
> 2. **Digital Health Interventions as Pre-Clinical Triage**: Examine how Progressive Web Apps (PWAs), multilingual conversational AI buffers (English and Cebuano/Bisaya), and gamified micro-interventions (e.g., Cat Sudoku, streak tracking) can reduce initial hesitation without replacing human professionals.
> 3. **The Regulatory & Ethical Gap in Existing Solutions**: Critique existing commercial solutions that risk legal liability by offering unmonitored out-of-hours queues or pseudo-diagnostic claims that violate RA 11036 and RA 10173.
> 4. **The Rationale for Amuma**: Synthesize why Amuma is uniquely engineered as a decoupled pre-clinical triage buffer, gamified self-care motivator, and college-routed appointment bridge featuring static emergency hotline referrals and encrypted intake briefings for RGCs.
> 
> **Mandatory Constraints**:
> - Abide strictly by the System Instruction guardrails and `research-rules.md`.
> - Include appropriate APA 7th in-text citations for validated instruments (e.g., PHQ-9; Kroenke et al., 2001) and national statutes.
> - Ensure zero clinical or diagnostic overreach.
> - Format in 4–5 coherent academic paragraphs with clear transitions.

---

###### Prompt Template C: Chapter 1, Section 1.2 (Statement of the Problem) Prompt
*Paste this into the user prompt field when generating Section 1.2:*

> **USER PROMPT:**
> 
> **Task**: Draft Section 1.2 (*Statement of the Problem*) for Chapter 1 of the AMUMA research paper.
> 
> **Required Content**:
> 1. **General Problem Statement**: Formulate an overarching statement addressing the lack of a secure, stigma-reducing, and privacy-compliant digital middleman platform connecting USTP-CDO students with university Registered Guidance Counselors (RGCs).
> 2. **Specific Research Questions**: Develop 4 targeted research questions:
>    - *RQ1 (Intake Friction & Venting)*: How does a multilingual conversational AI buffer assist students in articulating emotional distress without making clinical diagnoses?
>    - *RQ2 (Gamified Engagement & Retention)*: To what extent do gamified mental fitness mechanics (daily mood check-ins, CBT micro-exercises, streaks) sustain student self-care engagement?
>    - *RQ3 (Triage & Guidance Scheduling)*: How effectively does college-routed appointment booking and encrypted pre-session intake summarization streamline RGC consultation preparation?
>    - *RQ4 (System Usability & Regulatory Compliance)*: What is the usability rating of the Amuma PWA across ISO/IEC 25010 criteria, and does it strictly comply with RA 10173 (Data Privacy) and RA 11036 (Mental Health)?
> 
> **Mandatory Constraints**:
> - Adhere to APA 7th style and `research-rules.md`.
> - Maintain strict non-diagnostic phrasing across all research questions.

---

###### Prompt Template D: Post-Generation Compliance Audit Prompt
*Paste this into the notebook session immediately after generating text to perform a self-audit:*

> **USER PROMPT:**
> 
> **Audit Task**: Review the preceding draft text against the AMUMA research protocol (`research-rules.md`).
> 
> Check and report on each item:
> 1. **Diagnostic Overreach**: Does any sentence claim or imply that Amuma diagnoses, treats, or evaluates mental illness? If yes, flag the exact sentence and rewrite it to adhere to RA 11036.
> 2. **Emergency Dispatch Liability**: Does the text mention automated crisis dispatching or unmonitored crisis ticketing? If yes, correct it to reference static, offline-cached emergency hotline cards.
> 3. **Demographic & Cohort Fidelity**: Are the demographic targets (USTP-CDO, 18–24 cohort, Cochran $n=687$) cited accurately?
> 4. **Citation Check**: Flag any citation that cannot be verified in established scholarly literature or official statutory gazettes.
> 5. **Tone & Style**: Does the text maintain formal APA 7th academic standards without conversational filler?

---

##### 5. Post-Prompt Verification Checklist (Definition of Done)
- [ ] Master System Instruction (Prompt A) was active throughout generation.
- [ ] Text strictly frames Amuma as a pre-clinical triage buffer, not a diagnostic or clinical tool.
- [ ] National statutes (RA 10173, RA 11036, RA 9258) are accurately referenced.
- [ ] Target cohort is explicitly limited to USTP-CDO tertiary students aged 18–24 (Cochran $n=687$).
- [ ] All citations follow APA 7th format and have been independently verified against legitimate literature.
- [ ] Output audited with Compliance Audit Prompt (Prompt D) and verified for $<15\%$ similarity ceiling.

---

### VI. Tools and Equipment

#### VI.A. Tools (Software & Frameworks)
- **Frontend**: Next.js, React, Tailwind CSS, Service Workers (PWA)
- **Backend & APIs**: Python 3.11+, FastAPI, Uvicorn, Pydantic
- **Database & ORM**: PostgreSQL, SQLAlchemy / Alembic
- **Data Science & Analytics**: Jupyter Notebook, Pandas, NumPy, Seaborn, Matplotlib (see [GEMINI_NOTEBOOK_PROMPTING_GUIDE.md](file:///c:/Users/Nitro/Desktop/Projects/School/amuma/GEMINI_NOTEBOOK_PROMPTING_GUIDE.md))
- **Security & Cryptography**: PyCryptodome / Cryptography (AES-256), OpenSSL (TLS 1.3), JSON Web Tokens (PyJWT)
- **Version Control & Collaboration**: Git, GitHub, Visual Studio Code

#### VI.B. Equipment (Hardware & Infrastructure)
- **Development Workstations**: Multi-core development PCs / Laptops running Windows 11 / Linux
- **Testing Devices**: Android and iOS mobile smartphones for PWA testing and responsive layout verification
- **Hosting / Server Infrastructure**: Containerized runtime environment (Docker), cloud deployment instance or local test server
- **Networking Equipment**: Secure internet connection with SSL/TLS termination proxies
