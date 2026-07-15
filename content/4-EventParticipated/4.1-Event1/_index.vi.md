---
title: "AWS First Cloud AI Journey Community Day"
date: 2026-05-26
weight: 3
chapter: false
pre: " <b> 4.1. </b> "
---

# Bài thu hoạch “AWS First Cloud AI Journey Community Day”

### Mục Đích Của Sự Kiện

- **Lý thuyết chuyên sâu & Vận hành AI:** Tìm hiểu bản chất toán học và hạ tầng đứng sau LLM, cơ chế xử lý Context (Ngữ cảnh), mô hình Multi-Agent cấp doanh nghiệp và các công cụ trợ lý Agentic AI.
- **Tối ưu hóa hạ tầng Cloud:** Khảo sát các giải pháp tối ưu hóa chi phí, bảo mật hệ thống và tăng cường hiệu năng từ vùng biên (Edge) đến máy chủ gốc (Origin).
- **Thực chiến Hackathon & Tư duy Sản phẩm:** Trải nghiệm hành trình 36 giờ áp lực cao biến ý tưởng thành sản phẩm thực tế, đồng thời đập tan tư duy "làm bài tập đồ chơi" để đáp ứng tiêu chuẩn khắt khe từ thị trường lao động.

### Danh Sách Diễn Giả & Đội Thi

- **Duc Dao** - Solution Architect, Cloud Kinetics
- **Vy Lam** - Senior Business Systems Analyst, VPBank
- **Tinh Trương** - Platform Engineer, GoTymeX
- **Pham Ng Anh Hai** - G-AsiaPacific Vietnam, AWS Community Builder
- **Nguyen Tuan Thinh** - DevOps Engineer
- **Đội thi UTMorpho** - Thí sinh cuộc thi LotusHacks 2026
---
### Nội Dung

#### 1. Tính Bất Định Của Cấu Hình "Định Tính" Trong LLM (Diễn giả Duc Dao)

- **Bản chất Probabilistic Engine:** LLM sinh văn bản theo từng token. Tại mỗi bước, mô hình tính toán một điểm số thô (*Logits*) cho toàn bộ từ điển, chuyển thành xác suất qua hàm *Softmax* rồi tiến hành lấy mẫu.
- **Nghiên cứu thực tế (Assumption vs. Reality):** Lý thuyết cho rằng đặt `Temperature = 0` sẽ kích hoạt giải mã tham lam (*Greedy Decoding / Argmax*) giúp kết quả cố định hoàn toàn. Tuy nhiên, nghiên cứu của *Atil et al. (2024) (Penn State University & Comcast AI)* chỉ ra rằng đầu ra vẫn bị biến thiên ở cả chuỗi thô (*Torr-R*) và chuỗi cốt lõi (*Torr-A*).
- **Nguyên nhân cốt lõi:**
  - *Kỹ thuật:* Sai số làm tròn số thập phân và tính toán song song (*Parallel computing*) của GPU làm thay đổi thứ tự phép toán khi xử lý hàng tỷ phép tính.
  - *Thương mại:* Các nhà cung cấp Cloud API lớn sử dụng kỹ thuật *Inference Optimization (Batching)* – tự động gộp các Prompt ngắn của nhiều người dùng để chạy một lượt trên GPU nhằm tối ưu chi phí, làm thay đổi hoàn toàn bối cảnh tính điểm Logits.
- **Giải pháp:** Tự host mô hình cục bộ (như demo Local Llama 3 12B) để kiểm soát tuyệt đối hạ tầng, hoặc đặt `Temperature = 0.1` kết hợp tăng `Repeat Penalty` để vừa định tính cao vừa tránh lỗi lặp từ hệ thống (*Repetitive loops*).

#### 2. Hệ Thống Multi-Agent Cấp Doanh Nghiệp - Chấm Điểm Tín Dụng Startup (Diễn giả Vy Lam)

