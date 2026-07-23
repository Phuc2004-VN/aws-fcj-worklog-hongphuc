---
title: "Testing and Verification"
date: 2026-07-09
weight: 4
chapter: false
pre: " <b> 5.4. </b> "
---

### System Testing and Result Verification

After deploying the complete Serverless infrastructure and Database, we perform functional testing steps to verify the end-to-end flow of the system from the user interface to backend processing services.

---

#### 1. System Login via Amazon Cognito
Access the system Dashboard page. The login interface is integrated with Amazon Cognito User Pool for user authentication.

![Cognito Login Interface](/images/5-Workshop/5.4-Test/image1.png)

*Note:* Since the trader's account was previously created in the User Pool, the login process is direct and secure.

---

#### 2. Financial Management Dashboard Interface
After successful login, the Dashboard interface displays the list of monitored stock tickers. Initially, the Dashboard only displays sample data (e.g., ticker `FPT`).

![Initial Dashboard Interface](/images/5-Workshop/5.4-Test/image2.png)

---

#### 3. Performing Analysis on a New Stock Ticker
To run an analysis, the trader selects the desired stock ticker (e.g., `VNM` - Vinamilk) from the toolbar and clicks the **Analyze** button.

![Selecting VNM ticker for analysis](/images/5-Workshop/5.4-Test/image3.png)

---

#### 4. Asynchronous Backend Processing Flow
When the **Analyze** button is clicked, the system triggers the following asynchronous processing flow:
1.  **API Gateway** receives the request from the Client and invokes the **Ingestion Lambda**.
2.  **Ingestion Lambda** calls the Yahoo Finance API to scrape historical data and the current price for ticker `VNM`.
3.  Raw data is captured and stored as a JSON file in **Amazon S3**.
4.  S3 sends an Event Notification to push a message into the **Amazon SQS Queue**.
5.  **Processing Lambda** is triggered by the SQS queue, retrieves the message, reads raw data from S3, and calculates advanced technical indicators (such as RSI, MACD, MA20, MA50, Volume).

*   **SQS Queue status during processing:**
    
    ![SQS Queue Status](/images/5-Workshop/5.4-Test/image4.png)
    
    ![SQS Queue Details](/images/5-Workshop/5.4-Test/image5.png)

*After Processing Lambda finishes processing the message:* The number of messages in the SQS queue drops to 0 (as shown below), confirming that the message has been successfully consumed.

![Empty SQS Queue after processing](/images/5-Workshop/5.4-Test/image6.png)

---

#### 5. Storing Analysis Results in Amazon DynamoDB
After calculating technical indicators and calling the AI model for recommendations, the final results are saved into the DynamoDB table `Stock_reports_1`.

![Stored Results in DynamoDB](/images/5-Workshop/5.4-Test/image7.png)

---

#### 6. Displaying Analysis Report on Dashboard
Returning to the Dashboard page, ticker `VNM` information appears along with detailed technical indicator parameters. 

![Dashboard displaying VNM ticker](/images/5-Workshop/5.4-Test/image8.png)
*(Image displaying a list of 3 stock tickers successfully analyzed on the Dashboard)*

![Technical Indicator Details on Dashboard](/images/5-Workshop/5.4-Test/image9.png)

---

#### 7. Checking System Logs on Amazon CloudWatch
Access Amazon CloudWatch Logs to monitor detailed activities of Processing Lambda and check for any arising errors.

![View Logs on CloudWatch](/images/5-Workshop/5.4-Test/image10.png)

Logs record that the execution flow succeeded according to the designed business logic.

![Detailed Successful Execution Logs](/images/5-Workshop/5.4-Test/image11.png)

---

#### 8. Token Quota Limit Exceeded Issue at Amazon Bedrock
During testing, the system recorded an error from Amazon Bedrock: **"Too many tokens per day, please try again."** (Exceeded daily token quota limit).

![Bedrock Quota Limit Error](/images/5-Workshop/5.4-Test/image12.png)

*   **Cause:** Due to default AWS account limits for the Claude model.
*   **Consequence:** When encountering this error, the system automatically triggers a data fallback mechanism, assigning a default confidence score of `68` (lower than the safety threshold of `75` required for sending) to ensure the system does not crash.
    
    ![Fallback Data in DynamoDB](/images/5-Workshop/5.4-Test/image13.png)

*   **Resolution:** Submit a Request Quota to increase limits for the Claude 3.5 Sonnet v2 model on the Amazon Bedrock management console.
    
    ![Bedrock Request Quota Interface](/images/5-Workshop/5.4-Test/image14.png)

---

#### 9. Final Review (Human-in-the-Loop)
After resolving the quota issue, Bedrock can successfully analyze and return a high confidence score. Reports with clear signals such as **STRONG BUY** or **STRONG SELL** will be reviewed by the trader on the Dashboard once more before clicking the button to send official email notifications to clients.

![Dashboard Interface After Quota Increase](/images/5-Workshop/5.4-Test/image15.png)

![Trader Report Approval Screen](/images/5-Workshop/5.4-Test/image16.png)