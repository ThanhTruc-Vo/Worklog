---
title: "Week 11 Worklog"
date: 2026-06-29
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

### Week 11 Objectives:

* Implement the Serverless Intelligent Document Processing (IDP) architecture on AWS.
* Develop a secure document upload workflow using Amazon S3 Presigned URLs.
* Build an Event-Driven document processing pipeline with Amazon SQS, AWS Lambda, and Amazon Textract.
* Implement multi-layer security using Amazon Cognito and AWS WAF.
* Develop the ReactJS Dashboard and complete the core features of the system.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | - Deploy Amazon S3 Upload Bucket and configure S3 Event Notification <br> - Create Amazon SQS Standard Queue and DynamoDB On-Demand table <br> - Configure S3 Lifecycle Rule to automatically remove processed raw files | 06/29/2026 | 06/29/2026 | IDP Project Documentation & AWS Documentation |
| 3 | - Develop the Lambda Presign API for generating Amazon S3 Presigned URLs <br> - Implement the Lambda AI Worker integrated with Amazon Textract (Queries) <br> - Store extracted information in Amazon DynamoDB | 06/30/2026 | 06/30/2026 | AWS SDK Documentation |
| 4 | - Configure Amazon Cognito User Pool and JWT Authentication <br> - Configure Amazon API Gateway Authorizer <br> - Deploy AWS WAF to protect APIs against spam and DDoS attacks | 07/01/2026 | 07/01/2026 | AWS Security Documentation |
| 5 | - Develop the ReactJS Dashboard <br> - Display invoice history and statistical charts <br> - Apply Data Masking before returning sensitive information to the frontend | 07/02/2026 | 07/02/2026 | ReactJS Documentation |
| 6 | - Perform end-to-end testing of the Upload → AI Processing → Dashboard workflow <br> - Review the architecture, optimize performance, and update project documentation | 07/03/2026 | 07/03/2026 | AWS Well-Architected Framework |

### Week 11 Achievements:

| Day | Task | Achievement |
| --- | --- | --- |
| 2 | Storage Infrastructure Deployment | Successfully configured the Amazon S3 Upload Bucket, Amazon SQS Standard Queue, and Amazon DynamoDB. S3 Event Notification and Lifecycle Rules were implemented to automate document processing and optimize storage costs. |
| 3 | Serverless Backend Development | Successfully developed the Lambda Presign API and AI Worker. The system automatically generates Presigned URLs, processes uploaded documents with Amazon Textract, and stores structured results in DynamoDB. |
| 4 | Security Implementation | Integrated Amazon Cognito with Amazon API Gateway using JWT Authentication. AWS WAF was configured with rate-limiting rules to mitigate spam and DDoS attacks. |
| 5 | Dashboard Development | Developed the ReactJS Dashboard to display processed invoices and analytical charts. Implemented Data Masking to protect sensitive information before sending responses to users. |
| 6 | Testing and System Review | Successfully validated the complete Event-Driven workflow from document upload to AI processing and dashboard visualization. Reviewed the architecture based on the AWS Well-Architected Framework and updated the project documentation for the next implementation phase. |