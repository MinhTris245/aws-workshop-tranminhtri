---
title: "Blog 1"
date: 2026-07-01
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

# Giám sát bảo mật Amazon S3 không cần xây pipeline

## Cách CloudWatch biến Access Log thành dashboard bảo mật hoàn chỉnh

Sau khi nghiên cứu tài liệu từ AWS Cloud Operations Blog về cách tích hợp Amazon S3 Server Access Logs với Amazon CloudWatch Logs, mình xin chia sẻ những điểm cốt lõi để cộng đồng cùng tham khảo.

![Luồng giám sát bảo mật S3 với CloudWatch](/images/blog1-s3-cloudwatch-flow.svg)

## 1. Vai trò và bối cảnh nghiên cứu

Amazon S3 Server Access Logs ghi lại chi tiết các request gửi đến bucket S3, gồm request thành công hoặc thất bại, có xác thực hoặc ẩn danh. Dữ liệu chứa hơn 25 trường ở tầng HTTP như requester, IP nguồn, loại xác thực, thao tác, dung lượng truyền tải, phiên bản TLS và cấu hình mã hóa.

Đây là một trong hai nguồn dữ liệu bổ trợ cho giám sát tầng dữ liệu S3. Nguồn còn lại là AWS CloudTrail data events, ghi nhận thao tác cấp object như GetObject, PutObject và DeleteObject cùng ngữ cảnh IAM chi tiết.

Trước đây, để khai thác access log, đội ngũ vận hành thường phải quản lý bucket đích, xây pipeline phân tích tùy chỉnh, kết nối công cụ cảnh báo và xử lý lifecycle cho hàng triệu file log nhỏ.

## 2. Các điểm nổi bật về kỹ thuật

S3 Server Access Logs có thể trở thành nguồn dữ liệu gốc của CloudWatch thông qua Vended Logs, giảm nhu cầu tự xây ETL hoặc quản lý bucket log riêng.

- **Tự động chuyển đổi:** CloudWatch chuyển log văn bản thành JSON có cấu trúc mà không cần tự viết logic parse.
- **Telemetry Enablement Rules:** Bật thu thập log ở cấp organization, organizational unit hoặc account và có thể lọc theo tag.
- **CloudWatch Logs Insights:** Truy vấn các trường như remote_ip, http_status và bytes_sent_size để tìm hành vi bất thường.
- **Metric Filters và Alarms:** Chuyển mẫu log thành metric và cảnh báo khi lỗi 403/404, lỗi 5xx hoặc request ẩn danh vượt ngưỡng.
- **Contributor Insights:** Xếp hạng IP, requester hoặc bucket có hoạt động nhiều nhất.
- **CloudWatch Pipelines:** Chuẩn hóa log sang OCSF để tích hợp với công cụ bảo mật và data lake.
- **Logs Centralization:** Tập trung log từ nhiều account và Region về một account giám sát, đồng thời giữ thông tin nguồn.

## 3. Ứng dụng trong thực tế

### Dashboard bảo mật dựng sẵn

AWS cung cấp CloudFormation template để triển khai dashboard tổng hợp:

- Tổng số request, lỗi và request ẩn danh.
- Truy cập bị từ chối và các IP tạo nhiều lỗi 403/404.
- Dấu hiệu tải xuống bất thường hoặc rò rỉ dữ liệu.
- Hoạt động xóa hàng loạt.
- Mức độ tuân thủ TLS và mã hóa.
- Hoạt động lifecycle và sự kiện chi tiết phục vụ điều tra.

### Phát hiện truy cập trái phép

Tổng hợp lỗi 403/404 theo IP giúp phát hiện hành vi dò quét object key, truy cập sai lặp lại hoặc brute-force.

### Phát hiện rò rỉ dữ liệu

Tổng hợp dung lượng tải xuống theo requester và IP giúp nhận diện phiên tải dữ liệu bất thường, có thể liên quan đến thông tin xác thực bị lộ.

### Cảnh báo chủ động

Đội ngũ vận hành định nghĩa pattern một lần bằng Metric Filters. CloudWatch theo dõi log mới và kích hoạt alarm khi điều kiện vượt ngưỡng.

### Tối ưu chi phí

S3 access log đưa vào CloudWatch được tính theo mô hình Vended Logs với mức giá giảm dần theo khối lượng dữ liệu.

## 4. Khả năng mở rộng

- Enablement Rules hỗ trợ organization, OU, account và lọc theo tag.
- Dashboard mẫu hỗ trợ định dạng log tiêu chuẩn của AWS và OCSF.
- Log đa account, đa Region có thể được tập trung để điều tra.
- Có thể xem S3 access log cùng CloudTrail, VPC Flow Logs và application logs để tạo chiến lược phòng thủ theo chiều sâu.

## 5. Hạn chế và lưu ý

- S3 Server Access Logs được giao theo cơ chế best-effort; phần lớn bản ghi có thể đến trong vòng vài giờ nên không phải nguồn thời gian thực tuyệt đối.
- Access log có dữ liệu tầng HTTP nhưng không đầy đủ ngữ cảnh IAM như CloudTrail data events. Nên kết hợp cả hai.
- Cần kiểm tra đúng organization, OU, account, Region và tag trong enablement rule.
- Chi phí thu thập và lưu trữ tăng theo lượng log.
- Cần xóa enablement rule, metric filter, Contributor Insights rule và CloudFormation stack không còn sử dụng.

## Kết luận

Đưa Amazon S3 Server Access Logs thành nguồn dữ liệu gốc của CloudWatch giúp đơn giản hóa giám sát bảo mật S3. Không cần tự xây pipeline ETL và quản lý bucket log riêng, đội ngũ bảo mật có thể chuyển từ log thô sang dashboard giám sát, cảnh báo, tuân thủ và kiểm toán.

**Tài liệu gốc:** [Using Amazon S3 Server Access Logs with Amazon CloudWatch Logs — AWS Cloud Operations Blog](https://aws.amazon.com/blogs/mt/using-amazon-s3-server-access-logs-with-amazon-cloudwatch-logs/)

