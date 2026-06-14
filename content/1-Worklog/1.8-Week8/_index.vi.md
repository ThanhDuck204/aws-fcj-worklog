---
title: "Worklog Tuần 8"
date: 2026-06-08
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

## Mục tiêu tuần 8

* Tiếp tục làm việc nhóm tại công ty để rà soát tiến độ dự án AI Meeting Workforce Platform.
* Tiếp nhận góp ý cải tiến từ các thành viên và điều chỉnh hướng phát triển dự án.
* Thảo luận lại kiến trúc diagram, luồng xử lý chính và cách các dịch vụ AWS phối hợp với nhau.
* Dự đoán chi phí có thể phát sinh khi sử dụng các dịch vụ AWS trong giai đoạn MVP.
* Tìm hiểu thêm công nghệ, thuật toán và cách tối ưu để dự án hoạt động ổn định hơn.
* Nghiên cứu các bài viết/blog AWS liên quan đến Kiro để chuẩn bị bài blog đăng lên group.
* Tiếp tục phát triển dự án theo các góp ý và hướng cải tiến đã thống nhất.

---

## Công việc đã thực hiện

| Ngày | Công việc | Kết quả | Tài liệu | Ghi chú |
|---|---|---|---|---|
| 08/06/2026 | Lên công ty bàn và làm việc nhóm về dự án; tiếp tục tiếp nhận góp ý cải tiến. | Cùng nhóm rà soát lại tiến độ hiện tại của AI Meeting Workforce Platform, xác định các phần đã ổn và các phần cần cải tiến thêm. Ghi nhận góp ý về luồng người dùng, cách tổ chức module, xử lý dữ liệu cuộc họp và cách chuẩn bị cho phần tích hợp AWS sau này. | Không có | Tập trung làm việc nhóm và thống nhất hướng cải tiến tiếp theo. |
| 08/06/2026 | Thảo luận về kiến trúc diagram và dự đoán chi phí khi sử dụng dịch vụ AWS. | Cùng nhóm xem lại kiến trúc diagram, làm rõ vai trò của các dịch vụ như S3, Lambda, API Gateway, DynamoDB, Cognito, CloudFront và CloudWatch. Bắt đầu ước lượng các loại chi phí có thể phát sinh: lưu trữ transcript/audio trên S3, số lần gọi Lambda, request qua API Gateway, đọc/ghi DynamoDB, truyền dữ liệu qua CloudFront và log/monitoring trên CloudWatch. | [AWS Pricing Calculator](https://calculator.aws/#/) <br> [AWS Architecture Center](https://aws.amazon.com/architecture/) | Đây là bước chuẩn bị để tránh chọn kiến trúc quá tốn chi phí so với quy mô MVP. |
| 09/06/2026 | Tiếp tục cải tiến dự án và tìm thêm công nghệ, thuật toán có thể áp dụng. | Nghiên cứu thêm các hướng cải tiến cho dự án như tối ưu xử lý transcript, tách pipeline xử lý AI thành các bước rõ ràng, cải thiện cách trích xuất task từ nội dung cuộc họp và chuẩn hóa dữ liệu đầu ra. Đánh giá thêm các kỹ thuật có thể giúp hệ thống ổn định hơn như retry logic, queue-based processing, caching kết quả xử lý và validation dữ liệu trước khi lưu vào database. | Không có | Tập trung tìm giải pháp phù hợp với dự án thay vì thêm công nghệ quá phức tạp. |
| 10/06/2026 | Thảo luận nhóm và cùng tìm hiểu các bài viết/blog AWS về Kiro để chuẩn bị viết blog. | Cùng nhóm đọc và tổng hợp thông tin về Kiro, tập trung vào cách Kiro hỗ trợ quy trình phát triển phần mềm, làm rõ yêu cầu, tạo spec và hỗ trợ lập trình theo hướng có cấu trúc. Bắt đầu chọn các ý chính có thể đưa vào bài blog đăng lên group. | [AWS Blog](https://aws.amazon.com/blogs/) | Nội dung tập trung vào việc hiểu Kiro và cách trình bày lại thành bài viết dễ đọc. |
| 11/06/2026 | Tiếp tục thảo luận, hoàn thiện ý tưởng và dàn ý cho bài blog về Kiro. | Cùng nhóm thống nhất dàn ý bài blog: giới thiệu Kiro, vấn đề Kiro giải quyết, cách Kiro hỗ trợ developer, điểm khác biệt so với việc chỉ dùng AI assistant thông thường, và khả năng áp dụng vào dự án nhóm. Chuẩn bị nội dung để đăng lên group với văn phong ngắn gọn, dễ hiểu và có liên hệ thực tế. | [AWS Blog](https://aws.amazon.com/blogs/) | Kết hợp đọc tài liệu với thảo luận nhóm để bài blog không chỉ là tóm tắt mà có thêm góc nhìn thực tế. |
| 12/06/2026 | Tiếp tục làm dự án. | Tiếp tục phát triển AI Meeting Workforce Platform dựa trên các góp ý đã nhận trong tuần. Ưu tiên hoàn thiện các phần còn thiếu, kiểm tra lại luồng xử lý chính và chuẩn bị cho các bước tích hợp hoặc cải tiến tiếp theo. | Không có | Tập trung vào tiến độ dự án và giữ cấu trúc đã thống nhất với nhóm. |

---

## Thảo luận kiến trúc & dự đoán chi phí AWS

Trong tuần này, nhóm tiếp tục rà soát kiến trúc tổng thể của **AI Meeting Workforce Platform** để đảm bảo các dịch vụ AWS được chọn phù hợp với quy mô MVP:

| Thành phần | Dịch vụ AWS dự kiến | Chi phí cần chú ý |
|---|---|---|
| Lưu trữ transcript/audio | Amazon S3 | Dung lượng lưu trữ, số request upload/download, lifecycle policy |
| Xử lý backend/AI | AWS Lambda | Số lần invoke, thời gian chạy, memory allocation |
| API | Amazon API Gateway | Số lượng request từ frontend |
| Database | Amazon DynamoDB | Read/write capacity, query pattern, index phụ |
| Authentication | Amazon Cognito | Số lượng MAU, user pool usage |
| CDN | Amazon CloudFront | Data transfer, request count |
| Monitoring | Amazon CloudWatch | Log volume, metric, alarm |

**Nhận xét:** Với giai đoạn MVP, hướng serverless vẫn phù hợp vì chi phí có thể tăng theo mức sử dụng thực tế. Tuy nhiên, nhóm cần kiểm soát log, số lần gọi API/Lambda, kích thước file lưu trữ và cách đọc/ghi DynamoDB để tránh phát sinh chi phí không cần thiết.

---

## Công nghệ và thuật toán đã xem xét

* **Transcript preprocessing**: Làm sạch nội dung transcript trước khi đưa vào bước AI summarization/task extraction.
* **Task extraction pipeline**: Tách quy trình thành các bước như nhận diện action item, xác định người phụ trách, độ ưu tiên và deadline.
* **Retry logic**: Xử lý lại các tác vụ thất bại khi gọi API hoặc xử lý Lambda.
* **Queue-based processing**: Cân nhắc dùng hàng đợi cho các tác vụ xử lý transcript dài để tránh timeout.
* **Caching**: Lưu cache kết quả dashboard hoặc kết quả truy vấn thường dùng để giảm số lần đọc database.
* **Validation layer**: Chuẩn hóa dữ liệu trước khi lưu vào DynamoDB để giảm lỗi dữ liệu trong quá trình phát triển.

---

## Nghiên cứu Kiro và chuẩn bị bài blog

Nhóm cùng tìm hiểu các bài viết liên quan đến **Kiro** trên AWS để chuẩn bị một bài blog đăng lên group. Nội dung chính được định hướng gồm:

* Kiro là gì và hỗ trợ developer như thế nào.
* Vì sao spec-driven development giúp giảm mơ hồ khi làm dự án.
* Cách Kiro có thể hỗ trợ viết yêu cầu, chia task, tạo kế hoạch và sinh code.
* Điểm khác biệt giữa Kiro và việc chỉ dùng AI assistant để hỏi đáp từng phần.
* Khả năng áp dụng Kiro vào dự án AI Meeting Workforce Platform.

---

## Kiến thức & kỹ năng đạt được

* Hiểu rõ hơn cách rà soát architecture diagram theo góc nhìn triển khai thực tế.
* Biết cách nhìn kiến trúc AWS không chỉ theo mặt kỹ thuật mà còn theo chi phí vận hành.
* Có thêm kinh nghiệm ước lượng các loại chi phí chính trong một hệ thống serverless.
* Tìm hiểu thêm các kỹ thuật giúp hệ thống ổn định hơn như retry, queue, caching và validation.
* Biết cách đọc tài liệu/blog kỹ thuật, tổng hợp ý chính và chuyển thành nội dung chia sẻ cho cộng đồng.
* Rèn luyện kỹ năng làm việc nhóm, tiếp nhận feedback và điều chỉnh hướng phát triển dự án.

---

## Khó khăn gặp phải & Cách khắc phục

* **Dự đoán chi phí AWS còn nhiều biến số**: Chi phí phụ thuộc vào số request, dung lượng file, thời gian chạy Lambda và pattern đọc/ghi database. Cách khắc phục: chia nhỏ từng dịch vụ để ước lượng riêng, sau đó tổng hợp lại bằng AWS Pricing Calculator.
* **Kiến trúc diagram cần cân bằng giữa đầy đủ và dễ hiểu**: Nếu thêm quá nhiều dịch vụ, diagram dễ rối. Cách khắc phục: chỉ giữ các thành phần cần cho MVP, các dịch vụ mở rộng sẽ ghi chú cho giai đoạn sau.
* **Tìm công nghệ phù hợp cho dự án**: Có nhiều công nghệ và thuật toán có thể áp dụng nhưng không phải cái nào cũng cần thiết. Cách khắc phục: ưu tiên giải pháp đơn giản, dễ triển khai và giải quyết trực tiếp vấn đề của dự án.
* **Viết blog về Kiro cần dễ hiểu với người đọc trong group**: Tài liệu kỹ thuật có nhiều khái niệm mới. Cách khắc phục: nhóm thống nhất viết theo hướng ngắn gọn, có ví dụ thực tế và liên hệ với project đang làm.

---

## Bài học rút ra

* Khi thiết kế kiến trúc AWS, cần nghĩ song song giữa luồng kỹ thuật và chi phí vận hành.
* Serverless phù hợp với MVP, nhưng vẫn cần kiểm soát log, số lần gọi API và cách lưu trữ dữ liệu.
* Góp ý từ nhóm giúp phát hiện sớm các điểm chưa rõ trong kiến trúc và luồng xử lý.
* Việc tìm hiểu thêm thuật toán/công nghệ nên bắt đầu từ vấn đề thực tế của dự án, không nên thêm công nghệ chỉ vì mới hoặc phổ biến.
* Viết blog kỹ thuật là một cách tốt để kiểm tra lại mức độ hiểu của bản thân và chia sẻ kiến thức cho người khác.
