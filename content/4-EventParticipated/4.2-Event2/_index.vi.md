---
title: "Event 2"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 4.2. </b> "
---

# Bài thu hoạch “Định hướng nghề nghiệp và ứng dụng AI trên AWS”

### Thông Tin Sự Kiện

- **Thời gian:** Ngày 23/05
- **Vai trò:** Người tham dự
- **Chủ đề chính:** Định hướng nghề nghiệp, Prompt Engineering, Multi-Agent, Amazon CloudFront và bảo mật AI trong doanh nghiệp

### Mục Đích Của Sự Kiện

- Định hướng nghề nghiệp và chiến lược phát triển cho kỹ sư CNTT trong bối cảnh AI phát triển mạnh.
- Chia sẻ best practices về Prompt Engineering và cách cung cấp Context để làm việc với AI hiệu quả.
- Hướng dẫn áp dụng kiến trúc Multi-Agent ở cấp độ doanh nghiệp nhằm giải quyết bài toán phức tạp nhưng vẫn tuân thủ các yêu cầu bảo mật.
- Cập nhật cơ chế tính phí mới và các tính năng bảo mật nâng cao của Amazon CloudFront.

### Danh Sách Diễn Giả

- **Nguyễn Gia Hưng** — Solution Architect, AWS Việt Nam; người sáng lập SC
- **Tình Trương** — Platform Engineer, Gotam X
- **Hải Anh** — Pacific Việt Nam
- **Nguyễn Tuấn Thịnh** — DevOps Engineer
- **Uyển và Thảo** — Đội thi Hackathon, dự án UTM Morpo
- **Vy Lam** — Chuyên gia triển khai hệ thống AI cho ngân hàng VBBank

### Nội Dung Nổi Bật

#### Định hướng nghề nghiệp trong kỷ nguyên AI

- Nghịch lý Jevons cho thấy khi AI làm giảm chi phí tạo phần mềm, nhu cầu sử dụng phần mềm có thể tăng mạnh và tạo ra thêm nhiều công việc mới.
- Những công việc như sửa lỗi do AI sinh ra, bảo trì hệ thống, AI DevOps và Platform Engineering sẽ ngày càng quan trọng.
- Để cạnh tranh, kỹ sư cần kết hợp nền tảng học thuật, kiến thức kỹ thuật vững chắc, hiểu nghiệp vụ doanh nghiệp và có sản phẩm thực tế thay vì chỉ dừng ở bản demo.

#### Tối ưu Context cho AI

- Cần tránh tư duy “Internet Buller”, nhồi quá nhiều plugin, rule và dữ liệu không liên quan vào AI.
- Việc thay đổi Context liên tục có thể khiến mô hình mất tập trung và đưa ra câu trả lời sai lệch.
- Context nên hẹp nhưng sâu, xác định rõ **Goal, Role và Format** dựa trên nghiệp vụ thực tế.
- AI Mindset và khả năng áp dụng AI đúng cách là những kỹ năng quan trọng khi tham gia thị trường lao động.

#### Giảm thiểu độ lệch của LLM

- LLM là một **Probabilistic Engine**, vì vậy kết quả có thể thay đổi giữa các lần chạy, kể cả khi `temperature = 0`.
- Sai khác có thể đến từ phép tính số thực trên GPU và các kỹ thuật Inference Optimization của nhà cung cấp.
- Một số giải pháp gồm chạy nhiều lần để tìm kết quả chung, tự host model, sử dụng JSON Mode và kiểm thử liên tục.
- Hệ thống downstream phải được thiết kế để phát hiện và xử lý output sai định dạng hoặc không ổn định từ AI.

#### Tối ưu chi phí và bảo mật với Amazon CloudFront

- Flat Rate Pricing cung cấp các gói Free, Pro, Business và Premium, tích hợp AWS WAF nhằm giảm nguy cơ Bill Spike do DDoS hoặc lưu lượng bất thường.
- VPC Origin giúp ẩn Origin Server khỏi public internet và chỉ cho phép kết nối nội bộ với CloudFront.
- CloudFront còn hỗ trợ mTLS, giới hạn truy cập theo vị trí địa lý và chống DDoS tại Edge.

#### Kinh nghiệm Hackathon 36 giờ

- Morpo là một trình Editor sử dụng AI để tạo giao diện HTML/CSS từ ảnh chụp hoặc bản vẽ tay.
- Người dùng có thể chỉnh sửa trực tiếp trên giao diện thay vì yêu cầu AI tạo lại toàn bộ, qua đó tiết kiệm token.
- Bài học quan trọng là tập trung vào một vấn đề thực tế, tránh Feature Creep, phân chia công việc rõ ràng và duy trì sức khỏe trong quá trình thi.

#### Xây dựng Enterprise Multi-Agent System

