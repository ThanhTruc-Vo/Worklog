---
title: "Worklog Tuần 11"
date: 2026-06-29
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

### Mục tiêu tuần 11:

* Hiện thực hóa kiến trúc Serverless Intelligent Document Processing (IDP) trên AWS.
* Xây dựng quy trình upload tài liệu an toàn bằng Amazon S3 Presigned URL.
* Triển khai luồng xử lý tài liệu bất đồng bộ (Event-Driven) sử dụng Amazon SQS, AWS Lambda và Amazon Textract.
* Thiết lập cơ chế bảo mật nhiều lớp với Amazon Cognito và AWS WAF.
* Phát triển giao diện Dashboard và hoàn thiện các chức năng chính của hệ thống.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Triển khai Amazon S3 Upload Bucket và cấu hình S3 Event Notification <br> - Khởi tạo Amazon SQS Standard Queue và DynamoDB On-Demand <br> - Thiết lập S3 Lifecycle Rule tự động xóa dữ liệu gốc sau khi xử lý | 29/06/2026 | 29/06/2026 | Tài liệu đồ án IDP & AWS Documentation |
| 3 | - Xây dựng Lambda Presign API tạo S3 Presigned URL <br> - Phát triển Lambda AI Worker tích hợp Amazon Textract (Queries) <br> - Lưu dữ liệu trích xuất vào Amazon DynamoDB | 30/06/2026 | 30/06/2026 | AWS SDK Documentation |
| 4 | - Triển khai Amazon Cognito User Pool và JWT Authentication <br> - Cấu hình Amazon API Gateway Authorizer <br> - Thiết lập AWS WAF bảo vệ API và chống Spam/DDoS | 01/07/2026 | 01/07/2026 | AWS Security Documentation |
| 5 | - Phát triển giao diện ReactJS Dashboard <br> - Hiển thị danh sách hóa đơn và biểu đồ thống kê <br> - Áp dụng Data Masking đối với dữ liệu nhạy cảm trước khi trả về Frontend | 02/07/2026 | 02/07/2026 | ReactJS Documentation |
| 6 | - Kiểm thử toàn bộ quy trình Upload → AI Processing → Dashboard <br> - Rà soát kiến trúc, tối ưu hiệu năng và cập nhật tài liệu dự án | 03/07/2026 | 03/07/2026 | AWS Well-Architected Framework |

### Kết quả đạt được tuần 11:

| Thứ | Công việc | Kết quả đạt được |
| --- | --- | --- |
| 2 | Triển khai hạ tầng lưu trữ | Hoàn thành cấu hình Amazon S3 Upload Bucket, Amazon SQS và Amazon DynamoDB. Thiết lập thành công S3 Event Notification và Lifecycle Rule giúp tự động xử lý cũng như tối ưu chi phí lưu trữ. |
| 3 | Xây dựng Serverless Backend | Phát triển thành công Lambda Presign API và AI Worker. Hệ thống tự động tạo Presigned URL, gửi tài liệu đến Amazon Textract để trích xuất dữ liệu và lưu kết quả vào DynamoDB. |
| 4 | Triển khai bảo mật hệ thống | Hoàn thành tích hợp Amazon Cognito với API Gateway thông qua JWT Authentication. AWS WAF được cấu hình để giới hạn số lượng request và giảm thiểu nguy cơ tấn công Spam hoặc DDoS. |
| 5 | Phát triển Dashboard | Xây dựng giao diện ReactJS hiển thị lịch sử tài liệu, biểu đồ thống kê và thực hiện Data Masking để bảo vệ thông tin nhạy cảm trước khi hiển thị cho người dùng. |
| 6 | Kiểm thử và hoàn thiện | Kiểm thử thành công toàn bộ luồng Event-Driven từ Upload → AI Processing → Dashboard. Rà soát kiến trúc theo AWS Well-Architected Framework và cập nhật tài liệu phục vụ giai đoạn triển khai tiếp theo. |