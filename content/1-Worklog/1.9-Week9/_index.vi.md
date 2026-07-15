---
title: "Worklog Tuần 9"
date: 2026-06-15
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

### Mục tiêu tuần 9:

* Tìm hiểu các dịch vụ Machine Learning và AI trên nền tảng AWS.
* Thực hành triển khai mô hình Machine Learning bằng Amazon SageMaker.
* Nghiên cứu các dịch vụ AI như Amazon Textract, Rekognition, Comprehend và Bedrock.
* Tìm hiểu quy trình xây dựng ứng dụng AI tích hợp với kiến trúc Serverless.
* Tổng hợp kiến thức để chuẩn bị áp dụng vào đồ án Serverless Intelligent Document Processing (IDP) System.
* 
### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc                                                                                                                                                                                                                               | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                                                                     |
| --- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ---------------------------------------------------------------------------------- |
| 2   | - Thực hành Lab 28: IAM Roles & Policies <br> - Tạo IAM User, IAM Policy và IAM Role <br> - Thực hành Switch Role, kiểm soát quyền truy cập theo Region và Tags <br> - Dọn dẹp IAM Users, Roles, Policies và EC2 sau khi hoàn thành Lab | 15/06/2026   | 15/06/2026      | [https://cloudjourney.awsstudygroup.com/](https://cloudjourney.awsstudygroup.com/) |
| 3   | - Thực hành Lab 30: IAM User Limits <br> - Cấu hình Permission Boundaries <br> - Kiểm thử giới hạn quyền truy cập của IAM User <br> - Dọn dẹp tài nguyên sau khi hoàn thành Lab                                                         | 16/06/2026   | 16/06/2026      | [https://cloudjourney.awsstudygroup.com/](https://cloudjourney.awsstudygroup.com/) |
| 4   | - Thực hành Lab 33: Data Encryption & Auditing <br> - Tạo Customer Managed Key (KMS) <br> - Mã hóa dữ liệu Amazon S3 bằng AWS KMS                                                                                                       | 17/06/2026   | 17/06/2026      | [https://cloudjourney.awsstudygroup.com/](https://cloudjourney.awsstudygroup.com/) |
| 5   | - Tiếp tục Lab 33 <br> - Cấu hình AWS CloudTrail <br> - Ghi nhận lịch sử API và mã hóa CloudTrail Logs bằng AWS KMS <br> - Dọn dẹp CloudTrail, S3 Buckets và lên lịch xóa KMS Key sau khi hoàn thành Lab                                | 18/06/2026   | 18/06/2026      | [https://cloudjourney.awsstudygroup.com/](https://cloudjourney.awsstudygroup.com/) |
| 6   | - Ôn tập và xem lại các bài Lab 28, Lab 30 và Lab 33 <br> - Viết nhật ký thực tập tuần 9 <br> - Tổng hợp kiến thức về IAM, KMS và CloudTrail                                                                                            | 19/06/2026   | 19/06/2026      | [https://cloudjourney.awsstudygroup.com/](https://cloudjourney.awsstudygroup.com/) |


### Kết quả đạt được tuần 9:

| Thứ | Công việc                 | Kết quả đạt được                                                                                                                                                                                             |
| --- | ------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 2   | Quản trị IAM nâng cao     | Hiểu cơ chế hoạt động của IAM User, IAM Policy và IAM Role; thực hành thành công Switch Role, áp dụng điều kiện giới hạn theo Region và Resource Tags, đồng thời hoàn thành việc dọn dẹp tài nguyên sau Lab. |
| 3   | Permission Boundaries     | Thiết lập thành công Permission Boundaries để giới hạn quyền tối đa của IAM User, hiểu cơ chế ngăn chặn leo thang đặc quyền và hoàn thành dọn dẹp tài nguyên sau Lab.                                        |
| 4   | AWS KMS                   | Tạo thành công Customer Managed Key (CMK) và áp dụng AWS KMS để mã hóa dữ liệu lưu trữ trên Amazon S3, nâng cao khả năng bảo vệ dữ liệu.                                                                     |
| 5   | AWS CloudTrail            | Cấu hình thành công AWS CloudTrail để ghi nhận lịch sử các API Calls, mã hóa CloudTrail Logs bằng AWS KMS và hoàn thành việc dọn dẹp CloudTrail, S3 Bucket cũng như lên lịch xóa KMS Key.                    |
| 6   | Tổng hợp kiến thức tuần 9 | Ôn tập lại toàn bộ các bài Lab đã thực hiện, củng cố kiến thức về IAM, Permission Boundaries, AWS KMS và AWS CloudTrail, đồng thời hoàn thành nhật ký thực tập tuần 9.                                       |


#### Lab28

![alt text](/images/1-Worklog/1.9-Week9/image-27.png)
![alt text](/images/1-Worklog/1.9-Week9/image-28.png)
![alt text](/images/1-Worklog/1.9-Week9/image-29.png)
![alt text](/images/1-Worklog/1.9-Week9/image-30.png)
![alt text](/images/1-Worklog/1.9-Week9/image-31.png)
![alt text](/images/1-Worklog/1.9-Week9/image-32.png)
![alt text](/images/1-Worklog/1.9-Week9/image-33.png)
![alt text](/images/1-Worklog/1.9-Week9/image-34.png)
![alt text](/images/1-Worklog/1.9-Week9/image-35.png)
![alt text](/images/1-Worklog/1.9-Week9/image-36.png)
![alt text](/images/1-Worklog/1.9-Week9/image-37.png)

#### Lab30

![alt text](/images/1-Worklog/1.9-Week9/image-38.png)
![alt text](/images/1-Worklog/1.9-Week9/image-39.png)
![alt text](/images/1-Worklog/1.9-Week9/image-40.png)
![alt text](/images/1-Worklog/1.9-Week9/image-41.png)

#### Lab33
![alt text](/images/1-Worklog/1.9-Week9/image42.png)
![alt text](/images/1-Worklog/1.9-Week9/image43.png)
![alt text](/images/1-Worklog/1.9-Week9/image44.png)
![alt text](/images/1-Worklog/1.9-Week9/image45.png)
![alt text](/images/1-Worklog/1.9-Week9/image46.png)
![alt text](/images/1-Worklog/1.9-Week9/image47.png)