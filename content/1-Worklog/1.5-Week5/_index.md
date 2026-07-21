---
title: "Week 5 Worklog"
date: 2026-05-24
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---



## FIRST CLOUD AI JOURNEY (FCAJ)

## 1. Overview of Week 05 Goals and Plan
This week, focus was placed on container technologies, hybrid cloud storage solutions, and community networking:
* Learning Docker, packaging web applications (containerization), and connecting them to an Amazon RDS database.
* Creating repository on Amazon ECR to securely store and manage Docker images.
* Studying and configuring AWS Storage Gateway (NFS File Share) to sync local files to Amazon S3.
* Attending the FCAJ Community Day (May 23rd) to learn from industry experts and build connections.

## 2. Tasks to Implement in the Week
Below is the summary of activities performed from May 18th to May 24th, 2026:

| Day / Date | Work Content | Task Details | Results Achieved | Reference Sources |
| --- | --- | --- | --- | --- |
| Mon (May 18) | Container Studies | - Docker packaging: <br> &emsp; + Studied Docker concepts <br> &emsp; + Wrote Dockerfile to package NodeJS/Python app | Understood Docker image building and environment isolation. | [Docker Documentation](https://000015.awsstudygroup.com/vi) |
| Tue (May 19) | RDS DB Deployment | - Database integration: <br> &emsp; + Created RDS database instance <br> &emsp; + Used Docker Compose on EC2 to connect to RDS | Deployed structured Web + DB architecture with clean separation. | [RDS](https://000015.awsstudygroup.com/vi) |
| Wed (May 20) | Container Registry | - Container registry: <br> &emsp; + Provisioned ECR repository <br> &emsp; + Pushed Docker images from EC2 to ECR | Stored container images securely in the cloud; cleaned up resources afterwards. | [Container Registry](https://000016.awsstudygroup.com/vi) |
| Thu (May 21) | Hybrid Storage Study | - Hybrid storage concepts: <br> &emsp; + Studied AWS Storage Gateway types <br> &emsp; + Analyzed data sync mechanisms | Mastered data synchronization architectures connecting on-premises systems to AWS. | [AWS Storage Guide](https://000024.awsstudygroup.com/vi) |
| Fri (May 22) | Storage Gateway Lab | - Storage Gateway practice: <br> &emsp; + Configured File Share on File Gateway <br> &emsp; + Mounted NFS share locally and tested sync | Files saved to local network share were automatically synchronized to an S3 bucket. | [Storage Gateway](https://000024.awsstudygroup.com/vi) |
| Sat (May 23) | FCAJ Community Day | - Community events: <br> &emsp; + Attended FCAJ Community Day <br> &emsp; + Engaged in expert presentations on AI | Acquired real-world insights into AI, Serverless, and enterprise success stories. | Live Event |
| Sun (May 24) | Cleanup & Review | - Cost control cleanup: <br> &emsp; + Terminated RDS database <br> &emsp; + Deleted Storage Gateway VM and ECR resources | Released resources to conserve credits; updated weekly worklog documentation. | Personal Records |

## 3. Results Achieved
During this week's containerization, hybrid storage gateway, and community networking activities, several key takeaways were gained:

* **Containerization & Repository Management (Docker & ECR):**
  + Successfully packaged a web application using Dockerfile and ran it via Docker Compose connected to an Amazon RDS (PostgreSQL) database. Created an ECR repository and pushed container images securely.
  + Takeaway: Containerization decouples application runtimes from host OS dependencies. Storing images on ECR is a critical baseline for setting up CI/CD pipelines to serverless container services like ECS or Fargate later.

* **Hybrid Cloud Storage Integration (AWS Storage Gateway):**
  + Configured a File Storage Gateway NFS File Share, mounted it locally on a client machine, and tested automated file uploads directly into an Amazon S3 bucket.
  + Takeaway: Storage Gateway acts as a highly effective bridge, allowing legacy on-premises applications to consume scalable cloud storage without code refactoring. This is highly useful for data archiving and Disaster Recovery (DR) setups.

* **Community Insights from FCAJ Community Day:**
  + Attended presentations on Amazon Bedrock, Generative AI models, Serverless architecture patterns, and FinOps budgeting.
  + Takeaway: Connecting with the community helps validate cloud theories against actual corporate case studies and builds valuable professional networks.

* **FinOps and Resource Governance:**
  + Takeaway: Since running a Storage Gateway VM and RDS instance consumes credits quickly, testing was completed promptly and all resources were cleaned up on Sunday.
