---
title: "Worklog Tuần 5"
date: 2026-05-15
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}


### Mục tiêu tuần 5:

* Tìm hiểu tư duy phát triển Serverless trên nền tảng AWS.
* Sử dụng dịch vụ AWS Lambda kết hợp API Gateway cấu hình các REST API.
* Khảo sát dịch vụ hàng đợi Amazon SQS, dịch vụ SNS và cơ sở dữ liệu NoSQL Amazon DynamoDB.

### Các công việc cần triển khai trong tuần này:
| Day | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | :---: | :---: | --- |
| 29 | Nghiên cứu ưu điểm của kiến trúc Serverless và cơ chế hoạt động của AWS Lambda. | 15/05/2026 | 15/05/2026 | [FCAJ Playlist](https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i) |
| 30 | Tìm hiểu ứng dụng của Message Queue thông qua dịch vụ Amazon SQS trong lập trình bất đồng bộ. | 16/05/2026 | 16/05/2026 | [FCAJ Playlist](https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i) |
| 31 | Thực hành viết Lambda Function và gán SQS làm sự kiện Trigger tự động thực thi hàm. | 17/05/2026 | 17/05/2026 | [FCAJ Playlist](https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i) |
| 32 | Nghiên cứu giải pháp thông báo Amazon SNS theo cơ chế truyền phát Pub/Sub Event. | 18/05/2026 | 18/05/2026 | [FCAJ Playlist](https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i) |
| 33 | Tìm hiểu CSDL NoSQL Amazon DynamoDB, cách thiết kế cấu trúc Primary Key và Sort Key. | 19/05/2026 | 19/05/2026 | [FCAJ Playlist](https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i) |
| 34 | Triển khai luồng API Serverless hoàn chỉnh: API Gateway tiếp nhận gọi Lambda cập nhật database DynamoDB. | 20/05/2026 | 20/05/2026 | [FCAJ Playlist](https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i) |
| 35 | Kiểm thử tích hợp chuỗi API Serverless và dọn dẹp các tài nguyên Lab tránh phát sinh phí. | 21/05/2026 | 21/05/2026 | [FCAJ Playlist](https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i) |


### Kết quả đạt được tuần 5:

* Hiểu rõ cơ chế vận hành của mô hình điện toán phi máy chủ Serverless trên AWS.
* Triển khai hoàn chỉnh API Serverless: Client -> API Gateway -> Lambda -> DynamoDB.
* Có kinh nghiệm cấu hình hàng đợi SQS và dịch vụ notification SNS trong các luồng xử lý bất đồng bộ.
