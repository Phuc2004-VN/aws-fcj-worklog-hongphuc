---
title: "Week 9 Worklog"
date: 2026-06-21
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

# FIRST CLOUD AI JOURNEY (FCAJ)

## 1. Overview of Week 09 Objectives and Plans
Week 9 focuses on finalizing the project description document, building the Data Flow Diagram (DFD) and overall system architecture on AWS, and researching machine learning model integration using **AWS SageMaker** to inject intelligent predictions into the application.

> **So What:** Visualizing data flows with DFD and integrating SageMaker translates abstract AI concepts into a concrete cloud solution that addresses business needs intelligently.

---

## 2. Detailed Worklog
Below is the summary of activities performed from 15/06/2026 - 21/06/2026:

| Day / Date | Work Content | Task Details | Results Achieved | Reference Sources |
| --- | --- | --- | --- | --- |
| Mon (Jun 15) | Project Documentation | Documented business problems, data collection processes, and technical output requirements. | Completed the draft project specification document. | Project Specifications |
| Tue (Jun 16) | DFD Design | Drafted the Data Flow Diagram (DFD) to illustrate data ingestion, processing, and output. | Visualized the end-to-end data processing stages of the application. | Draw.io Tool |
| Wed (Jun 17) | Architecture Finalization | Finalized the overall AWS architecture diagram connecting ingestion, storage, and AI tiers. | Produced a comprehensive architectural blueprint ready for review. | Draw.io Tool |
| Thu (Jun 18) | SageMaker Research | Studied AWS SageMaker features (SageMaker Studio, Notebooks, Training Jobs, Endpoints). | Understood the machine learning model building, training, and hosting lifecycle. | AWS SageMaker Guide |
| Fri (Jun 19) | AI Integration Design | Modeled the API interface between the backend application and the SageMaker Endpoint. | Defined the data exchange flow for real-time model predictions. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Sat (Jun 20) | AI Security Config | Configured prototype IAM policies allowing SageMaker to read training datasets from S3. | Ensured secure access to model artifacts following Least Privilege principles. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Sun (Jun 21) | Milestone Review | Consolidated diagrams and documentation; submitted Week 9 report. | Finalized the complete design pack for the graduation project. | Project Documents |

> **So What:** Designing clear data flows and securing SageMaker access parameters optimizes processing throughput while strictly protecting proprietary AI models.

---

### 3. Data Flow Diagram (DFD) and Pipeline Design
An intelligent data processing system requires a clear data flow to isolate processing bottlenecks and protect information at each transit point.

**Pipeline Components:**
1. **Data Ingestion:** Users upload raw files directly to **Amazon S3** using secure Presigned URLs to minimize backend server loads.
2. **Data Processing:** **AWS Lambda** processes the upload, extracting text and cleansing raw inputs.
3. **Model Inference:** Transmitted clean datasets to an active **Amazon SageMaker Endpoint** to request real-time predictions.
4. **Data Storage:** Persisted inference outputs to **Amazon RDS (PostgreSQL)** for dashboard visualization.

> **So What:** Designing decoupled ingestion and processing workflows ensures high system elasticity and processing resilience.

---

### 4. Machine Learning Operations (MLOps) with AWS SageMaker
**AWS SageMaker** provides a fully managed platform covering the entire Machine Learning lifecycle.

**Operational Flow Researched:**
* **SageMaker Notebooks:** Interactive Jupyter workspaces for data scientists to analyze datasets and prototype models.
* **SageMaker Training Jobs:** Automated distributed training running on optimized compute instances (e.g., `ml.m5.large`).
* **SageMaker Endpoints:** Deploying trained model artifacts as persistent HTTPS API endpoints, processing inference requests in real time.

> **So What:** SageMaker standardizes the path from experimental research (Jupyter Notebooks) to scalable production services (Inference APIs).

---

### 5. Defining Technical Success Metrics for the Project
Establishing quantifiable metrics is essential to evaluate system performance and model quality objectively:

* **Model Accuracy:** Target above 85% accuracy on test datasets.
* **API Latency:** Keep response latency under 2 seconds per inference request.
* **System Availability:** Employ Multi-AZ architectures to target 99.9% uptime.

> **So What:** Defining explicit metrics provides the development team with clear targets to benchmark the solution during tests.

---

### 6. Summary and Evaluation of Week 9 Results

#### 6.1. Soft Skills & Communication
* **Presentation Skills:** Transformed complex data concepts into readable DFD diagrams, simplifying team review sessions.
* **Cohesion:** Collaborated smoothly to finalize the project design documentation.

#### 6.2. Resource & Cost Management (FinOps)
* **SageMaker Cost Controls:** Aware that active SageMaker Endpoints incur high hourly charges. Configured test endpoints to terminate immediately post-verification.

#### 6.3. Security & Infrastructure
* **AI Security Boundaries:** Implemented tight S3 bucket access policies within SageMaker execution roles.

#### 6.4. Technical & AI Mindset
* **MLOps Mindset:** Gained a deep understanding of deploying and operating machine learning pipelines in the cloud.

---
**Overall Assessment:** Week 9 completed with outstanding results. The design package is fully signed off, and the team is ready for implementation.
