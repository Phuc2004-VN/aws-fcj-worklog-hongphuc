---
title: "Week 9 Worklog"
date: 2026-06-21
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

# FIRST CLOUD AI JOURNEY (FCAJ)

## 1. Overview of Week 09 Goals and Plan
This week, focus was placed on finalizing the graduation project design documentation and researching how to integrate AI/ML models into the cloud infrastructure:
* Writing the project specification document (defining business goals, data flows, and output expectations).
* Designing the Data Flow Diagram (DFD) to visualize how data traverses through the system.
* Studying the machine learning lifecycle and deployment workflow on AWS using AWS SageMaker.
* Configuring secure IAM policies to allow AI services to access S3 data safely.

## 2. Tasks to Implement in the Week
Below is the summary of activities performed from June 15th to June 21st, 2026:

| Day / Date | Work Content | Task Details | Results Achieved | Reference Sources |
| --- | --- | --- | --- | --- |
| Mon (Jun 15) | Project Documentation | - Project specifications: <br> &emsp; + Documented business problems <br> &emsp; + Defined data collection and output goals | Completed the draft of the graduation project specification document. | Project Specifications |
| Tue (Jun 16) | DFD Design | - Data flows mapping: <br> &emsp; + Drafted the Data Flow Diagram (DFD) for AI system <br> &emsp; + Outlined ingestion and processing paths | Visualized the processing and storage steps of the application. | [Draw.io Tool](https://app.diagrams.net/) |
| Wed (Jun 17) | Architecture Finalization | - Infrastructure mapping: <br> &emsp; + Finalized the overall AWS architecture diagram <br> &emsp; + Connected S3, web servers, and AI tiers | Obtained a detailed architecture diagram ready for presentation to the committee. | [Draw.io Tool](https://app.diagrams.net/) |
| Thu (Jun 18) | SageMaker Research | - MLOps study: <br> &emsp; + Studied AWS SageMaker features <br> &emsp; + Explored Studio, Notebooks, and Endpoints | Understood the process of building, training, and deploying machine learning models. | [AWS SageMaker Guide](https://docs.aws.amazon.com/sagemaker/) |
| Fri (Jun 19) | AI Integration Design | - API designs: <br> &emsp; + Modeled backend API queries to SageMaker Endpoint <br> &emsp; + Defined payload formats | Built the AI/ML integration flow into the web application architecture. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Sat (Jun 20) | AI Security Config | - Security boundaries: <br> &emsp; + Configured prototype IAM policies for SageMaker <br> &emsp; + Restricted S3 reads to model datasets | Ensured input data security for the AI model according to the Least Privilege standard. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Sun (Jun 21) | Milestone Review | - Milestone review: <br> &emsp; + Consolidated diagrams and documentation <br> &emsp; + Submitted Week 9 report | Completed the graduation project design documentation; ready to start the coding phase. | Project Documents |

## 3. Results Achieved
During this week's graduation project specification and machine learning operations (MLOps) labs, several key takeaways were gained:

* **Data Flow Diagram (DFD) and Pipeline Design:**
  + Mapped out the system DFD showing the data lifecycle: Client uploads files directly to S3 via Presigned URLs -> Lambda is triggered to extract clean text -> Text is sent to the SageMaker Endpoint for AI predictions -> Results are stored in RDS PostgreSQL and loaded onto the web interface.
  + Takeaway: Using S3 Presigned URLs is a major AWS Best Practice that allows clients to upload files directly to S3. This eliminates file-handling load from the API backend servers.

* **MLOps workflows with AWS SageMaker:**
  + Researched using SageMaker Notebooks for prototyping models, launching Training Jobs, and deploying the model to an active HTTPS Endpoint (Real-time Inference) for API consumption.
  + Takeaway: Hosting the model as an active API endpoint allows the backend to query AI predictions easily without needing complex server runtimes.

* **Security Boundaries for AI Services (IAM Policies):**
  + Created a dedicated SageMaker Execution Role, restricting access policies exclusively to the project S3 buckets (following Least Privilege principles).
  + Takeaway: Setting tight IAM constraints secures the training data and model artifacts from unauthorized access.

* **Technical Success Metrics and Cost Controls:**
  + Aligned on target metrics: Model Accuracy > 85%, API latency < 2 seconds, and Multi-AZ high availability.
  + Takeaway: SageMaker Endpoints run continuously and consume credit quickly. To save the budget, the test endpoint was deleted immediately after verification.