- Case study tập trung vào bài toán đánh giá tín dụng cho startup không có tài sản thế chấp, chủ yếu dựa trên Intellectual Property.
- Multi-Agent phù hợp khi Context quá lớn và bài toán cần nhiều vai trò chuyên môn như tài chính, nghiên cứu thị trường và quản trị rủi ro.
- Việc chia nhỏ vai trò giúp hạn chế Context Window phình to và giảm sai lệch kiến thức.
- Doanh nghiệp cần triển khai Guardrails cho input/output, phòng chống Prompt Injection, Output Filtering, Rotate API Key và duy trì Audit Trail.
- Knowledge Transfer cần lựa chọn đúng dữ liệu mà chuyên gia thực tế sử dụng, thay vì đưa nguyên tài liệu dài cho AI.

### Những Gì Học Được

#### Tư Duy Thiết Kế

- **Business-first:** Bắt đầu bằng các câu hỏi ai sử dụng, sử dụng gì và tại sao cần sử dụng theo phương pháp Working Backwards.
- Hệ thống không chỉ cần hoạt động mà còn phải an toàn, đáng tin cậy và có Audit Trail để xác định trách nhiệm.
- Mọi quyết định áp dụng AI cần gắn với nhu cầu người dùng và giá trị kinh doanh cụ thể.

#### Kiến Trúc Kỹ Thuật

- Hiểu rủi ro của MCP Attack Vector và tầm quan trọng của việc cô lập quyền truy cập của từng Agent.
- Nắm được tư duy Infrastructure as Code và vai trò của Terraform trong quản lý, tự động hóa hạ tầng.
- Multi-Agent Orchestration nên áp dụng nguyên tắc chia để trị, trong đó mỗi Agent có một Role và Goal rõ ràng.
- Hệ thống downstream cần chủ động kiểm tra và xử lý output không ổn định của LLM.

#### Chiến Lược Phát Triển

- Không nên quá phụ thuộc vào AI mà bỏ qua các kỹ năng Core Backend như mã hóa mật khẩu và triển khai JWT Authentication.
- AI Engineer trong doanh nghiệp trước hết cần là một Software Engineer có khả năng tích hợp AI an toàn.
- Trước khi triển khai giải pháp cần tính toán ROI bằng dữ liệu thực tế để thuyết phục các bên liên quan.

### Ứng Dụng Vào Công Việc

- **Cải thiện cách sử dụng LLM:** Chuẩn hóa Prompt, loại bỏ rule dư thừa và cung cấp Context phù hợp để output ổn định hơn.
- **Tăng cường bảo mật dự án:** Áp dụng CloudFront để lọc request không mong muốn và VPC Origin để bảo vệ Origin Server.
- **Thiết kế Multi-Agent:** Chia quy trình thành Agent nghiên cứu, Agent review và Agent tổng hợp thay vì giao mọi nhiệm vụ cho một chatbot.
- **Luyện tập Infrastructure as Code:** Học Terraform để quản lý hạ tầng thay cho thao tác thủ công trên AWS Console.
- **Bổ sung kiểm thử:** Thiết kế downstream validation cho JSON và các output do AI tạo ra.

### Trải Nghiệm Trong Sự Kiện

Sự kiện mang tính định hướng cao, giúp tôi có góc nhìn thực tế hơn về cả tiềm năng lẫn giới hạn của AI trong môi trường doanh nghiệp.

#### Học hỏi từ chuyên gia thực chiến

- Các chia sẻ bao quát nhiều chủ đề, từ chiến lược nghề nghiệp trong ngành CNTT đến quy trình đánh giá tín dụng nội bộ của ngân hàng.
- Nội dung tập trung vào cách kỹ sư thích nghi, phát triển năng lực và tạo ra giá trị thực tế trong kỷ nguyên AI.

#### Bài học về Security Mindset

- Những cảnh báo về việc sao chép mã nguồn từ ChatGPT vào Production cho thấy output của AI luôn cần được review và kiểm thử.
- Các tình huống ứng dụng bị từ chối triển khai do nguy cơ rò rỉ dữ liệu nhấn mạnh vai trò sống còn của bảo mật trong doanh nghiệp.

#### Bài học từ Hackathon

- Cách các đội quản lý thời gian và loại bỏ tính năng bề nổi để tập trung vào trải nghiệm cốt lõi mang lại nhiều kinh nghiệm hữu ích cho dự án cá nhân.
- Một sản phẩm giải quyết tốt một vấn đề thực tế có giá trị hơn sản phẩm chứa quá nhiều tính năng chưa hoàn thiện.

#### Bài Học Rút Ra

- Sự phát triển của AI không làm mất đi vai trò của kỹ sư phần mềm, nhưng yêu cầu kỹ sư nâng cao năng lực thiết kế hệ thống, quản lý quy trình và hiểu nghiệp vụ.
- Kiến thức Backend, Security và Infrastructure as Code là nền tảng để triển khai GenAI an toàn.
- Hệ thống doanh nghiệp phải an toàn, đáng tin cậy và phục vụ đúng nhu cầu người dùng, không chỉ đơn thuần là chạy được.

> Tổng thể, sự kiện giúp tôi xây dựng tư duy thực tế hơn về nghề nghiệp, Prompt Engineering, Multi-Agent, Amazon CloudFront, bảo mật và cách triển khai AI ở cấp độ doanh nghiệp.
