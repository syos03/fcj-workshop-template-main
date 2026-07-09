---
title: "Worklog Tuần 12"
date: 2024-01-01
weight: 12
chapter: false
pre: " <b> 1.12. </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}


### Mục tiêu tuần 12:

* Cấu hình giám sát hoạt động và cảnh báo qua Amazon CloudWatch và Amazon SNS.
* Chạy kiểm thử toàn trình hệ thống (End-to-End Testing) theo các kịch bản lỗi thực tế.
* Hoàn thiện tài liệu và chính thức nộp báo cáo thực tập tốt nghiệp vào ngày 08/07/2026.

### Các công việc cần triển khai trong tuần này:
| Day | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | :---: | :---: | --- |
| 78 | Cấu hình AWS Lambda đẩy logs và metrics tự động về Amazon CloudWatch Logs. | 03/07/2026 | 03/07/2026 |  |
| 79 | Thiết lập CloudWatch Alarms để theo dõi các ngưỡng lỗi cảm biến xe (quá nhiệt động cơ). | 04/07/2026 | 04/07/2026 |  |
| 80 | Khởi tạo Topic trên Amazon SNS và liên kết với CloudWatch Alarm để tự động kích hoạt thông báo Email. | 05/07/2026 | 05/07/2026 |  |
| 81 | Chạy thử nghiệm E2E kịch bản lỗi quá nhiệt động cơ (>105°C) để chẩn đoán bằng AI và nhận mail SNS. | 06/07/2026 | 06/07/2026 |  |
| 82 | Rà soát bảo mật phân quyền IAM Roles, xử lý lỗi CORS trên các endpoint API Gateway. | 07/07/2026 | 07/07/2026 |  |
| 83 | Chính thức nộp Báo cáo thực tập tốt nghiệp và bàn giao mã nguồn cho đơn vị thực tập. | 08/07/2026 | 08/07/2026 |  |
| 84 | Thực hiện dọn dẹp (Cleanup) các tài nguyên đã cấu hình trên AWS và tổng kết quá trình thực tập. | 09/07/2026 | 09/07/2026 |  |


### Kết quả đạt được tuần 12:

* Thiết lập thành công hệ thống giám sát CloudWatch Logs/Alarms và cơ chế gửi email cảnh báo tự động qua Amazon SNS.
* Kiểm thử toàn hệ thống (E2E Test) chạy ổn định và đạt hiệu năng phản hồi tốt.
* Đóng gói mã nguồn sạch, bảo mật phân quyền IAM Roles đầy đủ.
* Nộp báo cáo thực tập tốt nghiệp thành công vào ngày 08/07/2026 và tiến hành cleanup tài nguyên đám mây.
