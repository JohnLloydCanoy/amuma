# REPUBLIC OF THE PHILIPPINES
## UNIVERSITY OF SCIENCE AND TECHNOLOGY OF SOUTHERN PHILIPPINES
### CAGAYAN DE ORO CAMPUS
*C.M. Recto Avenue, Lapasan, Cagayan de Oro City 9000, Philippines*

**COLLEGE OF INFORMATION TECHNOLOGY AND COMPUTING**  
*Department of Information Technology*

---

# SOFTWARE REQUIREMENTS SPECIFICATION

## AMUMA
### An AI-Driven Appointment Scheduling, Gamified Mental Fitness, and Pre-Clinical Triage System for University Guidance Counseling

**PROPONENTS:**  
* Arevalo, Zach Alfred M.
* Canoy, John Lloyd D.
* Cinco, John Dave P.
* Jandayan, Carl Bernie A.
* Pimentel, Domvi Ford B.

**ADVISER:** JC Vanny Mill S. Tong  
**DATE:** September 2026  

---

## Revision History

| Version | Date | Description | Author |
| :--- | :--- | :--- | :--- |
| **1.0** | September 13, 2026 | Initial Draft of the SRS | Project Team |
| **1.1** | October 15, 2026 | Consolidated Scope, Removed NLP Emergency Detection, SMART FRs/NFRs, and Complete Appendices | Project Team |

---

## Table of Contents

