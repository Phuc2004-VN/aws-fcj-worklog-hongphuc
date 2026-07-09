---
title: "Week 8 Worklog"
date: 2026-06-14
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

# FIRST CLOUD AI JOURNEY (FCAJ)

## 1. Weekly Goals
This week, the team focused entirely on detailed architectural design and preparing the implementation plan for the graduation project:
* Studying AWS architecture diagram standards and practicing drawing infrastructure setups using Draw.io.
* Discussing business scenarios and target user personas to scope the Minimum Viable Product (MVP) features.
* Utilizing the AWS Pricing Calculator to estimate the monthly operational budget of the system.
* Allocating tasks and setting timelines (milestones) for each team member.

## 2. Tasks to Implement in the Week
Below is the summary of activities performed from June 8th to June 14th, 2026:

| Day / Date | Work Content | Task Details | Results Achieved | Reference Sources |
| --- | --- | --- | --- | --- |
| Mon (Jun 08) | Diagram Training | - Diagram design practice: <br> &emsp; + Reviewed AWS architecture layout guidelines <br> &emsp; + Initialized Draw.io with AWS icon packs | Grasped layout principles for standardized architecture diagrams. | [AWS Architecture Center](https://www.youtube.com/watch?v=l8isyDe-GwY&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=2) |
| Tue (Jun 09) | Infrastructure Draft | - Infrastructure blueprint: <br> &emsp; + Sketched VPC, subnets, and routing tables on Draw.io <br> &emsp; + Mapped out traffic flows | Created a visual diagram showing data flow from client to AWS. | [Draw.io Tool](https://app.diagrams.net/) |
| Wed (Jun 10) | Problem Definition | - Project scoping: <br> &emsp; + Met with the team to define business problem <br> &emsp; + Detailed the text analysis use case | Agreed on the business description and project scope. | Team Meeting Notes |
| Thu (Jun 11) | Persona Mapping | - Feature planning: <br> &emsp; + Mapped target user personas <br> &emsp; + Listed features required to solve pain points | Identified the list of prioritized Minimum Viable Product (MVP) features. | Requirements Doc |
| Fri (Jun 12) | AI Solution Design | - AI integration: <br> &emsp; + Designed pipeline combining S3, EC2, and RDS <br> &emsp; + Linked data flows to AI model | Proposed an overall architectural solution integrated with AI. | [AWS Machine Learning](https://aws.amazon.com/what-is/artificial-intelligence/) |
| Sat (Jun 13) | Cost Estimation | - Budget modeling: <br> &emsp; + Input resource configurations for EC2 and RDS into AWS Calculator | Estimated the operational budget of the architecture to ensure cost-efficiency. | [AWS Pricing Calculator](https://calculator.aws/#/) |
| Sun (Jun 14) | Project Roadmap | - Tasks delegation: <br> &emsp; + Allocated tasks across infrastructure, backend, and frontend <br> &emsp; + Set milestones on Trello | Established a clear Sprint plan for the following weeks. | Trello / Jira |

## 3. Results Achieved
During this week's detailed design, budgeting, and roadmap planning labs, several key takeaways were gained:

* **AWS Infrastructure Layout and Architecture Design (Draw.io):**
  + Sketched out the system diagram using Draw.io with the official AWS icon set, organizing resources into Region, VPC, Public Subnets, and Private Subnets. Placed RDS database instances and backend servers in the Private Subnet to prevent public internet access.
  + Takeaway: The architecture diagram functions as the engineering blueprint for the deployment phase. A precise design from the start avoids security and routing issues down the line.

* **MVP Scoping & Project Board Setup:**
  + Mapped out target user requirements and defined MVP feature boundaries (file upload -> text extraction -> call model -> save results in RDS and display them).
  + Takeaway: Defining a clear MVP scope prevents scope creep – the primary cause of project delays. Allocating tasks on Trello maps out clear sprint deadlines for the team.

* **Infrastructure Budget Projections (AWS Pricing Calculator):**
  + Used the AWS Pricing Calculator to estimate monthly running costs. Entering planned resource specifications (EC2 `t3.medium`, RDS PostgreSQL `db.t3.micro`, 50GB S3 storage) generated a monthly run-rate of under $15.
  + Takeaway: Cost modeling controls credit usage and ensures the construction of economically viable setups. Budget estimation is a critical FinOps skill for any Cloud Engineer.
