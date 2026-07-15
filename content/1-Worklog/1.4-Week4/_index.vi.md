---
title: "Worklog Tuần 4"
date: 2026-05-11
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Mục tiêu tuần 4:

- Tìm hiểu cơ chế hoạt động của Hybrid DNS trong AWS Cloud.
- Thực hành triển khai Route 53 Resolver để kết nối và phân giải tên miền giữa các môi trường mạng.
- Thiết lập kết nối VPC Peering nhằm cho phép các VPC giao tiếp nội bộ an toàn.
- Nghiên cứu AWS Transit Gateway và mô hình mạng Hub-and-Spoke phục vụ quản lý nhiều VPC.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Nghiên cứu lý thuyết Hybrid DNS và cơ chế phân giải tên miền trong AWS <br> - Tìm hiểu kiến trúc VPC Peering và khả năng kết nối giữa các VPC | 11/05/2026 | 11/05/2026 | Khóa học First Cloud AI Journey |
| 3 | - Thực hành Lab 10: Thiết lập Hybrid DNS với Amazon Route 53 Resolver <br> - Cấu hình Resolver Endpoint và Resolver Rules | 12/05/2026 | 12/05/2026 | Khóa học First Cloud AI Journey |
| 4 | - Thực hành Lab 19: Thiết lập VPC Peering giữa các VPC <br> - Cấu hình Route Table và kiểm tra Cross-VPC Communication | 13/05/2026 | 13/05/2026 | Khóa học First Cloud AI Journey |
| 5 | - Nghiên cứu lý thuyết AWS Transit Gateway <br> - Tìm hiểu mô hình mạng Hub-and-Spoke và kết nối nhiều VPC | 14/05/2026 | 14/05/2026 | Khóa học First Cloud AI Journey |
| 6 | - Thực hành Lab 20: Thiết lập AWS Transit Gateway <br> - Cấu hình định tuyến và kết nối giữa nhiều VPC | 15/05/2026 | 15/05/2026 | Khóa học First Cloud AI Journey |

### Kết quả đạt được tuần 4:

| Thứ | Công việc | Kết quả đạt được |
| --- | --- | --- |
| 2 | Nghiên cứu Hybrid DNS và VPC Peering | Hiểu cơ chế hoạt động của Hybrid DNS trong AWS Cloud, nguyên lý phân giải tên miền giữa các môi trường mạng và kiến trúc kết nối VPC Peering. |
| 3 | Triển khai Route 53 Resolver | Cấu hình thành công Route 53 Resolver, Resolver Endpoint và Resolver Rules, đồng thời kiểm tra khả năng phân giải tên miền giữa các hệ thống. |
| 4 | Thiết lập VPC Peering | Thiết lập thành công kết nối VPC Peering, cấu hình Route Table và xác nhận khả năng giao tiếp giữa các VPC thông qua Cross-VPC Communication. |
| 5 | Nghiên cứu AWS Transit Gateway | Hiểu nguyên lý hoạt động của AWS Transit Gateway và mô hình Hub-and-Spoke Network trong việc quản lý kết nối tập trung giữa nhiều VPC. |
| 6 | Triển khai AWS Transit Gateway | Cấu hình thành công Transit Gateway, thiết lập định tuyến giữa nhiều VPC và nắm được vai trò của Route Table, Network ACL, Security Group trong Hybrid Networking. |
---

### Hình ảnh minh chứng thực tế bài thực hành:

#### 1. Khởi tạo máy chủ Windows Server (RDGW-Server)

Giao diện quản lý EC2 ghi nhận máy chủ RDGW-Server chạy nền tảng Windows đã được khởi tạo thành công và đang ở trạng thái Running, sẵn sàng làm môi trường kiểm tra định tuyến.
![alt text](/images/1-Worklog/1.4-Week4/image.png)

#### 2. Cấu hình bảo mật mạng (Security Groups)

Thiết lập và chỉnh sửa thành công các luật truy cập đầu vào (Inbound Rules) cho nhóm bảo mật RDGW-SG, cho phép các luồng dữ liệu cần thiết phục vụ cho việc kiểm tra DNS và điều khiển máy chủ.
![alt text](/images/1-Worklog/1.4-Week4/image-1.png)

#### 3. Tạo điểm cuối Inbound (Route 53 Resolver Inbound Endpoint)

Hệ thống báo cáo cấu hình thành công điểm cuối Inbound (R53-InboundEndpoint) trên Route 53, cho phép môi trường On-Premises có thể truy vấn ngược lại các tên miền được lưu trữ trên hạ tầng AWS.
![alt text](/images/1-Worklog/1.4-Week4/image-2.png)

#### 4. Tạo điểm cuối Outbound (Route 53 Resolver Outbound Endpoint)

Khởi tạo trạng thái Operational cho điểm cuối Outbound (R53-OutboundEndpoint), đóng vai trò cầu nối chuyển tiếp các gói tin truy vấn DNS từ AWS sang mạng nội bộ.
![alt text](/images/1-Worklog/1.4-Week4/image-3.png)

#### 5. Thiết lập quy tắc chuyển tiếp (Resolver Rules)