- [1. Introduction](#1-introduction)
  - [1.1 Purpose](#11-purpose)
  - [1.2 Scope](#12-scope)
  - [1.3 Definitions, Acronyms, and Abbreviations](#13-definitions-acronyms-and-abbreviations)
  - [1.4 References](#14-references)
  - [1.5 Overview](#15-overview)
- [2. Overall Description](#2-overall-description)
  - [2.1 Product Perspective](#21-product-perspective)
  - [2.2 Product Functions](#22-product-functions)
  - [2.3 User Classes and Characteristics](#23-user-classes-and-characteristics)
  - [2.4 Operating Environment](#24-operating-environment)
  - [2.5 Design and Implementation Constraints](#25-design-and-implementation-constraints)
  - [2.6 Assumptions and Dependencies](#26-assumptions-and-dependencies)
- [3. Specific Requirements](#3-specific-requirements)
  - [3.1 Functional Requirements](#31-functional-requirements)
  - [3.2 Non-Functional Requirements](#32-non-functional-requirements)
  - [3.3 External Interface Requirements](#33-external-interface-requirements)
  - [3.4 System Feature: AI-Powered Student Mental Wellness Support & Booking Bridge (Use Case)](#34-system-feature-ai-powered-student-mental-wellness-support--booking-bridge-use-case)
- [4. Appendices](#4-appendices)
  - [Appendix A: Project Research Reference Data & Clinical Screening Tools](#appendix-a-project-research-reference-data--clinical-screening-tools)
  - [Appendix B: System Analysis & Design Models](#appendix-b-system-analysis--design-models)
  - [Appendix C: Data Privacy, Ethical Compliance & Regulatory Checklists](#appendix-c-data-privacy-ethical-compliance--regulatory-checklists)

---

# 1. Introduction

## 1.1 Purpose
The purpose of this Software Requirements Specification (SRS) document is to define the complete functional, non-functional, interface, and legal requirements for **Amuma**. Amuma is a mobile Progressive Web App (PWA) designed as a digital pre-screening buffer, gamified self-care platform, and appointment scheduling bridge between university students and Registered Guidance Counselors (RGCs) at the University of Science and Technology of Southern Philippines – Cagayan de Oro Campus (USTP-CDO).

This specification is intended for the capstone development team, faculty evaluators, institutional administrators, and guidance office stakeholders to guide software architecture, system implementation, verification, and ethical compliance.

## 1.2 Scope

### 1.2.1 Product Name & Description
**Amuma** is a privacy-first, multilingual Progressive Web App (PWA) engineered to eliminate counseling intake friction, reduce student self-stigma, and optimize guidance scheduling workflows at USTP-CDO within the broader demographic setting of Cagayan de Oro City.

### 1.2.2 System Modules (In-Scope)
1. **Multilingual Conversational AI Buffer**: Offers text- and voice-based emotional venting in English and Cebuano (Bisaya) with supportive, non-clinical responses.
2. **Gamified Mental Fitness & Mood Tracking Hub**: Includes daily check-ins, interactive stress-relief mini-games (e.g., Cat Sudoku), CBT micro-exercises, virtual companion pet nurturing, check-in streaks, and automatic exam-week "Streak Freezes".
3. **Centralized Appointment Booking Bridge**: Enables smart, college-based routing to assigned Registered Guidance Counselors (RGCs), real-time slot selection, and automated encrypted booking vouchers.
4. **Counselor Dashboard & Pre-Screening Summaries**: Aggregates qualitative pre-screening insights, primary stressor tags, PHQ-9 distress indicators, and 14-day CBT habit trends into encrypted dashboard summaries with 1-click printable A4 PDF exports.
5. **Static Emergency Resource Card**: Features permanent, offline-cached click-to-call (`tel:` URI) buttons for 24/7 emergency hotlines alongside non-diagnostic disclaimers.

### 1.2.3 System Out-of-Scope (Boundaries & Exclusions)
1. **No Autonomous Medical Diagnosis or Medication Prescription**: Amuma strictly operates as a pre-screening buffer and triage router—not a medical diagnostic tool or virtual therapist.
2. **No Replacement for Human Psychotherapy**: The platform does not issue clinical diagnoses or conduct formal psychiatric treatment.
3. **No Real-Time Automated AI Crisis Detection or Emergency Dispatching**: The system explicitly avoids automated real-time NLP keyword scanning, risk-scoring, or active emergency dispatching to eliminate out-of-hours counselor "last touch" legal liabilities.
4. **No Unsupervised Out-of-Hours Ticket Queuing**: The platform does not queue unmonitored urgent distress tickets during off-hours, directing students to static emergency hotlines instead.
5. **No Disciplinary Tracking or Academic Integration**: System databases are strictly isolated from academic records, student discipline portals, faculty accounts, or external government registries.

## 1.3 Definitions, Acronyms, and Abbreviations

| Term / Acronym | Definition |
| :--- | :--- |
| **Amuma** | Visayan term meaning "to nurture, care for, or foster gently"; the project title for the mental wellness platform. |
| **AES-256** | Advanced Encryption Standard with a 256-bit key; enforced for database storage at rest. |
| **CBT** | Cognitive Behavioral Therapy; evidence-based psychological interventions adapted into micro-workouts. |
| **CSWD** | City Social Welfare and Development office of Cagayan de Oro City, operating 24/7 psychosocial hotlines. |
| **DFD** | Data Flow Diagram; structural representation of data inputs, processes, stores, and outputs. |
| **DPO** | Data Privacy Officer; university official responsible for enforcing organizational privacy policies. |
| **FastAPI** | High-performance Python web framework used for backend microservices and AI payload processing. |
| **JWT** | JSON Web Token; compact, URL-safe means of representing claims for secure authentication. |
| **Next.js** | React-based web framework utilized for building the Progressive Web App frontend. |
| **PHQ-9** | Patient Health Questionnaire-9; standardized 9-item clinical instrument measuring depression severity. |
| **PWA** | Progressive Web App; cross-platform web application installable on mobile devices with offline support. |
| **RA 10173** | Republic Act No. 10173, also known as the Philippine Data Privacy Act of 2012. |
| **RA 11036** | Republic Act No. 11036, also known as the Philippine Mental Health Act. |
| **RBAC** | Role-Based Access Control; system security restricting data access based on validated user roles. |
| **RGC** | Registered Guidance Counselor; licensed professional authorized to review intake summaries and conduct therapy. |
| **TLS 1.3** | Transport Layer Security protocol version 1.3; enforced for all data transmitted in transit. |
| **USTP-CDO** | University of Science and Technology of Southern Philippines – Cagayan de Oro Campus; primary study setting. |

## 1.4 References
1. Republic Act No. 10173 (2012). *Philippine Data Privacy Act of 2012*. Official Gazette of the Republic of the Philippines.
2. Republic Act No. 11036 (2018). *Philippine Mental Health Act*. Official Gazette of the Republic of the Philippines.
3. Kroenke, K., Spitzer, R. L., & Williams, J. B. (2001). The PHQ-9: Validity of a brief depression severity measure. *Journal of General Internal Medicine*, 16(9), 606-613.
4. IEEE Computer Society (1998). *IEEE Std 830-1998: IEEE Recommended Practice for Software Requirements Specifications*. IEEE.
5. USTP Guidance and Counseling Office Interview Records (2026). Stakeholder Consultation with RGC Faculty, USTP-CDO.

## 1.5 Overview
This Software Requirements Specification (SRS) is structured into four main sections following standard IEEE 830 guidelines. **Section 1 (Introduction)** provides the purpose, core objectives, project scope, definitions, references, and document structure. **Section 2 (Overall Description)** presents a high-level overview of the Amuma platform, detailing its product perspective as a digital middleman bridge, core product functions, four-tier user classes (Students, Registered Guidance Counselors, Administrative Clerks, and System Administrators), mobile PWA operating environment, legal and technical design constraints (RA 10173 and RA 11036), and operational dependencies. **Section 3 (Specific Requirements)** details the specific functional requirements (spanning student profile management, multilingual AI venting, gamified wellness tools, college-routed appointment booking, and RGC intake summarization), non-functional performance and security quality benchmarks, external interface specifications, and a detailed use case. Finally, **Section 4 (Appendices)** provides supporting research data, including the PHQ-9 depression severity index, Cochran sample size parameters, Data Flow Diagram (DFD) context architecture, appointment booking state models, and regulatory compliance matrices.

---

# 2. Overall Description

## 2.1 Product Perspective
Amuma is an independent, specialized digital middleman ecosystem designed to bridge the gap between student self-care and professional university guidance counseling. Rather than operating as an isolated chatbot or an administrative scheduling portal, Amuma unifies pre-clinical conversational AI buffering, habit gamification, and college-routed appointment scheduling into a seamless, privacy-compliant PWA.

```
 [ USTP-CDO Student (PWA) ]
        │
        ├── Multilingual Venting / Mood Logs / Casual Gaming
        ├── College-Specific RGC Slot Booking
        ▼
 [ Amuma Middleman Platform Engine (Next.js / FastAPI) ]
        │
        ├── TLS 1.3 Encrypted Transit / AES-256 Storage at Rest
        ├── Role-Based Access Control (RBAC) Isolation
        ▼
 [ RGC Clinical Dashboard ] ──► Standardized Intake Summary A4 PDF Export
```

## 2.2 Product Functions
1. **Multilingual Emotional Venting Buffer**: Accepts text/voice venting in English or Cebuano (Bisaya) and provides supportive, non-clinical responses.
2. **Gamified Fitness & Mood Tracking**: Records mood check-ins, tracks streaks, provides "Streak Freezes", awards virtual pet items, and renders stress-relief mini-games (e.g., Cat Sudoku).
3. **College-Routed Appointment Scheduling**: Displays live calendar slots managed by the assigned college RGC and issues booking vouchers.
4. **Pre-Session Intake Summarization**: Compiles qualitative intake trends, primary stressor tags, and baseline PHQ-9 indicators into encrypted dashboard summaries with A4 PDF export capabilities.
5. **Static Emergency Referral**: Displays click-to-call (`tel:` URI) buttons for 24/7 emergency hotlines with explicit non-diagnostic disclaimers.

## 2.3 User Classes and Characteristics

| User Class | Description | Technical Literacy | Security Clearance |
| :--- | :--- | :--- | :--- |
| **Student** | Enrolled USTP-CDO tertiary student (aged 18–24) accessing self-care tools, AI venting, and appointment booking. | Moderate to High | Access restricted strictly to personal account, logs, and booking vouchers. |
| **Registered Guidance Counselor (RGC)** | Licensed professional reviewing assigned college intake summaries, managing appointment calendars, and exporting intake PDFs. | Moderate | Access restricted to intake summaries and booking slots for their assigned academic college unit. |
| **Administrative Clerk** | Guidance office staff managing general appointment slot availability and aggregated anonymized statistics. | Moderate | Strictly prohibited from viewing student chat transcripts, PHQ-9 narrative data, or clinical summaries. |
| **System Administrator** | Technical team member maintaining server infrastructure, security configurations, RBAC rules, and system backups. | High | System-level maintenance access; user data remains encrypted at rest. |

## 2.4 Operating Environment
* **Client Frontend**: Progressive Web App (PWA) accessible via modern web browsers (Chrome, Safari, Edge, Firefox) across Android, iOS, Windows, and macOS devices.
* **Server Infrastructure**: Cloud or local containerized hosting (Docker) executing Next.js Node server and Python FastAPI microservices.
* **Database Management System**: Encrypted PostgreSQL database storing user profiles, hashed credentials, calendar slots, and encrypted intake summaries.

## 2.5 Design and Implementation Constraints

### 2.5.1 Legal, Regulatory, and Ethical Constraints
* **Philippine Data Privacy Act of 2012 (RA 10173)**: All transmitted and stored student triage data must enforce end-to-end encryption (**TLS 1.3 in transit, AES-256 at rest**). Access to student records is governed by strict, segmented Role-Based Access Control (RBAC), ensuring detailed clinical intake summaries are accessible exclusively by assigned Registered Guidance Counselors (RGCs) for their designated college units. Digital log retention and purging routines must strictly align with institutional Data Privacy Officer (DPO) guidelines and the university’s Central Records Unit archiving policies.
* **Philippine Mental Health Act (RA 11036) & Non-Diagnostic Architecture**: Amuma strictly operates as an informative pre-screening buffer, self-care motivator, and booking bridge—**not a medical diagnostic tool or virtual therapist**. The system cannot issue formal clinical diagnoses, psychological evaluations, or medical prescriptions, shielding both the student development team and the university from clinical liability.
* **Emergency & Out-of-Hours Duty of Care Boundaries**: To protect counselors and the university under "last touch" legal liabilities and institutional ethics, **the system explicitly avoids promising automated 24/7 crisis monitoring or real-time AI emergency intervention**. Instead, the platform incorporates a permanent, prominent Emergency Resource Card featuring click-to-call links to active 24/7 municipal and campus emergency services (such as the **CSWD 24/7 Psychosocial Hotline, 911, and CUMC Emergency Room**). Clear, explicit disclaimers inform users that Amuma is a non-acute self-care platform and instruct individuals experiencing immediate crisis or self-harm to contact live emergency responders directly, rather than queuing an unmonitored offline ticket.

### 2.5.2 Hardware, Software, and Security Constraints
* System API traffic must execute exclusively over HTTPS secured via TLS 1.3.
* All database tables containing user-identifying metadata or intake notes must be encrypted using AES-256 algorithms.
* Front-end UI components must maintain responsive, mobile-first layouts optimized for entry-level smartphone displays.

### 2.5.3 Operating Environment Constraints
* PWA assets and the static emergency card must be cached locally using Service Workers to allow offline access during network outages.

## 2.6 Assumptions and Dependencies
* **Assumptions**: Students possess access to an internet-connected smartphone or computing device; RGCs maintain updated availability on their calendar dashboards.
* **Dependencies**: Emergency hotline referrals depend on maintaining accurate contact numbers verified periodically with municipal providers (CSWD, 911, CUMC).

---

# 3. Specific Requirements

## 3.1 Functional Requirements

### 3.1.1 Student Account & Profile Management
* **FR-01**: The system shall allow USTP-CDO students to securely register for an account and authenticate using valid credentials.
* **FR-02**: The system shall allow authenticated students to view and update permitted profile information (such as academic program and year level).
* **FR-03**: The system shall enforce data isolation ensuring that students can strictly access only their own personal account information, wellness logs, and booking records.

### 3.1.2 Multilingual Conversational AI Buffer
* **FR-04**: The system shall enable students to engage in text-based conversational AI emotional venting sessions.
* **FR-05**: The system shall support voice-based conversational AI emotional venting when browser microphone permissions and Web Audio APIs are enabled.
* **FR-06**: The system shall provide supportive, non-judgmental conversational responses that assist students in identifying non-clinical self-care steps.
* **FR-07 (Static Emergency Resource Card & Crisis Disclaimer)**: The system shall maintain a permanent, prominent Emergency Resource Card accessible on the main student dashboard and offline fallback screens, displaying click-to-call (`tel:` URI) links for active 24/7 hotlines (CSWD 24/7 Psychosocial Hotline, 911, CUMC Emergency) alongside an explicit legal disclaimer confirming that Amuma is a non-acute self-care platform rather than a 24/7 emergency medical service.
* **FR-08**: The system shall explicitly display disclaimers informing students that Amuma AI is an intake assistant and self-care motivator, not a replacement for human psychotherapy, and does not issue medical diagnoses or prescriptions.

### 3.1.3 Gamified Mental Fitness Hub & Mood Tracking
* **FR-09**: The system shall allow students to record daily mood check-ins and primary stressor tags (academic, family, financial, interpersonal).
* **FR-10**: The system shall display student mood histories on an interactive monthly calendar interface.
* **FR-11**: The system shall host lightweight, non-stressful mental wellness mini-games (such as Cat Sudoku and memory puzzles) for immediate situational stress relief.
* **FR-12**: The system shall provide interactive virtual companion pet care mechanics (nurturing virtual cats with experience points and cosmetic care items) tied to completing real-world self-care tasks.
* **FR-13**: The system shall track daily check-in streaks and automatically apply a "Streak Freeze" buffer (up to 1 missed day per 7-day period) to prevent user drop-off during academic exam weeks.

### 3.1.4 Centralized Appointment Booking Bridge
* **FR-14**: The system shall display real-time available 45-to-60-minute guidance counseling appointment slots managed by Registered Guidance Counselors (RGCs) assigned to the student’s specific academic college unit.
* **FR-15**: The system shall allow pre-screened students to select an available time slot, confirm the booking, and automatically receive an encrypted PWA booking voucher.
* **FR-16**: The system shall transmit automated appointment confirmation notices and 24-hour reminder notifications to the student’s PWA dashboard to minimize appointment drop-offs.
* **FR-17**: The system shall allow authorized RGCs to view, manage, and update their assigned appointment schedules and booking statuses.

### 3.1.5 Counselor Dashboard & Pre-Screening Summaries
* **FR-18**: The system shall automatically aggregate pre-clinical AI interactions into a structured pre-screening summary card (including student demographics, primary stressor category, and baseline PHQ-9 severity indicator) for every confirmed booking.
* **FR-19**: The system shall enforce Role-Based Access Control (RBAC) to restrict access to pre-screening summaries strictly to the Registered Guidance Counselor (RGC) assigned to the student's specific academic college unit.
* **FR-20**: The system shall allow authorized RGCs to review 14-day aggregated student habit completion trends (CBT exercise completion, mood stability graphs) on their dashboard prior to consultations.
* **FR-21**: The system shall allow authorized RGCs to export structured pre-screening summaries as standardized, printable PDF documents formatted for physical archiving in the USTP Guidance Office Central Records Unit.

### 3.1.6 Administration, Security & Multilingual Support
* **FR-22**: The system shall allow authorized system administrators to manage user accounts, system configurations, and security settings.
* **FR-23**: The system shall enforce strict Role-Based Access Control (RBAC) to prevent unauthorized user roles (administrative clerks, peer facilitators, and external users) from accessing confidential student conversations, PHQ-9 narrative responses, or clinical case summaries.
* **FR-24**: The system shall provide a 1-tap language toggle allowing students to switch the application interface, AI conversation buffer, and PHQ-9 pre-screening questions seamlessly between English and Cebuano (Bisaya).
* **FR-25**: The system shall automatically render a static emergency fallback screen displaying active click-to-call hotline numbers whenever server connectivity is disrupted.

## 3.2 Non-Functional Requirements

### 3.2.1 Performance Requirements
* **NFR-PERF-01 (General UI & Dashboard Response Time)**: The system shall render page loads, dashboard navigation, and mood history queries within **three (3) seconds** under standard network conditions (3G/4G/Wi-Fi).
* **NFR-PERF-02 (AI Response Generation & Feedback Latency)**: The system shall generate and display conversational AI text/voice responses within **five (5) seconds** under normal API service availability, displaying an active visual feedback indicator within **500 milliseconds** of user input.

### 3.2.2 Security & Data Privacy Requirements
* **NFR-SEC-01 (Encryption Standard)**: 100% of network traffic shall be encrypted via TLS 1.3 in transit, and all persistent database records shall be encrypted at rest using AES-256.
* **NFR-SEC-02 (RBAC Access Isolation)**: System RBAC shall prevent 100% of unauthorized roles (administrative clerks, peer facilitators, and faculty) from accessing student conversational logs or PHQ-9 intake summaries.

### 3.2.3 Availability & Offline Reliability Requirements
* **NFR-REL-01 (Static Offline Fallback)**: The application Service Worker shall maintain 100% availability of the Static Emergency Resource Card and local mood checking cached screens during server downtime or network disruption.

## 3.3 External Interface Requirements

### 3.3.1 User Interfaces
The user interface shall be designed as a mobile-first, responsive Progressive Web App (PWA) with a 1-tap English/Bisaya language toggle, soft visual aesthetics, accessible navigation bars, and dedicated student and counselor dashboard views.

### 3.3.2 Hardware Interfaces
The system requires no specialized external hardware, operating standard smartphone microphones and speakers via HTML5 Web Audio APIs for optional voice venting.

### 3.3.3 Software Interfaces
* **Frontend-Backend API**: RESTful JSON HTTP endpoints secured via JWT authentication.
* **Database Interface**: PostgreSQL database connection pool executing encrypted SQL transactions.

### 3.3.4 Communication Interfaces
All client-server data transmissions shall strictly enforce HTTPS protocols encrypted via **TLS 1.3** to ensure student data confidentiality in transit. To support emergency outreach without automated dispatching liabilities, the system provides native click-to-call (`tel:` URI) protocol links that open the user's smartphone dialer pre-filled with active 24/7 emergency hotlines (such as the CSWD 24/7 Psychosocial Hotline, 911, and CUMC Emergency Room). Out-of-hours crisis support relies on this static emergency resource card rather than queuing unmonitored offline tickets. Furthermore, peer facilitators and student listening buddies are strictly prohibited from receiving or viewing student triage data, pre-screening records, or clinical case summaries, enforced via Role-Based Access Control (RBAC) in compliance with the **Philippine Data Privacy Act of 2012 (RA 10173)**.

## 3.4 System Feature: AI-Powered Student Mental Wellness Support & Booking Bridge (Use Case)

### 3.4.1 Description and Priority
Enables students to engage in multilingual emotional venting, casual gaming, or CBT habit tracking, with the option to escalate to an appointment booking with their assigned college RGC.  
*Priority: High (Core Feature)*

### 3.4.2 Actors
* Primary Actor: Tertiary Student (USTP-CDO)
* Secondary Actor: Registered Guidance Counselor (RGC)
* System Actor: Amuma PWA Engine & FastAPI Microservice

### 3.4.3 Preconditions
1. The student is authenticated on the Amuma PWA.
2. The assigned college counselor's schedule is active in the database.

### 3.4.4 Main Flow
1. **Application Access & Language Selection**: The student opens the Amuma PWA on their device and selects their preferred interaction language (**English or Cebuano/Bisaya**).
2. **Dashboard Activity Selection**: The student chooses their desired activity on their personal dashboard—engaging in **low-barrier casual gaming and mental fitness** (such as Cat Sudoku), interacting with the **Multilingual Conversational AI Buffer** (text/voice venting), or logging daily wellness indicators.
3. **Casual Gaming & Self-Care Engagement**: The student plays cognitive distraction mini-games, engages in CBT micro-workouts, or interacts with their virtual companion pet.
4. **Streak & Habit Processing**: The system records the activity, increments the daily check-in streak (+1), awards virtual pet experience points (XP), and updates the interactive mood calendar.
5. **Flexible Path Choice**:
   * **Path A (Standalone Gaming & Self-Care)**: The student completes their self-care routine and exits **without initiating a counseling booking**. *(See Alternative Flow 3.4.5-A)*
   * **Path B (Escalation to Appointment Booking)**: The student explicitly requests professional guidance and opts to schedule a consultation.
6. **Smart College Counselor Routing**: For Path B, the system automatically filters and displays live 45-to-60-minute available appointment slots managed directly by the **Registered Guidance Counselor (RGC)** assigned to the student's academic college unit (e.g., CITC, CEA).
7. **Slot Confirmation & Voucher Issue**: The student selects an available time slot and confirms the reservation. The system generates an encrypted PWA booking voucher and schedules 24-hour reminders.
8. **Automated Intake Summary Dispatch**: Upon booking confirmation, the system automatically compiles student demographics, primary stressor tags, and baseline PHQ-9 distress indicators into an encrypted intake summary card delivered to the assigned counselor’s dashboard calendar entry.
9. **Counselor Review & PDF Export**: Prior to the consultation, the assigned RGC accesses the **RGC Clinical Dashboard**, reviews the intake summary and 14-day habit trends, and exports a standardized, printable A4 PDF summary report.
10. **Consultation & Post-Care Continuity**: The counselor conducts the consultation, after which the student continues utilizing the platform for between-session habit tracking.

### 3.4.5 Alternative Flows
* **3.4.5-A Standalone Gaming & Casual Self-Care (No Booking Required)**:
  1. At Step 2 or 5, the student chooses to play a wellness mini-game or complete a daily mood log rather than booking an appointment.
  2. The system renders the game session locally within the PWA.
  3. Upon completion, the system updates the streak counter and virtual pet rewards.
  4. The session completes cleanly **without queuing an appointment or dispatching an intake summary**.
* **3.4.5-B Offline Emergency Fallback (Static Hotline Card)**:
  1. In the event of network disruption or if the user selects the emergency button, the Service Worker renders the **Static Emergency Resource Card**.
  2. The system displays click-to-call (`tel:` URI) buttons for 24/7 crisis hotlines (CSWD, 911, CUMC Emergency) alongside non-diagnostic disclaimers for immediate self-directed user outreach.

### 3.4.6 Postconditions
1. **Self-Care & Gamification**: Mood check-ins, CBT completions, and mini-game scores are recorded; daily streak counters (+1) and virtual pet XP are updated. If no booking was made, the session terminates cleanly.
2. **Appointment Booking & Pre-Clinical Dispatch**: A confirmed slot is reserved for the assigned college RGC, an encrypted booking voucher is stored on the student dashboard, and an encrypted pre-clinical intake summary card is delivered to the RGC dashboard with 1-click A4 PDF export capabilities.
3. **Data Privacy Compliance**: All data is encrypted (**AES-256 at rest, TLS 1.3 in transit**) and restricted via RBAC, isolating student logs from administrative staff, peer facilitators, and academic databases in compliance with RA 10173.
4. **Emergency Resource Availability**: The permanent Emergency Resource Card remains accessible across online and offline PWA states with direct click-to-call hotline links.

---

# 4. Appendices

## Appendix A: Project Research Reference Data & Clinical Screening Tools

### A.1 PHQ-9 Depression Severity & Pre-Clinical Triage Index
*The system uses the standardized Patient Health Questionnaire-9 (PHQ-9) scoring criteria to calculate preliminary distress severity indicators attached to counselor intake summaries:*

| Raw Score Range | Severity Level | System Pre-Clinical Triage Category | Recommended Action / Routing |
| :--- | :--- | :--- | :--- |
| **0 – 4** | Minimal / None | **Green (Low Risk)** | Encourage daily gamified self-care (Cat Sudoku, CBT micro-workouts, habit tracking). |
| **5 – 9** | Mild Distress | **Yellow (Moderate)** | Recommend routine booking with assigned USTP Guidance Counselor; offer self-guided CBT exercises. |
| **10 – 14** | Moderate Distress | **Orange (Elevated)** | Fast-track appointment availability options for assigned college RGC; highlight intake summary. |
| **15 – 19** | Moderately Severe | **Red (High Priority)** | Prioritize RGC schedule booking; display prominent static emergency hotline options on dashboard. |
| **20 – 27** | Severe Distress | **Red (High Priority)** | Immediate priority RGC booking display; prominently show click-to-call emergency hotlines (CSWD, 911). |

### A.2 Target Demographic & Cochran Sample Size Parameters
* **Target Population ($N$)**: ~106,973 young adults aged 18–24 in Cagayan de Oro City (focusing on USTP-CDO tertiary students).
* **Statistical Formula (Cochran’s Equation)**:
  $$n_0 = \frac{Z^2 \cdot p \cdot (1-p)}{e^2}$$
* **Parameters**: $Z = 1.96$ (95% Confidence Level), $p = 0.50$ (Maximum Variability), $e = 0.04$ (4% Margin of Error).
* **Computed Sample Size ($n$)**: **600 respondents** + 15% non-response/incomplete buffer = **687 total target respondents**.

### A.3 Primary Stressor Classification Taxonomy
1. **Academic**: Exam anxiety, heavy workload, thesis pressure, grade stress, class schedule conflicts.
2. **Family & Domestic**: Parental expectations, household conflicts, financial dependence, grief.
3. **Financial / Living**: Allowance insufficiency, boarding house isolation, cost-of-living distress.
4. **Interpersonal & Emotional**: Peer pressure, relationship conflicts, loneliness, identity struggles.

---

## Appendix B: System Analysis & Design Models

### B.1 System Context & Data Flow Architecture (DFD Summary)
```
[ Tertiary Student (PWA Client) ] 
       │ 
       ├── (1) Multilingual Venting / Mood Logs (TLS 1.3 Encrypted)
       ├── (2) Appointment Slot Selection
       ▼
[ Amuma Middleman Engine (Next.js / Python FastAPI) ] ── (3) Static Referral ──► [ Emergency Hotlines (911 / CSWD) ]
       │
       ├── (4) AES-256 Storage & Role-Based Access Control (RBAC)
       ▼
[ RGC Clinical Dashboard ] ──► (5) Standardized Intake Summary PDF Export
```

### B.2 Appointment Booking Lifecycle (State Transition Summary)
* **State 1: Venting / Pre-Screening** — Student engages with AI buffer (English/Bisaya); qualitative concerns and PHQ-9 indicators are logged.
* **State 2: Slot Selection** — Student views real-time 45–60 minute available calendar blocks for their designated college RGC.
* **State 3: Booking Confirmed** — Appointment voucher generated on student PWA; encrypted intake summary card dispatched to RGC dashboard.
* **State 4: Pre-Session Summary Export** — RGC reviews 14-day habit trends and exports intake PDF for physical filing.
* **State 5: Consultation Completed / Closed** — Session marked complete; student enters 14-day post-care habit monitoring.

---

## Appendix C: Data Privacy, Ethical Compliance & Regulatory Checklists

### C.1 Philippine Data Privacy Act of 2012 (RA 10173) Compliance Matrix

| Compliance Requirement | Technical Implementation in Amuma | System Verification |
| :--- | :--- | :--- |
| **Data Encryption in Transit** | Enforces HTTPS via **TLS 1.3** across all frontend-backend API traffic. | 100% encrypted network packets. |
| **Data Encryption at Rest** | Database logs, chat transcripts, and intake summaries encrypted via **AES-256**. | Database disk dumps unreadable without master key. |
| **Role-Based Access Control (RBAC)** | Clinical intake summaries accessible **strictly by assigned college RGCs**. Administrative clerks restricted to non-identifying stats. | Peer facilitators and administrative staff blocked from viewing clinical summaries. |
| **Data Separation** | Amuma database strictly isolated from academic records and discipline offices. | Zero database linkage with university registrar or student affairs portals. |
| **Data Retention & Purging** | Automated digital log purging routines synchronized with USTP Central Records Unit archiving schedules. | Inactive pre-screening logs automatically purged per university retention limits. |

### C.2 Philippine Mental Health Act (RA 11036) Non-Diagnostic Disclaimer
> *"Amuma operates strictly as a pre-screening buffer, habit tracker, and appointment bridge. It does not issue formal clinical diagnoses, psychological evaluations, or psychiatric prescriptions. All diagnostic authority remains exclusively with licensed healthcare professionals."*

### C.3 Key Stakeholder Validation Summary
* **USTP Guidance Office (Ma'am Kristine Macesar, RGC)**: Confirmed necessity of college-routed scheduling, pre-session intake summaries, and strict exclusion of peer facilitators from clinical triage data.
* **CSWD CDO Psychosocial Unit**: Validated static emergency hotline referrals (`tel:` URI links) and non-diagnostic boundaries for out-of-hours student support.
