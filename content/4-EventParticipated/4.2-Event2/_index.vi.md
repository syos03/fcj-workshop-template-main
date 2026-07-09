---
title: "Event 2"
date: 2026-05-30
weight: 2
chapter: false
pre: " <b> 4.2. </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}

# Bài thu hoạch "FCAJ Community Meetup - 30/05/2026"

### Mục Đích Của Sự Kiện

- Học hỏi các kinh nghiệm thực tế về phát triển và nâng cao năng lực AWS thông qua game hóa và công cụ mô phỏng.
- Phân tích và thấu hiểu nguyên lý tâm lý học đứng sau thói quen trì hoãn trong công việc và dự án.
- Nghiên cứu tầm quan trọng của yếu tố Con người, Quy trình và Công nghệ trong việc vận hành văn hóa DevOps.
- Tìm hiểu các kinh nghiệm xây dựng ứng dụng AI thần tốc trong 36 giờ từ các đội ngũ tham gia các kỳ Hackathon thực tế.

### Danh Sách Diễn Giả

- **Huỳnh Thái Linh** - DevOps Engineer
- **Phạm Khắc Uy** - Sinh viên năm 3, Đại học Việt Đức (VGU)
- **Nguyễn Thị Quỳnh Như** - Thành viên chương trình FCAJ
- **Phạm Quang Thái** - Game Backend & Cloud Engineer
- **Trần Hữu Nghĩa** - Software Engineer & Product Builder
- **Trần Minh Quân** - DevOps Architect & Cloud Specialist
- **Team The Ballers** (Huỳnh An Khương, Mai Quốc Anh, Nguyễn Trần Minh Quân) - Đội thi Hackathon

### Nội Dung Nổi Bật

#### Nâng cao kỹ năng AWS với Cloud Quest và Floci (Huỳnh Thái Linh)
- Phân tích rào cản khi tiếp cận AWS thực tế (chi phí cao, tài nguyên phức tạp, giao diện nhiều nút bấm).
- Giới thiệu **AWS Cloud Quest**: Nền tảng học AWS theo mô hình game 3D trực quan, giúp tăng cường tương tác thực tế.
- Giới thiệu **Floci**: Công cụ mã nguồn mở giả lập môi trường AWS cục bộ (local emulator), giúp chạy thử nghiệm các dịch vụ AWS không tốn chi phí.
- Điểm qua một số mặt hạn chế của Floci như hỗ trợ dịch vụ giới hạn, kết quả giả lập (mock result) và không giống hoàn toàn 100% môi trường thật.

#### Tâm lý trì hoãn - Góc nhìn triết lý Builder (Phạm Khắc Uy)
- Phân tích bản chất của sự trì hoãn: Không đơn giản là "lười biếng" mà là biểu hiện bên ngoài của nỗi sợ hãi (bao gồm sợ kém cỏi, sợ bị phán xét và sợ thất bại).
- Trình bày về "Vòng lặp tội lỗi" (The Guilt Loop) thúc đẩy thói quen trì hoãn kéo dài.
- Áp dụng triết lý **AWS Builder**: *"Go Build. Fail fast. Learn faster. Keep shipping"* để đập tan sự trì hoãn, khuyến khích hành động nhanh và xem thất bại là bài học giá trị.

#### Sức mạnh của Sự tự tin (Nguyễn Thị Quỳnh Như)
- Định nghĩa lại sự tự tin: Tự tin là dám hành động ngay cả khi đang lo lắng hay sợ hãi, chứ không phải là cái tôi cao hay sự cầu toàn.
- Phân tích ảnh hưởng của Hội chứng kẻ giả mạo (Imposter Syndrome) và hiệu ứng Dunning-Kruger đối với hiệu suất làm việc.
- Ứng dụng quy luật "Start With Why" của Simon Sinek và các nghiên cứu về tính dễ tổn thương của Brené Brown để vượt qua nỗi sợ và xây dựng sự tự tin từ sự chuẩn bị kỹ lưỡng.

#### Kiến trúc đám mây trong Game Multiplayer (Phạm Quang Thái)
- Phân tích thách thức hạ tầng của game nhiều người chơi thời gian thực (độ trễ latency, đồng bộ trạng thái game).
- So sánh kiến trúc máy chủ chuyên dụng (Dedicated Game Server) và Serverless trong lập trình game.
- Phương pháp tự động co giãn (auto-scaling) tài nguyên máy chủ theo số lượng người chơi đồng thời (CCU) để tối ưu hóa chi phí vận hành.

#### Nền tảng chiêm tinh thế hệ mới kết hợp công nghệ (Trần Hữu Nghĩa)
- Giới thiệu dự án xây dựng sản phẩm kết hợp bản đồ sao (birth chart) truyền thống với các giải pháp phần mềm hiện đại.
- Cơ chế tính toán các góc chiếu, tọa độ hành tinh tự động dựa trên thời gian và địa điểm sinh của người dùng với độ chính xác cao.
- Trải nghiệm xây dựng sản phẩm từ ý tưởng sơ khai đến khi triển khai thực tế phục vụ cộng đồng thế hệ mới.

