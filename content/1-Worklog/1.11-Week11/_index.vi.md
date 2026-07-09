---
title: "Worklog Tuần 11"
date: 2024-01-01
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}


### Mục tiêu tuần 11:

* Hosting Web Dashboard lên Amazon S3 tĩnh và cấu hình CDN phân phối Amazon CloudFront.
* Tích hợp Amazon Cognito xác thực JWT và bảo vệ API trên Amazon API Gateway.
* Lập trình AWS Lambda (API Handler), tích hợp Google Gemini AI và hoàn tất lập trình.

### Các công việc cần triển khai trong tuần này:
| Day | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | :---: | :---: | --- |
| 71 | Triển khai giao diện tĩnh Web Dashboard lên Amazon S3 và cấu hình Static Website Hosting. | 26/06/2026 | 26/06/2026 |  |
| 72 | Cấu hình CDN Amazon CloudFront phân phối trang web và bảo mật S3 Origin bằng OAC. | 27/06/2026 | 27/06/2026 |  |
| 73 | Khởi tạo User Pool trên Amazon Cognito để xử lý đăng ký, đăng nhập và cấp JWT Token. | 28/06/2026 | 28/06/2026 |  |
| 74 | Thiết lập Amazon API Gateway, tích hợp Cognito Authorizer bảo mật các endpoint truy xuất. | 29/06/2026 | 29/06/2026 |  |
| 75 | Lập trình AWS Lambda (API Handler) thực hiện truy vấn và cập nhật dữ liệu DynamoDB. | 30/06/2026 | 30/06/2026 |  |
| 76 | Tích hợp Google Gemini AI vào Lambda API Handler để trả về tư vấn chẩn đoán sự cố cho tài xế. | 01/07/2026 | 01/07/2026 |  |
| 77 | Hoàn tất lập trình các tính năng, kết nối Dashboard với API Gateway và chuyển sang chạy thử nghiệm. | 02/07/2026 | 02/07/2026 |  |


### Kết quả đạt được tuần 11:

* Host thành công Web Dashboard tĩnh trên S3 kết hợp mạng phân phối tối ưu CloudFront CDN.
* Triển khai hệ thống xác thực người dùng Cognito JWT và bảo mật API Gateway thành công.
* Tích hợp thành công cụm Lambda API Handler kết nối DynamoDB và chẩn đoán sự cố qua Gemini AI.
* Hoàn thành 100% việc viết mã nguồn phát triển hệ thống và bắt đầu giai đoạn kiểm thử.
