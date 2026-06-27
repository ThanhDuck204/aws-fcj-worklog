---
title: "Worklog Tuần 8"
date: 2026-06-08
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

## Mục tiêu tuần 8

* Làm việc với nhóm để rà soát lại tiến độ dự án AI Meeting Workforce Platform.
* Chỉnh kiến trúc theo góp ý, đặc biệt là luồng xử lý transcript, task và dữ liệu người dùng.
* Ước lượng sơ bộ chi phí AWS cho giai đoạn MVP.
* Tìm thêm hướng tối ưu cho phần xử lý AI, validation dữ liệu và caching.
* Chuẩn bị nội dung blog ngắn về Kiro để chia sẻ trong group.

---

## Công việc đã thực hiện

| Ngày | Công việc | Kết quả | Tài liệu | Ghi chú |
|---|---|---|---|---|
| 08/06/2026 | Lên công ty làm việc nhóm, rà soát tiến độ dự án và nhận góp ý. | Nhóm kiểm tra lại phần đã làm ở tuần trước, gồm layout, mock data, routing theo role và luồng xử lý cuộc họp. Một số điểm cần chỉnh được ghi lại: cách chia module, dữ liệu đầu ra của AI và hướng chuẩn bị cho AWS integration. | Không có | Chốt lại các phần cần cải tiến trong tuần. |
| 09/06/2026 | Xem lại architecture diagram và ước lượng chi phí AWS. | Làm rõ vai trò của S3, Lambda, API Gateway, DynamoDB, Cognito, CloudFront và CloudWatch. Ghi lại các khoản chi phí cần chú ý như dung lượng file transcript/audio, số lần gọi Lambda/API Gateway, log CloudWatch và request DynamoDB. | [AWS Pricing Calculator](https://calculator.aws/#/) <br> [AWS Architecture Center](https://aws.amazon.com/architecture/) | Ưu tiên kiến trúc vừa đủ cho MVP. |
| 10/06/2026 | Tìm thêm hướng tối ưu cho dự án. | Xem xét các phần có thể cải thiện như xử lý transcript trước khi đưa vào AI, tách pipeline xử lý thành nhiều bước, chuẩn hóa dữ liệu đầu ra, thêm retry logic và cân nhắc caching cho dashboard. | Không có | Chọn giải pháp đơn giản trước, tránh làm hệ thống phức tạp quá sớm. |
| 11/06/2026 | Tìm hiểu Kiro và chuẩn bị dàn ý blog. | Nhóm thống nhất các ý chính: Kiro là gì, spec-driven development giúp giảm mơ hồ ra sao, và có thể áp dụng vào dự án nhóm như thế nào. Dàn ý được viết theo hướng ngắn gọn, dễ đọc. | [AWS Blog](https://aws.amazon.com/blogs/) | Nội dung blog sẽ tập trung vào trải nghiệm thực tế hơn là chỉ tóm tắt tài liệu. |
| 12/06/2026 | Tiếp tục phát triển dự án theo góp ý trong tuần. | Kiểm tra lại luồng chính của AI Meeting Workforce Platform, chỉnh các phần còn thiếu và chuẩn bị cho bước tích hợp/cải tiến tiếp theo. Đồng thời ghi lại vài quyết định kiến trúc để nhóm dễ theo dõi. | Không có | Tập trung giữ cấu trúc dự án rõ ràng. |

---

## Ghi chú trong tuần

Tuần này nhóm nhìn lại dự án kỹ hơn thay vì chỉ thêm code mới. Phần kiến trúc được rà soát lại theo cả hai góc: hệ thống chạy như thế nào và chi phí AWS có thể phát sinh ở đâu.

Điểm mình thấy quan trọng là không nên đưa quá nhiều dịch vụ vào MVP chỉ vì dịch vụ đó hay. Với quy mô hiện tại, kiến trúc cần đủ rõ để phát triển tiếp, nhưng vẫn phải gọn để nhóm dễ triển khai và debug.

---

## Khó khăn gặp phải

* Ước lượng chi phí AWS còn chưa chính xác vì phụ thuộc vào số request, dung lượng file và cách người dùng sử dụng hệ thống.
* Architecture diagram cần đủ chi tiết để triển khai nhưng không nên quá nhiều thành phần làm nhóm khó theo dõi.
* Phần xử lý transcript và task extraction cần tách bước rõ ràng, nếu gom hết vào một luồng sẽ khó debug khi có lỗi.
* Khi chuẩn bị blog về Kiro, cần viết ngắn và dễ hiểu thay vì chỉ tóm tắt lại tài liệu kỹ thuật.

---

## Kiến thức rút ra

* Khi thiết kế kiến trúc AWS, cần nghĩ cả luồng kỹ thuật và chi phí vận hành.
* Serverless phù hợp với MVP, nhưng vẫn phải kiểm soát log, request và dữ liệu lưu trữ.
* Feedback từ nhóm giúp phát hiện sớm những phần chưa rõ trong kiến trúc.
* Với dự án nhóm, cách ghi lại quyết định thiết kế giúp giảm nhầm lẫn khi phát triển tiếp.
