---
title: "Week 8 Worklog"
date: 2026-06-14
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

# FIRST CLOUD AI JOURNEY (FCAJ)

## 1. Overview of Week 08 Objectives and Plans
Week 8 marks the start of detailed architectural design for the final graduation Project. Key activities included: learning **Draw.io** combined with official AWS icons to draft hierarchical infrastructure diagrams; conducting meetings to detail business scenarios and functional specifications; profiling target customers and defining core engineering obstacles; and outlining a development roadmap with clear task allocation.

> **So What:** A clear, visual architecture diagram and an explicit project roadmap serve as the blueprint, guiding team collaboration and preventing resource configuration drift during implementation.

---

## 2. Detailed Worklog
Below is the summary of activities performed from 08/06/2026 - 14/06/2026:

| Day / Date | Work Content | Task Details | Results Achieved | Reference Sources |
| --- | --- | --- | --- | --- |
| Mon (Jun 08) | Diagram Training | Studied AWS architecture layout guidelines; initialized Draw.io with AWS icon packs. | Mastered standards for clean, structured architecture diagrams. | AWS Architecture Center |
| Tue (Jun 09) | Infrastructure Draft | Sketched the baseline cloud setup; mapped VPC limits, public/private subnets, and routes. | Produced a visual diagram showing traffic and data flow from clients to AWS. | Draw.io Tool |
| Wed (Jun 10) | Problem Definition | Met with the team; finalized the business problem (e.g., AI-driven document extraction). | Aligned on the project's functional boundaries and scope. | Team Meeting Notes |
| Thu (Jun 11) | Persona Mapping | Documented target customer personas; listed core features required to satisfy users. | Created an MVP (Minimum Viable Product) feature list. | Requirements Doc |
| Fri (Jun 12) | AI Solution Design | Studied combining AWS core services (S3, EC2, RDS) with ML/AI engines to resolve pain points. | Outlined a comprehensive AI-integrated system design. | AWS Machine Learning |
| Sat (Jun 13) | Cost Estimation | Used the AWS Pricing Calculator to estimate the monthly operational costs of the setup. | Generated a budget forecast, ensuring economic viability. | AWS Pricing Calculator |
| Sun (Jun 14) | Project Roadmap | Allocated tasks (infrastructure, backend/AI, documentation) and set milestones. | Established a clear sprint plan for the upcoming implementation weeks. | Trello / Jira |

> **So What:** Meticulous planning this week eliminates ambiguity in system requirements, ensuring every team member is aligned on the project's goal.

---

### 3. AWS Standard Architecture Design Using Draw.io
A professional architecture diagram must follow AWS design patterns so any cloud engineer can instantly interpret it.

**Design Principles Applied:**
* **Hierarchical Layout:** Outlined layers from outside in: Region -> VPC -> Availability Zones -> Subnets -> Resources.
* **Official Icon Library:** Used the latest official AWS icon sets. Avoided generic symbols or outdated icons.
* **Directional Connectors:** Indicated specific data flows and protocol ports (e.g., HTTPS Port 443, JDBC Port 5432).

> **So What:** Visually clean schematics reduce explanation overhead among team members and clarify design logic to external auditors.

---

### 4. Scoping the MVP (Minimum Viable Product) for the Project
Focusing on core functionalities ensures the team delivers a working product on time without getting bogged down by non-essential features.

**MVP Feature Scoping Steps:**
1. **User Persona Profiling:** Mapped user behaviors, expectations, and operational constraints.
2. **Core Feature Identification:** Determined must-have functionalities (e.g., File Upload -> AI Processing -> Save Output).
3. **Task Prioritization:** Ranked tasks using an Impact-vs-Effort matrix to schedule development sprints.

> **So What:** Scoping the MVP keeps development efforts lean, securing a functional pilot system within the internship timeframe.

---

### 5. Budgeting Infrastructure via AWS Pricing Calculator
A solid architecture must be economically viable. The team leveraged AWS calculators to model the monthly budget.

**Model Inputs & Assumptions:**
* **Compute (EC2):** One `t3.medium` instance to host the backend application.
* **Database (RDS):** One `db.t3.micro` instance for persistent structured data.
* **Storage (S3):** Approximately 50 GB of standard storage for raw uploads.
* **AWS Budgets:** Alert rules set up to trigger notifications if predicted monthly spend nears $15.

> **So What:** Estimating cloud spend beforehand prevents billing surprises and informs early architectural adjustments.

---

### 6. Summary and Evaluation of Week 8 Results

#### 6.1. Soft Skills & Communication
* **Task Management:** Set up a detailed Trello board, ensuring transparent assignment of responsibilities.
* **Architectural Debates:** Conducted peer reviews of the proposed designs to eliminate single points of failure.

#### 6.2. Resource & Cost Management (FinOps)
* **Budget Forecasting:** Modeled project running costs prior to deployment, eliminating the risk of exceeding the $200 credit boundary.

#### 6.3. Security & Infrastructure
* **Secure Networking:** Designed the system following AWS security practices: placing backend systems and databases in private subnets.

#### 6.4. Technical & AI Mindset
* **Architecture Visualization:** Mastered using Draw.io to translate technical concepts into production-ready diagrams.

---
**Overall Assessment:** Week 8 objectives successfully met. The architectural blueprint and project roadmap are finalized for development.
