---
title: "Các bài blogs đã dịch"
date: 2026-08-07
weight: 3
chapter: false
pre: " <b> 3. </b> "
---

{{% notice warning %}}  
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}

Tại đây sẽ là phần liệt kê, giới thiệu các blogs mà các bạn đã dịch. Ví dụ:

###  [Blog 1 - Sử dụng định tuyến dựa trên độ trễ với Amazon CloudFront cho kiến trúc đa vùng hoạt động song song](3.1-Blog1/)
Bài viết này tìm hiểu cách triển khai kiến trúc đa vùng hoạt động song song (multi-Region active-active) trên AWS bằng sự kết hợp giữa Amazon CloudFront và chính sách định tuyến dựa trên độ trễ của Amazon Route 53. Hướng dẫn thiết lập endpoint khu vực, chính sách định tuyến DNS, cấu hình CDN và chiến lược đồng bộ dữ liệu.
###  [Blog 2 - Cache dữ liệu giữa các Microservices trong kiến trúc Serverless](3.2-Blog2/)
Bài viết này phân tích các chiến lược triển khai cơ chế lưu đệm dữ liệu (caching) gần với lớp tính toán của serverless microservices. Nội dung bao gồm in-memory caching, sử dụng Lambda extensions, cache phân tán qua Amazon ElastiCache, và cache cấp cơ sở dữ liệu với DynamoDB Accelerator (DAX).
###  [Blog 3 - Tối ưu hóa hạ tầng AWS vì sự phát triển bền vững, Phần III: Mạng](3.3-Blog3/)
Bài viết này phân tích các nguyên tắc thiết kế mạng tối ưu trên AWS thân thiện với môi trường (sustainability). Trọng tâm bao gồm việc giảm quãng đường dữ liệu di chuyển thông qua các dịch vụ ở biên như Amazon CloudFront và CloudFront Functions, giảm kích thước gói tin nhờ cơ chế nén dữ liệu, Jumbo frames, và theo dõi hiệu năng hệ thống qua Amazon CloudWatch.