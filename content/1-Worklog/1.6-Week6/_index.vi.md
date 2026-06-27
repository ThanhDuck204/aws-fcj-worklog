---
title: "Worklog Tuần 6"
date: 2026-05-25
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

## Mục tiêu tuần 6

* Tiếp tục các lab còn lại của Module 05 về IAM, permission boundary, KMS và role-based access.
* Thực hành Lab 28, Lab 30 và Lab 33 ở mức phù hợp với tài khoản học tập.
* Nghiên cứu Lab 44 và Lab 48 để hiểu thêm về IAM Role, condition và cách cấp quyền cho ứng dụng.
* Bắt đầu Module 06 về database, Redshift và ElastiCache.

---

## Công việc đã thực hiện

| Ngày | Công việc | Kết quả | Tài liệu | Ghi chú |
|---|---|---|---|---|
| 26/05/2026 | Thực hành Lab 28 về quản lý quyền EC2 bằng Resource Tags và tìm hiểu Lab 30 về Permission Boundary. | Lab 28 làm được các bước tạo policy/role nhưng bị lỗi khi cập nhật role policy. Lab 30 hoàn thành phần tạo policy giới hạn quyền theo Region và đọc tiếp các bước còn lại. | [Lab 28](https://000028.awsstudygroup.com/) <br> [Lab 30](https://000030.awsstudygroup.com/vi/1-introduce/) | Ghi lại lỗi để kiểm tra lại policy JSON và trust relationship. |
| 26/05/2026 | Thực hành Lab 33: mã hóa dữ liệu at rest bằng AWS KMS. | Tạo IAM resources, KMS key, S3 bucket mã hóa KMS, CloudTrail và Athena. Kiểm thử truy cập dữ liệu mã hóa để hiểu mối liên hệ giữa quyền S3 và quyền KMS. | [Lab 33 - Encrypt at rest with AWS KMS](https://000033.awsstudygroup.com/1-introduce/) | Hoàn thành các bước chính. |
| 27/05/2026 | Nghiên cứu Lab 44, Lab 48 và bắt đầu Module 06-01. | Đọc luồng assume role, condition theo IP/thời gian và cách gắn IAM Role cho EC2 thay vì hardcode access key. Sau đó học lại các khái niệm database nền tảng. | [Lab 44](https://000044.awsstudygroup.com/vi/1-iam-intro/) <br> [Lab 48](https://000048.awsstudygroup.com/vi/1-prepare/) <br> [Module 06-01](https://www.youtube.com/watch?v=OOD2RwWuLRw&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=217) | Lab 44/48 chỉ nghiên cứu để tránh tạo quá nhiều quyền và tài nguyên. |
| 29/05/2026 | Học Module 06-03 về Redshift và ElastiCache. | Hiểu Redshift cho OLAP/data warehouse, kiến trúc MPP và columnar storage. Với ElastiCache, nắm cách Redis/Memcached giúp giảm tải database và tăng tốc ứng dụng. | [Module 06-03 - Redshift - ElastiCache](https://www.youtube.com/watch?v=UvdiRW34aNI&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=219&t=145s) | Tập trung lý thuyết và use case, chưa tạo cluster thật. |
| 30/05/2026 | Nghỉ cá nhân. | Không có hoạt động học tập trong ngày. |  | Nghỉ. |

---

## Ghi chú trong tuần

Tuần này có khá nhiều nội dung IAM nâng cao. Phần khó nhất là policy condition vì chỉ cần sai một key hoặc thiếu trust relationship thì role sẽ không hoạt động như mong muốn.

Lab 33 là phần thực hành rõ nhất trong tuần. Khi mã hóa file trên S3 bằng KMS, mình thấy quyền truy cập không chỉ phụ thuộc vào bucket policy mà còn phụ thuộc vào quyền sử dụng KMS key. Đây là điểm rất dễ bỏ sót nếu chỉ nhìn S3.

Phần Module 06 giúp chuyển dần từ bảo mật sang database. Redshift và ElastiCache có mục đích rất khác nhau: một bên phục vụ phân tích dữ liệu lớn, một bên dùng để cache dữ liệu truy cập thường xuyên.

---

## Khó khăn gặp phải

* Lab 28 bị dừng ở bước cập nhật role policy, cần kiểm tra lại JSON policy, ARN và trust relationship.
* IAM Permission Boundary dễ hiểu sai thành một loại policy cấp quyền, trong khi thực tế nó chỉ giới hạn trần quyền tối đa.
* Khi dùng KMS với S3, nếu thiếu quyền decrypt trên KMS key thì có quyền S3 vẫn chưa đủ để đọc dữ liệu.
* Lab 44 và Lab 48 có rủi ro tạo nhiều IAM user, role, access key và tài nguyên EC2/S3 nên chỉ nghiên cứu thay vì triển khai toàn bộ.
* Redshift và ElastiCache có nhiều khái niệm mới như MPP, columnar storage, cache miss và cache invalidation nên cần ghi chú theo use case.

---

## Kiến thức rút ra

* IAM condition mạnh nhưng cần kiểm tra kỹ cú pháp policy, ARN và trust relationship.
* Permission Boundary không tự cấp quyền, mà chỉ giới hạn mức quyền tối đa của user/role.
* Khi dùng KMS với S3, phải xét cả quyền đọc object và quyền dùng key để decrypt.
* IAM Role trên EC2 an toàn hơn access key cố định trong code.
* Redshift phù hợp cho OLAP/data warehouse, không phải database giao dịch thay thế RDS.
* ElastiCache chỉ hiệu quả khi có chiến lược cache rõ ràng: cache gì, TTL bao lâu và khi nào invalidate.

---

## Hình ảnh thực hành

### Lab 28 – Quản lý quyền truy cập EC2 bằng Resource Tags thông qua IAM

![Lab28 Create Admin group and add IAM users](/images/Worklog-week6/Lab28-Create%20Admin%20group%20and%20add%20IAM%20users.png)

![Lab28 Create policies](/images/Worklog-week6/Lab28-Create%20policies.png)

![Lab28 Create IAM Role with policies](/images/Worklog-week6/Lab28-Create%20an%20IAM%20Role%20with%20the%20policies%20that%20were%20just%20created..png)

### Lab 30 – IAM Permission Boundary

![Lab30 Create policy limited](/images/Worklog-week6/Lab30-Create%20policty%20limited.png)

### Lab 33 – Encrypt at rest with AWS KMS

![Lab33 Create roles and policy](/images/Worklog-week6/Lab33-Create%20roles%20and%20policy.png)

![Lab33 Create Group and user with role S3](/images/Worklog-week6/Lab33-Create%20Group%20and%20user%20with%20role%20S3.png)

![Lab33 Create KMS Key](/images/Worklog-week6/Lab33-Create%20KMS%20Key.png)

![Lab33 Create S3 kms key](/images/Worklog-week6/Lab33-Create%20S3%20kms%20key.png)

![Lab33 Upload data to S3](/images/Worklog-week6/Lab33-Upload%20data%20to%20S3.png)

![Lab33 Create CloudTrail](/images/Worklog-week6/Lab33-Create%20Cloudtrail.png)

![Lab33 Logging to CloudTrail](/images/Worklog-week6/Lab33-Logging%20to%20CloudTrail.png)

![Lab33 Create Amazon Athena](/images/Worklog-week6/Lab33-Create%20Amazon%20Athena.png)

![Lab33 Retrieve data with Athena](/images/Worklog-week6/Lab33-Retrieve%20data%20with%20Athena.png)

![Lab33 Test and share encrypted data on S3](/images/Worklog-week6/Lab33-Test%20and%20share%20encrypted%20data%20on%20S3.png)
