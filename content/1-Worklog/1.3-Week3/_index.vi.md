---
title: "Worklog Tuần 3"
date: 2026-05-01
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}


### Mục tiêu tuần 3:

* Kiến thiết hạ tầng mạng ảo biệt lập an toàn bằng Amazon VPC.
* Phân vùng địa chỉ IP qua Subnet và thiết lập các Route Table định tuyến.
* Cấu hình tường lửa lớp mạng bằng Security Group và Network ACL (NACL).

### Các công việc cần triển khai trong tuần này:
| Day | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | :---: | :---: | --- |
| 15 | Nghiên cứu nguyên lý hoạt động của mạng nội bộ ảo Amazon VPC và dải CIDR Block. | 05/01/2026 | 05/01/2026 | [FCAJ Playlist](https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i) |
| 16 | Tìm hiểu cơ chế bảo mật mạng đa lớp với Security Group (Stateful) và Network ACL (Stateless). | 05/02/2026 | 05/02/2026 | [FCAJ Playlist](https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i) |
| 17 | Khảo sát các giải pháp kết nối mạng mở rộng: Elastic Load Balancer (ELB), VPN và AWS Direct Connect. | 05/03/2026 | 05/03/2026 | [FCAJ Playlist](https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i) |
| 18 | Khởi tạo một VPC tùy chỉnh, phân chia các mạng con thành Public Subnet và Private Subnet. | 05/04/2026 | 05/04/2026 | [FCAJ Playlist](https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i) |
| 19 | Tạo và gắn Internet Gateway (IGW), thiết lập Route Table để cấp quyền ra internet cho Public Subnet. | 05/05/2026 | 05/05/2026 | [FCAJ Playlist](https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i) |
| 20 | Triển khai NAT Gateway tại Public Subnet để hỗ trợ Private Subnet truy cập outbound an toàn. | 05/06/2026 | 05/06/2026 | [FCAJ Playlist](https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i) |
| 21 | Thiết lập và kiểm thử các quy tắc firewall trên Security Group/NACL để kiểm soát lưu lượng. | 05/07/2026 | 05/07/2026 | [FCAJ Playlist](https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i) |


### Kết quả đạt được tuần 3:

* Khởi tạo thành công VPC biệt lập phục vụ các kiến trúc kết nối đám mây an toàn.
* Thiết lập hệ thống định tuyến thông lượng ổn định bằng Route Table, NAT và Internet Gateway.
* Cấu hình phân tầng bảo mật chặt chẽ cho máy chủ bằng cơ chế Stateful Security Group và Stateless NACL.