#### Vận hành DevOps trong dự án (Trần Minh Quân)
- Sử dụng mô hình tảng băng (Iceberg Metaphor) để mô tả các sự cố dự án: Các biểu hiện bên ngoài như trễ deadline hay bug nhiều thực chất bắt nguồn từ các vấn đề ẩn bên dưới (sự thiếu giao tiếp, các silo phòng ban và quy trình làm việc thủ công).
- Khẳng định 3 trụ cột của DevOps: Con người (People), Quy trình (Process) và Công nghệ (Technology). Trong đó, **Con người** (lòng tin, tinh thần tự chủ, sự giao tiếp) là phần nền tảng quan trọng nhất dưới đáy tảng băng mà công nghệ không thể tự động hóa được.

#### Trải nghiệm Hackathon - Xây dựng SynthHunter (Team The Ballers)
- Chia sẻ trải nghiệm 36 giờ thi đấu căng thẳng để hoàn thành dự án **SynthHunter** - hệ thống xác minh giọng nói AI để phòng chống cuộc gọi lừa đảo giả mạo giọng nói.
- Chi tiết kỹ thuật sử dụng:
  * **XLS-R** để phân tích đặc tính âm thanh (Speech Dynamics).
  * **Whisper** để phân tích hành vi mã hóa ngữ âm (Encoder Behavior).
  * Phân tích nhịp điệu ngắt nghỉ tự nhiên (Pause Analysis).
- Rút ra bài học: Luôn nhắm trực tiếp vào nỗi đau thực tế của thị trường, thử nghiệm liên tục không ngừng nghỉ và tận dụng tối đa các công cụ/nguồn lực sẵn có.

### Những Gì Học Được

#### Tư Duy Phát Triển Bản Thân & Builder
- Hiểu rằng thói quen trì hoãn phải được khắc phục bằng cách hành động ngay, "fail fast" để rút kinh nghiệm thay vì chờ đợi sự hoàn hảo.
- Rèn luyện tư duy tự tin thông qua việc chuẩn bị tốt và chấp nhận sự không hoàn hảo trong giai đoạn đầu xây dựng sản phẩm.

#### Thiết Kế Hệ Thống & DevOps
- Nhận thức sâu sắc rằng công cụ và công nghệ DevOps chỉ phát huy tác dụng khi giải quyết được nút thắt về giao tiếp và lòng tin giữa các thành viên trong đội ngũ.
- Học cách sử dụng Floci để cấu hình mock dịch vụ AWS nhanh chóng cho các kịch bản test ở môi trường local trước khi deploy lên AWS thật.

#### Phát triển Ứng dụng AI thực tế
- Học hỏi phương pháp thiết kế và phát triển nhanh một ứng dụng AI toàn trình (giống dự án SynthHunter) kết hợp nhiều mô hình pre-trained chuyên sâu (Whisper, XLS-R) để giải quyết bài toán bảo mật giọng nói.

### Ứng Dụng Vào Công Việc

- **Tối ưu quy trình Lab:** Áp dụng phương pháp làm việc phối hợp không silo của DevOps để tăng cường giao tiếp giữa các thành viên dự án AutoRx / Proptimizer.
- **Tận dụng Local Mock:** Tích hợp các công cụ giả lập AWS cục bộ vào quy trình kiểm thử trước khi triển khai các tài nguyên lên tài khoản AWS Lab để giảm chi phí phát sinh ngoài ý muốn.
- **Đập tan trì hoãn:** Áp dụng triết lý Builder để thúc đẩy tiến độ hoàn thành các module chức năng còn dang dở của hệ thống.

### Trải nghiệm trong event

Sự kiện Meetup ngày 30/05/2026 mang lại bầu không khí rất cởi mở, kết hợp hài hòa giữa kiến thức kỹ thuật khô khan và những chia sẻ kỹ năng mềm vô cùng thực tế:

#### Không khí chia sẻ đa chiều
- Sự kiện kết nối từ các DevOps Specialist dày dặn kinh nghiệm đến các bạn sinh viên đầy nhiệt huyết, đem đến những góc nhìn rất đa dạng từ quản trị hệ thống lớn đến hành trình vượt qua áp lực thi cử và hackathon.

#### Case study sinh động
- Các bài trình bày đều đi kèm các ví dụ thực tiễn sinh động, từ trò chơi Cloud Quest đến hệ thống SynthHunter chống lừa đảo thực tế giúp buổi chia sẻ trở nên vô cùng lôi cuốn.

#### Bài học rút ra cho bản thân
- Việc phát triển một hệ thống Cloud/AI tốt không chỉ dựa vào viết code giỏi mà còn phụ thuộc vào khả năng giao tiếp của đội ngũ, sự tự tin cá nhân và tinh thần dám nghĩ dám làm (Builder).

#### Một số hình ảnh khi tham gia sự kiện
![Hình ảnh sự kiện](/images/event2.jpg)
> Tổng kết lại, Meetup 30/05 là một sự kiện truyền cảm hứng mạnh mẽ, trang bị cho tôi nhiều bài học đắt giá về cả chuyên môn Cloud/DevOps lẫn tư duy làm việc nhóm và phát triển bản thân.
