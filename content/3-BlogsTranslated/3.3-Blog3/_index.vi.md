---
title: "Blog 3"
date: 2026-07-08
weight: 3
chapter: false
pre: " <b> 3.3. </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}

# Tối ưu hóa hạ tầng AWS vì sự phát triển bền vững (Sustainability), Phần III: Mạng (Networking)

Tối ưu hóa lớp mạng là một phần quan trọng khi thiết kế các kiến trúc đám mây bền vững trên AWS. Bằng cách giảm khoảng cách vật lý mà dữ liệu phải di chuyển và giảm thiểu kích thước tổng thể của dữ liệu được truyền tải, các tổ chức có thể giảm lượng tiêu thụ năng lượng và lượng khí thải carbon. Bài viết này trình bày các chiến lược chính để nâng cao hiệu quả hoạt động mạng vì sự phát triển bền vững.

---

## 1. Giảm thiểu quãng đường dữ liệu di chuyển cho mỗi yêu cầu

Hiệu quả truyền tải dữ liệu bị ảnh hưởng trực tiếp bởi đường dẫn định tuyến và khoảng cách. Các tổ chức nên hướng tới việc giữ dữ liệu ở local và xử lý dữ liệu gần hơn với người dùng.

- **Đọc local, Ghi toàn cầu (Read local, Write global):** Lựa chọn các Vùng AWS gần nhất với phần lớn người dùng của bạn. Đối với người dùng phân tán về mặt địa lý, hãy duy trì các bản sao dữ liệu chỉ đọc (ví dụ: sử dụng Amazon RDS cross-Region read replicas hoặc Amazon DynamoDB global tables).
- **Sử dụng mạng phân phối nội dung (CDN):** Amazon CloudFront lưu trữ bộ nhớ đệm của nội dung tĩnh tại các vị trí Edge toàn cầu, rút ngắn khoảng cách vật lý mà dữ liệu phải di chuyển từ máy chủ gốc.

<img src="https://d2908q01vomqb2.cloudfront.net/fc074d501302eb2b93e2554793fcaf50b3bf7291/2021/10/21/Figure-1.-Comparison-of-accessing-an-S3-bucket-directly-versus.jpg" alt="Figure 1. Comparison of accessing an S3 bucket directly versus via CloudFront" style="max-width:100%; border-radius: 8px; margin: 16px 0;" />

- **Tối ưu hóa tỷ lệ Cache Hit của CloudFront:** Tinh chỉnh các cài đặt chuyển tiếp header, query string và cookie để tối đa hóa số lần truy cập trúng cache, ngăn chặn các truy vấn vòng không cần thiết về origin.
- **Tận dụng các dịch vụ biên (Edge Services):** Sử dụng các tính năng tính toán tại biên như CloudFront Functions hoặc Lambda@Edge cho các tác vụ đơn giản (định tuyến, xử lý header) và AWS IoT Greengrass để tính toán biên cho các thiết bị IoT.

---

## 2. Giảm thiểu kích thước dữ liệu truyền tải

Giảm kích thước tải trọng (payload) trực tiếp giúp giảm lượng điện năng cần thiết để truyền các gói tin đi qua mạng.

- **Nén tệp dữ liệu khi truyền tải:** Kích hoạt tính năng nén tự động (như Gzip hoặc Brotli) trên CloudFront để nén các tài nguyên tĩnh trước khi gửi đi.
- **Nâng cao hiệu năng mạng Amazon EC2:** Kích hoạt Jumbo frames (MTU lên đến 9001 bytes) bên trong mạng VPC để tăng kích thước tải trọng gói tin và giảm thiểu tài nguyên xử lý mạng.
- **Tối ưu hóa các API:**
  - Nén tải trọng của REST API.
  - Chọn **Edge-optimized API endpoints** cho các máy khách phân tán địa lý toàn cầu.
  - Chọn **Regional API endpoints** cho các dịch vụ phụ trợ nằm trong cùng một vùng để tránh chi phí định tuyến bổ sung qua mạng toàn cầu.
  - Triển khai cache cho phản hồi API.

---

## 3. Giám sát các chỉ số mạng vì sự phát triển bền vững

Giám sát hành vi mạng giúp phát hiện các điểm nghẽn và các đường dẫn dữ liệu dư thừa. Các dịch vụ hỗ trợ bao gồm:
- **CloudFront Cache Hit Rate** trên CloudWatch metrics.
- **Amazon S3 Data Transfer** (Bytes In/Out).
- **Amazon EC2 Network Packets** (NetworkPacketsIn/NetworkPacketsOut).
- **AWS Trusted Advisor** để kiểm tra mức độ tối ưu hóa phân phối CloudFront và cấu hình forwarded headers.

<img src="https://d2908q01vomqb2.cloudfront.net/fc074d501302eb2b93e2554793fcaf50b3bf7291/2021/10/21/Figure-2.-Overview-of-services-that-integrate-with-CloudWatch-and-Trusted-Advisor-for-monitoring-metrics.jpg" alt="Figure 2. Overview of services that integrate with CloudWatch and Trusted Advisor" style="max-width:100%; border-radius: 8px; margin: 16px 0;" />
