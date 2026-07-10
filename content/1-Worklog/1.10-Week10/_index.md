---
title: "Week 10 Worklog"
date: 2026-06-22
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

### Week 10 Objectives:

* Design and finalize the Runtime Architecture for the Serverless Intelligent Document Processing (IDP) System.
* Apply the Defense in Depth security model and implement user authentication using Amazon Cognito.
* Build an Event-Driven Architecture to process documents asynchronously and improve system scalability.
* Optimize infrastructure costs following FinOps principles and the AWS Well-Architected Framework.
* Finalize the system architecture in preparation for the team's implementation phase.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | - Design the Runtime Architecture for the Serverless IDP System.<br>- Define Network Boundaries (Global Services and Regional Services).<br>- Standardize Data Flow and Data Flow Legend following AWS Architecture Diagram best practices. | 22/06/2026 | 22/06/2026 | Project Documentation |
| 3 | - Design the Edge Security architecture.<br>- Integrate AWS WAF with Amazon CloudFront.<br>- Design JWT authentication flow using Amazon Cognito and API Gateway Authorizer. | 23/06/2026 | 23/06/2026 | Project Documentation |
| 4 | - Design the Event-Driven Architecture.<br>- Implement the S3 Presigned URL upload workflow.<br>- Design the processing pipeline: S3 Event → Amazon SQS → AWS Lambda AI Worker → Amazon Textract → Amazon DynamoDB. | 24/06/2026 | 24/06/2026 | Project Documentation |
| 5 | - Optimize the architecture based on the AWS Well-Architected Framework.<br>- Evaluate system scalability, availability, and performance.<br>- Finalize the system architecture diagram. | 25/06/2026 | 25/06/2026 | AWS Well-Architected Framework |
| 6 | - Analyze infrastructure costs using FinOps principles.<br>- Remove unnecessary cost-generating components (EC2 and NAT Gateway).<br>- Prepare the AWS Pricing Calculator and finalize the project proposal. | 26/06/2026 | 26/06/2026 | AWS Pricing Calculator |

### Week 10 Achievements:

| Day | Activity | Achievement |
| --- | --- | --- |
| 2 | Runtime Architecture Design | Successfully completed the Runtime Architecture diagram following AWS architecture standards, clearly separating Global Services, Regional Services, and the end-to-end data flow of the system. |
| 3 | Edge Security Design | Successfully implemented a Defense in Depth security model by integrating AWS WAF with Amazon CloudFront and designing secure JWT authentication using Amazon Cognito before API Gateway access. |
| 4 | Event-Driven Architecture Design | Successfully designed an asynchronous document processing workflow using S3 Presigned URL, Amazon SQS, AWS Lambda, Amazon Textract, and Amazon DynamoDB, improving scalability and eliminating API bottlenecks. |
| 5 | Architecture Optimization | Optimized the system architecture according to the AWS Well-Architected Framework, meeting the key pillars of Security, Reliability, Performance Efficiency, Cost Optimization, and Operational Excellence. |
| 6 | Cost Optimization & Proposal | Completed the FinOps cost optimization strategy by eliminating EC2 and NAT Gateway, adopting a fully Serverless architecture, and finalizing the AWS Pricing Calculator and project proposal for implementation. |