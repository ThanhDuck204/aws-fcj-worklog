---
title: "Worklog Tuần 10"
date: 2026-06-22
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

## Mục tiêu tuần 10

* Tiếp tục phát triển dự án nhóm và hoàn thiện các chức năng đang làm dở.
* Bắt đầu tích hợp dịch vụ AWS vào dự án theo kiến trúc đã thống nhất.
* Điều chỉnh dự án cho khớp với dịch vụ và kiến trúc đã thiết kế.
* Tham gia sự kiện của công ty vào cuối tuần.

---

## Công việc đã thực hiện

| Ngày | Công việc | Kết quả | Tài liệu | Ghi chú |
|---|---|---|---|---|
| 22/06/2026 | Tiếp tục làm dự án nhóm. | Hoàn thiện các phần code đang dang dở, rà soát lại các chức năng hiện tại và chuẩn bị codebase cho việc tích hợp AWS. Đảm bảo mọi thứ sẵn sàng trước khi bắt đầu gắn dịch vụ. | [GitHub Worklog](https://github.com/NTL0210/FACJ_Worklog) | Chuẩn bị tích hợp |
| 23/06/2026 | Bắt đầu gắn dịch vụ AWS vào dự án. | Tìm hiểu và triển khai các bước đầu tiên để tích hợp AWS services như Cognito, DynamoDB, và S3 vào dự án theo kiến trúc đã thiết kế. Thiết lập cấu hình và kết nối cơ bản. | [AWS Study Group YouTube](https://www.youtube.com/@AWSStudyGroup) <br> [Cloud Journey](https://cloudjourney.awsstudygroup.com/) <br> [GitHub Worklog](https://github.com/NTL0210/FACJ_Worklog) | Tích hợp AWS |
| 24/06/2026 | Nghỉ - lý do sức khỏe. | Không có hoạt động học tập. | Không có | Nghỉ sức khỏe |
| 25/06/2026 | Tiếp tục gắn dịch vụ AWS vào dự án. | Triển khai thêm các kết nối AWS, xử lý authentication với Cognito, cấu hình storage với S3, và tích hợp database với DynamoDB. Xử lý các lỗi phát sinh trong quá trình kết nối. | [AWS Study Group YouTube](https://www.youtube.com/@AWSStudyGroup) <br> [Cloud Journey](https://cloudjourney.awsstudygroup.com/) <br> [GitHub Worklog](https://github.com/NTL0210/FACJ_Worklog) | Tích hợp AWS |
| 26/06/2026 | Điều chỉnh dự án cho khớp với dịch vụ và kiến trúc. | Rà soát lại toàn bộ kiến trúc dự án, điều chỉnh code và cấu hình để phù hợp với các dịch vụ AWS đã gắn. Đã gắn được một phần dịch vụ AWS thành công — các kết nối cơ bản đã hoạt động và sẵn sàng cho các bước tiếp theo. | [AWS Study Group YouTube](https://www.youtube.com/@AWSStudyGroup) <br> [Cloud Journey](https://cloudjourney.awsstudygroup.com/) <br> [GitHub Worklog](https://github.com/NTL0210/FACJ_Worklog) | Điều chỉnh & đồng bộ |
| 27/06/2026 | Lên công ty tham gia sự kiện. | Tham gia sự kiện do công ty tổ chức, kết nối với đồng nghiệp, học hỏi kinh nghiệm từ các buổi chia sẻ và mở rộng mạng lưới quan hệ chuyên môn. | [Thư viện ảnh Event 4](#thu-vien-anh-event-4) | Sự kiện công ty |

---

## Ghi chí trong tuần

Tuần này đánh dấu bước chuyển quan trọng khi bắt đầu gắn dịch vụ AWS thật vào dự án. Sau nhiều tuần thiết kế kiến trúc, học lý thuyết và chuẩn bị, đây là lúc đưa những kiến thức đó vào thực tế.

Việc tích hợp AWS Cognito cho authentication, S3 cho storage, và DynamoDB cho database là những bước đầu tiên. Tuy nhiên, quá trình này không hoàn toàn suôn sẻ — có nhiều lỗi phát sinh khi kết nối, cần debug và điều chỉnh cấu hình nhiều lần. Dù vậy, đến cuối tuần mình đã gắn được một phần dịch vụ AWS, các kết nối cơ bản đã hoạt động ổn.

Giữa tuần mình nghỉ một ngày vì lý do sức khỏe, nên tiến độ có chậm lại đôi chút nhưng vẫn ổn.

Cuối tuần, mình lên công ty tham gia sự kiện — một dịp tốt để giao lưu, học hỏi và nạp lại năng lượng sau những ngày làm việc căng thẳng.

---

## Khó khăn gặp phải

* Khi bắt đầu tích hợp AWS services, việc cấu hình kết nối và xử lý lỗi phát sinh khá phức tạp, cần kiên nhẫn debug từng bước.
* Điều chỉnh codebase cho phù hợp với kiến trúc mới có AWS service đòi hỏi phải rà soát lại nhiều phần — từ cấu hình, xử lý dữ liệu, đến luồng hoạt động tổng thể.
* Một ngày nghỉ giữa tuần vì sức khỏe khiến tiến độ bị gián đoạn, cần bắt kịp vào các ngày sau.
* Việc tích hợp dịch vụ thực tế khác xa so với chạy mock — có nhiều edge case và lỗi môi trường không lường trước được.

---

## Kiến thức rút ra

* Tích hợp AWS services vào dự án thực tế cho thấy sự khác biệt rõ rệt giữa chạy với mock service và chạy với service thật.
* Cần kiên nhẫn khi xử lý lỗi kết nối — phần lớn lỗi đến từ cấu hình sai hoặc thiếu quyền truy cập (IAM permissions).
* Cognito giúp xử lý authentication nhanh chóng, nhưng cần hiểu rõ flow để tích hợp đúng.
* DynamoDB với thiết kế NoSQL phù hợp cho MVP, nhưng cần thiết kế table và query patterns cẩn thận ngay từ đầu.
* Việc kết hợp nhiều AWS services đòi hỏi phải có cái nhìn tổng thể về kiến trúc để tránh xung đột cấu hình.
* Các sự kiện công ty là cơ hội tốt để học hỏi kinh nghiệm thực tế và mở rộng mạng lưới quan hệ.

---

## Thư viện ảnh Event 4

![Event 4 - Ảnh 1](/images/Event/event4_1.jpg)

![Event 4 - Ảnh 2](/images/Event/event4_2.jpg)

![Event 4 - Ảnh 3](/images/Event/event4_3.jpg)
