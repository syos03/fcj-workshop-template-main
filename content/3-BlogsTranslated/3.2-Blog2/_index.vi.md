---
title: "Blog 2"
date: 2026-08-07
weight: 2
chapter: false
pre: " <b> 3.2. </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}

# Cache dữ liệu giữa các Microservices trong kiến trúc Serverless

Các tổ chức đang chuyển dịch các ứng dụng nguyên khối (monolith) truyền thống sang microservices để đạt được sự linh hoạt và khả năng mở rộng. Do mỗi microservice đảm nhận một chức năng duy nhất, chúng thường phải truy xuất và xử lý dữ liệu từ nhiều nguồn khác nhau (kho lưu trữ dữ liệu, hệ thống cũ hoặc cơ sở dữ liệu on-premises). Việc truy vấn trực tiếp theo thời gian thực làm tăng đáng kể độ trễ. Triển khai một lớp đệm (cache) gần với lớp tính toán serverless (AWS Lambda) giúp giảm độ trễ và giảm thiểu việc giao tiếp trực tiếp giữa các microservices.

---

## Kịch bản 1: Caching theo nhu cầu (On-Demand) để giảm các cuộc gọi thời gian thực

Trong kịch bản này, mô hình **Cache-Aside (Lazy Loading)** được áp dụng. Dữ liệu chỉ được lưu vào cache khi người dùng yêu cầu và microservice sẽ quyết định xem đối tượng đó có cần lưu lại hay không.

### Quy trình hoạt động thực tế
1. **Tiếp nhận yêu cầu:** Microservice Hóa đơn (Billing) nhận yêu cầu và kiểm tra cache bằng `object_key`. Nếu dữ liệu tồn tại (cache hit), hệ thống trả kết quả ngay lập tức.
2. **Xử lý khi Cache Miss:** Nếu dữ liệu chưa có trong cache (cache miss), dịch vụ Billing sẽ gọi trực tiếp đến các nguồn dữ liệu backend, tổng hợp kết quả, trả về cho người dùng và lưu kết quả đó vào cache kèm theo thời gian tồn tại (TTL) xác định.
3. **Thu hồi Cache (Cache Invalidation):** Khi khách hàng thực hiện thanh toán qua microservice Thanh toán (Payment), số dư cũ trong cache sẽ bị lỗi thời. Dịch vụ Payment sẽ đẩy một sự kiện bất đồng bộ `payment_processed` lên Event Store.
4. **Cập nhật từ Cache Manager:** Microservice quản lý cache (CacheManager) lắng nghe sự kiện này và thực hiện xóa/cập nhật lại bản ghi tương ứng trong cache.

<img src="https://d2908q01vomqb2.cloudfront.net/fc074d501302eb2b93e2554793fcaf50b3bf7291/2021/07/14/Figure-1.-Reducing-latency-by-caching-frequently-accessed-data-on-demand.png" alt="Figure 1. Reducing latency by caching frequently accessed data on demand" style="max-width:100%; border-radius: 8px; margin: 16px 0;" />

### Kiến trúc AWS đề xuất
- **API Gateway:** Cung cấp các endpoint API cho bên ngoài.
- **AWS Lambda:** Đảm nhiệm xử lý logic nghiệp vụ (lớp tính toán).
- **Amazon ElastiCache:** Bộ nhớ đệm phân tán trong bộ nhớ (in-memory) có tốc độ cao.
- **Amazon EventBridge:** Điều phối các sự kiện nghiệp vụ bất đồng bộ.

<img src="https://d2908q01vomqb2.cloudfront.net/fc074d501302eb2b93e2554793fcaf50b3bf7291/2021/07/14/Figure-2.-Suggested-AWS-services-for-implementing-use-case-1.png" alt="Figure 2. Suggested AWS services for implementing use case 1" style="max-width:100%; border-radius: 8px; margin: 16px 0;" />

---

## Kịch bản 2: Caching chủ động (Proactive Caching) cho lượng dữ liệu lớn

Trong quá trình di chuyển và hiện đại hóa hệ thống, một số hệ thống backend cũ (như Mainframe) chạy bằng các tiến trình xử lý theo lô (batch jobs) định kỳ và không thể đáp ứng được tần suất gọi API liên tục từ ứng dụng hiện đại ở frontend. Dữ liệu cần thiết sẽ được xác định trước và tải chủ động vào hệ thống cache.

### Quy trình hoạt động thực tế
1. **Nạp dữ liệu ban đầu & CDC:** Một tiến trình tự động nạp dữ liệu ban đầu vào cache. Các thay đổi tiếp theo ở hệ thống lưu trữ gốc được cập nhật vào cache thông qua một đường dẫn CDC (Change Data Capture) tự động.
2. **Truy cập trực tiếp từ Cache:** Các microservices đọc dữ liệu trực tiếp từ cache đã được nạp sẵn thay vì gọi thời gian thực xuống backend cũ.
3. **Cập nhật theo yêu cầu:** Nếu có thay đổi do các giao dịch mới, microservice ghi trực tiếp xuống hệ thống lưu trữ gốc và phát đi sự kiện. Dịch vụ CacheManager sẽ kích hoạt làm mới lại phần dữ liệu bị ảnh hưởng.

<img src="https://d2908q01vomqb2.cloudfront.net/fc074d501302eb2b93e2554793fcaf50b3bf7291/2021/07/14/Figure-3.-Eliminating-real-time-calls-by-caching-massive-data-volumes-proactively.png" alt="Figure 3. Eliminating real-time calls by caching massive data volumes proactively" style="max-width:100%; border-radius: 8px; margin: 16px 0;" />

### Kiến trúc AWS đề xuất
- **Amazon DynamoDB:** Cơ sở dữ liệu NoSQL cung cấp khả năng truy xuất với độ trễ thấp ở mọi quy mô.
- **Amazon DynamoDB Accelerator (DAX):** Bộ nhớ đệm trong bộ nhớ được quản lý hoàn toàn nằm trước DynamoDB, giúp nâng cao hiệu năng đọc lên gấp 10 lần (độ trễ giảm xuống mức micro-giây).

<img src="https://d2908q01vomqb2.cloudfront.net/fc074d501302eb2b93e2554793fcaf50b3bf7291/2021/07/14/Figure-4.-Suggested-AWS-services-for-implementing-use-case-2.png" alt="Figure 4. Suggested AWS services for implementing use case 2" style="max-width:100%; border-radius: 8px; margin: 16px 0;" />

---

## Các phương pháp tối ưu độ trễ bổ sung cho Lambda
- **Tái sử dụng môi trường thực thi (Execution Environment Reuse):** Khai báo các cấu hình tĩnh và biến dữ liệu bên ngoài hàm xử lý (handler code) của Lambda để tận dụng lưu lại trạng thái giữa các lần khởi động ấm (warm starts).
- **AWS Lambda Extensions:** Chạy các tiến trình phụ song song với tiến trình chính của Lambda để quản lý cache, đọc cấu hình hoặc lưu trữ khóa bảo mật.