- **Sự lệch pha dữ liệu (Structural Mismatch):** Hệ thống ngân hàng truyền thống luôn từ chối Startup vì đòi hỏi 3+ năm báo cáo tài chính và tài sản thế chấp. Startup thực tế sở hữu dữ liệu đa chiều, phi cấu trúc (IP, năng lực team, burn rate, runway dòng tiền).
- **Mô hình Đa Tác Nhân (Multi-Agent Paradigm):** Xây dựng một "Hội đồng tín dụng ảo" bao gồm các Agent chuyên trách:
  - *Financial Analyst Agent:* Phân tích dòng tiền, tốc độ tiêu tiền và thời gian sống sót.
  - *Market Research Agent:* Đánh giá quy mô thị trường (TAM/SAM/SOM) và bối cảnh cạnh tranh.
  - *Risk Assessor Agent:* Đánh giá rủi ro pháp lý và hồ sơ năng lực của các Founder.
- **Tư duy Enterprise-Grade:** Đưa AI vào thực tế phải đi kèm an toàn, bảo mật từ ngày đầu tiên thông qua các building block của AWS: **Bedrock AgentCore, ECR, API Gateway**, tích hợp xác thực **Cognito/OAuth2 (JWT validation)**, bộ lọc an toàn **Bedrock Guardrails**, phân quyền **IAM least-privilege** và quản lý bằng **Terraform**. Hệ thống đem lại ROI ấn tượng: giảm hơn 90% chi phí vận hành và tăng 95% tốc độ xử lý hồ sơ.

#### 3. Context Is Everything - Đưa AI Vào Vận Hành Thực Tế (Diễn giả Tinh Trương)

- **Bộ khung Ngữ cảnh chuẩn (Context Framework):** Trước khi tương tác với AI, cần chuẩn bị kỹ 4 yếu tố:
  1. *Goal (Mục tiêu):* AI cần giúp đạt được kết quả cụ thể nào?
  2. *Relevant Info (Thông tin liên quan):* Chỉ đưa vào dữ liệu thực sự cần thiết cho tác vụ.
  3. *Constraints (Ràng buộc):* Giới hạn về công nghệ, phong cách, định dạng đầu ra.
  4. *Success Criteria (Tiêu chí thành công):* Định nghĩa thế nào là kết quả đạt chuẩn chất lượng.
- **Platform Engineering:** Khi quy mô doanh nghiệp lớn lên, Platform Engineer đóng vai trò xây dựng nền tảng hạ tầng tự động (*Internal Developer Platform*) để tích hợp sẵn các bộ Blueprint/Context nội bộ riêng biệt vào sản phẩm, giúp AI hiểu sâu bối cảnh doanh nghiệp thay vì chỉ nhồi nhét kiến thức phổ thông.

#### 4. Friendly AI Assistant w/ Amazon Quick (Diễn giả Pham Ng Anh Hai)

- **Nỗi đau của Business Users:** Nhân sự kinh doanh hàng ngày phải tốn quá nhiều thời gian để thu thập, phân tích dữ liệu thủ công từ nhiều nguồn rời rạc và lặp đi lặp lại các tác vụ nhàm chán.
- **Giải pháp Agentic AI Enterprise:** Tận dụng **Amazon Quick Suite** với hơn 40 kết nối dữ liệu doanh nghiệp và thế giới tri thức, kết hợp các mô hình Bedrock để xây dựng trợ lý thông minh.
- **Use case thực tế - PM Assistant:** Trợ lý quản lý sản phẩm tự động tạo Biên bản cuộc họp (*MoM - Minutes of Meeting*), tự động gửi email cập nhật cho các bên liên quan (Stakeholders) và tự động lên lịch cho buổi họp tiếp theo, giải phóng sức lao động tối đa.

#### 5. CloudFront as Your Foundation - Tối Ưu Hóa Từ Vùng Biên Đến Server Gốc (Diễn giả Nguyen Tuan Thinh)

- **Thách thức của các Founder:** Nỗi sợ lớn nhất là nhận phải những hóa đơn CDN/Hạ tầng tăng vọt đột biến (*bill spike* lên tới $100K) do traffic biến động bất thường hoặc bị tấn công.
- **Chiến lược tối ưu hóa:** Tận dụng Amazon CloudFront làm nền tảng cốt lõi:
  - *Giảm độ trễ:* Áp dụng cơ chế dồn luồng **HTTP/3 (QUIC / UDP) multiplexing** cho phép tải song song nhiều tài nguyên (ví dụ 11 luồng song song thay vì giới hạn 4 luồng của HTTP/1.1); tích hợp tính năng nén dữ liệu (*CloudFront HTTP compression*) giúp giảm tới 81% latency.
  - *Tối ưu đường truyền:* Tận dụng mạng lưới xương sống toàn cầu của AWS (*AWS global backbone*), duy trì kết nối bền vững (*Persistent connections*) để tránh bắt tay TCP lặp lại nhiều lần.
  - *Xử lý tại vùng biên (Edge Logic):* Sử dụng **CloudFront Functions** và **Lambda@Edge** để xử lý điều hướng địa lý, rewrite URL, chặn rate limit hoặc handle lỗi ngay tại vùng biên mà không cần chạm vào server gốc (Origin).

