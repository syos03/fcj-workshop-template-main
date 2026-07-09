---
title: "Event 1"
date: 2026-05-09
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}

# Bài thu hoạch "FCAJ Community Day - 09/05/2026"

**Ngày diễn ra:** 09/05/2026

### Mục Đích Của Sự Kiện

- Chia sẻ các phương pháp thực tế giúp người học xây dựng thói quen học tập bền vững, tận dụng cơ chế hoạt động của não bộ.
- Giới thiệu kỹ thuật Prompt Engineering chuyên sâu và vai trò tối ưu hóa câu lệnh trong việc nâng cao chất lượng đầu ra của các mô hình ngôn ngữ lớn (LLM).
- Thảo luận về vị trí của lập trình viên trẻ trong thời đại AI và tầm quan trọng của kiến thức nền tảng.
- Giới thiệu phương pháp BMAD — một framework phát triển phần mềm kết hợp AI có cấu trúc, thay thế cho lối "vibe coding" thiếu kỷ luật.

### Danh Sách Diễn Giả

- **Huỳnh Hoàng Long** - FCAJ Member
- **Nguyễn Tuấn Thịnh** - DevOps/Cloud Engineer (đại diện FCAJ)
- **Anh Khang** - Solutions Architect tại Cloud Kinetics
- **Diễn giả thứ tư** - Chuyên gia về phương pháp BMAD

### Nội Dung Nổi Bật

#### Hack Não Để Học Như Nghiện Game (Huỳnh Hoàng Long)

Huỳnh Hoàng Long mở đầu bằng một câu hỏi thực tế quen thuộc: tại sao ta có thể cuộn TikTok hàng giờ mà không biết mệt, nhưng chỉ ngồi học 10 phút là chán nản?

- **Phân tích nguyên nhân tâm lý:** Não bộ ưu tiên hoạt động tiêu hao ít năng lượng, phần thưởng đến nhanh và kích thích tính tò mò — đây đều là đặc tính cốt lõi mà mạng xã hội và game online đã khai thác triệt để.
- **Cơ chế dopamine:** Dopamine không được tiết ra khi nhận phần thưởng, mà tiết ra khi **kỳ vọng** phần thưởng sắp đến. Đây chính là lý do các thuật toán TikTok và cơ chế slot machine giữ chân người dùng hiệu quả đến vậy.
- **Kỹ thuật "hộp phần thưởng bí ẩn":** Viết nhiều phần thưởng nhỏ ngẫu nhiên vào từng tờ giấy, bỏ vào hộp, cứ mỗi 10 phút học thì bốc một tờ. Sự tò mò về phần thưởng tiếp theo sẽ kích thích não bộ tiết dopamine liên tục, giúp duy trì động lực.
- **Khai thác nỗi sợ mất mát:** Dùng lịch điểm danh học tập hàng ngày như hệ thống "chuỗi streak" của Duolingo hay điểm danh sự kiện trong game. Khi chuỗi đã dài, bạn sẽ sợ gãy chuỗi hơn là lười học.
- **Chia nhỏ nhiệm vụ:** Chia nội dung học thành các phần nhỏ, mỗi ngày một dịch vụ AWS thay vì cố học tất cả trong một buổi. Tương tự như cách một người mới tập chạy chia lộ trình 5km thành nhiều chặng ngắn.
- **Quy tắc 2 phút:** Bất kỳ việc gì giải quyết được trong 2 phút thì làm ngay, không để sang sau.
- **Hệ thống XP:** Tự xây dựng hệ thống điểm kinh nghiệm (XP) cho bản thân — học xong một chủ đề cộng điểm, đạt mốc thì tự thưởng (một ly cà phê, một bữa ngon...).
- **Chia sẻ kiến thức thay vì lướt mạng xã hội:** Thay vì cuộn feed vô nghĩa, hãy chuyển thói quen đó thành đăng bài chia sẻ kiến thức mới học được — đây cũng là con đường để trở thành speaker tại các sự kiện như FCAJ Community Day.

#### Automated Prompt Engineering & Proptimizer trên AWS (Nguyễn Tuấn Thịnh)

Nguyễn Tuấn Thịnh trình bày hoàn toàn bằng tiếng Anh, chia sẻ về nghệ thuật giao tiếp hiệu quả với các mô hình AI.

