---
title: "Worklog Tuần 4"
date: 2026-05-11
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

## Mục tiêu tuần 4

* Tiếp tục Module 04 về Storage trên AWS.
* Tìm hiểu Snow Family, Storage Gateway, Disaster Recovery và AWS Backup.
* Nghiên cứu Cost Explorer API, Billing API và IAM API để chuẩn bị ý tưởng AWS Management Dashboard.
* Xem lại nội dung Event 1 về Prompt Engineering, Proptimizer và BMAD.

---

## Công việc đã thực hiện

| Ngày | Công việc | Kết quả | Tài liệu | Ghi chú |
|---|---|---|---|---|
| 11/05/2026 | Học Snow Family, Storage Gateway, Disaster Recovery và AWS Backup. | Hiểu cách AWS hỗ trợ chuyển dữ liệu lớn, lưu trữ hybrid và backup tập trung. Ghi lại RTO/RPO để phân biệt các chiến lược disaster recovery. | [Module 04-04 - Snow Family and Storage Gateway](https://www.youtube.com/watch?v=YXn8Q_Hpsu4&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=106) | Phần DR cần liên hệ nhiều với tình huống thực tế. |
| 12/05/2026 | Nghiên cứu AWS Cost Explorer API, Billing API và kiến trúc dashboard quản lý AWS. | Hiểu cách lấy dữ liệu chi phí qua `GetCostAndUsage`, phân biệt Cost Explorer API với Billing API và phác thảo backend layer cho dashboard. | [AWS Cost Management API](https://docs.aws.amazon.com/aws-cost-management/latest/APIReference/Welcome.html) | Bắt đầu có hướng cho dashboard theo dõi chi phí. |
| 13/05/2026 | Nghiên cứu IAM API và mô hình phân quyền cho dashboard. | Biết cách liệt kê users, groups, policies và roles qua IAM API. Ghi chú lại nguyên tắc chỉ dùng quyền read-only nếu dashboard chỉ phục vụ quan sát. | [IAM API Reference](https://docs.aws.amazon.com/IAM/latest/APIReference/Welcome.html) | Cần cẩn thận với phạm vi quyền IAM. |
| 14/05/2026 | Xem lại Event 1: Proptimizer Extension, BMAD methodology và tối ưu chi phí AWS. | Nắm được cách dùng prompt có cấu trúc hơn, cách BMAD hỗ trợ chia nhỏ yêu cầu và một số hướng tối ưu chi phí khi làm việc với AWS. | [Bài Thu Hoạch Event 1](/4-eventparticipated/4.1-event1/) | Liên hệ với workflow học và làm lab. |
| 15/05/2026 | Viết bài thu hoạch Event 1 và tổng hợp ghi chú trong tuần. | Hoàn thành bài thu hoạch, gom lại các ý chính về Prompt Engineering, BMAD và cách áp dụng vào quá trình học/làm dự án. | [Bài Thu Hoạch Event 1](/4-eventparticipated/4.1-event1/) | Kết thúc tuần bằng phần tổng hợp. |

---

## Ghi chú trong tuần

Tuần này không chỉ học thêm dịch vụ AWS mà còn bắt đầu nghĩ về cách lấy dữ liệu từ AWS API để làm dashboard quản lý. Phần này khá thú vị vì nó nối giữa kiến thức cloud và hướng xây dựng sản phẩm thực tế.

Với Cost Explorer và IAM API, mình thấy rõ việc dùng API không chỉ là gọi endpoint. Cần hiểu quyền truy cập, giới hạn dữ liệu trả về, cách gom dữ liệu theo thời gian và cách hiển thị sao cho người dùng dễ đọc.

---

## Khó khăn gặp phải

* Các chiến lược Disaster Recovery dễ bị nhầm nếu chỉ nhớ tên, cần so sánh bằng RTO và RPO.
* Cost Explorer API và Billing API có phạm vi khác nhau, phải đọc tài liệu để hiểu dữ liệu nào lấy từ đâu.
* IAM API liên quan trực tiếp đến quyền truy cập nên cần cẩn thận khi nghĩ đến thiết kế dashboard.
* Nội dung Event 1 có nhiều ý mới như Proptimizer và BMAD, cần tổng hợp lại theo cách có thể áp dụng vào workflow cá nhân.

---

## Kiến thức rút ra

* Disaster Recovery nên được đánh giá bằng RTO/RPO thay vì chỉ nhìn tên mô hình.
* Cost Explorer API phù hợp để lấy dữ liệu chi phí theo ngày, service hoặc tag.
* Dashboard quản lý AWS nên bắt đầu với quyền read-only để giảm rủi ro.
* Prompt Engineering và BMAD hữu ích khi cần chia nhỏ yêu cầu trước khi triển khai.
