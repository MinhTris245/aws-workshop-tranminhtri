---
title: "Event 2"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 4.2. </b> "
---

# Bài thu hoạch “FCAJ Community Day”

### Thông Tin Sự Kiện

- **Tên sự kiện:** FCAJ Community Day
- **Thời gian:** Ngày 27/06/2026
- **Vai trò:** Người tham dự

### Mục Đích Của Sự Kiện

- Chia sẻ kinh nghiệm, trải nghiệm và góc nhìn thực tế về điện toán đám mây từ môi trường doanh nghiệp.
- Giới thiệu các giải pháp AI Agent ứng dụng trong vận hành Cloud, xử lý giọng nói tiếng Việt và quy trình nhân sự.
- Hướng dẫn phương pháp thiết kế kiến trúc bảo mật tiêu chuẩn khi tích hợp AI vào hệ thống nội bộ của doanh nghiệp.
- Tạo cơ hội kết nối, trao đổi giữa cộng đồng, sinh viên và các chuyên gia đang làm việc trong lĩnh vực Cloud và AI.

### Danh Sách Diễn Giả

- **Steve Trần** — Founder, Cloud Thinker
- **Hiếu Nghị** — Renova Cloud
- **Kiệt** — Student Builder Group
- **Trung** — CEO, Re AI
- **Bảo và Nguyên** — Cloud Engineer, Cloud Kinetics
- **Trường** — AI Solution, Noventiq
- **Minh Anh** — Solution Sales, Noventiq
- **Toàn Nguyễn** — AWS Security Builder

### Nội Dung Nổi Bật

#### Ứng dụng AI Agent trong Cloud Operations

- Hệ thống microservices ngày càng phức tạp khiến việc vận hành thủ công tốn nhiều thời gian, chi phí và khó mở rộng.
- AI Agent có thể hỗ trợ kỹ sư DevOps điều tra sự cố, kiểm tra mã nguồn, tối ưu chi phí FinOps và tự động hóa hoạt động đánh giá bảo mật, kiểm thử xâm nhập.
- AI đóng vai trò như một trợ lý phân tích và đề xuất, giúp đội ngũ kỹ thuật xử lý công việc nhanh chóng và có hệ thống hơn.

#### Xây dựng Voice AI chuyên biệt cho tiếng Việt

- Các mô hình Speech-to-Speech truyền thống còn hạn chế với ngôn ngữ có nguồn dữ liệu thấp như tiếng Việt.
- Kiến trúc được chia thành ba bước: **STT (Speech-to-Text) → LLM (Large Language Model) → TTS (Text-to-Speech)**, giúp kiểm soát nội dung tốt hơn và hạn chế hiện tượng hallucination.
- Hệ thống tích hợp Tool Calling, khả năng nhận diện ngữ cảnh, giới tính và thời điểm ngắt lời để tạo phản hồi tự nhiên hơn.

#### Tối ưu xử lý sự cố với AWS DevOps Agent

- AWS DevOps Agent hỗ trợ giải quyết tình trạng **Fragmented Telemetry**, khi log và trace bị phân tán ở nhiều nguồn khác nhau.
- Quy trình tự động gồm bốn bước: **Phân loại thông tin → Điều tra nguyên nhân gốc rễ → Đề xuất phương án khắc phục → Cải thiện hệ thống**.
- Mô hình **Human-in-the-loop** vẫn được duy trì: AI đưa ra đề xuất, còn con người kiểm duyệt và quyết định thực thi.

#### Chuyển đổi số quy trình nhân sự với Amazon Q

- Quy trình lọc CV thủ công dễ chịu ảnh hưởng bởi cảm tính và có thể bỏ sót ứng viên phù hợp.
- Amazon Q có thể đọc hiểu mô tả công việc, trích xuất dữ liệu từ CV, kể cả tệp PDF hoặc ảnh scan, sau đó đối chiếu và hỗ trợ chấm điểm ứng viên khách quan hơn.
- Giải pháp giúp bộ phận nhân sự giảm các công việc lặp lại và dành nhiều thời gian hơn cho hoạt động đánh giá chuyên sâu.

#### Thiết lập kiến trúc bảo mật cho Amazon Q

- Public Endpoint có thể làm tăng nguy cơ DDoS, nghe lén hoặc rò rỉ dữ liệu trong quá trình truyền tải.
- Luồng kết nối an toàn sử dụng **VPC Connection, Private Subnet và Application Load Balancer (ALB)** để bảo vệ dữ liệu nội bộ.
- Quyền truy cập và kết nối riêng tư cần được thiết kế ngay từ đầu khi doanh nghiệp tích hợp AI vào môi trường Production.

### Những Gì Học Được