#### 6. Hành Trình 36 Giờ Biến Ý Tưởng Thành Thực Tế Tại LotusHacks 2026 (Đội thi UTMorpho)

- **Từ con số 0 đến Ý tưởng:** Xuất phát điểm vào Giờ thứ 0 , trải qua ngày khai mạc đầy lạc lõng. Bước ngoặt xuất hiện khi đội quyết định "nhìn vào công việc thực tế hàng ngày" để tìm ra nỗi đau thực sự của người dùng, từ đó dự án **UTMorpho** chính thức ra đời.
- **Áp lực trong 36 giờ Sprint liên tục:** Vượt qua chuỗi mắt xích thử thách khốc liệt: thiết lập đội ngũ -> code tính năng cốt lõi -> đối mặt khủng hoảng giữa kỳ (AI sinh tràn dữ liệu - *AI Overgeneration*, chạm giới hạn *Token Limits*, kiệt sức, kiệt quệ năng lượng trước giờ pitching) -> hoàn thiện sản phẩm và thực hiện bài Pitch quyết định.
- **Bài học xương máu rút ra:**
  - *Real Frustration Creates Real Ideas:* Sự ức chế và nỗi đau trong thực tế cuộc sống mới là thứ tạo ra ý tưởng giá trị, không phải lý thuyết suông.
  - *Chất lượng hơn Số lượng:* Nhiều ý tưởng không bằng một ý tưởng tập trung sâu sắc.
  - *Sức bền và Sự đồng bộ:* Hackathon là cuộc thi thử thách sức bền, và sự đồng bộ/thấu hiểu giữa các thành viên trong team (*Team Sync*) là yếu tố quan trọng nhất quyết định sự sống còn của dự án.

---

### Những Gì Học Được

#### Tư Duy Thiết Kế & Kiến Trúc Kỹ Thuật
- **Probabilistic Mindset:** LLM là mô hình xác suất, không phải định tính. Toàn bộ kiến trúc phần mềm hạ nguồn (*downstream services*) phải được thiết kế một cách chủ động để sẵn sàng xử lý các trường hợp AI trả về sai định dạng cấu trúc hoặc lệch đáp án giữa các lượt chạy.
- **Context is the Experience:** Ngữ cảnh không phải là phần thông tin bổ sung, nó chính là trải nghiệm của sản phẩm AI. Hãy tư duy như một người thầy, cung cấp đúng và đủ nguyên liệu (bộ khung 4 yếu tố) để AI làm việc hiệu quả.
- **Hạ tầng toàn diện (Enterprise Mindset):** Đưa AI vào doanh nghiệp lớn là một bài toán tổng hòa, bắt buộc phải giải quyết đồng thời các bài toán về bảo mật (Auth, IAM), quản trị dữ liệu (Guardrails) và tự động hóa hạ tầng (Terraform/Platform Engineering).

#### Thực Thực Trạng Thị Trường Lao Động
- Thị trường tuyển dụng công nghệ hiện tại vô cùng khốc liệt và bão hòa. Doanh nghiệp hoàn toàn không tuyển những ứng viên chỉ biết làm bài tập lý thuyết hay tạo các bản Demo đồ chơi. 
- Tiêu chuẩn của một **AI Engineer thực thụ** là phải tự chủ xây dựng các **Use Case thực tế** và đóng gói thành một **Sản phẩm hoàn chỉnh (Product)** có khả năng chạy ổn định.
- **Tư duy không trì hoãn:** Cứ mỗi 4 tháng, năng lực và sức mạnh của AI lại tăng lên gấp đôi. Trì hoãn thực hành hay học tập dù chỉ 1 tuần hay 1 tháng sẽ tạo ra một khoảng cách năng lực cực kỳ khủng khiếp, khiến nhân sự nhanh chóng bị bỏ lại phía sau.

