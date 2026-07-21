---
title: "Blog 3"
date: 2026-07-20
weight: 3
chapter: false
pre: " <b> 3.3. </b> "
---

# AWS Architecture Blog | Xây dựng Upload File Service trên AWS với Presigned URL – Điều mình học được sau khi tìm hiểu kiến trúc Serverless

Xin chào mọi người,

Trong quá trình tìm hiểu về AWS, mình nhận ra rằng một hệ thống upload file không chỉ đơn giản là xây dựng một API nhận file rồi lưu xuống Amazon S3.

Ban đầu mình nghĩ đây là cách triển khai hợp lý. Tuy nhiên, khi đọc các tài liệu và kiến trúc mà AWS khuyến nghị, mình mới hiểu rằng nếu mọi file đều đi qua Backend thì hệ thống sẽ phải xử lý rất nhiều dữ liệu không cần thiết, đặc biệt khi số lượng người dùng hoặc kích thước file ngày càng lớn.

Điều mình học được là AWS có một cách tiếp cận hiệu quả hơn bằng việc sử dụng **Presigned URL** kết hợp với các dịch vụ Serverless.

![Kiến trúc Upload File Service trên AWS với Presigned URL](/images/blog3-presigned-url-architecture.jpg)

## 1. Không nhất thiết phải upload file thông qua Backend

Điều đầu tiên mình học được là Backend không cần trực tiếp nhận và xử lý toàn bộ dữ liệu file.

Thay vào đó, Backend chỉ có nhiệm vụ xác thực người dùng và tạo Presigned URL. Sau khi nhận được URL này, Client sẽ upload trực tiếp lên Amazon S3.

Theo mình, cách làm này giúp giảm đáng kể tải cho Backend, đồng thời tận dụng khả năng mở rộng của Amazon S3.

## 2. AWS sử dụng API Gateway, Lambda và Amazon S3 như thế nào?

Trong kiến trúc này, AWS kết hợp một số dịch vụ quen thuộc:

- **Amazon API Gateway** tiếp nhận yêu cầu từ Client.
- **AWS Lambda** xác thực người dùng và tạo Presigned URL.
- **Amazon S3** lưu trữ file được upload.
- **AWS IAM** quản lý quyền truy cập giữa các dịch vụ.

Điều mình thấy hay là Lambda không phải xử lý dữ liệu file mà chỉ thực hiện việc cấp quyền upload, giúp API phản hồi nhanh hơn và giảm chi phí xử lý.

## 3. Upload thành công chưa phải là kết thúc

Một điểm mình ấn tượng là sau khi file được upload lên Amazon S3, hệ thống vẫn có thể tiếp tục xử lý nhiều công việc khác.

Thông qua S3 Event Notification hoặc Amazon EventBridge, AWS Lambda có thể được kích hoạt để:

- Resize hình ảnh.
- Quét virus.
- Lưu metadata vào cơ sở dữ liệu.
- Gửi thông báo cho người dùng.

Nhờ đó, việc upload và xử lý file được tách thành các bước độc lập, giúp hệ thống dễ mở rộng hơn.

## 4. Đây là một ví dụ hay về kiến trúc Serverless

Theo mình, điểm thú vị nhất của kiến trúc này là mỗi dịch vụ chỉ đảm nhận đúng vai trò của mình. Amazon API Gateway tiếp nhận request, AWS Lambda xử lý logic nghiệp vụ, Amazon S3 lưu trữ dữ liệu và EventBridge hỗ trợ xử lý các sự kiện phát sinh sau khi upload.

Việc kết hợp các dịch vụ này giúp hệ thống vừa đơn giản, vừa có khả năng mở rộng mà không cần quản lý máy chủ.

## Điều mình rút ra sau khi tìm hiểu

Sau khi tìm hiểu kiến trúc này, mình nhận ra rằng tối ưu hệ thống không chỉ nằm ở việc chọn cấu hình mạnh hơn mà còn là thiết kế đúng ngay từ đầu.

Việc sử dụng Presigned URL giúp Backend không phải xử lý dữ liệu file, giảm tải cho hệ thống và tận dụng tối đa khả năng mở rộng của Amazon S3. Đồng thời, kiến trúc hướng sự kiện cũng giúp dễ dàng bổ sung các chức năng như xử lý ảnh, quét virus hoặc gửi thông báo mà không ảnh hưởng đến trải nghiệm của người dùng.

## Kết luận

Đối với mình, đây không chỉ là một giải pháp upload file mà còn là một ví dụ điển hình về cách AWS thiết kế các hệ thống Serverless.

Thay vì để một thành phần xử lý mọi công việc, AWS khuyến khích chia nhỏ trách nhiệm cho từng dịch vụ và kết hợp chúng để tạo nên một kiến trúc linh hoạt, dễ mở rộng và tối ưu chi phí.

Nếu mọi người đang tìm hiểu về Amazon S3 hoặc xây dựng chức năng upload file trên AWS, mình nghĩ đây là một kiến trúc rất đáng tham khảo.

Cảm ơn mọi người đã dành thời gian đọc bài chia sẻ của mình. Nếu anh/chị hoặc các bạn đã từng triển khai giải pháp upload file trên AWS hoặc có kinh nghiệm thực tế về Presigned URL, mình rất mong được lắng nghe thêm những chia sẻ từ mọi người.

**Tài liệu tham khảo:** [Uploading to Amazon S3 directly from a web or mobile application](https://aws.amazon.com/blogs/compute/uploading-to-amazon-s3-directly-from-a-web-or-mobile-application/)
