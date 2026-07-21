---
title: "Introduction"
date: 2026-07-09
weight: 1
chapter: false
pre: " <b> 5.1. </b> "
---

#### System Overview
The system is built to support the stock analysis process using AWS Serverless architecture. Stock price data is retrieved from Yahoo Finance and then processed through services such as Lambda, S3, SQS, Amazon Bedrock, and DynamoDB.

The system automatically collects market data, calculates technical indicators such as RSI, MACD, MA, and Volume, and then sends the calculated metrics to Amazon Bedrock to generate analysis and investment recommendations. The analysis results are displayed on the Dashboard for traders to review, approve, or reject before sending email notifications to clients.

#### System Architecture

![Stock Alerts System Architecture](/images/5-Workshop/5.1-Workshop-overview/stock-alerts-architecture.png)

The system architecture is designed around asynchronous, serverless microservices decoupled by queues and storage buffers:

1. **Data Ingestion Tier**: Amazon EventBridge triggers an Ingestion Lambda function periodically to fetch market ticker data from Yahoo Finance and store raw JSON datasets into Amazon S3.
2. **Buffering & Processing Tier**: An S3 Event Notification pushes incoming dataset metadata into an Amazon SQS Queue. A Processing Lambda consumes queue events, calculates key technical indicators (RSI, MACD, Moving Averages), and prepares prompt context.
3. **AI Analysis Tier**: Processing Lambda invokes Amazon Bedrock (Claude 3.5 / Titan) to synthesize technical indicators and generate human-readable stock analysis recommendations.
4. **Persistence & Presentation Tier**: Results are stored in Amazon DynamoDB. The Frontend Dashboard (hosted on Amazon S3 & CloudFront with AWS WAF & Cognito authentication) displays pending recommendations to Financial Analysts / Traders.
5. **Notification Tier**: Upon analyst approval, Amazon SES / SNS sends final automated email reports to subscribed clients.

#### Who are the clients?
The clients of the system are those interested in tracking and investing in stocks, including:
*   Individual investors who want to receive stock analysis suggestions.
*   Beginners in the market who need a tool to help understand technical signals.
*   Traders or financial advisors who need a dashboard to review recommendations before sending them to clients.

In this system, end-users do not receive direct recommendations from the AI immediately. Instead, the analysis results are reviewed by a trader first to ensure safety and mitigate investment information risks.

#### What problem does the system solve?
The system solves the problem of manual stock analysis, which is time-consuming and prone to missing technical signals. As the number of stocks increases, it becomes difficult for traders to continuously monitor price data, volume, and technical indicators.

The system helps automate key steps:
*   Collecting stock data from Yahoo Finance.
*   Storing raw data for audit and reprocessing.
*   Calculating technical indicators at the backend.
*   Using AI to assist in analyzing the calculated metrics.
*   Saving analysis results into DynamoDB.
*   Allowing traders to approve recommendations before emailing clients.

Consequently, the system shortens analysis time, increases the capacity to track multiple stocks simultaneously, and ensures that the final recommendation remains under human control.