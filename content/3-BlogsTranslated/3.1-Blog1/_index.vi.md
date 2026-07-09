---
title: "Blog 1"
date: 2026-07-08
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}

# Sử dụng định tuyến dựa trên độ trễ với Amazon CloudFront cho kiến trúc đa vùng hoạt động song song (Multi-Region Active-Active)

Triển khai kiến trúc ứng dụng đa vùng hoạt động song song (Multi-Region Active-Active) trên AWS giúp mang lại tính sẵn sàng cao, khả năng khôi phục sau thảm họa và độ trễ thấp cho người dùng toàn cầu. Trong kiến trúc này, cơ chế định tuyến dựa trên độ trễ (latency-based routing) của Amazon Route 53 sẽ kết hợp với Amazon CloudFront để điều hướng yêu cầu đến nguồn (origin) ứng dụng gần nhất và đang hoạt động ổn định.

---

## Tổng quan về mô hình kiến trúc

Một mô hình phổ biến cho các ứng dụng đa vùng hoạt động song song là sử dụng Amazon CloudFront làm CDN toàn cầu và bộ tăng tốc API, kết hợp với Amazon Route 53 để quản lý định tuyến ở cấp độ DNS đến các nguồn tài nguyên vùng dựa trên độ trễ và kết quả kiểm tra sức khỏe (health checks).

- **Điểm truy cập toàn cầu (CloudFront):** Một phân phối CloudFront duy nhất hoạt động như điểm truy cập cho cả yêu cầu tĩnh và động. Người dùng kết nối đến vị trí biên (Edge location) của CloudFront gần nhất.
- **Định tuyến nguồn động (Route 53):** Khi CloudFront chuyển tiếp các yêu cầu động (ví dụ: API) đến nguồn (origin), Route 53 sẽ phân giải tên miền tùy chỉnh của origin thành endpoint của vùng gần nhất (chẳng hạn như Application Load Balancer hoặc API Gateway) bằng cách sử dụng chính sách định tuyến dựa trên độ trễ (Latency-Based Routing).
- **Cơ chế tự động chuyển vùng khi có sự cố (Failover):** Các health checks của Route 53 liên tục giám sát các endpoint của vùng. Nếu một vùng gặp sự cố, Route 53 sẽ tự động cập nhật bản ghi DNS để chuyển hướng lưu lượng sang vùng hoạt động bình thường có độ trễ thấp tiếp theo.

---

## Các thành phần cốt lõi và các bước triển khai

### 1. Endpoint ứng dụng đa vùng
Triển khai các tài nguyên ứng dụng giống nhau ở nhiều Vùng AWS (ví dụ: `us-east-1` và `eu-west-1`). Mỗi vùng cần có:
- **Application Load Balancer (ALB) hoặc API Gateway** để tiếp nhận lưu lượng truy cập.
- **Tài nguyên tính toán** (EC2, ECS, hoặc Lambda).
- **Chứng chỉ SSL/TLS** được yêu cầu qua AWS Certificate Manager (ACM) tại từng vùng hoạt động để bảo mật kết nối.

### 2. Cấu hình DNS với Amazon Route 53
Thiết lập các bản ghi Route 53 để điều phối lưu lượng bằng chính sách định tuyến độ trễ (Latency Routing Policies):
- Tạo một Hosted Zone public cho tên miền của bạn.
- Tạo các bản ghi **A** hoặc **AAAA** dựa trên độ trễ cho tên miền phụ của origin (ví dụ: `api.example.com`).
- Cấu hình health check cho từng endpoint vùng và liên kết chúng với các bản ghi DNS tương ứng.

### 3. Thiết lập phân phối Amazon CloudFront
Cấu hình CDN toàn cầu để truyền tải dữ liệu:
- Đặt Origin Domain của phân phối CloudFront thành tên miền phụ của origin (`api.example.com`).
- Cấu hình các hành vi bộ nhớ đệm (caching behaviors) động, chuyển tiếp các header, query string và cookie cần thiết về origin.
- Liên kết chứng chỉ tên miền tùy chỉnh (được quản lý trong ACM ở vùng `us-east-1`) với phân phối CloudFront.

### 4. Lớp nhất quán dữ liệu (Data Consistency Layer)
Kiến trúc active-active yêu cầu đồng bộ hóa dữ liệu giữa các vùng. Bạn có thể sử dụng:
- **Amazon DynamoDB Global Tables** để đồng bộ hóa cơ sở dữ liệu NoSQL đa vùng tự động.
- **Amazon Aurora Global Database** để đồng bộ dữ liệu quan hệ với độ trễ cực thấp.

---

## Lợi ích và Đánh giá đánh đổi

| Tiêu chí | Mô tả chi tiết |
| :--- | :--- |
| **Độ trễ tối thiểu** | Người dùng được phục vụ bởi Edge CloudFront gần nhất và origin AWS đang hoạt động có độ trễ thấp nhất. |
| **Tính sẵn sàng cao** | Tự động chuyển hướng lưu lượng khỏi vùng bị lỗi chỉ trong vòng vài phút nhờ tích hợp Route 53 Health Checks. |
| **Độ phức tạp vận hành** | Đòi hỏi việc thiết kế lớp dữ liệu đồng bộ đa vùng phức tạp và xử lý xung đột ghi dữ liệu (write conflicts). |
| **Chi phí** | Việc triển khai đa vùng sẽ làm nhân đôi chi phí tài nguyên và phát sinh thêm phí chuyển dữ liệu giữa các vùng (cross-region data transfer). |
