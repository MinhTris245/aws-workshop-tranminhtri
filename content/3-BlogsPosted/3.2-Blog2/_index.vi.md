---
title: "Blog 2"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 3.2. </b> "
---

# AWS Compute Blog | Amazon EC2 Auto Scaling Group – Điều mình học được sau khi tìm hiểu về dịch vụ tự động mở rộng trên AWS

Xin chào mọi người,

Trong quá trình học và làm đồ án trên AWS, mình có cơ hội tìm hiểu khá nhiều dịch vụ thuộc nhóm Amazon EC2. Một trong những dịch vụ khiến mình ấn tượng nhất là **Amazon EC2 Auto Scaling Group (ASG)**.

Ban đầu mình nghĩ Auto Scaling chỉ đơn giản là “tự động tạo thêm EC2”. Nhưng sau khi tìm hiểu tài liệu và các bài viết từ AWS, mình nhận ra dịch vụ này không chỉ giúp mở rộng hệ thống mà còn là một phần rất quan trọng trong việc xây dựng các ứng dụng có khả năng chịu tải cao và vận hành ổn định trên Cloud.

![Kiến trúc hệ thống sử dụng Amazon EC2 Auto Scaling Group](/images/sodo1.drawio.png)

## Điều mình từng hiểu sai về Auto Scaling Group

Lúc mới học AWS, mình luôn có một câu hỏi:

> “Một EC2 chẳng phải đã đủ để chạy website rồi sao? Tại sao phải cần nhiều EC2?”

Thực tế, một EC2 hoàn toàn có thể phục vụ rất nhiều người dùng cùng lúc nếu cấu hình đủ mạnh.

Tuy nhiên, vấn đề không nằm ở việc một EC2 có chạy được hay không, mà là điều gì sẽ xảy ra khi lượng người dùng tăng đột biến hoặc máy chủ gặp sự cố?

Đó cũng chính là lý do Auto Scaling Group được thiết kế.

## Auto Scaling Group không chỉ để tăng thêm EC2

Điều mình thấy thú vị nhất là nhiều người, bao gồm cả mình trước đây, thường nghĩ Auto Scaling chỉ có nhiệm vụ tạo thêm máy chủ.

Sau khi tìm hiểu kỹ hơn, mình nhận ra Auto Scaling Group thực sự là một dịch vụ quản lý toàn bộ vòng đời của EC2.

Nó có thể:

- Tự động tạo EC2 mới khi tải hệ thống tăng.
- Tự động giảm số lượng EC2 khi hệ thống ít người sử dụng.
- Tự động thay thế EC2 bị lỗi.
- Luôn duy trì đúng số lượng EC2 mà quản trị viên đã cấu hình.

Điều này giúp hệ thống luôn hoạt động ổn định mà không cần quản trị viên theo dõi liên tục.

## Điều mình thấy hay nhất là khả năng tự phục hồi

Theo mình, đây mới là điểm đáng giá nhất của Auto Scaling Group.

Giả sử hệ thống đang chạy với 3 EC2. Nếu một EC2 bị lỗi hoặc Health Check thất bại, Auto Scaling Group sẽ tự động tạo một EC2 mới để thay thế.

Toàn bộ quá trình diễn ra gần như tự động. Người dùng hầu như không nhận ra rằng phía sau hệ thống vừa có một máy chủ bị hỏng.

Đây cũng là lý do các hệ thống Production trên AWS thường sử dụng Auto Scaling Group kết hợp với Application Load Balancer.

## CloudWatch đóng vai trò rất quan trọng

Một điều mình học được nữa là Auto Scaling Group không tự “đoán” khi nào cần mở rộng. Nó hoạt động dựa trên các chỉ số do Amazon CloudWatch cung cấp.

Ví dụ:

- CPU vượt 70%.
- Lượng request tăng cao.
- Network Traffic tăng mạnh.

CloudWatch sẽ gửi tín hiệu để Auto Scaling Group quyết định có nên tạo thêm EC2 hay không.

Ngược lại, khi tải giảm xuống, Auto Scaling Group cũng sẽ tự động giảm số lượng EC2 để tiết kiệm chi phí. Điều này giúp việc mở rộng hệ thống trở nên hoàn toàn tự động.

## Không phải lúc nào cũng nên sử dụng Auto Scaling Group

Theo mình, đây cũng là điều khá nhiều người mới học AWS thường hiểu nhầm.

Nếu chỉ xây dựng:

- Website cá nhân.
- Website nội bộ.
- Hệ thống demo.
- Đồ án nhỏ.

thì một EC2 duy nhất hoàn toàn có thể đáp ứng. Việc triển khai thêm Auto Scaling Group đôi khi chỉ làm tăng độ phức tạp và phát sinh thêm chi phí.

Tuy nhiên, đối với các hệ thống phục vụ nhiều người dùng hoặc cần đảm bảo tính sẵn sàng cao thì Auto Scaling Group gần như là một thành phần rất đáng cân nhắc.

## Góc nhìn cá nhân

Sau khi tìm hiểu về Auto Scaling Group, mình nhận ra rằng việc xây dựng một hệ thống trên Cloud không chỉ đơn giản là tạo một EC2 rồi chạy ứng dụng.

Điều quan trọng hơn là chuẩn bị sẵn khả năng mở rộng khi lượng người dùng tăng và khả năng tự phục hồi khi máy chủ gặp sự cố.

Theo mình, Auto Scaling Group chính là một trong những dịch vụ thể hiện rất rõ tư duy thiết kế hệ thống của AWS: không chỉ giúp hệ thống chạy được mà còn giúp hệ thống luôn sẵn sàng trước những thay đổi của thực tế.

## Kết luận

Đối với mình, Amazon EC2 Auto Scaling Group không đơn thuần là dịch vụ tự động tạo thêm EC2.

Đó là giải pháp giúp hệ thống:

- Tự động mở rộng theo nhu cầu sử dụng.
- Tăng tính sẵn sàng của ứng dụng.
- Giảm công sức vận hành.
- Tối ưu chi phí khi lưu lượng truy cập thay đổi.

Nếu mọi người đang học AWS hoặc chuẩn bị triển khai một ứng dụng thực tế trên Cloud, mình nghĩ Auto Scaling Group là một dịch vụ rất đáng dành thời gian để tìm hiểu.

Cảm ơn mọi người đã dành thời gian đọc bài chia sẻ của mình. Nếu anh/chị hoặc các bạn đã từng triển khai Auto Scaling Group trong thực tế, mình rất mong được lắng nghe thêm những kinh nghiệm và góc nhìn từ mọi người.

**Tài liệu tham khảo:** [Introducing Instance Refresh for EC2 Auto Scaling](https://aws.amazon.com/blogs/compute/introducing-instance-refresh-for-ec2-auto-scaling/)
