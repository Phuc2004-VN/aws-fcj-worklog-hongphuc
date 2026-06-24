---
title: "Week 5 Worklog"
date: 2026-05-24
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

# FIRST CLOUD AI JOURNEY (FCAJ)

## 1. Overview of Week 05 Objectives and Plans
Week 5 centers on Container technology and Hybrid Storage solutions. Students studied application packaging with **Docker/Docker Compose** and deployed them on EC2 instances connected to **Amazon RDS** database; configured private **Amazon Elastic Container Registry (ECR)** repositories; researched **AWS Storage Gateway** (File Storage Gateway File Shares) to synchronize files from On-premises to Amazon S3; and attended the **FCAJ Community Day** event on May 23rd.

> **So What:** Mastering Docker alongside AWS Storage Gateway enables Builders to connect modern containerized applications with legacy file storage workflows, improving application portability and hybrid data synchronization.

---

## 2. Detailed Worklog
Below is the summary of activities performed from 18/05/2026 - 24/05/2026:

| Day / Date | Work Content | Task Details | Results Achieved | Reference Sources |
| --- | --- | --- | --- | --- |
| Mon (May 18) | Container Studies | Studied Docker concepts; wrote a Dockerfile to package a simple NodeJS/Python web app. | Understood Docker image creation and application environment isolation. | Docker Documentation |
| Tue (May 19) | RDS DB Deployment | Created Amazon RDS (PostgreSQL/MySQL); used Docker Compose on EC2 to deploy multi-container app. | Deployed a standard Web + DB application architecture, separating web and database servers. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Wed (May 20) | Container Registry | Created Amazon ECR repository; configured IAM permissions; pushed Docker images to ECR. | Stored container images securely in the cloud; cleaned up resources afterwards. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Thu (May 21) | Hybrid Storage Study | Studied AWS Storage Gateway; compared File Gateway, Volume Gateway, and Tape Gateway. | Mastered data synchronization architectures connecting on-premises systems to AWS. | AWS Storage Guide |
| Fri (May 22) | Storage Gateway Lab | Configured NFS File Share on File Gateway; mounted it locally; synced local files to S3. | Files saved to local network share were automatically synchronized to an S3 bucket. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Sat (May 23) | FCAJ Community Day | Attended FCAJ Community Day; engaged with AWS experts; built professional connections. | Acquired real-world insights into AI, Serverless, and enterprise success stories. | Live Event |
| Sun (May 24) | Cleanup & Review | Terminated RDS database, deleted Storage Gateway VM and ECR resources. | Released resources to conserve credits; updated weekly worklog documentation. | Personal Records |

> **So What:** Combining Docker ECR and Storage Gateway demonstrates the modern architecture pattern: applications run as lightweight containers, and data is synced intelligently across cloud boundaries.

---

### 3. Application Containerization with Docker & Amazon ECR
Containerization is key to migrating workloads to the Cloud without facing environment inconsistency issues.

**Deployment Process:**
1. **Dockerfile:** Specifies the execution environment (Base image, dependencies, ports, and startup script).
2. **Docker Compose:** Defines relationship between the Web App and Amazon RDS, starting them on EC2 with a single command `docker-compose up -d`.
3. **Amazon ECR:** Serves as a secure container registry. Builders login via CLI (`aws ecr get-login-password`) and push images to ECR for automated deployments.

> **So What:** Docker containerization simplifies software deployment workflows (CI/CD) and ensures consistency between development (Dev) and production (Prod) environments.

---

### 4. Hybrid Cloud Storage Integration via AWS Storage Gateway
For enterprises unable to migrate fully to the cloud, **AWS Storage Gateway** provides a hybrid storage bridge.

**File Storage Gateway:**
* Exposes standard file protocols like **NFS** or **SMB** to on-premises servers.
* Automatically converts files saved to the local directory into objects stored in **Amazon S3**.
* Employs a local cache to deliver low-latency access to frequently used files.

![File Storage Gateway Model](/images/1-Worklog/Week5/storage-gateway.png)

> **So What:** Storage Gateway allows organizations to leverage Amazon S3's massive scale and cost-efficiency without modifying legacy, on-premises applications.

---

### 5. Insights from FCAJ Community Day 2026
The event on May 23rd gathered cloud practitioners, AWS partners, and FCAJ students.

**Key Highlights:**
* **Generative AI on AWS:** Leveraging Amazon Bedrock to solve text processing and business workflow automation challenges.
* **Serverless Mindset:** Transitioning from server management to code optimization, cutting infrastructure costs by up to 70%.
* **Professional Networking:** Learned from career trajectories and project advice shared by senior Solutions Architects.

> **So What:** Community engagement updates students on cutting-edge technologies and aligns their skills with market demand.

---

### 6. Summary and Evaluation of Week 5 Results

#### 6.1. Soft Skills & Communication
* **Networking:** Actively participated in FCAJ Community Day, exchanging ideas and experiences with other participants.
* **Teamwork:** Coordinated productively on planning container deployment topologies.

#### 6.2. Resource & Cost Management (FinOps)
* **Cost Minimization:** Understood AWS Storage Gateway pricing models, removing gateway VMs immediately after validating integration.

#### 6.3. Security & Infrastructure
* **Container Security:** Enforced IAM policies to govern push/pull permissions on private Amazon ECR repositories.
* **Hybrid Storage:** Successfully integrated hybrid file synchronization using NFS File Shares.

#### 6.4. Technical & AI Mindset
* **Container Mindset:** Gained expertise in Docker Compose and packaging applications for cross-environment portability.

---
**Overall Assessment:** Week 5 completed successfully. Containerization and hybrid storage skills are firmly established.
