---
title: "Week 10 Worklog"
date: 2026-06-28
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

# FIRST CLOUD AI JOURNEY (FCAJ)

## 1. Overview of Week 10 Goals and Plan
This week, I focused on researching serverless architectures, drafting the dashboard interface, setting up API endpoints, and building a fully functional demo flow for data ingestion and AI processing:
* Studying serverless architectures (AWS Lambda, Amazon API Gateway) and writing a technical experience sharing article for the AWS Study Group VN community.
* Designing and drafting the dashboard UI, configuring API endpoints, and defining the AWS service architecture for our graduation project.
* Implementing the ingestion Lambda function combined with Amazon EventBridge to automatically scrape and store data in Amazon S3.
* Integrating AWS Bedrock for AI/NLP processing, combined with an asynchronous message queue via Amazon SQS to prevent data loss, and successfully testing the end-to-end demo flow.

## 2. Tasks to Implement in the Week
Below is the summary of activities performed from June 22nd to June 28th, 2026:

| Day / Date | Work Content | Task Details | Results Achieved | Reference Sources |
| --- | --- | --- | --- | --- |
| Mon (Jun 22) | Serverless Research | - Serverless architecture study: <br> &emsp; + Learned how AWS Lambda and Amazon API Gateway work <br> &emsp; + Analyzed benefits in scalability and cost savings | Acquired a deep understanding of Serverless and cloud resource optimization. | AWS Documentation |
| Tue (Jun 23) | Technical Sharing Blog | - Writing a technical article: <br> &emsp; + Summarized core serverless concepts and best practices <br> &emsp; + Published the sharing article on AWS Study Group VN | Shared valuable knowledge with the community and received constructive feedback. | AWS Study Group VN |
| Wed (Jun 24) | Dashboard UI Design | - Dashboard wireframing: <br> &emsp; + Sketched wireframes to display parsed data and AI results <br> &emsp; + Mapped out main application pages | Created a low-fidelity UI layout to guide front-end development. | Figma / Draw.io |
| Thu (Jun 25) | Architecture & API Spec | - AWS Services & API mapping: <br> &emsp; + Defined API endpoints connecting front-end and back-end <br> &emsp; + Confirmed graduation project's AWS cloud architecture | Completed the specification of API endpoints and optimized the AWS design. | Project Specifications |
| Fri (Jun 26) | Ingestion Lambda Code | - Programming the ingestion pipeline: <br> &emsp; + Developed a Lambda function to scrape external data source <br> &emsp; + Configured Amazon EventBridge rules for cron scheduling | Enabled automated data ingestion Lambda saving raw files to S3. | AWS Lambda Guide |
| Sat (Jun 27) | AWS Bedrock & SQS | - Asynchronous AI integration: <br> &emsp; + Connected AWS Bedrock to process ingested data via AI <br> &emsp; + Configured Amazon SQS queue to orchestrate workloads | Prevented backend bottlenecks and guaranteed message delivery under high load. | AWS Bedrock Guide |
| Sun (Jun 28) | Demo Test & Summary | - End-to-End testing: <br> &emsp; + Verified the entire flow: scraping, queuing with SQS, and Bedrock AI calls <br> &emsp; + Wrote Week 10 report and summary | Checked off a fully functional demo flow; ready for comprehensive testing in Week 11. | Demo Project |

## 3. Results Achieved
During this week's serverless design, API configurations, and AI-integrated pipeline prototype development, I gained several key takeaways:

* **Serverless Architecture & Community Sharing:**
  + Gained hands-on knowledge of AWS Lambda (FaaS) and API Gateway. Mastered routing requests from API Gateway to Lambda, configuring CORS, and setting up Authorizers.
  + Takeaway: Writing and sharing technical articles on AWS Study Group VN helps solidify theoretical concepts through community discussions and peer feedback.

* **API Specification & Dashboard Design:**
  + Successfully defined all necessary API Endpoints (CRUD operations, AI trigger endpoints, dashboard statistics queries) and sketched out a user-friendly frontend dashboard.
  + Takeaway: Designing API specifications early ensures parallel front-end and back-end development works smoothly without data structure conflicts.

* **Automated Data Ingestion via EventBridge & S3:**
  + Programmed a Lambda function to automatically scrape data on a scheduled basis (Cron pattern) triggered by EventBridge rules, writing raw JSON payloads directly into an S3 bucket.
  + Takeaway: EventBridge rules are a perfect serverless substitute for traditional OS-level cronjobs running on EC2 instances, eliminating 24/7 active infrastructure costs.

* **AWS Bedrock Integration & Asynchronous Messaging via Amazon SQS:**
  + Integrated AWS Bedrock (utilizing large language models like Claude) to parse crawled data. Implemented an SQS queue between ingestion and AI processing to buffer and decouple the services.
  + Takeaway: SQS acts as a crucial buffer, ensuring the system is highly fault-tolerant. Even if Bedrock hits request limits (Rate Limit exceptions), tasks remain safely queued and will retry automatically without data loss.
