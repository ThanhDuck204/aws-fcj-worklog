---
title: "Worklog Tuần 12"
date: 2026-07-06
weight: 12
chapter: false
pre: " <b> 1.12. </b> "
---

## Mục tiêu tuần 12

* Tiếp tục phát triển và hoàn thiện dự án.
* Sửa lỗi phát sinh trong quá trình deploy dự án lên AWS.
* Đảm bảo các chức năng chính hoạt động ổn định trên môi trường deployment.
* Nộp workshop đúng hạn do thời gian không còn nhiều.

---

## Công việc đã thực hiện

| Ngày | Công việc | Kết quả | Tài liệu | Ghi chú |
|---|---|---|---|---|
| 06/07/2026 | Tiếp tục phát triển dự án — hoàn thiện các chức năng còn lại. | Tiếp tục code và tích hợp các chức năng còn dang dở của dự án. Rà soát lại toàn bộ luồng hoạt động để chuẩn bị cho việc deploy. | | Phát triển dự án |
| 07/07/2026 | Tiếp tục phát triển dự án và sửa lỗi khi deploy. | Tiến hành deploy dự án lên AWS, phát hiện và xử lý các lỗi phát sinh trong quá trình triển khai như lỗi cấu hình, lỗi kết nối giữa các service, và lỗi môi trường. | | Deploy & sửa lỗi |
| 08/07/2026 | Sửa lỗi deploy — debug các vấn đề trên môi trường production. | Tiếp tục debug và fix các lỗi phát sinh trên môi trường deployment. Kiểm tra lại cấu hình các AWS service, log lỗi và điều chỉnh code cho phù hợp với môi trường thực tế. | | Fix lỗi deploy |
| 09/07/2026 | Tiếp tục test và sửa lỗi workshop. | Rà soát và kiểm tra lại toàn bộ các chức năng của workshop, phát hiện và sửa các lỗi còn tồn đọng. Tiến hành test lại các luồng hoạt động để đảm bảo dự án hoạt động ổn định. | | Test & sửa lỗi |
| 10/07/2026 | Tiếp tục test, sửa lỗi và điều chỉnh setting dịch vụ AWS (tuần 1). | Tiếp tục công việc test và sửa lỗi workshop, đồng thời điều chỉnh lại một số cấu hình dịch vụ AWS cho phù hợp với môi trường thực tế. Đây là tuần đầu tiên thực tập nên cần làm quen với môi trường làm việc và các quy trình. | | Test & cấu hình AWS |

---

## Ghi chú trong tuần

Tuần này là tuần cuối cùng để hoàn thiện dự án và nộp workshop. Hai ngày đầu tuần (Thứ 2, Thứ 3) tập trung vào việc phát triển nốt các chức năng còn lại và bắt đầu quá trình deploy dự án lên AWS.

Tuy nhiên, quá trình deploy gặp khá nhiều lỗi phát sinh — từ lỗi cấu hình service, lỗi kết nối giữa các thành phần, cho đến các vấn đề về môi trường production khác với môi trường development. Ngày Thứ 4 dành gần như trọn vẹn để debug và fix các lỗi này.

Đến Thứ 5 và Thứ 6, mình tiếp tục test và sửa các lỗi còn lại trong workshop, đồng thời điều chỉnh một số cấu hình dịch vụ AWS cho phù hợp với môi trường thực tế trong tuần đầu tiên thực tập.

---

## Khó khăn gặp phải

* Quá trình deploy lên AWS gặp nhiều lỗi phát sinh không lường trước được từ môi trường development.
* Lỗi cấu hình giữa các AWS service khi triển khai thực tế khác với khi chạy local.
* Thời gian eo hẹp — không đủ thời gian để fix triệt để tất cả các lỗi phát sinh.
* Phải đưa ra quyết định khó khăn giữa việc cố sửa thêm lỗi hay nộp workshop đúng hạn.
* Áp lực deadline khi đây là tuần cuối cùng để hoàn thiện mọi thứ.
* Tuần đầu tiên thực tập cần làm quen với môi trường làm việc, quy trình và các công cụ mới.

---

## Kiến thức rút ra

* Deploy dự án lên môi trường thực tế luôn phát sinh nhiều vấn đề không thấy được khi chạy local — cần chuẩn bị kỹ lưỡng hơn cho giai đoạn này.
* Kỹ năng debug trên môi trường production rất quan trọng: đọc log, phân tích lỗi, và fix nhanh dưới áp lực thời gian.
* Biết cách ưu tiên công việc: không phải lỗi nào cũng cần fix ngay, cần đánh giá mức độ ảnh hưởng và quyết định những gì quan trọng nhất để hoàn thành.
* Quản lý thời gian và kỷ luật bản thân là yếu tố then chốt để hoàn thành dự án đúng hạn.
* Chấp nhận rằng một dự án thực tế không bao giờ hoàn hảo 100% — biết điểm dừng đúng lúc cũng quan trọng không kém việc cố gắng fix mọi lỗi.
