---
title: "Worklog Tuần 3"
date: 2026-05-04
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

## Mục tiêu tuần 3

* Bắt đầu Module 03 về Compute trên AWS.
* Hiểu các khái niệm chính của EC2 như instance type, AMI, key pair, user data, metadata và Auto Scaling.
* Thực hành AWS Backup, Storage Gateway và S3 static website.
* Chuẩn bị kiến thức nền để chuyển sang Module 04 về Storage.

---

## Công việc đã thực hiện

| Ngày | Công việc | Kết quả | Tài liệu | Ghi chú |
|---|---|---|---|---|
| 04/05/2026 | Học lý thuyết EC2: instance type, AMI, key pair và pricing model. | Hiểu cách chọn instance theo CPU/RAM/network, cách AMI ảnh hưởng đến hệ điều hành và cấu hình ban đầu. So sánh sơ bộ On-Demand, Reserved, Savings Plans và Spot. | [Cloud Journey](https://cloudjourney.awsstudygroup.com/) | Đây là nền tảng của phần Compute. |
| 05/05/2026 | Tìm hiểu EC2 User Data, EC2 Metadata và EC2 Auto Scaling. | Biết cách dùng user data để bootstrap server khi khởi tạo instance. Hiểu metadata endpoint và ý tưởng scale out/scale in dựa trên nhu cầu tải. | [Cloud Journey](https://cloudjourney.awsstudygroup.com/) | Ghi chú thêm vì các phần này hay dùng trong automation. |
| 06/05/2026 | Hoàn thành Lab 13 về AWS Backup, SNS và kiểm thử restore. | Triển khai được hạ tầng AWS Backup, cấu hình SNS để nhận cảnh báo và kiểm thử quy trình restore thông qua Lambda. | [AWS Backup Lab](https://000013.awsstudygroup.com/) | Lab này giúp hiểu backup không chỉ là tạo bản sao, mà còn phải kiểm thử khôi phục. |
| 07/05/2026 | Tìm hiểu Storage Gateway, S3 Static Website và CloudFront. | Hiểu cách Storage Gateway hỗ trợ hybrid storage. Thực hành host website tĩnh trên S3, kết hợp versioning và CloudFront/OAC để truy cập an toàn hơn. | [Storage Gateway Workshop](https://000024.awsstudygroup.com/vi/3-cleanup/) <br> [S3 Static Website Workshop](https://000057.awsstudygroup.com/) | Hoàn thành Module 03. |
| 08/05/2026 | Bắt đầu học Module 04 về Storage. | Xem phần tổng quan storage trên AWS và học lại các khái niệm quan trọng của Amazon S3 trước khi đi sâu hơn ở tuần sau. | [Module 04-01 - Storage on AWS](https://www.youtube.com/watch?v=hsCfP0IxoaM&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=103) <br> [Module 04-02 - Amazon S3](https://www.youtube.com/watch?v=_yunukwcAwc&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=104) | Chuẩn bị cho tuần 4. |

---

## Ghi chú trong tuần

Tuần này giúp mình hiểu rõ hơn sự khác nhau giữa compute và storage trong AWS. EC2 là phần dễ tiếp cận vì giống máy chủ truyền thống, nhưng khi thêm user data, metadata và Auto Scaling thì cách vận hành bắt đầu khác nhiều so với tự quản lý server thủ công.

Phần AWS Backup cũng khá thực tế. Mình nhận ra backup chỉ có ý nghĩa khi có quy trình restore rõ ràng và đã được kiểm thử, không chỉ đơn giản là bật một plan rồi để đó.

---

## Khó khăn gặp phải

* EC2 có nhiều lựa chọn instance type và pricing model, cần so sánh theo workload chứ không thể chọn đại.
* Phần User Data và Metadata ban đầu hơi khó hình dung vì liên quan đến automation lúc instance vừa khởi tạo.
* Lab AWS Backup yêu cầu nhiều quyền IAM và nhiều tài nguyên nên phải đọc kỹ từng bước trước khi chạy.
* Storage Gateway không thể thực hành đầy đủ trong tài khoản học tập, nên phải bù bằng cách đọc tài liệu và ghi lại kiến trúc.

---

## Kiến thức rút ra

* Chọn instance type cần dựa vào workload, không chỉ chọn theo giá thấp nhất.
* User Data hữu ích cho việc tự động cấu hình server lúc khởi tạo.
* AWS Backup cần đi kèm kiểm thử restore để chắc chắn dữ liệu dùng lại được.
* S3 static website và CloudFront giúp thấy rõ cách storage có thể tham gia trực tiếp vào kiến trúc ứng dụng.