- **Vấn đề của prompt chung chung:** Prompt mơ hồ → output kém chất lượng, tốn nhiều token, phát sinh chi phí API không cần thiết và khiến AI rơi vào trạng thái hallucination (bịa đặt thông tin).
- **7 thành phần của một prompt tốt:**
  - **Role** (Vai trò): Định nghĩa danh tính AI đóng giả (ví dụ: "You are a senior career coach").
  - **Instruction** (Chỉ dẫn): Hành động cụ thể cần thực hiện.
  - **Context** (Ngữ cảnh): Thông tin nền tảng liên quan.
  - **Input** (Dữ liệu đầu vào): Văn bản thô cần xử lý.
  - **Output Format** (Định dạng đầu ra): JSON, Markdown, bullet list...
  - **Examples** (Ví dụ mẫu): Few-shot prompting để định hướng phong cách.
  - **Constraints** (Ràng buộc): Giới hạn độ dài, ngôn ngữ, phạm vi.
- **Kỹ thuật nâng cao:**
  - **Chain of Thought (CoT):** Yêu cầu AI suy nghĩ từng bước để giải quyết bài toán phức tạp.
  - **Self-Consistency:** Chạy nhiều luồng suy luận, lấy kết quả đa số.
  - **Tree of Thought (ToT):** AI dùng BFS/DFS khám phá nhiều nhánh lập luận để tìm câu trả lời tối ưu.
- **Token Economics:** Token là đơn vị xử lý của LLM; tiếng Việt tốn gấp đôi token so với tiếng Anh; chi phí tính theo input + output tokens.
- **Demo Proptimizer trên AWS:**
  - **Frontend:** Next.js được host trên Amazon S3, phân phối toàn cầu qua Amazon CloudFront (CDN với OAC).
  - **Xác thực:** Amazon Cognito quản lý đăng ký, đăng nhập và phát hành JWT token — không cần tự xây dựng hệ thống auth.
  - **API & Backend:** Amazon API Gateway điều phối request → AWS Lambda (serverless compute) xử lý logic nghiệp vụ.
  - **AI Core:** Amazon Bedrock cung cấp quyền truy cập có bảo mật vào các Foundation Model (Claude, GPT...) không cần triển khai server.
  - **Lưu trữ:** Amazon DynamoDB (NoSQL) lưu lịch sử prompt, cấu hình người dùng; Amazon S3 lưu file tĩnh.
  - **Giám sát:** Amazon CloudWatch theo dõi log Lambda, đo latency API Gateway.
  - **Tính năng sản phẩm:** Proptimizer là browser extension cho phép bôi đen bất kỳ đoạn văn bản nào trên web → tự động tối ưu hóa prompt → paste vào ChatGPT/Gemini để nhận phản hồi chất lượng cao nhất.

#### Nền Tảng Kiến Thức & Vai Trò Của AI Đối Với Fresher (Anh Khang)

Anh Khang — Solutions Architect tại Cloud Kinetics với 3 năm kinh nghiệm — chia sẻ góc nhìn thực tế từ phía nhà tuyển dụng:

- **Tập trung vào nền tảng (Foundation):** Trong một thế giới đổi thay quá nhanh, thứ duy nhất giữ vững giá trị là kiến thức nền tảng. Nhà tuyển dụng không cần bạn biết hết 200 service AWS; họ cần bạn thực sự hiểu 5 service cốt lõi và có **thought process** (quy trình tư duy) đúng đắn.
- **AI amplify (AI khuếch đại):** AI không thay thế lập trình viên mà khuếch đại năng lực của họ. Nếu bạn giỏi, AI giúp bạn giỏi hơn gấp 10 lần. Nếu bạn yếu, AI chỉ làm lộ rõ điểm yếu của bạn nhanh hơn.
- **Bạn có thể outsource tư duy, nhưng không thể outsource sự hiểu biết:** Khi nhà tuyển dụng thay đổi một chi tiết nhỏ trong đề bài assignment, những bạn chỉ copy output của AI mà không hiểu bản chất sẽ lập tức bị loại.
- **Không có đúng sai tuyệt đối trong kiến trúc:** Điều quan trọng là lý do bạn chọn giải pháp đó — lý do hợp lý và có tư duy phân tích rõ ràng là yếu tố quyết định bạn vượt qua vòng phỏng vấn.

#### BMAD Method — Phát Triển Phần Mềm Có Cấu Trúc Với AI

BMAD (Breakthrough Method for Agile AI-Driven Development) là framework mã nguồn mở giúp tổ chức quy trình phát triển phần mềm với AI một cách có kỷ luật, thay thế cho lối "vibe coding" hỗn độn:

- **Agentic Roles (Vai trò AI chuyên biệt):** Phân vai cho các AI agent đóng vai Product Manager, Architect, Developer, QA, Scrum Master — mỗi agent chịu trách nhiệm một giai đoạn SDLC cụ thể.
- **Hai giai đoạn chính:**
  - **Phase 1 - Agentic Planning:** Tạo đầy đủ tài liệu PRD (Product Requirements Document), thiết kế kiến trúc hệ thống và user stories **trước khi** viết bất kỳ dòng code nào.
  - **Phase 2 - Context-Engineered Development:** Dùng tài liệu đã tạo ở Phase 1 làm context để hướng dẫn AI sinh code chính xác, nhất quán và dễ bảo trì.
