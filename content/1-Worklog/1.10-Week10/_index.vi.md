---
title: "Worklog Tuần 10"
date: 2026-06-22
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

### Mục tiêu tuần 10:

* Thiết kế và hoàn thiện kiến trúc Runtime Architecture cho hệ thống Serverless Intelligent Document Processing (IDP).
* Áp dụng mô hình bảo mật nhiều lớp (Defense in Depth) và cơ chế xác thực người dùng bằng Amazon Cognito.
* Xây dựng kiến trúc Event-Driven giúp xử lý tài liệu bất đồng bộ và tối ưu hiệu năng hệ thống.
* Tối ưu chi phí vận hành theo tư duy FinOps và AWS Well-Architected Framework.
* Chuẩn bị kiến trúc hoàn chỉnh để nhóm triển khai đồ án thực tế.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Thiết kế Runtime Architecture cho hệ thống Serverless IDP <br> - Phân chia Network Boundaries (Global Services, Regional Services) <br> - Chuẩn hóa Data Flow và Data Flow Legend theo AWS Architecture Icons | 22/06/2026 | 22/06/2026 | Tài liệu đồ án nhóm |
| 3 | - Thiết kế lớp bảo mật Edge Security <br> - Tích hợp AWS WAF với Amazon CloudFront <br> - Thiết kế luồng xác thực JWT sử dụng Amazon Cognito và API Gateway Authorizer | 23/06/2026 | 23/06/2026 | Tài liệu đồ án nhóm |
| 4 | - Thiết kế luồng Event-Driven Architecture <br> - Áp dụng S3 Presigned URL cho chức năng Upload <br> - Thiết kế luồng S3 Event → Amazon SQS → AWS Lambda AI Worker → Amazon Textract → DynamoDB | 24/06/2026 | 24/06/2026 | Tài liệu đồ án nhóm |
| 5 | - Tối ưu kiến trúc theo AWS Well-Architected Framework <br> - Đánh giá khả năng mở rộng, tính sẵn sàng và hiệu năng của hệ thống <br> - Hoàn thiện sơ đồ kiến trúc cuối cùng | 25/06/2026 | 25/06/2026 | AWS Well-Architected Framework |
| 6 | - Phân tích chi phí theo tư duy FinOps <br> - Loại bỏ các thành phần phát sinh chi phí không cần thiết (EC2, NAT Gateway) <br> - Chuẩn bị AWS Pricing Calculator và hoàn thiện Proposal dự án | 26/06/2026 | 26/06/2026 | AWS Pricing Calculator |

### Kết quả đạt được tuần 10:

| Thứ | Công việc | Kết quả đạt được |
| --- | --- | --- |
| 2 | Thiết kế Runtime Architecture | Hoàn thiện sơ đồ Runtime Architecture theo tiêu chuẩn AWS Architecture Diagram, phân chia rõ các vùng Global Services, Regional Services và luồng xử lý dữ liệu của hệ thống. |
| 3 | Thiết kế Edge Security | Hoàn thiện mô hình bảo mật nhiều lớp (Defense in Depth), tích hợp AWS WAF với CloudFront và xây dựng cơ chế xác thực JWT bằng Amazon Cognito trước khi truy cập API Gateway. |
| 4 | Thiết kế Event-Driven Architecture | Hoàn thiện luồng xử lý bất đồng bộ sử dụng S3 Presigned URL, Amazon SQS, AWS Lambda, Amazon Textract và Amazon DynamoDB giúp hệ thống xử lý tài liệu linh hoạt, không gây nghẽn API. |
| 5 | Chuẩn hóa kiến trúc | Kiến trúc được tối ưu theo AWS Well-Architected Framework, đáp ứng các tiêu chí về Security, Reliability, Performance Efficiency, Cost Optimization và Operational Excellence. |
| 6 | Tối ưu chi phí và Proposal | Hoàn thiện phương án tối ưu chi phí theo FinOps, loại bỏ EC2 và NAT Gateway, sử dụng hoàn toàn kiến trúc Serverless. Đồng thời hoàn thiện Proposal và chuẩn bị triển khai đồ án thực tế. |