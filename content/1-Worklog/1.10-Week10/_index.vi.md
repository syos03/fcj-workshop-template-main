---
title: "Worklog Tuần 10"
date: 2024-01-01
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}


### Mục tiêu tuần 10:

* Triển khai luồng thu thập dữ liệu IoT Telemetry sử dụng dịch vụ AWS IoT Core.
* Tích hợp hàng đợi Amazon SQS để trung chuyển dữ liệu, chống mất mát tin nhắn.
* Lập trình AWS Lambda (Telemetry Processor) xử lý dữ liệu và lưu vào Amazon DynamoDB.

### Các công việc cần triển khai trong tuần này:
| Day | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | :---: | :---: | --- |
| 64 | Thiết lập AWS IoT Core, khởi tạo Thing đại diện cho xe và cấu hình X.509 Certificate bảo mật. | 19/06/2026 | 19/06/2026 |  |
| 65 | Xây dựng chương trình giả lập Vehicle Simulator truyền dữ liệu telemetry qua giao thức MQTT. | 20/06/2026 | 20/06/2026 |  |
| 66 | Cấu hình AWS IoT Rule Engine để tự động bắt các bản tin MQTT từ thiết bị gửi lên. | 21/06/2026 | 21/06/2026 |  |
| 67 | Khởi tạo hàng đợi Amazon SQS (Standard Queue) để nhận và lưu trữ tạm thời các telemetry message. | 22/06/2026 | 22/06/2026 |  |
| 68 | Lập trình hàm AWS Lambda (Telemetry Processor) bóc tách dữ liệu xe thô nhận từ hàng đợi SQS. | 23/06/2026 | 23/06/2026 |  |
| 69 | Thiết lập liên kết SQS làm Event Source Trigger cho Lambda Processor xử lý theo Batch. | 24/06/2026 | 24/06/2026 |  |
| 70 | Viết logic cho Lambda ghi nhận dữ liệu xe và cập nhật trạng thái mới nhất vào Amazon DynamoDB. | 25/06/2026 | 25/06/2026 |  |


### Kết quả đạt được tuần 10:

* Triển khai thành công luồng IoT Telemetry truyền dữ liệu an toàn từ Simulator lên AWS IoT Core.
* Tích hợp thành công hàng đợi SQS trung chuyển dữ liệu và AWS Lambda tự động xử lý.
* Lưu trữ thành công dữ liệu hành trình cảm biến xe trên cơ sở dữ liệu Amazon DynamoDB.
