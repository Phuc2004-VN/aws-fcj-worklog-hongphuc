---
title: "Week 2 Worklog"
date: 2026-05-03
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

# FIRST CLOUD AI JOURNEY (FCAJ)

## 1. Weekly Goals
This week, focus was placed on network design and completing official office onboarding documentation:
* Completing the official internship registration.
* Studying network theory (IP addressing, CIDR blocks, Subnets, Security Groups, Network ACLs).
* Practicing creating a Custom VPC, separating Public/Private subnets, and testing routing.
* Setting up advanced AWS Budgets alerts to monitor networking resource costs.

## 2. Tasks to Implement in the Week
Below is the summary of activities performed from April 24th to May 3rd, 2026:

| Day / Date | Work Content | Task Details | Results Achieved | Reference Sources |
| --- | --- | --- | --- | --- |
| Fri (Apr 24) | Info Registration | - Onboarding paperwork: <br> &emsp; + Completed the internship survey link <br> &emsp; + Received guidelines for office onboarding | Completed administrative procedures; ready for office onboarding. | [AWS Registration Link](https://hcm-rules.awsfcaj.com/2-instructions/2.4-moving/) |
| Sat (Apr 25) | VPC Basics Research | - VPC theory study: <br> &emsp; + Watched AWS training videos <br> &emsp; + Studied IP addressing, CIDR blocks, and Subnets | Understood IP address allocation and network segmentation within a VPC. | [Provided Videos](https://www.youtube.com/watch?v=BPuD1l2hEQ4&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=26)|
| Sun (Apr 26) | Network Schema Draft | - Subnet design layout: <br> &emsp; + Sketched a network model with Public/Private subnets | Visualized the traffic flow from the Internet into the private network. | [AWS Documentation](https://aws.amazon.com/vi/architecture/)|
| Mon (May 27) | Budget Management | - Budgeting configurations: <br> &emsp; + Configured advanced AWS Budgets alerts for networking | Set up cost threshold alerts to control NAT Gateway and VPN expenses. | [AWS Billing Console](https://000007.awsstudygroup.com/vi/) |
| Tue (Apr 28) | VPC Initialization | - VPC creation: <br> &emsp; + Created Custom VPC with CIDR `10.0.0.0/16` <br> &emsp; + Provisioned Public and Private Subnets | Successfully configured an isolated private network partition. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Wed (Apr 29) | Network Routing | - Routing setup: <br> &emsp; + Configured Route Tables and Internet Gateway (IGW) <br> &emsp; + Associated IGW with Public Subnet | Enabled resources in the Public Subnet to connect to the Internet. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Thu (Apr 30) | Network Security Study | - Firewall study: <br> &emsp; + Studied differences between Security Groups and NACLs | Mastered the two firewalls protecting EC2 instances and Subnets. | [AWS Security Guide](https://000003.awsstudygroup.com/vi/3-prerequisite/3.5-createsecuritygroup/) |
| Fri (May 01) | International Labor Day | - High Availability: <br> &emsp; + Self-studied HA best practices for VPC design | Understood how to deploy Subnets across multiple Availability Zones (AZs). | [AWS Architecture Center](https://000019.awsstudygroup.com/) |
| Sat (May 02) | EC2 & VPC Verification | - Network verification: <br> &emsp; + Launched EC2 in Public Subnet and verified SSH <br> &emsp; + Launched EC2 in Private Subnet | Verified that routing and security configurations function correctly. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Sun (May 03) | Weekly Reporting | - Documentation work: <br> &emsp; + Compiled Week 2 worklog <br> &emsp; + Prepared plans for next week | Completed documentation for tracking internship progress. | Personal Records |

## 3. Results Achieved
During this week's custom VPC setup lab, several key takeaways were gained:

* **VPC Subnetting and IP Allocation:**
  + Gained a solid understanding of IP addressing and **CIDR** network segmentation. Created a custom VPC (`10.0.0.0/16`) and partitioned it into Public Subnets (for internet-facing resources like web servers and load balancers) and Private Subnets (for backend apps and databases).
  + Takeaway: Planning network IP ranges carefully from the start prevents IP exhaustion and routing overlaps when connecting different VPCs in the future.

* **Routing Configuration and Verification:**
  + Configured an Internet Gateway (IGW) and updated the Public Route Table to enable outbound connectivity. Tested connection paths by launching EC2 instances in both subnets; successfully SSH'd into the public instance while verifying the private subnet remained secure.
  + Takeaway: Verifying cross-subnet routing paths directly helps map traffic flows in real-world scenarios.

* **Multi-Layered Security (Security Groups vs. NACLs):**
  + Configured Security Groups (Stateful – working at instance level, automatically opening return ports) and Network ACLs (Stateless – working at subnet level, requiring explicit rules for both directions).
  + Takeaway: Implementing a dual-layer firewall pattern is a critical Defense-in-Depth practice. If one layer is misconfigured, the other still protects the resources.

* **NAT Gateway and VPN Cost Control (FinOps):**
  + Takeaway: Network gateway resources (like NAT Gateways or VPN connections) accumulate hourly charges quickly. Configured advanced AWS Budgets alerts at 50%, 80%, and 100% thresholds to manage practice credits.
