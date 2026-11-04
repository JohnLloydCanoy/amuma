# Scientific Research Paper Writing & Protocol Rules (Manuscript Template)
## AMUMA: An AI-Driven Appointment Scheduling, Gamified Mental Fitness, and Pre-Clinical Triage System for University Guidance Counseling
**Document Identifier:** `AMUMA-RESEARCH-RULES-v1.0`  
**Target Venue:** IEEE / ACM / Scopus-Indexed Computing & Health Informatics Conference / Journal  
**Affiliation:** College of Information Technology and Computing (CITC), Department of Information Technology, University of Science and Technology of Southern Philippines (USTP-CDO)  
**Authors / Proponents:** Arevalo, Zach Alfred M. · Canoy, John Lloyd D. · Cinco, John Dave P. · Jandayan, Carl Bernie A. · Pimentel, Domvi Ford B.  
**Adviser:** JC Vanny Mill S. Tong  
**Standard Compliance:** Singapore Statement on Research Integrity · APA 7th Edition · IEEE / ACM Author Guidelines · CONSORT-AI / CHERRIES · ISO/IEC 25010 · RA 10173 · RA 11036 · RA 9258  

---

## Table of Contents
1. [Core Scientific Research Philosophy & Integrity](#1-core-scientific-research-philosophy--integrity)
2. [Ethical Governance, Human Subjects, & Regulatory Mandates](#2-ethical-governance-human-subjects--regulatory-mandates)
3. [Data Management, Provenance, & FAIR Principles](#3-data-management-provenance--fair-principles)
4. [Academic Writing Tone, Tense, & Manuscript Conventions](#4-academic-writing-tone-tense--manuscript-conventions)
5. [Standards for Reporting Methodology & AI in the Paper](#5-standards-for-reporting-methodology--ai-in-the-paper)
6. [Empirical Evaluation, System Testing, & Statistical Standards](#6-empirical-evaluation-system-testing--statistical-standards)
7. [Academic Writing, Authorship, & Plagiarism Standards](#7-academic-writing-authorship--plagiarism-standards)
8. [Operational Research Pre-Flight Checklist (Definition of Done)](#8-operational-research-pre-flight-checklist-definition-of-done)
9. [Detailed Operational Rule: k-Anonymity & Quasi-Identifier Aggregation](#9-detailed-operational-rule-k-anonymity--quasi-identifier-aggregation)

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
* **Read-Only Raw Data Rule:** Original, uncleaned survey datasets and response files must be treated as **write-protected and immutable**. 
* **Zero In-Place Edits:** Never modify original raw data files in place.
* **Deterministic Transformation Pipelines:** Any cleaning, column renaming, imputation, or filtering must be executed via auditable, documented transformation scripts or computational notebooks, maintaining a clear separation between raw inputs and cleaned analytical datasets.

### 3.2 De-Identification & Anonymization Protocols
Before any dataset or figure is published or pushed to a public repository:
1. **Direct Identifier Elimination:** Remove names, student ID numbers, phone numbers, email addresses, IP addresses, and exact timestamps.
2. **K-Anonymity & Quasi-Identifier Aggregation:** Group sparse demographic categories (e.g., combining low-count academic programs or age extremes) to prevent re-identification through cross-referencing.
3. **Text Scrubbing:** All free-form qualitative feedback (e.g., Column 29: Suggestions/Concerns) must be inspected and scrubbed of specific names, dorm locations, or unique personal identifiers.

### 3.3 Data Dictionary & Codebook
* Every dataset utilized in the study must be accompanied by a formal Data Dictionary / Codebook detailing:
  * Variable name and original survey prompt.
  * Data type (categorical, Likert scale 1–5, float, binary, string).
  * Valid range and coding schema (e.g., `0 = Minimal`, `1 = Mild`, `2 = Moderate`, `3 = Severe`).
  * Missing value conventions and handling logic.

---

## 4. Academic Writing Tone, Tense, & Manuscript Conventions

This section governs the formal grammar, academic register, and rhetorical conventions required when writing all chapters, drafts, and submissions of the research paper.

### 4.1 Academic Voice, Tone, & Scholarly Register
* **Objective Third-Person Stance:** The manuscript must maintain a formal, scholarly register. Avoid informal first-person narratives (*"we felt"*, *"I decided"*, *"in our opinion"*). Structure statements around the empirical evidence, the methodology, or the system:
  * *Disallowed:* *"We built Amuma because we noticed counseling in USTP is hard to book."*
  * *Standard Academic:* *"The Amuma platform was engineered to mitigate institutional intake friction and address student-reported hesitancy within university guidance counseling workflows."*
* **Prohibition of Hype & Commercial Slang:** Never use conversational colloquialisms, marketing buzzwords, or emotional superlatives (*"revolutionary"*, *"game-changing"*, *"groundbreaking app"*, *"super helpful"*, *"miracle cure"*). Use precise, measured scientific descriptors (*"statistically significant"*, *"empirically evaluated"*, *"computationally efficient"*, *"clinically aligned"*).
* **Active vs. Passive Voice Conventions (APA 7th Edition Standard):**
  * **Use Passive Voice** when reporting standardized experimental procedures where the researcher is secondary to the scientific method (*"Surveys were administered across university units...", "Responses were cleaned and de-identified...", "System components were evaluated..."*).
  * **Use Active Voice** when describing software mechanics, architecture, or conceptual frameworks (*"The FastAPI microservice processes triage payloads...", "Figure 2 illustrates the state transition architecture..."*).

### 4.2 Section-by-Section Academic Tense Matrix
To guarantee grammatical consistency across chapters, adhere strictly to this academic tense matrix:

| Manuscript Section | Primary Tense | Concrete Usage Rules & Examples |
| :--- | :--- | :--- |
| **Title & Subheadings** | **Noun Phrases** (Title Case) | Concise, descriptive noun phrases (*"Multilingual Conversational Buffering for University Guidance Intake"*). |
| **Abstract** | **Past Tense** (methods/results)<br>**Present Tense** (conclusions) | • *Past:* *"A pre-clinical triage platform was developed..."*, *"The system demonstrated high usability ($M = 82.4$)..."*<br>• *Present:* *"These findings highlight the feasibility of digital buffers in university mental health."* |
| **Introduction & Problem Statement** | **Present Tense** (current realities)<br>**Present Perfect** (ongoing gaps) | • *Present:* *"Mental health stigma remains a pervasive barrier to help-seeking in Philippine higher education..."*<br>• *Present Perfect:* *"Recent institutional studies have documented widening counselor-to-student ratios..."* |
| **Literature Review / Related Work** | **Past Tense** (prior studies)<br>**Present Tense** (established theories) | • *Past:* *"Santos et al. (2024) investigated student reluctance toward manual intake..."*<br>• *Present:* *"The Cognitive Behavioral Therapy (CBT) paradigm posits that structured cognitive reframing mitigates acute distress..."* |
| **Methodology & System Architecture** | **Past Tense** (procedures executed)<br>**Present Tense** (permanent architecture) | • *Past:* *"A hybrid survey of 709 respondents was conducted...", "Data were partitioned using stratified sampling..."*<br>• *Present:* *"The Amuma architecture comprises four interconnected service tiers..."* |
| **Results & Empirical Findings** | **Past Tense** (observed data)<br>**Present Tense** (tables & charts) | • *Past:* *"The model achieved an F1-score of 0.89...", "Students reported significantly higher comfort..."*<br>• *Present:* *"Table 3 presents the comparative latency metrics...", "Figure 4 displays the confusion matrix..."* |
| **Discussion & Analytical Synthesis** | **Present Tense** (interpreting meaning)<br>**Past Tense** (recalling observations) | • *Present:* *"These outcomes indicate that dialect-aware venting reduces initial intake apprehension..."*<br>• *Past:* *"Because respondents highlighted severe privacy anxieties during preliminary evaluations..."* |
| **Conclusion & Future Directions** | **Present Tense** (final deductions)<br>**Future / Modal Tense** (next steps) | • *Present:* *"Amuma provides an empirical blueprint for low-barrier university counseling triage..."*<br>• *Future/Modal:* *"Future investigations will expand longitudinal habit tracking across multi-campus university systems."* |

### 4.3 Mathematical, Numerical, & Statistical Prose Conventions
* **Number Formatting Rules:**
  * Spell out words for cardinal numbers below 10 (*"four functional modules"*, *"three primary stressors"*); use numerals for 10 and above (*"709 respondents"*, *"14-day observation window"*).
  * Always use numerals when paired with units of measurement, percentages, or mathematical operations (*"3 seconds"*, *"5-point Likert scale"*, *"15% buffer"*).
* **Statistical Notation Formatting (APA 7th Edition Standard):**
  * Italicize all standard statistical symbols: *$N$* (total sample), *$n$* (subsample), *$M$* (mean), *$SD$* (standard deviation), *$p$* (probability), *$t$*, *$F$*, *$z$*, *$R^2$*, *$d$*.
  * **No Leading Zero on Probabilities:** Because probability values cannot exceed 1.0, omit the leading zero: report *$p = .003$*, *$p = .042$*, or *$p < .001$*. **Never write $p = 0.000$**.
  * Always report dispersion alongside central tendency: e.g., *$M = 82.5, SD = 6.4$*, and provide 95% Confidence Intervals: *$95\% \text{ CI } [78.2, 86.8]$*.
* **Acronym & Abbreviation Protocol:**
  * Spell out every acronym on first occurrence in the Abstract and again on first appearance in the manuscript body, followed immediately by its abbreviation in parentheses: e.g., *"Registered Guidance Counselor (RGC)"*, *"Role-Based Access Control (RBAC)"*, *"Progressive Web App (PWA)"*.
  * Once defined, use the acronym consistently; avoid alternating between the full term and the abbreviation.

### 4.4 Scientific Citation & Paraphrasing Integrity (Strict APA 7th Edition)
* **Synthesis Over Direct Quotation:** Avoid block quotes or verbatim literature excerpts. Synthesize external research into original analytical prose that directly supports your thesis.
* **In-Text Citation Formatting (Strict APA 7th Edition):** All in-text citations must strictly adhere to the APA 7th Edition author-date format:
  * **Parenthetical Citation:** Place author surname(s) and publication year in parentheses: `(Santos & Cruz, 2024)` or `(Kroenke et al., 2001)`. Use an ampersand (`&`) between two authors within parentheses.
  * **Narrative Citation:** Integrate author surname(s) directly into the sentence prose with the year in parentheses: `Santos and Cruz (2024) observed that...` or `Kroenke et al. (2001) established that...`. Spell out the word *"and"* in narrative running text.
  * **Three or More Authors:** From the very first citation, truncate to the first author's surname followed immediately by *"et al."* and the year: `(Arevalo et al., 2026)` or `Arevalo et al. (2026)`.
  * **Multiple Citations in One Parenthesis:** Alphabetize multiple parenthetical citations by the first author's surname and separate distinct studies with semicolons: `(Brooke, 1996; Kroenke et al., 2001; Sweeney, 2002)`.
  * **In-Text Citation Placement:** Position parenthetical citations immediately adjacent to the relevant claim or statistic, strictly before the terminal punctuation mark.
* **Reference List Formatting (APA 7th Edition):**
  * Include a dedicated References section at the end of the paper with a hanging indent (0.5 in).
  * Alphabetize all entries by the surname of the first author.
  * Provide clickable Digital Object Identifier (DOI) URLs formatted as `https://doi.org/10.xxxx/...` for all journal articles and proceedings.
* **Primary Literature Ratio:** Ensure at least 80% of cited sources consist of peer-reviewed journal articles, conference proceedings, or official statutory acts published within the last 5 years.

---

## 5. Standards for Reporting Methodology & AI in the Paper

This section establishes how the technical implementation, conversational AI buffer, multilingual dialect handling, and evaluation pipelines must be formally articulated and justified within the paper's narrative.

### 5.1 Manuscript Standards for Reporting the Multilingual AI Buffer
* **Academic Terminology:** Formally describe the conversational module as a *"multilingual pre-clinical conversational buffer"* or *"supportive digital middleman interface"*. Strictly avoid referring to the system as a *"virtual therapist"* or *"automated medical psychologist"*.
* **Linguistic Rationale (Cebuano/Bisaya & Code-Switching):**
  * The Methodology section must provide empirical justification for supporting Cebuano and *Bislish* (Bisaya-English-Tagalog mixing): document that university students in Cagayan de Oro articulate intimate emotional distress more authentically when utilizing native dialectal expressions.
  * Report the qualitative verification process: state that generated Cebuano responses were reviewed by native speakers and an RGC to confirm cultural sensitivity, absence of inappropriate idioms, and supportive emotional cadence.
* **System Prompt & Guardrail Disclosure:** Document the core prompt engineering constraints within the paper (or an appendix): describe how the AI is explicitly instructed to provide supportive, non-clinical listening while prohibiting diagnostic assertions or prescription recommendations.

### 5.2 Manuscript Standards for Reporting Data Partitioning & Reproducibility
* **Zero Data Leakage Documentation:**
  * In the Methodology section, clearly state the train/validation/test split ratios (e.g., 70/15/15 or 80/20) and the stratification criteria used across student year levels and college departments.
  * **Report User-Level Splitting:** Explicitly document that partitioning for longitudinal interactions or multi-session evaluations was executed strictly at the **individual participant level** rather than the interaction level, ensuring no student's data appears in both training and test partitions.
* **Computational Determinism Statement:** Include an explicit reproducibility statement in Chapter 3:  
  > *"To ensure complete computational reproducibility, all data partitioning, clustering, and baseline evaluation routines were executed using a fixed pseudo-random seed parameter ($SEED = 42$) across all experimental iterations."*

### 5.3 Manuscript Standards for Reporting Non-Diagnostic Guardrails & Ethical Safety
* **Dedicated Ethics & Safety Subsection:** The paper must feature a dedicated subsection titled *Ethical Governance and Non-Diagnostic Safety Protocols*, detailing:
  1. **Compliance with the Philippine Mental Health Act (RA 11036):** Emphasizing that Amuma operates solely as a pre-screening bridge, preserving 100% of diagnostic and therapeutic authority for human Registered Guidance Counselors (RGCs).
  2. **Statutory Data Privacy Protection (RA 10173):** Reporting end-to-end data encryption (TLS 1.3 in transit, AES-256 at rest) and RBAC data isolation preventing unauthorized personnel (clerks, peer facilitators) from viewing student intake logs.
  3. **Adversarial Red-Teaming Results:** Report the methodology used to stress-test the conversational buffer with adversarial crisis prompts, self-harm keywords, and diagnostic baiting. Report that the system achieved 100% compliance by withholding diagnostic claims and immediately rendering the static Emergency Resource Card (`tel:` URI links to 911 and CSWD CDO).

### 5.4 Tabular & Narrative Standards for Reporting Evaluation Metrics
* **Dual-Modality Evaluation Reporting:** The Results section must present both objective computational metrics and subjective human-expert ratings:
  * **Quantitative Computational Benchmarks:** Present Precision, Recall, Macro-averaged F1-score, Confusion Matrix classifications, and Latency benchmarks (UI page load $< 3$s, AI inference $< 5$s).
  * **Qualitative Clinical Expert Ratings:** Present Registered Guidance Counselor (RGC) evaluations conducted on structured 5-point Likert scales covering:
    1. *Empathy and Supportive Tone* ($1 = \text{Cold/Robotic}$, $5 = \text{Highly Empathetic}$).
    2. *Non-Diagnostic Safety Compliance* ($\text{Pass/Fail}$).
    3. *Bisaya Dialectal Authenticity* ($1 = \text{Artificial/Literal Translation}$, $5 = \text{Culturally Natural}$).
* **Linking Metrics to Practical Significance:** Every metric reported in the narrative must be contextualized: discuss how lower response latency and higher dialectal comfort directly eliminate intake hesitation and facilitate successful counseling appointments.

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
- [ ] Original raw dataset is unedited, safely backed up, and write-protected.
- [ ] All data cleaning steps are documented in an executable script/notebook.
- [ ] Direct PII has been scrubbed; demographic categories satisfy k-anonymity.
- [ ] Random seed (`SEED = 42`) is pinned across all analytical scripts.

### Phase 2: Regulatory & Ethical Compliance
- [ ] System strictly avoids autonomous diagnosis (RA 11036 compliance verified).
- [ ] Static Emergency Resource Card with click-to-call hotlines functions offline.
- [ ] RBAC isolates student logs from administrative and peer accounts (RA 10173).
- [ ] All participant survey data has documented informed consent (CHERRIES).

### Phase 3: Academic Tone, Tense, & Manuscript Quality
- [ ] Objective third-person voice maintained; zero conversational colloquialisms or marketing hype.
- [ ] Section-by-section academic tense rules strictly verified (Past for methods/results, Present for theories/architecture).
- [ ] All statistical values correctly formatted ($p < .001$, no leading zeros on probabilities, italicized symbols).
- [ ] All acronyms explicitly expanded upon first use in Abstract and Body.

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

## 9. Detailed Operational Rule: k-Anonymity & Quasi-Identifier Aggregation

### 9.1 The Re-Identification Vulnerability (The "Jigsaw Effect")
In scientific health informatics and under the **Philippine Data Privacy Act (RA 10173)**, removing **Direct Identifiers** (such as Student Names, ID Numbers, Email Addresses, and Phone Numbers) is **necessary but insufficient** to guarantee participant privacy.

When secondary attributes—known as **Quasi-Identifiers**—are combined, they can uniquely single out an individual through cross-referencing:
* **Direct Identifiers (Explicit PII):** Full Name, Student ID, Email, Phone, IP Address, Physical Address. *(Must be 100% eliminated before analysis).*
* **Quasi-Identifiers (Indirect Clues):** Age, Academic College/Department, Specific Degree Program, Year Level, Dialect, Living Arrangement.

> [!WARNING] The Re-Identification Scenario
> Suppose the dataset contains an entry with: `Age: 27`, `Program: BS Technology Communication Management`, `Year: 4th Year`, paired with sensitive disclosures regarding severe depression or interpersonal trauma.  
> Even without a name, anyone within that small department can easily deduce the student's exact identity because only one student fits that precise demographic profile. This constitutes a severe privacy violation.

---

### 9.2 The Mathematical Standard of $k$-Anonymity
To systematically eliminate re-identification risks, the project enforces **$k$-Anonymity** (Sweeney, 2002):
* A dataset satisfies **$k$-anonymity** if every distinct combination of quasi-identifiers is shared by at least **$k$ individuals** within the release.
* For Project AMUMA's public reporting, cross-tabulations, and paper publications, the team enforces a minimum threshold of **$k \ge 5$**. No reported demographic cell or published subgroup may isolate fewer than 5 respondents.

$$\forall Q \in \text{Quasi-Identifiers}, \quad \text{count}(Q) \ge k \quad (\text{where } k = 5)$$

---

### 9.3 Practical Transformation Strategies for AMUMA Survey Data

When preparing data tables, statistical models, or visualization charts, researchers must apply **Generalization** and **Suppression/Aggregation**:

| Survey Variable | Raw / Vulnerable Format | Aggregated / $k$-Anonymous Rule | Rationale |
| :--- | :--- | :--- | :--- |
| **Age** | Raw continuous integers (e.g., `17, 26, 27, 28`) | Bin into standard demographic tiers:<br>• `< 18`<br>• `18 – 20`<br>• `21 – 23`<br>• `24+` | Collapses outliers and elderly/minor extremes into broader cohorts. |
| **Academic Program** | Granular text labels with sparse counts (e.g., programs with only 1–2 respondents) | Group programs with $n < 5$ respondents into broader classifications:<br>• `"Other CITC Programs"`<br>• `"Engineering & Architecture (CEA)"`<br>• `"External / Non-USTP"` | Prevents isolating single students enrolled in niche degree programs. |
| **Year Level** | Rare statuses (e.g., `Irregular 5th Year`, `Extended`) | Recode sparse categories into standard tiers:<br>• `1st Year`<br>• `2nd Year`<br>• `3rd Year`<br>• `4th Year / Senior+` | Blends non-traditional student standing into common cohorts. |
| **Free-Form Text (Suggestions & Concerns)** | Unfiltered qualitative text containing names, dorm names, or course codes | Perform manual de-identification scrubbing:<br>• Replace specific professor/staff names with `[FACULTY]`<br>• Replace dorm/boarding house addresses with `[OFF-CAMPUS HOUSING]`<br>• Replace specific section codes with `[SECTION]` | Ensures students venting about personal or departmental incidents cannot be identified by wording. |

---

### 9.4 Pre-Publication Verification Checklist
Before submitting any manuscript chapter, conference slide, or public repository release:
1. **Frequency Table Audit:** Run a frequency distribution on all quasi-identifier combinations (`Age Group` $\times$ `College` $\times$ `Year Level`). If any group has a count $n < 5$, apply further aggregation.
2. **Cell Suppression in Cross-Tabs:** In multi-dimensional demographic tables, suppress cells with counts under 5 (displaying `< 5` or `*`) to prevent re-identification.
3. **No Direct Row Dumps:** Never publish raw individual survey rows in paper appendices; always present aggregated summaries, frequency distributions, or anonymized quotes.

---
*End of Protocol. This document governs all technical sprints, data analytics, and academic writing for Project AMUMA.*
