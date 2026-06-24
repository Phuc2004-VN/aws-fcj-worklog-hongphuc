---
title: "Week 6 Worklog"
date: 2026-05-31
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

# FIRST CLOUD AI JOURNEY (FCAJ)

## 1. Overview of Week 06 Objectives and Plans
Week 6 focuses on automated security compliance and EC2 operational cost optimization. Students investigated **AWS Security Hub** to evaluate compliance against CIS, PCI DSS, and Foundational Security benchmarks; analyzed EC2 cost-saving strategies using tags and IAM roles; and developed an **AWS Lambda** function triggered by **Amazon EventBridge** to automate EC2 start/stop schedules.

> **So What:** Merging automated security audits with resource scheduling reduces idle EC2 bills by up to 60% during non-business hours, while continuously upgrading the cloud security posture.

---

## 2. Detailed Worklog
Below is the summary of activities performed from 25/05/2026 - 31/05/2026:

| Day / Date | Work Content | Task Details | Results Achieved | Reference Sources |
| --- | --- | --- | --- | --- |
| Mon (May 25) | Security Hub Research | Studied AWS Security Hub; reviewed CIS AWS Foundations and PCI DSS standards. | Grasped automated security assessment and compliance scoring. | AWS Security Hub Guide |
| Tue (May 26) | Security Audit | Enabled Security Hub; analyzed findings and security alerts. | Identified configuration drift and prioritized security fixes. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Wed (May 27) | EC2 Optimization | Studied EC2 cost-saving strategies (Right-sizing, Reserved Instances, Savings Plans). | Understood server size optimization based on workload telemetry. | AWS Cost Optimization |
| Thu (May 28) | Tagging & IAM Roles | Applied standard tags (Env: Dev, Project: FCAJ); associated IAM Roles with EC2 instances. | Managed cloud assets systematically; eliminated hardcoded credentials on EC2. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Fri (May 29) | Lambda Design | Wrote a Python Boto3 script to filter EC2 instances by tag and perform Start/Stop calls. | Developed serverless control logic using Python Boto3. | AWS Lambda Developer Guide |
| Sat (May 30) | Scheduler Testing | Configured EventBridge Cron rules; deployed Lambda; verified execution logs in CloudWatch. | Instances successfully started at 8:00 AM and stopped at 6:00 PM automatically. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Sun (May 31) | Review & Cleanup | Analyzed CloudWatch logs; cleaned up test cron rules and stopped running EC2s. | Compiled weekly worklog; maintained credit balances in good standing. | Personal Records |

> **So What:** Implementing Lambda to automate EC2 state management reflects serverless engineering: Operations as Code.

---

### 3. Continuous Compliance Audits with AWS Security Hub
**AWS Security Hub** provides a comprehensive view of security posture across all AWS accounts.

**Core Capabilities:**
* **Compliance Scoring:** Rates infrastructure against industry standards (e.g., CIS AWS Foundations).
* **Aggregation:** Integrates alerts from Amazon GuardDuty, Inspector, and Macie into a single pane.
* **Config Drift Detection:** Flags security issues like disabled MFA on Root account, or Security Groups exposing SSH port 22 to `0.0.0.0/0`.

> **So What:** Leveraging Security Hub transitions teams from reactive firefighting to proactive, continuous security monitoring and remediation.

---

### 4. Automated EC2 State Scheduling: AWS Lambda & EventBridge
Running development or testing EC2 instances 24/7 when teams are offline is a primary cause of cloud waste.

**Automation Architecture:**
1. **Amazon EventBridge (CloudWatch Events):** acts as the scheduler trigger (e.g., cron trigger at 6:00 PM every weekday).
2. **AWS Lambda (Python/Boto3):** Serverless function querying EC2 instances tagged with `Auto-Stop: True` and invoking `stop_instances()` API.
3. **IAM Role:** Assigns least privilege policy allowing Lambda to execute `ec2:DescribeInstances`, `ec2:StartInstances`, and `ec2:StopInstances` only.

![EC2 Scheduler Architecture](/images/1-Worklog/Week6/lambda-scheduler.png)

> **So What:** Automating infrastructure lifecycles enables organizations to match resource consumption with actual working hours, maximizing ROI.

---

### 5. Tagging Strategies for Cloud Governance
Tagging is crucial for both administrative organization and Cost Allocation billing reports.

**Tagging Best Practices:**
* Environment classification: `Environment` (Dev, Staging, Prod).
* Project mapping: `Project` (FCAJ-AI).
* Resource ownership: `Owner` (HongPhuc).

> **So What:** Consistent tagging enables automated security enforcement, lifecycle scripts, and precise billing audits.

---

### 6. Summary and Evaluation of Week 6 Results

#### 6.1. Soft Skills & Communication
* **Coding Discipline:** Documented serverless scripts thoroughly, explaining Lambda triggers and logic structures clearly.
* **Peer Support:** Resolved IAM Policy boundary issues that were blocking classmates' Lambda executions.

#### 6.2. Resource & Cost Management (FinOps)
* **Smart Savings:** Successfully ran the Lambda Scheduler to cut compute waste on non-working hours.

#### 6.3. Security & Infrastructure
* **Compliance Checks:** Leveraged Security Hub to gauge infrastructure compliance against CIS benchmarks.
* **Role Delegation:** Utilized temporary AWS credentials (IAM Roles) for server and function executions.

#### 6.4. Technical & AI Mindset
* **Serverless Execution:** Converted functions utilizing Boto3 Python to control AWS resources programmatically.

---
**Overall Assessment:** Week 6 targets fully completed. Security hardening and automated cost controls have been successfully integrated into the system.