Bảng quy tắc điều hướng DNS ghi nhận luật ForwardToOnPremAD đã được tạo hoàn chỉnh. Luật này chịu trách nhiệm bắt các truy vấn tới tên miền corp.internal và đẩy qua Outbound endpoint.
![alt text](/images/1-Worklog/1.4-Week4/image-4.png)

#### 6. Kiểm tra phân giải tên miền Hybrid DNS bằng nslookup

Truy cập vào máy chủ Windows (RDGW-Server) và chạy lệnh nslookup. Kết quả cho thấy hệ thống đã phân giải thành công tên miền nội bộ corp.internal ra địa chỉ IP 10.0.4.201 thông qua máy chủ DNS trung gian 10.0.0.2.
![alt text](/images/1-Worklog/1.4-Week4/image-5.png)

### 1.Thực hành Lab 20 

#### 1. Khởi tạo hạ tầng mạng Lab 20 qua CloudFormation

Hệ thống báo cáo quá trình triển khai ngăn xếp (Stack) Lab20-Stack thành công, tự động tạo ra 4 mạng VPC và các máy chủ EC2 đi kèm để phục vụ cho bài Lab Transit Gateway.
![alt text](/images/1-Worklog/1.4-Week4/image6.png)

#### 2. Khởi tạo bộ định tuyến trung tâm AWS Transit Gateway

Giao diện hiển thị cổng kết nối trung tâm lab20-tgw đã được khởi tạo thành công và đang ở trạng thái khả dụng (Available).
![alt text](/images/1-Worklog/1.4-Week4/image7.png)

#### 3. Cấu hình liên kết mạng (Transit Gateway Attachments)

Thực hiện gắn kết thành công cả 4 mạng VPC độc lập vào Transit Gateway, tạo thành mô hình mạng trung tâm Hub-and-Spoke.
![alt text](/images/1-Worklog/1.4-Week4/image8.png)

#### 4. Cấu hình bảng định tuyến TGW - Tab Associations

Bảng định tuyến của Transit Gateway ghi nhận các VPC đã được liên kết (Associated) thành công, sẵn sàng cho việc nhận định tuyến.
![alt text](/images/1-Worklog/1.4-Week4/image9.png)

#### 5. Cấu hình bảng định tuyến TGW - Tab Propagations

Kích hoạt thành công tính năng truyền bá định tuyến tự động (Propagation), giúp Transit Gateway tự động nhận diện các dải IP của 4 mạng VPC đã kết nối.
![alt text](/images/1-Worklog/1.4-Week4/image10.png)

#### 6. Cập nhật Route Table tại các VPC

Định tuyến luồng mạng tại VPC đã được tinh chỉnh, thiết lập hướng đi cho dải IP 172.16.0.0/16 trỏ thẳng vào Transit Gateway thay vì mạng Internet.
![alt text](/images/1-Worklog/1.4-Week4/image11.png)

#### 7. SSH vào máy chủ Bastion Host (VPC 1)

Sử dụng MobaXterm truy cập thành công vào máy chủ EC2 nằm trong VPC 1 (IP 100.48.207.178) để làm máy nhảy (Bastion Host) chuẩn bị kiểm tra mạng lưới.
![alt text](/images/1-Worklog/1.4-Week4/image12.png)

#### 8. Kiểm tra kết nối Internet từ máy chủ Bastion

Thực hiện lệnh ping amazon.com và ping google.com thành công từ máy chủ VPC 1 để đảm bảo máy chủ có kết nối mạng ổn định ra bên ngoài trước khi test mạng nội bộ.
![alt text](/images/1-Worklog/1.4-Week4/image13.png)

#### 9. Thực hiện lệnh ping 172.16.2.5 (VPC 2). Tuy lệnh ping thất bại (100% packet loss) do Security Group chưa cho phép ICMP, nhưng định tuyến mạng đã thông suốt

Từ máy chủ Bastion thuộc VPC 1, thực hiện lệnh ping 172.16.2.5 (VPC 2). Dữ liệu phản hồi thành công chứng minh mạng trung tâm đã định tuyến thông suốt.
![alt text](/images/1-Worklog/1.4-Week4/image14.png)

#### 10. SSH chéo qua VPC 2 và kiểm tra tiếp đến VPC 3

Sử dụng file khóa (tgw-key.pem) để SSH trực tiếp từ máy nhảy ở VPC 1 sang Private IP của máy chủ ở VPC 2 (172.16.2.5). Ngay sau đó, thực hiện lệnh ping thành công đến dải IP của VPC 3 (172.16.3.7).
![alt text](/images/1-Worklog/1.4-Week4/image15.png)

#### 11. Hoàn tất kiểm tra định tuyến toàn diện (VPC 4)

Tiếp tục luồng kiểm tra mạng trung tâm Transit Gateway bằng cách ping thành công từ máy chủ hiện tại đến dải IP của VPC 4 (172.16.4.6). Hệ thống mạng của toàn bộ 4 VPC đã liên thông hoàn toàn bảo mật.
![alt text](/images/1-Worklog/1.4-Week4/image16.png)

