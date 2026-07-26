---
title: "Event 3"
date: 2026-07-25
weight: 3
chapter: false
pre: " <b> 4.3. </b> "
---

# Báo Cáo Sự Kiện: Agentic AI Buildweek 2026

### Thông Tin Sự Kiện

- **Thời gian:** Thứ Bảy, ngày 25 tháng 7 năm 2026 (diễn ra tiếp nối sau 24 giờ thi Hackathon liên tục)
- **Địa điểm:** Thành phố Hồ Chí Minh
- **Đơn vị tổ chức:** AWS, Quỹ đầu tư JI và Cộng đồng FCAJ (AWS Study Group)
- **Vai trò:** Khách tham dự

### Các Khách Mời Đặc Biệt Và Nội Dung Chia Sẻ

Sự kiện vinh dự có sự góp mặt và đồng hành của các chuyên gia hàng đầu từ AWS:

#### Mr. Nguyễn Gia Hưng – Head of Solution Architect, AWS Vietnam

- Tham dự với vai trò khách mời đặc biệt và giám khảo trực tiếp chấm điểm, đưa ra các câu hỏi phản biện chuyên sâu về kiến trúc điện toán đám mây cho các đội thi.
- Lên sân khấu trao chứng nhận và chụp ảnh kỷ niệm cùng các đội chiến thắng.

#### Mr. Joseph Marazota – Head of Technology, AWS ASEAN

- **Phát biểu khai mạc và truyền cảm hứng:** Nhìn lại hành trình 20 năm làm công nghệ, từ thời điểm việc phát hành phần mềm mất cả quý đến ngày nay khi các AI Agent có thể tự động triển khai phần mềm từng phút.
- **Tư duy đổi mới:** Khuyên các lập trình viên trẻ không để những kinh nghiệm hay tư duy cũ từ 20 năm trước trở thành rào cản. Thế hệ trẻ nên chủ động thử thách các góc nhìn truyền thống bằng một “mental model” hoàn toàn mới.
- **Thực tế công nghệ tại Amazon:** Chia sẻ ví dụ Amazon vận hành hơn một triệu robot tại các trung tâm xử lý. Robot hay phần mềm chỉ là phần cứng thô; dữ liệu, các Agent và con người trong cơ chế Human-in-the-loop mới tạo nên giá trị và sự cải tiến liên tục.
- **Thông điệp:** Động viên thế hệ trẻ tại Việt Nam trở thành những người học tập suốt đời (lifelong learners) để làm chủ công nghệ, tiên phong xây dựng tương lai công nghệ cho Việt Nam và khu vực.

### Mục Tiêu Sự Kiện

- Tạo môi trường Hackathon thực chiến để các thí sinh xây dựng và trình bày sản phẩm Agentic AI trên hạ tầng AWS.
- Kết nối sinh viên, kỹ sư và cộng đồng công nghệ thông qua các buổi demo, góp ý chuyên môn và chia sẻ kiến thức thực tế.
- Khuyến khích tư duy phát triển sản phẩm dựa trên bài toán thực tế, giá trị mang lại cho người dùng và tính khả thi khi triển khai.

### Trình Bày Sản Phẩm Và Demo (Pitching & Demos)

Hoạt động chính của chương trình là phần trình bày sản phẩm, demo trực tiếp và trả lời câu hỏi phản biện từ Ban giám khảo của năm đội thi:

#### One Team – Giải Nhất AWS Track

- **Sản phẩm:** Chatbot đặt món KFC đa kênh, tích hợp trực tiếp trên Zalo và WhatsApp.
- **Giải pháp:** Sử dụng AWS Bedrock Agent Core thay cho Lambda truyền thống để ghi nhớ ngữ cảnh và lịch sử giao dịch. Tiny Fish được dùng để tự động thu thập menu KFC; bước xác nhận cuối (Verify) giúp tránh đặt nhầm đơn do AI ảo giác. Chi phí hạ tầng được tối ưu còn khoảng 0,006 USD cho mỗi đơn hàng.

#### Signal Scout – Giải Nhì

- **Sản phẩm:** Hệ thống Multi-Agent tình báo kinh doanh (Competitive Intelligence).
- **Giải pháp:** Tự động thu thập các tín hiệu chiến lược và báo cáo tài chính rời rạc của đối thủ thông qua Tiny Fish và Apify. Agent Supervisor điều phối các Sub-Agent, kết hợp Langfuse để chấm điểm chất lượng dữ liệu và code thuần để ngăn Prompt Injection, đồng thời giảm chi phí token.

