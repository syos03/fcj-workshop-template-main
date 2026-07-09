---
title: "Worklog Tuần 7"
date: 2026-05-29
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}


### Mục tiêu tuần 7:

* Quản lý lưu trữ đối tượng dung lượng lớn an toàn bằng Amazon S3.
* Cấu hình lưu trữ Static Website Hosting để deploy mã nguồn giao diện Frontend.
* Thiết lập CDN Amazon CloudFront để phân phối nội dung tĩnh tối ưu hóa hiệu năng.

### Các công việc cần triển khai trong tuần này:
| Day | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | :---: | :---: | --- |
| 43 | Nghiên cứu phân nhóm lưu trữ Amazon S3 Storage Class để tối ưu vòng đời dữ liệu. | 29/05/2026 | 29/05/2026 | [FCAJ Playlist](https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i) |
| 44 | Khởi tạo S3 Bucket và cấu hình tường lửa chặn truy cập công cộng Public Access Block. | 30/05/2026 | 30/05/2026 | [FCAJ Playlist](https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i) |
| 45 | Cấu hình tính năng S3 Static Website Hosting để host các mã nguồn web tĩnh (HTML/CSS). | 31/05/2026 | 31/05/2026 | [FCAJ Playlist](https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i) |
| 46 | Thiết lập CORS policy trên S3 để kiểm soát việc chia sẻ tài nguyên giữa các domain. | 01/06/2026 | 01/06/2026 | [FCAJ Playlist](https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i) |
| 47 | Triển khai CDN Amazon CloudFront phân phối tệp tin từ S3 tới người dùng toàn cầu với độ trễ thấp. | 02/06/2026 | 02/06/2026 | [FCAJ Playlist](https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i) |
| 48 | Cấu hình Origin Access Control (OAC) để bảo mật S3, chặn hoàn toàn truy cập trực tiếp ngoài CDN. | 03/06/2026 | 03/06/2026 | [FCAJ Playlist](https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i) |
| 49 | Kiểm thử truy xuất web tĩnh qua CloudFront và dọn dẹp các tệp tin lưu trữ thử nghiệm. | 04/06/2026 | 04/06/2026 | [FCAJ Playlist](https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i) |


### Kết quả đạt được tuần 7:

* Triển khai lưu trữ tĩnh an toàn trên Amazon S3 và phân phối tài nguyên tối ưu.
* Host thành công mã nguồn Frontend trên S3 kết hợp bảo vệ truy cập qua CloudFront OAC.
* Nắm vững các khái niệm cấu hình CORS, Bucket Policy và quản lý vòng đời tệp tin.
