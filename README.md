# Serverless GenAI Chatbot (AWS Bedrock & Lambda)

A fully serverless AI chatbot built using Amazon Bedrock for intelligence, AWS Lambda for orchestration, and S3 for a static web frontend.

## 🚀 Overview
This project demonstrates how to build a scalable, cost-efficient chatbot without managing any servers. It leverages Amazon's Titan Text Express model to provide real-time AI responses through a web interface.

## 🏗️ Architecture
1. **Frontend:** HTML/JavaScript hosted on **Amazon S3**.
2. **API Layer:** **Amazon API Gateway** (REST API) acting as a bridge.
3. **Logic:** **AWS Lambda** (Python) processing requests and managing conversation history.
4. **AI Engine:** **Amazon Bedrock** (Titan Text Express v1) providing LLM inference.

## 🛠️ Tech Stack
* **Cloud:** AWS (S3, Lambda, API Gateway, Bedrock, IAM, CloudWatch)
* **Language:** Python 3.x (Boto3 SDK)
* **Frontend:** HTML5, CSS3, JavaScript (Fetch API)

## 🔧 Key Features & Implementation
* **Serverless Logic:** Lambda handles CORS preflight and communicates with Bedrock Runtime.
* **Context Awareness:** Passes conversation history to the model to maintain chat context.
* **Security:** Implements the Principle of Least Privilege via custom IAM policies.

## 💡 Lessons Learned & Debugging
During the lab, I encountered an issue where the frontend was live, but the AI wouldn't respond. 

* **The Problem:** The Lambda function had default logging permissions but lacked the `bedrock:InvokeModel` permission.
* **The Solution:** I successfully debugged the execution logs in CloudWatch and implemented a **Combined IAM Policy** that authorized both logging and Bedrock inference. This taught me the critical importance of service-to-service authorization in AWS.

## 🚀 How to Run
1. **Bedrock:** Request access to `amazon.titan-text-express-v1` in your AWS region.
2. **Lambda:** Deploy the code in `/backend`, increase timeout to 30s, and attach the policy in `/iam`.
3. **API Gateway:** Create a POST method with Lambda Proxy Integration and enable CORS.
4. **S3:** Upload `/frontend/index.html` and enable Static Website Hosting.
5. **Connect:** Update the `API_URL` in your `index.html` with your API Gateway Invoke URL.

---
Created by Narinder Soni - (https://www.linkedin.com/in/narinder-soni-9821095/)
=======
# AgenticAI
Projects related to Agentic AI