#### PLAN

- **Sản phẩm:** Trợ lý AI native dành riêng cho Solution Architect (SA).
- **Giải pháp:** Phân tích yêu cầu bằng ngôn ngữ tự nhiên hoặc file quy định, policy của doanh nghiệp để tự động vẽ sơ đồ kiến trúc chuẩn trên Draw.io; đồng thời xuất bảng chi phí và tạo mã hạ tầng dưới dạng Terraform hoặc CloudFormation để triển khai trực tiếp lên AWS.

#### 3K – Dự Án Shepherd

- **Sản phẩm:** Hệ thống AI giám sát và điều phối mật độ đám đông qua camera theo thời gian thực.
- **Giải pháp:** Amazon Kinesis Video Streams truyền video trực tiếp vào ECS Fargate chạy mô hình YOLOv8/v11 Small kết hợp ByteTrack để nhận diện và theo dõi luồng người. Người dùng có thể tự vẽ vùng (Edit Zone) để đếm người; AI Agent trên Amazon Bedrock tính thời gian chờ và đề xuất phương án điều phối nhân sự.

#### Six Pillars

- **Sản phẩm:** Hệ thống phòng chống rửa tiền (AML) cho ngân hàng và sàn giao dịch, giúp giảm tỷ lệ cảnh báo sai (False Positive).
- **Giải pháp:** Kiến trúc ba tầng gồm: tầng 1 lọc nhanh bằng Kinesis và XGBoost; tầng 2 điều phối hệ thống Multi-Agent (KYC, Money Flow, Sanction) kết hợp OpenSearch RAG và Guardrails; tầng 3 là giao diện Case Management để chuyên viên rà soát các trường hợp nghi vấn theo mô hình Human-in-the-loop. Hệ thống tăng cường bảo mật bằng KMS, IAM, Security Hub và AWS X-Ray.

### Các Bài Học Quan Trọng Rút Ra (Key Takeaways)

#### 1. Tư Duy Xây Dựng Sản Phẩm AI

- **Giải quyết đúng Pain Point:** Sản phẩm phải xuất phát từ vấn đề thực tế của người dùng, chẳng hạn việc mất ba giờ để xử lý một trường hợp nghi vấn rửa tiền hoặc rào cản phải tải ứng dụng khi đặt đồ ăn, thay vì chỉ tập trung phô diễn kỹ thuật phức tạp.
- **Kiểm soát phạm vi trong 24 giờ:** Ưu tiên xây dựng một MVP hoạt động được, tránh mở rộng phạm vi quá lớn khiến phần demo không thể hoàn thiện.
- **Độ tin cậy và con người:** AI phải có cơ chế kiểm duyệt đầu ra và xác nhận; con người luôn cần tham gia quyết định trong các quy trình quan trọng.

#### 2. Kỹ Năng Kỹ Thuật Và Hạ Tầng Cloud

- Nắm vững cách thiết kế kiến trúc Multi-Agent theo mô hình Supervisor–Sub-Agents và giao tiếp Agent-to-Agent (A2A).
- Biết kết hợp AI với code thuần để kiểm tra dữ liệu, giảm ảo giác và ngăn Prompt Injection.
- Hiểu cách tính toán và tối ưu chi phí sử dụng LLM và Amazon Bedrock trong môi trường thực tế.

#### 3. Kỹ Năng Mềm Và Làm Việc Nhóm

- Nâng cao khả năng giao tiếp, hạ cái tôi cá nhân để lắng nghe đồng đội và giải quyết xung đột dưới áp lực của đợt sprint 24 giờ.
- Luyện tập kỹ năng thuyết trình, demo sản phẩm thực tế và bảo vệ kiến trúc hệ thống trước chuyên gia, giám khảo từ AWS.

### Kết Luận Và Đánh Giá Chung

Agentic AI Buildweek 2026 không chỉ đem lại cái nhìn toàn cảnh về xu hướng phát triển AI Agent hiện nay mà còn truyền cảm hứng mạnh mẽ thông qua những chia sẻ thực tế từ đại diện lãnh đạo AWS ASEAN, Mr. Joseph Marazota và Mr. Nguyễn Gia Hưng. Sự kiện giúp củng cố tư duy phát triển sản phẩm lấy người dùng làm trung tâm, tầm quan trọng của việc kiểm soát phạm vi công việc và giá trị cốt lõi của tinh thần làm việc nhóm.
