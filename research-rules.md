# Scientific Research & Development Protocol Rules (Research Template)
## AMUMA: An AI-Driven Appointment Scheduling, Gamified Mental Fitness, and Pre-Clinical Triage System for University Guidance Counseling
**Document Identifier:** `AMUMA-RESEARCH-RULES-v1.0`  
**Target Venue:** IEEE / ACM / Scopus-Indexed Computing & Health Informatics Conference / Journal  
**Affiliation:** College of Information Technology and Computing (CITC), Department of Information Technology, University of Science and Technology of Southern Philippines (USTP-CDO)  
**Authors / Proponents:** Arevalo, Zach Alfred M. · Canoy, John Lloyd D. · Cinco, John Dave P. · Jandayan, Carl Bernie A. · Pimentel, Domvi Ford B.  
**Adviser:** JC Vanny Mill S. Tong  
**Standard Compliance:** Singapore Statement on Research Integrity · FAIR4RS · ACM Artifact Guidelines · CONSORT-AI / CHERRIES · ISO/IEC 25010 · RA 10173 · RA 11036 · RA 9258  

---

## Table of Contents
1. [Core Scientific Research Philosophy & Integrity](#1-core-scientific-research-philosophy--integrity)
2. [Ethical Governance, Human Subjects, & Regulatory Mandates](#2-ethical-governance-human-subjects--regulatory-mandates)
3. [Data Management, Provenance, & FAIR Principles](#3-data-management-provenance--fair-principles)
4. [Computational Reproducibility & Software Artifact Standards (FAIR4RS)](#4-computational-reproducibility--software-artifact-standards-fair4rs)
5. [AI, Multilingual NLP, & Algorithmic Rigor](#5-ai-multilingual-nlp--algorithmic-rigor)
6. [Empirical Evaluation, System Testing, & Statistical Standards](#6-empirical-evaluation-system-testing--statistical-standards)
7. [Academic Writing, Authorship, & Plagiarism Standards](#7-academic-writing-authorship--plagiarism-standards)
8. [Operational Research Pre-Flight Checklist (Definition of Done)](#8-operational-research-pre-flight-checklist-definition-of-done)

---

## 1. Core Scientific Research Philosophy & Integrity

All research and system development conducted under the **AMUMA** project must adhere to the international standards articulated in the **Singapore Statement on Research Integrity (2010)**:

1. **Honesty:** Every claim, metric, user trial finding, and algorithmic benchmark reported in the paper must accurately reflect verified, unfiltered experimental outcomes. Fabricating, falsifying, or cherry-picking baseline comparisons or survey figures is strictly prohibited.
2. **Accountability:** Proponents are collectively and individually accountable for the validity of the code, survey processing pipelines, system architecture, and conclusions drawn in the research.
3. **Professional Courtesy & Fairness:** Intellectual contributions must be appropriately credited via formal citations and CRediT taxonomy disclosures.
4. **Good Stewardship:** Research resources, sensitive participant datasets, university affiliations, and guidance counselor consultation time must be managed with respect, confidentiality, and legal compliance.

---

## 2. Ethical Governance, Human Subjects, & Regulatory Mandates

Because AMUMA operates at the intersection of digital mental health, AI, and human participant intake, the project must strictly abide by both national statutes and global digital health ethics.

```
       ┌────────────────────────────────────────────────────────┐
       │                USTP Research Ethics Board               │
       └───────────────────────────┬────────────────────────────┘
                                   │ Ethical Clearance & Protocols
       ┌───────────────────────────▼────────────────────────────┐
       │               Statutory Compliance Framework           │
       ├───────────────────────────┬────────────────────────────┤
       │  Philippine Data Privacy  │   Philippine Mental Health  │
       │       Act of 2012         │         Act of 2018        │
       │        (RA 10173)         │         (RA 11036)         │
       └─────────────┬─────────────┴──────────────┬─────────────┘
                     │                            │
       ┌─────────────▼─────────────┐┌─────────────▼─────────────┐
       │ • End-to-End Encryption   ││ • Non-Diagnostic Mandate   │
       │   (TLS 1.3 / AES-256)     ││ • Zero Autonomous Prescrip│
       │ • Strict RBAC Isolation   ││ • Human-in-the-Loop RGC    │
       │ • DPO Archiving & Purging ││ • Static Crisis Referral   │
       └───────────────────────────┘└───────────────────────────┘
```

### 2.1 Statutory Guardrails
* **Philippine Data Privacy Act of 2012 (RA 10173):**
  * All triage interactions, check-ins, and intake records constitute **Sensitive Personal Information (SPI)**.
  * In transit, data must enforce **TLS 1.3**; at rest, database records and intake backups must enforce **AES-256** encryption.
  * System architecture must enforce strict **Role-Based Access Control (RBAC)**: Peer facilitators, administrative clerks, and academic faculty are strictly barred from accessing student conversational logs or clinical intake cards.
  * Data retention schedules must match institutional Data Privacy Officer (DPO) and USTP Central Records Unit guidelines with automated log purging.
* **Philippine Mental Health Act (RA 11036) & Non-Diagnostic Architecture:**
  * **Zero Autonomous Medical Diagnosis:** Amuma is strictly engineered as a pre-screening buffer, gamified self-care motivator, and triage bridge—**never** an autonomous diagnostic engine, clinical evaluator, or virtual therapist.
  * **No Automated Crisis Dispatch Liability:** To prevent out-of-hours counselor "last touch" liability, the system explicitly prohibits unmonitored urgent queuing. It instead renders a **permanent, offline-cached Emergency Resource Card** (`tel:` URI links to 911, CSWD CDO 24/7 Psychosocial Hotline, and CUMC Emergency Room).
* **Guidance and Counseling Act of 2004 (RA 9258):**
  * All diagnostic and therapeutic authority remains exclusively with licensed **Registered Guidance Counselors (RGCs)**. System summaries serve only as pre-consultation briefings.

### 2.2 Human Subjects Research & Survey Standards
* **Informed Consent Protocol:** Every survey respondent (such as the $N = 709$ USTP student dataset) must have completed a physical or electronic Informed Consent Form (ICF) stating the research scope, voluntary participation, and an explicit disclaimer that once submitted, responses cannot be withdrawn or retracted due to the strictly anonymous nature of the collected data.
* **Survey Methodology Reporting (CHERRIES Guidelines):**
  * Survey administration and reporting in the paper must follow the **Checklist for Reporting Results of Internet E-Surveys (CHERRIES)**:
    1. **Study Design & Target Sample:** Target youth population ($N \approx 106,973$ in CDO); Cochran’s sample formula target $n \ge 600$; actual validated sample size $N = 709$.
    2. **Institutional & Departmental Ethics:** Documented clearance and compliance with CITC academic research standards.
    3. **Recruitment Channels (Geographically Delimited to CDO):** Hybrid sampling targeting tertiary students situated inside and directly outside the USTP campus, geographically delimited strictly to Cagayan de Oro City. Dissemination was augmented by academic instructors assisting in distributing questionnaires across college classes.
    4. **Incentive Protocol:** Participation was strictly voluntary with zero ($0) financial, gift, or academic grade incentives provided, preventing response inflation and incentive-driven bias.
    5. **Prevention of Duplicate Submissions (Dual-Modality Controls):**
       * *Physical Paper Forms:* Administered manually with a strict one-form-per-student protocol, directly monitored and collected upon completion.
       * *Digital Google Forms:* Floated with the "Limit to 1 response" security toggle strictly enabled (requiring single-response user authentication), systematically preventing respondents from submitting duplicate entries.
    6. **Data Cleansing Criteria:** Systematic handling of non-null counts, validation of completion fields (e.g., Column 0 and Column 30 consent checkboxes), and outlier detection.

---

## 3. Data Management, Provenance, & FAIR Principles

Data handling must conform to the **FAIR Data Principles (Wilkinson et al., 2016)**: **Findable, Accessible, Interoperable, and Reusable**.

### 3.1 Raw Data Immutability
* **Read-Only Raw Data Rule:** The raw data directory (`interpretation/rawdata/`) must be treated as **write-protected and immutable**. 
* **Zero In-Place Edits:** Never modify original CSV/XLSX files in place.
* **Deterministic Transformation Pipelines:** Any cleaning, column renaming, imputation, or filtering must be executed via auditable, documented scripts or computational notebooks, exporting to an intermediate or processed data directory (e.g., `interpretation/processed_data/`).

### 3.2 De-Identification & Anonymization Protocols
Before any dataset or figure is published or pushed to a public repository:
1. **Direct Identifier Elimination:** Remove names, student ID numbers, phone numbers, email addresses, IP addresses, and exact timestamps.
2. **K-Anonymity & Quasi-Identifier Aggregation:** Group sparse demographic categories (e.g., combining low-count academic programs or age extremes) to prevent re-identification through cross-referencing.
3. **Text Scrubbing:** All free-form qualitative feedback (e.g., Column 29: Suggestions/Concerns) must be inspected and scrubbed of specific names, dorm locations, or unique personal identifiers.

### 3.3 Data Dictionary & Codebook
* Every dataset utilized in the study must be accompanied by a formal `DATA_DICTIONARY.md` detailing:
  * Variable name and original survey prompt.
  * Data type (categorical, Likert scale 1–5, float, binary, string).
  * Valid range and coding schema (e.g., `0 = Minimal`, `1 = Mild`, `2 = Moderate`, `3 = Severe`).
  * Missing value conventions and handling logic.

---

## 4. Computational Reproducibility & Software Artifact Standards (FAIR4RS)

Following the **FAIR Principles for Research Software (FAIR4RS)** and **ACM Artifact Review and Badging** guidelines:

```
┌────────────────────────────────────────────────────────────────────────┐
│                   ACM ARTIFACT EVALUATION CRITERIA                     │
├───────────────────────┬───────────────────────┬────────────────────────┤
│  Artifacts Available  │  Artifacts Evaluated  │   Results Reproduced   │
│   (Public / Zenodo)   │ (Documented & Working)│ (Deterministic Scripts)│
└───────────────────────┴───────────────────────┴────────────────────────┘
```

### 4.1 Determinism & Seed Pinning
* **Global Seed Fixation:** All non-deterministic procedures (data splitting, cross-validation, synthetic dataset generation, weight initialization, k-means clustering, embedding generations) must explicitly set fixed seeds:
  ```python
  import os
  import random
  import numpy as np

  SEED = 42
  random.seed(SEED)
  np.random.seed(SEED)
  os.environ["PYTHONHASHSEED"] = str(SEED)
  ```
* Document the exact seed values in the paper's Methodology section.

### 4.2 Dependency Pinning & Environment Isolation
* **Lockfile Enforcement:** Development must occur inside a pinned virtual environment. All dependencies must be strictly version-locked in `requirements.txt` or a lockfile (`pip freeze > requirements.lock` or `conda env export`).
* **Hardware & Runtime Specification:** Record and publish:
  * Python version (e.g., `3.11.x`), Node.js version (e.g., `v20.x`).
  * OS platform (Windows 11 / Linux Ubuntu 22.04 LTS).
  * Compute architecture (CPU / GPU specs, RAM, acceleration libraries like CUDA if applicable).
* **Containerization:** Provide a `Dockerfile` and `docker-compose.yml` encapsulating the backend (FastAPI), frontend (Next.js PWA), and database (PostgreSQL) to enable 1-command replication by external reviewers.

### 4.3 Git Version Control & Commit Hygiene
All research contributions and codebase evolutions must follow **Conventional Commits** tied to specific research milestones:
* `feat(triage): implement PHQ-9 scoring router`
* `eval(nlp): benchmark Bisaya venting response latency`
* `data(survey): clean N=709 demographic survey columns`
* `docs(paper): complete Section 3.2 on ISO 25010 security evaluation`
* `repro(seed): pin random_state=42 across all cross-validation folds`

### 4.4 Software Citation & Archiving
* The repository must include a standardized `CITATION.cff` (Citation File Format) file in the root directory.
* Prior to camera-ready paper submission, create a release snapshot and mint a permanent **Digital Object Identifier (DOI)** using **Zenodo** or **Figshare**.

---

## 5. AI, Multilingual NLP, & Algorithmic Rigor

Given AMUMA's conversational AI venting buffer (English & Cebuano/Bisaya) and triage summary aggregator:

```
[ Student Venting Input (Text / Voice) ]
                     │
         Language Toggle (EN / CEB)
                     │
    ┌────────────────▼────────────────┐
    │     Multilingual AI Buffer      │
    │  - Supportive, Non-Clinical     │
    │  - Strict Grounding Guardrails  │
    └────────────────┬────────────────┘
                     │
      Crisis or Clinical Query Flagged?
         ├── YES ──► Static Emergency Card Triggered (tel: 911 / CSWD)
         └── NO  ──► CBT Micro-Workouts / Habit Rewards / RGC Booking Bridge
```

### 5.1 Multilingual & Dialectal Validation
* **Cebuano / Bisaya Dialect Fidelity:** The system must not rely on raw automated machine translation without human validation. A subset of Cebuano responses must be reviewed by native speakers and an RGC to confirm cultural sensitivity, absence of derogatory idioms, and accurate emotional tone.
* **Code-Switching Support:** Real-world university students in CDO frequently use *Bislish* (Bisaya-English-Tagalog mixing). The evaluation dataset must include authentic mixed-dialect samples to prevent out-of-vocabulary failures.

### 5.2 Train / Validation / Test Splitting Rules
* **Zero Data Leakage:** Ensure training, validation, and holdout test partitions are strictly separated prior to any feature selection, hyperparameter tuning, or normalization.
* **Stratified Sampling:** Stratify splits by key demographic variables (e.g., College unit, year level, language preference) to ensure balanced representation.
* **User-Level Partitioning:** For longitudinal mood tracking or multiple session evaluations, **split by user ID**, never randomly across interactions. Leaking an individual user's data across both train and test splits invalidates scientific claims.

### 5.3 Guardrails & Red-Teaming Against Harm
* **Strict Non-Diagnostic System Prompt:** System prompts must instruct the model to immediately deflect diagnostic questions (e.g., *"Do I have clinical depression?"*) with approved disclaimers directing the student to an RGC.
* **Safety Test Suite (Adversarial Red-Teaming):** Maintain a dedicated test suite (`tests/test_safety_guardrails.py`) containing simulated crisis inputs, self-harm keywords, and diagnostic baiting. Verify that in 100% of test cases:
  * The model outputs empathetic, non-diagnostic guidance.
  * The Static Emergency Resource Card is triggered.
  * No harmful or toxic content is emitted.

### 5.4 Evaluation Metrics Reporting
Papers must report both **computational metrics** and **human evaluation scores**:
* **Quantitative Metrics:** Precision, Recall, Macro-F1 score, Confusion Matrix, and Response Latency (NFR benchmark: UI response $< 3$s, AI response $< 5$s).
* **Qualitative / Human Expert Metrics:** Evaluated by Registered Guidance Counselors (RGCs) using a standardized 5-point Likert rubric:
  1. *Empathy & Tone Appropriateness* (1 = Cold/Robotic, 5 = Empathetic & Safe).
  2. *Safety & Non-Diagnostic Compliance* (Pass/Fail).
  3. *Bisaya Linguistic Naturalness* (1 = Unnatural/Literal translation, 5 = Culturally authentic).

---

## 6. Empirical Evaluation, System Testing, & Statistical Standards

### 6.1 ISO/IEC 25010 Software Product Quality Evaluation
Amuma’s system evaluation must be structured around the international standard **ISO/IEC 25010 SQuaRE**:

| Characteristic | Evaluation Method / Metric | Benchmark Target |
| :--- | :--- | :--- |
| **Functional Suitability** | Black-box test case execution rate across all SRS requirements (FR-01 to FR-25) | 100% Pass on Core Flows |
| **Performance Efficiency** | Page load latency, API response time, concurrent load testing | $< 3$s page load, $< 5$s AI latency |
| **Usability** | System Usability Scale (SUS) questionnaire (10-item standard instrument) | Mean Score $\ge 80$ (Grade A) |
| **Reliability & Availability**| Service Worker offline caching test of emergency hotlines during severed connectivity | 100% availability offline |
| **Security** | Automated vulnerability scans (OWASP ZAP), TLS 1.3 verification, RBAC penetration checks | Zero high/critical vulnerabilities |

### 6.2 System Usability Scale (SUS) Protocol
* Use the standardized 10-item Likert scale developed by John Brooke (1996).
* Compute individual scores using the canonical odd/even formula:
  $$\text{Score}_i = \left(\sum_{k=1,3,5,7,9} (R_k - 1) + \sum_{k=2,4,6,8,10} (5 - R_k)\right) \times 2.5$$
* Report mean, median, standard deviation, and 95% confidence intervals ($[CI_{95\%}]$).

### 6.3 Statistical Rigor in Reporting
1. **Never Report $p = 0.000$:** Report exact values (e.g., $p = .003$) or $p < .001$.
2. **Normality Testing:** Test continuous data for normality using the **Shapiro-Wilk test** prior to applying parametric tests (e.g., Student's t-test, ANOVA). If normality is violated, employ non-parametric equivalents (e.g., Mann-Whitney U, Wilcoxon signed-rank test).
3. **Effect Size:** Always accompany statistical significance with effect sizes (Cohen's $d$, Pearson's $r$, or $\eta^2$).
4. **Sample Size Justification:** The study’s sample size ($N = 709$) exceeds Cochran’s required sample ($n = 600$ at 95% CL, 4% margin of error). State this explicitly in the methodology.

---

## 7. Academic Writing, Authorship, & Plagiarism Standards

### 7.1 Authorship Criteria (ICMJE & CRediT Guidelines)
Following the International Committee of Medical Journal Editors (ICMJE) and CRediT (Contributor Roles Taxonomy), every co-author must fulfill:
1. Substantial contributions to conception, design, acquisition of data, or software development.
2. Drafting the work or revising it critically for important intellectual content.
3. Final approval of the version to be published.
4. Agreement to be accountable for all aspects of the work.

#### Amuma Project CRediT Author Contribution Matrix (To be completed for paper submission):
| Author | Roles (Conceptualization, Methodology, Software, Data Curation, Formal Analysis, Writing - Original Draft, Supervision) |
| :--- | :--- |
| **Arevalo, Zach Alfred M.** | Software Architecture, Backend API, Writing - Original Draft |
| **Canoy, John Lloyd D.** | Data Curation, Statistical Analysis, Survey Methodology |
| **Cinco, John Dave P.** | Multilingual NLP Buffer, Prompt Engineering, Evaluation |
| **Jandayan, Carl Bernie A.** | Frontend PWA, UI/UX Gamification, Usability Evaluation |
| **Pimentel, Domvi Ford B.** | Security Verification, RBAC Testing, Literature Review |
| **Tong, JC Vanny Mill S.** | Supervision, Methodology Validation, Paper Review & Editing |

### 7.2 Plagiarism & Similarity Thresholds
* **Similarity Ceiling:** The Turnitin or iThenticate similarity index must not exceed **15% total**, with no single source exceeding **2%** (excluding standard bibliography and institutional boilerplates).
* **Self-Plagiarism & Salami Slicing:** Avoid duplicating SRS text verbatim into the final journal paper without synthesizing and contextualizing it for academic peer review.

### 7.3 Responsible Use of Generative AI in Scientific Writing
* **IEEE & ACM AI Policies:** Large Language Models (LLMs) cannot be credited as authors.
* **Transparency Declaration:** If generative AI was used for copy-editing, code generation, or literature ideation, add an explicit declaration in the paper's Acknowledgments:
  > *"Acknowledgment of AI Use: During the preparation of this manuscript, the authors utilized [Tool Name] for [code debugging / proofreading / grammar enhancement]. The authors reviewed, validated, and take full responsibility for all content, code, and conclusions."*

---

## 8. Operational Research Pre-Flight Checklist (Definition of Done)

Prior to marking any software feature complete or submitting any paper draft, verify the following checklist:

```markdown
### Phase 1: Data Integrity & Provenance
- [ ] Raw data in `interpretation/rawdata/` is unedited and write-protected.
- [ ] All data cleaning steps are documented in an executable script/notebook.
- [ ] Direct PII has been scrubbed; demographic categories satisfy k-anonymity.
- [ ] Random seed (`SEED = 42`) is pinned across all analytical scripts.

### Phase 2: Regulatory & Ethical Compliance
- [ ] System strictly avoids autonomous diagnosis (RA 11036 compliance verified).
- [ ] Static Emergency Resource Card with click-to-call hotlines functions offline.
- [ ] RBAC isolates student logs from administrative and peer accounts (RA 10173).
- [ ] All participant survey data has documented informed consent (CHERRIES).

### Phase 3: Computational Reproducibility
- [ ] Codebase runs cleanly in an isolated virtual environment.
- [ ] `requirements.txt` contains pinned library versions without conflicts.
- [ ] Git commit messages follow Conventional Commits formatting.
- [ ] `CITATION.cff` is present in the repository root.

### Phase 4: AI & Scientific Evaluation
- [ ] Train/validation/test splits are strictly partitioned without data leakage.
- [ ] Multilingual Bisaya-English inputs are evaluated for both accuracy and cultural tone.
- [ ] Safety guardrail test suite passes with 100% compliance on crisis prompts.
- [ ] ISO/IEC 25010 and SUS usability benchmarks meet target thresholds.

### Phase 5: Scientific Reporting & Authorship
- [ ] Manuscript includes exact p-values, confidence intervals, and effect sizes.
- [ ] CRediT author contribution matrix is signed off by all proponents.
- [ ] Plagiarism similarity index is verified $< 15\%$.
- [ ] Generative AI tool usage is disclosed in the Acknowledgments section.
```

---
*End of Protocol. This document governs all technical sprints, data analytics, and academic writing for Project AMUMA.*
