---
title: "Week 2 Worklog"
date: 2026-05-03
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

# FIRST CLOUD AI JOURNEY (FCAJ)

## 1. Overview of Week 02 Objectives and Plans
Starting the second week, students dive deep into studying **Amazon Virtual Private Cloud (VPC)** and reinforcing cost management skills with **AWS Budgets**. Shifting from a default cloud environment to a strictly controlled custom network environment is a prerequisite to ensure data safety and cost optimization. Additionally, this week marks the completion of the official internship registration and preparing to work at the office.

> **So What:** Understanding network partitioning and traffic control helps students grasp the backbone of system design on AWS. Configuring VPC correctly prevents info leakage risks right from the baseline network layer.

---

## 2. Detailed Worklog
Below is the summary of activities performed from 24/04/2026 - 03/05/2026:

| Day / Date | Work Content | Task Details | Results Achieved | Reference Sources |
| --- | --- | --- | --- | --- |
| Fri (Apr 24) | Info Registration | Completed the internship survey link and received guidelines for office onboarding. | Completed administrative procedures; ready for office presence. | AWS Registration Link |
| Sat (Apr 25) | VPC Basics Research | Watched AWS training videos; studied IP addressing, CIDR blocks, and Subnets. | Grasped IP address allocation and network partitioning in VPC. | Provided Videos |
| Sun (Apr 26) | Network Schema Draft | Sketched a network model consisting of Public and Private Subnets. | Visualized traffic flow from the Internet to the internal network. | AWS Documentation |
| Mon (May 27) | Budget Management | Configured advanced AWS Budgets alerts for networking resources. | Set up cost thresholds to control potential NAT Gateway or VPN costs. | AWS Billing Console |
| Tue (Apr 28) | VPC Initialization | Created Custom VPC with CIDR `10.0.0.0/16` and custom subnets. | Successfully established an isolated private network partition. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Wed (Apr 29) | Network Routing | Configured Route Tables and Internet Gateway (IGW) for Public Subnet. | Enabled public internet connectivity for resources in the Public Subnet. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Thu (Apr 30) | Network Security Study | Studied the differences between Security Groups (Stateful) and NACLs (Stateless). | Mastered the two primary firewalls protecting EC2 instances and subnets. | AWS Security Guide |
| Fri (May 01) | International Labor Day | Self-studied High Availability (HA) best practices for VPC design. | Understood how to distribute subnets across multiple Availability Zones. | AWS Architecture Center |
| Sat (May 02) | EC2 & VPC Verification | Launched EC2 in Public Subnet (SSH verified) and EC2 in Private Subnet. | Verified routing and security configurations were working correctly. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Sun (May 03) | Weekly Reporting | Compiled Week 2 worklog and prepared the plan for the upcoming week. | Finalized internship progress documentation. | Personal Records |

> **So What:** This week's work concentrated on networking and onboarding setup. This preparation provides a robust foundation to implement advanced VPC Peering and Hybrid DNS next week.

---

### 3. Deep Dive Analysis: VPC Structure and Routing
Amazon Virtual Private Cloud (VPC) enables Builders to spin up a private virtual network in the cloud.

**Operation of Public & Private Subnets:**
* **Public Subnet:** Associated with a Route Table routing `0.0.0.0/0` traffic through the **Internet Gateway (IGW)**. Suitable for resources needing direct internet communication like Load Balancers or Web Servers.
* **Private Subnet:** Route Table does not point to an Internet Gateway. Resources (like Databases, Backend Services) are isolated and can only access the internet indirectly via a **NAT Gateway** located in a Public Subnet.

![Basic VPC Schema](/images/1-Worklog/Week2/vpc-schema.png)

> **So What:** Clear separation of Public and Private Subnets minimizes the external attack surface, isolating sensitive databases completely from the public internet.

---

### 4. Cost Management (FinOps) using AWS Budgets
When working with VPCs, resources like NAT Gateways accrue charges per hour and per GB of data processed. Thus, configuring AWS Budgets is vital.

**Cost Monitoring Strategy:**
* **Threshold Alerts:** Set alerts at 50%, 80%, and 100% of the monthly budget (e.g., $10).
* **Instant Notifications:** Send email alerts as soon as actual or forecasted costs exceed thresholds, enabling prompt termination of idle resources.

> **So What:** Applying FinOps enables Builders to combine technical skills with cost-awareness, managing cloud spend efficiently.

---

### 5. AWS CLI for VPC (Advanced Practice)
Using CLI commands accelerates network infrastructure deployment.

**Useful CLI Commands:**
* Create a VPC: `aws ec2 create-vpc --cidr-block 10.0.0.0/16`
* List Subnets: `aws ec2 describe-subnets --filters "Name=vpc-id,Values=vpc-xxxxx"`
* Inspect Route Tables: `aws ec2 describe-route-tables`

> **Pro Tip:** Script your VPC creation using Bash or PowerShell to eliminate manual configuration errors.

---

### 6. Summary and Evaluation of Week 2 Results

#### 6.1. Soft Skills & Communication
* **Team Synergy:** Kept active engagement on WhatsApp/Zalo to help teammates debug VPC configuration errors.
* **Onboarding admin:** Completed official internship registration documents accurately and on time.

#### 6.2. Resource & Cost Management (FinOps)
* **Cost Controls:** Created specific Budgets for VPC and EC2 resources, monitoring NAT Gateway costs actively during exercises.

#### 6.3. Security & Infrastructure
* **Network Security:** Mastered configuring Security Groups to allow only required ports (Port 22 for SSH, Port 80/443 for HTTP/HTTPS).
* **Infrastructure Design:** Successfully provisioned a Custom VPC and understood cloud routing tables.

#### 6.4. Technical & AI Mindset
* **Networking Mindset:** Shifted my technical perspective from on-premises local networking to elastic virtualized networking.

---
**Overall Assessment:** Successfully met all Week 2 goals. The VPC infrastructure is configured properly and ready for multi-VPC networking.
