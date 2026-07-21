---
title: "Week 6 Worklog"
date: 2026-05-31
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---



## FIRST CLOUD AI JOURNEY (FCAJ)

## 1. Overview of Week 06 Goals and Plan
This week, focus was placed on automating security compliance and optimizing EC2 instance operational costs:
* Enabling and exploring AWS Security Hub to perform automated vulnerability scans and evaluate compliance against CIS and PCI DSS standards.
* Studying EC2 cost-saving strategies (resource tagging and assigning IAM Roles to EC2 instances instead of using permanent credentials).
* Developing an AWS Lambda function using Python (Boto3) triggered by Amazon EventBridge to automatically start/stop dev EC2 instances during off-hours.

## 2. Tasks to Implement in the Week
Below is the summary of activities performed from May 25th to May 31st, 2026:

| Day / Date | Work Content | Task Details | Results Achieved | Reference Sources |
| --- | --- | --- | --- | --- |
| Mon (May 25) | Security Hub Research | - Security Hub study: <br> &emsp; + Studied AWS Security Hub <br> &emsp; + Reviewed CIS AWS Foundations and PCI DSS benchmarks | Grasped automated security assessment and compliance scoring. | [AWS Security Hub Guide](https://000018.awsstudygroup.com/) |
| Tue (May 26) | Security Audit | - Config audit: <br> &emsp; + Enabled Security Hub on AWS Console <br> &emsp; + Analyzed findings and security alerts | Identified configuration drift and prioritized security fixes. | [AWS Study Group](https://000018.awsstudygroup.com/) |
| Wed (May 27) | EC2 Optimization | - Cost controls study: <br> &emsp; + Studied EC2 cost-saving strategies (Right-sizing, RIs, Savings Plans) | Understood server size optimization based on workload telemetry. | [AWS Cost Optimization](https://000022.awsstudygroup.com/vi/) |
| Thu (May 28) | Tagging & IAM Roles | - Governance setup: <br> &emsp; + Applied standard tags (Env: Dev, Project: FCAJ) <br> &emsp; + Associated IAM Roles with EC2 instances | Managed cloud assets systematically; eliminated hardcoded credentials on EC2. | [Tag & Role](https://000022.awsstudygroup.com/vi/) |
| Fri (May 29) | Lambda Design | - Serverless script: <br> &emsp; + Wrote a Python Boto3 script to filter EC2 by tag <br> &emsp; + Implemented start/stop instances logic | Developed serverless control logic using Python Boto3. | [AWS Lambda Developer Guide](https://000022.awsstudygroup) |
| Sat (May 30) | Scheduler Testing | - Testing schedules: <br> &emsp; + Configured EventBridge Cron rules <br> &emsp; + Deployed Lambda and verified logs in CloudWatch | Instances successfully started at 8:00 AM and stopped at 6:00 PM automatically. | [AWS Study Group](https://000022.awsstudygroup) |
| Sun (May 31) | Review & Cleanup | - Final review: <br> &emsp; + Analyzed CloudWatch logs <br> &emsp; + Cleaned up test cron rules and stopped EC2s | Compiled weekly worklog; maintained credit balances in good standing. | Personal Records |

## 3. Results Achieved
During this week's automated compliance audits and server scheduling labs, several key takeaways were gained:

* **Active Security Hardening (AWS Security Hub):**
  + Enabled AWS Security Hub to run automated audit scans against the CIS AWS Foundations Benchmark, identifying misconfigurations such as wide-open SSH port 22 rules or missing MFA configurations.
  + Takeaway: Transitioning from manual security checks to automated compliance auditing catches misconfigurations early. The visual Security Score makes it easy to schedule configuration fixes by priority.

* **Resource Governance (Tagging & IAM Roles for EC2):**
  + Applied consistent tag keys (`Environment: Dev`, `Project: FCAJ`) to classify resources and configured IAM Roles directly to EC2 instances instead of hardcoding Access Keys on servers.
  + Takeaway: Organizing cloud resources systematically via tagging and IAM roles secures server operations and forms the baseline for automated administration.

* **Operations Automation & Cost Controls (Lambda & EventBridge):**
  + A Python (Boto3) Lambda function was written triggered by EventBridge cron rules to start EC2 instances at 8:00 AM and stop them at 6:00 PM daily. Monitored and debugged the execution using CloudWatch Logs.
  + Takeaway: Shutting down development instances automatically outside business hours can save up to 60% of EC2 compute costs. This is a practical MLOps and Serverless automation pattern.
