---
title: "Worklog Tuần 6"
date: 2026-05-22
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}


### Mục tiêu tuần 6:

* Tìm hiểu các dịch vụ lưu trữ dữ liệu nâng cao trên EC2 và cơ chế mở rộng Auto Scaling.
* Nghiên cứu mô hình bảo mật dùng chung Shared Responsibility Model của AWS.
* Tìm hiểu công cụ quản lý thư mục người dùng Amazon Cognito và giám sát hệ thống.

### Các công việc cần triển khai trong tuần này:
| Day | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | :---: | :---: | --- |
| 36 | Khảo sát vai trò của Amazon Machine Image (AMI) và lập lịch backup dữ liệu bằng AWS Backup. | 22/05/2026 | 22/05/2026 | [FCAJ Playlist](https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i) |
| 37 | So sánh lưu trữ khối Amazon EBS Volume (Persistence) và Instance Store (Ephemeral) trên máy chủ. | 23/05/2026 | 23/05/2026 | [FCAJ Playlist](https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i) |
| 38 | Nghiên cứu giải pháp tệp tin chia sẻ Amazon EFS và cấu hình tự động co giãn EC2 Auto Scaling. | 24/05/2026 | 24/05/2026 | [FCAJ Playlist](https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i) |
| 39 | Phân tích nguyên tắc phân chia trách nhiệm bảo mật thông qua Shared Responsibility Model. | 25/05/2026 | 25/05/2026 | [FCAJ Playlist](https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i) |
| 40 | Tìm hiểu Amazon Cognito để xây dựng hồ sơ người dùng ứng dụng và phát hành JWT Token. | 26/05/2026 | 26/05/2026 | [FCAJ Playlist](https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i) |
| 41 | Nghiên cứu công cụ AWS Security Hub và thu thập log lịch sử gọi API thông qua CloudTrail. | 27/05/2026 | 27/05/2026 | [FCAJ Playlist](https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i) |
| 42 | Thực hành tạo IAM Role cho Lambda để gán quyền đọc ghi an toàn sang DynamoDB và SQS. | 28/05/2026 | 28/05/2026 | [FCAJ Playlist](https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i) |


### Kết quả đạt được tuần 6:

* Nắm rõ cách tối ưu tài nguyên lưu trữ máy chủ ảo bằng EBS, EFS và nhóm co giãn Auto Scaling.
* Hiểu sâu sắc ranh giới bảo mật hạ tầng đám mây theo tiêu chuẩn Shared Responsibility.
* Ứng dụng thành công Cognito trong xác thực định danh và ghi log vết hệ thống bằng CloudTrail.
