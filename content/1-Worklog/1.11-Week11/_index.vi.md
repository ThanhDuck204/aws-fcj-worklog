---
title: "Worklog Tuần 11"
date: 2026-06-29
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

## Mục tiêu tuần 11

* Tiếp tục gắn kết nối các dịch vụ AWS vào dự án.
* Viết Blog 2 và hoàn thiện nội dung để được duyệt.
* Điều chỉnh lại kiến trúc dự án do bị giới hạn bởi Free Tier.
* Viết case support gửi AWS để được hỗ trợ.

---

## Công việc đã thực hiện

| Ngày | Công việc | Kết quả | Tài liệu | Ghi chú |
|---|---|---|---|---|
| 29/06/2026 | Làm dự án — nối kết nối từng dịch vụ AWS vào project. | Tiếp tục tích hợp các AWS services như Cognito, DynamoDB, S3 vào dự án. Xử lý các lỗi kết nối phát sinh và đảm bảo luồng hoạt động giữa các service được thông suốt. | [GitHub Worklog](https://github.com/ThanhDuck204/aws-fcj-worklog) | Kết nối dịch vụ |
| 30/06/2026 | Tiếp tục làm dự án — nối kết nối từng dịch vụ AWS. | Hoàn thiện các kết nối còn dang dở, kiểm tra lại toàn bộ luồng tích hợp và đảm bảo các service giao tiếp đúng với nhau theo kiến trúc đã thiết kế. | [GitHub Worklog](https://github.com/ThanhDuck204/aws-fcj-worklog) | Kết nối dịch vụ |
| 01/07/2026 | Viết Blog 2 — AWS Nitro Enclaves. | Hoàn thành bài blog nghiên cứu về AWS Nitro Enclaves và cách chạy ứng dụng Web truyền thống trong môi trường Enclave. Bài viết đã được duyệt. | [Bài viết Facebook](https://www.facebook.com/groups/awsstudygroupfcj/?multi_permalinks=2198943464203947) <br> [AWS China Blog](https://aws.amazon.com/cn/blogs/china/running-traditional-web-application-migration-practices-in-aws-nitro-enclaves/) <br> [GitHub Worklog](https://github.com/ThanhDuck204/aws-fcj-worklog) | Viết blog |
| 02/07/2026 | Điều chỉnh kiến trúc dự án do giới hạn Free Tier và viết case support. | Rà soát lại kiến trúc hiện tại, điều chỉnh thiết kế để phù hợp với các giới hạn của Free Tier (chỉ sử dụng được những service miễn phí). Viết case support gửi AWS để nhờ hỗ trợ kỹ thuật về các vấn đề gặp phải. | [GitHub Worklog](https://github.com/ThanhDuck204/aws-fcj-worklog) | Điều chỉnh kiến trúc |
| 03/07/2026 | Tiếp tục nối kết nối dịch vụ AWS vào dự án. | Tiếp tục tích hợp và cấu hình các AWS services, xử lý các lỗi phát sinh và đảm bảo các kết nối hoạt động ổn định. | [GitHub Worklog](https://github.com/ThanhDuck204/aws-fcj-worklog) | Kết nối dịch vụ |

---

## Ghi chú trong tuần

Tuần này tập trung chính vào việc kết nối các dịch vụ AWS vào dự án. Hai ngày đầu tuần dành để nối từng service lại với nhau, xử lý các lỗi phát sinh trong quá trình tích hợp.

Giữa tuần, mình dành thời gian viết Blog 2 về AWS Nitro Enclaves — một chủ đề khá thú vị về bảo mật trên AWS. Bài viết đã được duyệt, hoàn thành tốt.

Tuy nhiên, cuối tuần phát sinh vấn đề lớn: tài khoản AWS bị giới hạn ở Free Tier nên nhiều service không thể triển khai như kiến trúc ban đầu. Mình phải điều chỉnh lại thiết kế cho phù hợp, đồng thời viết case support gửi lên AWS để nhờ hỗ trợ. Đây là một bài học thực tế khá quan trọng về việc thiết kế kiến trúc phải tính đến giới hạn ngân sách ngay từ đầu.

---

## Khó khăn gặp phải

* Quá trình nối kết nối các dịch vụ AWS gặp nhiều lỗi cấu hình, cần debug và fix từng bước.
* Blog 2 cần dịch và tổng hợp từ tài liệu tiếng Trung, mất thời gian để đảm bảo nội dung chính xác.
* Phát hiện tài khoản AWS bị giới hạn Free Tier vào cuối tuần — nhiều service trong kiến trúc ban đầu không triển khai được.
* Cần điều chỉnh lại toàn bộ thiết kế kiến trúc để chỉ dùng các service nằm trong Free Tier.
* Viết case support bằng tiếng Anh với đầy đủ thông tin kỹ thuật để AWS hỗ trợ kịp thời.

---

## Kiến thức rút ra

* Tích hợp nhiều AWS services cùng lúc đòi hỏi kiên nhẫn và hiểu rõ cấu hình từng service.
* Việc dịch và tổng hợp tài liệu kỹ thuật từ tiếng Trung sang tiếng Việt giúp hiểu sâu hơn về chủ đề.
* Kiến trúc dự án cần được thiết kế có tính đến giới hạn ngân sách và tài khoản ngay từ đầu, không chỉ dựa trên lý thuyết.
* Free Tier của AWS có nhiều giới hạn — cần kiểm tra kỹ trước khi chọn service cho kiến trúc.
* Case support là kênh hỗ trợ quan trọng khi gặp vấn đề kỹ thuật với AWS, cần trình bày rõ ràng vấn đề và các bước đã thử để được hỗ trợ nhanh hơn.
