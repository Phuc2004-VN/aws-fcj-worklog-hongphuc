---
title: "Blog 2"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 3.2. </b> "
---

# AWS Cost & AI: When Running Cloud Becomes a Cost Management Problem

**Blog post link:** [Facebook - AWS Study Group FCJ](https://www.facebook.com/groups/awsstudygroupfcj/permalink/2199844680780492/)

During the early stage of learning and practicing with AWS, the focus is often technical: how to deploy an application to EC2, how to configure the backend environment, whether the server runs correctly, and whether the APIs respond as expected. However, once the system becomes more stable, another important topic becomes visible: cloud operating cost.

In parallel with backend deployment, the team also started exploring AWS AI services such as **Amazon Bedrock**, **Amazon SageMaker**, and other AWS AI Services like **Amazon Comprehend**. From that point, the team realized that cloud is not only about whether an application can be deployed, but also about how much it costs to run every day.

---

## Practice System Context

The initial practice system was simple:

- An EC2 Ubuntu instance running a Node.js backend.
- Several APIs for application logic.
- Continuous requests and logging during testing.
- Some extended experiments involving AI services.

At first, because the environment was still within AWS Free Tier, the team assumed that a small EC2 instance could run without much concern. But as testing time increased, several factors started affecting cost: EC2 running 24/7, growing logs, EBS storage usage, helper resources that were left enabled, and AI API calls that were made more often than expected.

![AWS Cost and AI practice architecture](/images/3-BlogsTranslated/3.2-Blog2/aws-cost-ai-architecture.png)

---

## Free Tier Does Not Mean Free Forever

A common misunderstanding for new AWS users is assuming that Free Tier means no cost at all. In reality, Free Tier is limited by time and usage. Once those limits are exceeded, AWS starts charging immediately.

During practice, costs can come from very familiar situations:

- EC2 keeps running without being shut down.
- Extra resources are created for testing and forgotten.
- EBS volumes remain after an instance is no longer used.
- Logs and requests grow over time.
- AI services generate cost based on requests or processed data.

The important point is that these small charges can accumulate. Without regular monitoring, users may discover the problem too late.

---

## When AI Is Added to the System

Unlike EC2, the cost of AI services is often not based only on running time. Many AI services charge by request count, token usage, or the amount of data analyzed.

Examples:

- **Amazon Comprehend** can charge based on the amount of text processed.
- **Amazon Bedrock** is often related to input and output tokens when invoking models.
- **Amazon SageMaker** can generate cost from instances, endpoints, notebooks, or training jobs.

A single small API call may not matter much. But with repeated testing, longer prompts, larger datasets, or frequent model invocations, cost can increase faster than expected. Therefore, AI usage limits should be designed from the beginning.

---

## Main Reasons Costs Increased Quickly

### 1. Running resources were not controlled well

During the learning stage, the team focused on making the system work and easily overlooked resource state. EC2 was not stopped after testing, EBS volumes were not cleaned up, and some supporting resources continued running even after they were no longer needed.

### 2. Cost monitoring was missing

At first, the team did not use tools such as **AWS Budgets**, **Billing Alarm**, or **Cost Explorer** consistently. Without dashboards and alerts, it is difficult to know how much the system costs each day.

### 3. AI experiments had no clear limits

AI service experiments can easily exceed expectations if there is no separate sandbox, no request limit, and no budget alert. With AI, “testing a few more times” can become more visible in cost compared with basic infrastructure services.

---

## Cost Optimization Direction

### Control EC2 and supporting resources

The team started changing how EC2 was used: only turn it on when testing, stop the instance after use, and delete resources that are no longer needed. For learning environments, automatic schedules can be used to stop instances outside working hours.

### Set up AWS Cost Management

Cost management tools should be enabled early:

- **AWS Budgets** to define cost thresholds.
- **Billing Alarm** to receive alerts when spending exceeds a limit.
- **Cost Explorer** to analyze cost by day, service, and tag.

These tools help shift from waiting for the bill to actively observing cost.

### Separate an AI sandbox environment

Instead of testing AI directly inside the main system flow, it is better to create a dedicated sandbox environment. This environment should have request limits, restricted permissions, and its own budget alerts to reduce unexpected cost risk.

### Understand the pricing logic of each service

Each AWS service has a different pricing model:

- EC2 is usually charged by running time.
- Storage is charged by stored capacity.
- AI services are charged by requests, tokens, or processed data.
- Load Balancers, NAT Gateways, endpoints, and logs can also create additional costs.

Because of this, one cost assumption cannot be applied to every service. Before enabling a new service, its pricing model and usage limit should be understood.

---

## A Practical View of AWS AI

AWS AI is powerful because it integrates well with the AWS ecosystem. A backend can call services through SDKs and combine them with IAM, VPC Endpoints, logging, and monitoring. However, this power also requires cost control.

For generative AI in particular, the question is not only whether the model can be invoked, but also:

- How much does each request cost?
- Does the prompt need to be that long?
- Should responses be cached?
- Should API calls be rate-limited?
- Are budget alerts already configured?

If these questions are considered early, the system becomes easier to operate as it grows.

---

## Lessons Learned

Cloud is not only about deployment; it is also about operations. A system that runs correctly but has no cost monitoring is not truly ready.

AI is not as “free” as it may feel at the beginning. The more tests are run, the longer prompts become, and the more data is processed, the more cost needs to be controlled.

Monitoring should be mandatory, not optional. Without monitoring, teams do not know how much they are spending, cannot control scale, and may exceed budget without noticing.

Automation is also a mindset upgrade. Instead of manually stopping EC2, teams can use schedulers, EventBridge, or lifecycle automation to move from using AWS manually to operating AWS with control.

---

## Conclusion

Through practicing AWS Cost management and exploring AI services, the team better understood that AWS is not only a place to deploy applications. It is an ecosystem that must be managed like a real operating system, where cost, performance, and architecture design are always connected.

From a backend running on EC2 to AI service experiments, the most important lesson is to design systems with a cost-aware mindset from the beginning. With that approach, cloud does not only run; it runs sustainably and under control.