- **Lợi ích thực tiễn:**
  - Giảm thiểu tình trạng AI hallucination nhờ các agent kiểm tra chéo lẫn nhau.
  - Tạo ra codebase có tài liệu rõ ràng, dễ audit và mở rộng.
  - Áp dụng được từ dự án cá nhân nhỏ đến hệ thống enterprise lớn.
  - Cài đặt qua CLI (`npx bmad-method install`), tích hợp vào Cursor, Claude Code...

### Những Gì Học Được

#### Phương Pháp Học Tập & Phát Triển Bản Thân
- Hiểu được cơ chế dopamine là nền tảng để thiết kế hệ thống học tập cá nhân hóa và bền vững hơn.
- Áp dụng ngay "hộp phần thưởng bí ẩn" và lịch điểm danh streak vào lộ trình tự học AWS.

#### Prompt Engineering & Chi Phí AI
- Nắm vững 7 thành phần của một prompt tốt và các kỹ thuật CoT, ToT để khai thác tối đa khả năng của LLM.
- Tính toán chi phí token khi xây dựng ứng dụng AI trên AWS Bedrock để tránh phát sinh chi phí ngoài dự kiến.

#### Tư Duy Kiến Trúc Cloud
- Hiểu rõ từng thành phần trong kiến trúc Serverless trên AWS (S3, CloudFront, Cognito, API Gateway, Lambda, Bedrock, DynamoDB, CloudWatch) và lý do lựa chọn từng dịch vụ.

#### Làm Việc Với AI Một Cách Chuyên Nghiệp
- Nhận thức rõ ràng rằng AI khuếch đại năng lực, không thay thế tư duy. Nền tảng kiến thức vững chắc mới là yếu tố cạnh tranh bền vững.
- Bước đầu tìm hiểu BMAD Method để áp dụng vào dự án cá nhân theo hướng có tổ chức hơn.

### Ứng Dụng Vào Công Việc

- **Cải thiện quy trình làm việc với AI:** Áp dụng 7 thành phần prompt và CoT vào các tác vụ hàng ngày như viết tài liệu, review code và sinh test case cho dự án AutoRx.
- **Xây dựng thói quen học tập:** Triển khai hệ thống điểm danh streak kết hợp hộp phần thưởng ngẫu nhiên để duy trì tiến độ học AWS hàng ngày.
- **Nghiên cứu BMAD Method:** Thử nghiệm áp dụng BMAD cho giai đoạn lập kế hoạch của dự án thực tập để tạo ra tài liệu PRD và kiến trúc rõ ràng trước khi bắt đầu code.
- **Quản lý chi phí Cloud:** Theo dõi chặt chẽ token usage và API logs của Bedrock để kiểm soát chi phí tài khoản AWS Lab.

### Trải Nghiệm Trong Event

Đây là lần đầu tiên tôi tham dự một buổi FCAJ Community Day và cảm xúc sau sự kiện là vô cùng tích cực:

#### Sự kết hợp độc đáo giữa kỹ năng mềm và kỹ thuật
- Buổi sự kiện hiếm hoi mở đầu bằng một bài nói về **tâm lý học học tập** thay vì chỉ toàn technical content. Phần trình bày của Huỳnh Hoàng Long thực sự chạm đúng vào nỗi đau của những bạn học viên đang vật lộn với sự mất động lực.

#### Thực hành thực tế trên AWS
- Phần demo **Proptimizer** của Nguyễn Tuấn Thịnh là highlight của buổi — nhìn thấy một browser extension thực sự hoạt động với kiến trúc Serverless đầy đủ trên AWS giúp tôi hình dung rõ hơn về mục tiêu cuối cùng của chương trình thực tập.

#### Góc nhìn thực tế từ nhà tuyển dụng
- Chia sẻ thẳng thắn của Anh Khang về cách đánh giá hồ sơ và bài assignment khiến tôi nhìn nhận lại cách mình đang sử dụng AI — và quyết tâm đầu tư hơn vào việc thực sự **hiểu** thay vì chỉ **copy output**.

#### Một số hình ảnh khi tham gia sự kiện
![Ảnh chụp tập thể](/images/AWSevent1.jpg)
![Slide chia sẻ](/images/event1_presentation.jpg)
> Tổng kết lại, FCAJ Community Day 09/05 là một buổi gặp mặt chất lượng cao, cung cấp cho tôi cả công cụ kỹ thuật (Prompt Engineering, BMAD, Serverless AWS) lẫn mindset (tư duy học tập, nền tảng kiến thức, AI amplify) để phát triển trong sự nghiệp IT một cách bền vững.
