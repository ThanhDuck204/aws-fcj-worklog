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
| 09/07/2026 | Gần như hoàn thiện dự án và nộp workshop. | Dự án đã cơ bản hoàn thiện, các chức năng chính hoạt động ổn định. Tiến hành nộp workshop vì thời gian không còn nhiều để sửa thêm. Chấp nhận các hạn chế hiện tại và hoàn thiện báo cáo. | | Hoàn thiện & nộp |

---

## Ghi chú trong tuần

Tuần này là tuần cuối cùng để hoàn thiện dự án và nộp workshop. Hai ngày đầu tuần (Thứ 2, Thứ 3) tập trung vào việc phát triển nốt các chức năng còn lại và bắt đầu quá trình deploy dự án lên AWS.

Tuy nhiên, quá trình deploy gặp khá nhiều lỗi phát sinh — từ lỗi cấu hình service, lỗi kết nối giữa các thành phần, cho đến các vấn đề về môi trường production khác với môi trường development. Ngày Thứ 4 dành gần như trọn vẹn để debug và fix các lỗi này.

Đến Thứ 5, dự án đã gần như hoàn thiện với các chức năng chính hoạt động ổn định. Do thời gian không còn nhiều, mình quyết định nộp workshop ở trạng thái hiện tại thay vì cố gắng sửa thêm — chấp nhận một số hạn chế nhỏ còn tồn đọng và tập trung vào việc hoàn thiện báo cáo để nộp đúng hạn.

---

## Khó khăn gặp phải

* Quá trình deploy lên AWS gặp nhiều lỗi phát sinh không lường trước được từ môi trường development.
* Lỗi cấu hình giữa các AWS service khi triển khai thực tế khác với khi chạy local.
* Thời gian eo hẹp — không đủ thời gian để fix triệt để tất cả các lỗi phát sinh.
* Phải đưa ra quyết định khó khăn giữa việc cố sửa thêm lỗi hay nộp workshop đúng hạn.
* Áp lực deadline khi đây là tuần cuối cùng để hoàn thiện mọi thứ.

---

## Kiến thức rút ra

* Deploy dự án lên môi trường thực tế luôn phát sinh nhiều vấn đề không thấy được khi chạy local — cần chuẩn bị kỹ lưỡng hơn cho giai đoạn này.
* Kỹ năng debug trên môi trường production rất quan trọng: đọc log, phân tích lỗi, và fix nhanh dưới áp lực thời gian.
* Biết cách ưu tiên công việc: không phải lỗi nào cũng cần fix ngay, cần đánh giá mức độ ảnh hưởng và quyết định những gì quan trọng nhất để hoàn thành.
* Quản lý thời gian và kỷ luật bản thân là yếu tố then chốt để hoàn thành dự án đúng hạn.
* Chấp nhận rằng một dự án thực tế không bao giờ hoàn hảo 100% — biết điểm dừng đúng lúc cũng quan trọng không kém việc cố gắng fix mọi lỗi.