---

### Ứng Dụng Vào Công Việc

1. **Chuẩn hóa Prompting của bản thân và Team:** Áp dụng triệt để bộ khung **Context Framework (Goal, Info, Constraints, Criteria)** cho mọi tác vụ tương tác với AI; loại bỏ hoàn toàn thói quen chat lan man nhiều chủ đề trên cùng một thread.
2. **Refactor cấu hình ứng dụng LLM hiện tại:** Thay vì để Temperature cố định bằng 0 dễ dẫn đến lỗi lặp từ, thực hiện refactor cấu hình hệ thống về mức **Temperature = 0.1** kết hợp tinh chỉnh **Repeat Penalty** để đạt được "điểm ngọt" (Sweet Spot) tối ưu về độ ổn định dữ liệu đầu ra.
3. **Triển khai kiến trúc xử lý lỗi hạ nguồn (Downstream Validation):** Bổ sung thêm các tầng kiểm tra cấu trúc dữ liệu (JSON Schema Validation) và cơ chế tự động thử lại (Retry logic) cho các dịch vụ nhận kết quả từ LLM để đảm bảo hệ thống tổng thể không bị crash khi AI sinh lỗi định dạng.
4. **Nghiên cứu ứng dụng Multi-Agent và DevOps/Edge:** Thử nghiệm xây dựng các Pilot Project phân vai tác nhân nhỏ cho các bài toán dữ liệu phi cấu trúc tại doanh nghiệp, áp dụng Terraform để quản lý hạ tầng và sử dụng CloudFront để tối ưu hiệu năng vùng biên, tiết kiệm chi phí hệ thống.
5. **Học tập với tinh thần Hackathon:** Áp dụng bài học từ đội UTMorpho, tập trung tìm kiếm các giải pháp giải quyết trực diện "nỗi đau thực tế" của dự án hiện tại, làm việc nhóm đồng bộ cao và kiên quyết bài trừ tư duy trì hoãn công việc.

---

### Trải nghiệm trong event

Chuỗi bài nói thực chiến tại hội thảo kết hợp với những câu chuyện lập nghiệp, thi đấu khốc liệt đã mang lại cho tôi những trải nghiệm vô cùng sâu sắc:

- **Đập tan ảo tưởng lý thuyết:** Việc chứng kiến tận mắt những lỗi sai lệch kết quả do Batching của các nhà đài Cloud API hay lỗi lặp từ khi cài đặt Temperature = 0 giúp tôi xây dựng một tư duy thiết kế hệ thống thực tế và cẩn trọng hơn.
- **Hiểu được tư duy Enterprise:** Qua case study chấm điểm tín dụng Startup của chị Vy Lam và bài toán Platform của anh Tinh Trương, tôi nhận ra giá trị cốt lõi của một kỹ sư không nằm ở việc prompt ra câu trả lời hay, mà là ở khả năng đóng gói sản phẩm an toàn, bảo mật, tự động hóa bằng code (Terraform) và có chỉ số ROI rõ ràng.
- **Động lực hành động mạnh mẽ:** Lời cảnh tỉnh về tốc độ phát triển "4 tháng nhân đôi sức mạnh" của AI cùng bài học xương máu từ hành trình 36 giờ vượt qua khủng hoảng của đội UTMorpho đã tạo ra một cú hích tâm lý cực lớn. Nó buộc tôi phải bước ra khỏi vùng an toàn, ngừng trì hoãn và bắt tay vào xây dựng những sản phẩm thực tế có giá trị ngay lập tức.

> Tổng kết lại, sự kiện đã giúp em hiểu rõ được doanh nghiệp cần gì , cách sử dụng AI hiểu quả ,sử dụng AI mới một cách tối ưu hiệu quả hơn , thử thách với bản thân qua các cuộc thi : lấy bài toán kinh doanh làm gốc, dùng sản phẩm thực tế làm câu trả lời, và luôn xây dựng hệ thống với tư duy sẵn sàng xử lý tính bất định của công nghệ tương lai.

![](/images/4.1-Event1/image1.jpg)
![](/images/4.1-Event1/image2.jpg)