#### Tư Duy Thiết Kế

- **Human-in-the-loop:** AI hỗ trợ và khuếch đại năng lực con người, không thay thế hoàn toàn kỹ sư có chuyên môn.
- **Business-first approach:** Công cụ AI và quy trình công nghệ phải xuất phát từ bài toán và nhu cầu thực tế của doanh nghiệp.
- Việc áp dụng AI cần đi kèm cơ chế kiểm duyệt, phân quyền và trách nhiệm ra quyết định rõ ràng.

#### Kiến Trúc Kỹ Thuật

- Hiểu cách tách các module STT, LLM và TTS để xử lý bài toán nhận diện và phản hồi giọng nói tiếng Việt.
- Nắm được phương pháp sử dụng VPC, Private Subnet và ALB để xây dựng môi trường mạng khép kín cho hệ thống AI và MCP Server.
- Nhận thức rõ vai trò của log, metric, trace và observability trong quá trình điều tra sự cố bằng AI.

#### Chiến Lược Ứng Dụng AI

- AI phù hợp với các tác vụ lặp lại như đọc CV, tổng hợp log lỗi và hỗ trợ phân tích nguyên nhân sự cố.
- Tự động hóa giúp nhân sự có thêm thời gian cho công việc chiến lược và hoạt động ra quyết định.
- Điều kiện tiên quyết để ứng dụng AI hiệu quả là hạ tầng phải có mức độ trưởng thành phù hợp, đặc biệt về observability và dữ liệu vận hành.

### Ứng Dụng Vào Công Việc

- **Thử nghiệm AWS DevOps Agent:** Tích hợp vào dự án để hỗ trợ giảm MTTR (Mean Time To Recovery) khi xảy ra sự cố.
- **Tích hợp GenAI vào quy trình nghiệp vụ:** Sử dụng Amazon Q Developer hoặc AI Agent để hỗ trợ các bộ phận non-tech như HR và Admin phân tích dữ liệu.
- **Nâng cấp bảo mật:** Rà soát các kết nối API với AI bên thứ ba và ưu tiên Private Connection để tăng mức độ an toàn thông tin.
- **Duy trì Human-in-the-loop:** Yêu cầu con người kiểm tra trước khi thực hiện những hành động có ảnh hưởng đến môi trường Production.

### Trải Nghiệm Trong Sự Kiện

Tham gia **FCAJ Community Day** là một trải nghiệm thực tế và chuyên sâu, giúp tôi cập nhật các xu hướng mới về AI Agent trên nền tảng AWS và hiểu rõ hơn cách các công nghệ này được ứng dụng trong doanh nghiệp.

#### Học hỏi từ các chuyên gia thực chiến

- Các chia sẻ từ Founder, CEO, Cloud Engineer và Security Builder mang lại góc nhìn đa chiều, từ startup đến doanh nghiệp lớn.
- Nội dung không chỉ giới thiệu công nghệ mà còn phân tích những bài toán vận hành, nhân sự và bảo mật trong thực tế.

#### Trải nghiệm kỹ thuật trực quan

- Các phiên live demo như Voice Bot phản hồi trực tiếp, AI rà soát lỗi hệ thống và AI phân tích CV giúp tôi dễ hình dung quy trình hoạt động.
- Những ví dụ thực tế cho thấy AI Agent có thể kết hợp khả năng phân tích với Tool Calling để hỗ trợ xử lý công việc.

#### Kết nối và giải đáp

- Sự kiện tạo cơ hội trao đổi trực tiếp với diễn giả về xử lý giọng vùng miền, chi phí Data Transfer và những khó khăn khi triển khai thực tế.
- Các câu hỏi và phản hồi tại sự kiện giúp làm rõ khoảng cách giữa một bản demo kỹ thuật và hệ thống Production.

#### Bài Học Rút Ra

- AI đang chuyển từ chatbot đơn thuần sang hệ sinh thái Agent có khả năng phân tích và gọi công cụ để thực hiện tác vụ.
- Data Security và Observability là hai nền tảng quan trọng trước khi tích hợp AI vào quy trình vận hành doanh nghiệp.
- Công nghệ mới phải đi kèm Role-based Access Control, cơ chế kiểm duyệt và giới hạn hành động rõ ràng.
- AI mang lại hiệu quả cao nhất khi hỗ trợ con người đưa ra quyết định nhanh chóng, chính xác và dựa trên đầy đủ dữ liệu.

> Tổng thể, FCAJ Community Day giúp tôi mở rộng kiến thức về Cloud, AI Agent, Voice AI, tự động hóa DevOps và kiến trúc bảo mật trên AWS, đồng thời định hướng rõ hơn cách áp dụng các công nghệ này vào dự án thực tế.
