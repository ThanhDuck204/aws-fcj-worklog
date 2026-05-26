---
title: "Worklog Tuần 6"
date: 2026-05-25
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

## Mục tiêu tuần 6

* Tiếp tục thực hành các bài lab AWS liên quan đến IAM, EC2 và quản lý quyền truy cập theo điều kiện.
* Tìm hiểu cách dùng IAM Policy, IAM Role và Resource Tags để giới hạn quyền thao tác với EC2.
* Thực hành Lab 28: quản lý quyền truy cập EC2 bằng Resource Tags thông qua IAM Services.
* Tìm hiểu Lab 30: giới hạn quyền IAM user bằng IAM Permission Boundary.
* Thực hành Lab 33: mã hóa dữ liệu S3 bằng AWS KMS và theo dõi hoạt động bằng CloudTrail, Athena.

---

## Công việc đã thực hiện

| Ngày | Công việc | Kết quả | Tài liệu | Ghi chú |
|---|---|---|---|---|
| 26/05/2026 | Thực hành Lab 28 và tìm hiểu Lab 30. | Lab 28 hoàn thành khoảng một nửa; Lab 30 làm được phần Create Policy và xem qua các phần còn lại. | [Lab 28 - EC2 Service Access Management with Resource Tags through IAM Services](https://000028.awsstudygroup.com/) <br> [Lab 30 - IAM Permission Boundary](https://000030.awsstudygroup.com/vi/1-introduce/) | Lab 28 lỗi update role policy; Lab 30 có vài mục Console không thấy/khác hướng dẫn. |
| 26/05/2026 | Thực hành Lab 33: Encrypt at rest with AWS KMS. | Tạo IAM resources, KMS key, S3 bucket mã hóa KMS, CloudTrail, Athena và kiểm thử chia sẻ dữ liệu mã hóa. | [Lab 33 - Encrypt at rest with AWS KMS](https://000033.awsstudygroup.com/1-introduce/) | Hoàn thành các bước chính. |

---

## Nội dung Lab 28

Lab 28 tập trung vào việc kiểm soát quyền truy cập EC2 bằng Resource Tags thông qua IAM. Bài lab dùng nguyên tắc Least Privilege và IAM policy conditions để chỉ cho phép người dùng thao tác với EC2 khi đáp ứng đúng điều kiện về Region và tag.

### 1. Introduction

* Tìm hiểu mục tiêu của bài lab: quản lý quyền truy cập EC2 theo tag thay vì cấp quyền rộng trên toàn bộ tài nguyên.
* Nắm cách Resource Tags hỗ trợ mô hình quản trị phân quyền, đặc biệt khi cần tách quyền theo team hoặc nhóm vận hành.
* Điều kiện chính trong bài lab là tag `Team=Alpha` và các AWS Region được phép như `us-east-1`, `us-west-1`.

### 2. Preparation

* Chuẩn bị AWS Account dùng để thực hành.
* Tạo IAM user có bật MFA để có thể thực hiện thao tác assume role.
* Xác định tài khoản cần có nhiều hơn một Region để kiểm thử điều kiện truy cập theo Region.

### 3. Create IAM Policy

* Tạo 5 IAM policies phục vụ kiểm soát quyền EC2:
  * `ec2-list-read`: cho phép đọc/thống kê EC2 trong các Region được chỉ định.
  * `ec2-create-tags`: cho phép tạo tag trong lúc tạo EC2 instance.
  * `ec2-create-tags-existing`: cho phép gắn tag cho tài nguyên EC2 hiện có nếu thỏa điều kiện tag.
  * `ec2-run-instances`: cho phép tạo EC2 instance khi thỏa điều kiện Region và tag `Team=Alpha`.
  * `ec2-manage-instances`: cho phép start, stop, reboot, terminate EC2 instance khi tài nguyên có tag phù hợp.
* Phần này giúp hiểu cách dùng condition key như `aws:RequestedRegion`, `aws:RequestTag`, `aws:TagKeys` và `ec2:ResourceTag`.

### 4. Create IAM Role

* Tạo IAM Role cho nhóm EC2 Administrator, ví dụ `ec2-admin-team-alpha`.
* Gắn 5 policy đã tạo vào role để role có đúng phạm vi quyền cần thiết.
* Cấu hình trust relationship để IAM user có thể assume role, đồng thời yêu cầu MFA theo best practice.
* Trạng thái thực hành hiện tại: đã đi đến phần tạo/cập nhật role policy nhưng gặp lỗi khi update policy nên chưa hoàn tất toàn bộ bước này.

### 5. Check Policy

* Phần kiểm thử dự kiến dùng switch role để xác nhận policy hoạt động đúng.
* Các tình huống cần kiểm tra gồm:
  * Truy cập Region không được phép.
  * Truy cập Region được phép.
  * Tạo EC2 khi thiếu tag hoặc tag không đúng điều kiện.
  * Chỉnh sửa tag trên EC2 instance.
  * Thao tác quản lý EC2 như start, stop, reboot, terminate với tag hợp lệ.
* Do lỗi ở bước update role policy, phần kiểm thử policy chưa hoàn thành.


---

## Nội dung Lab 30

Lab 30 tập trung vào **IAM Permission Boundary**, một cơ chế dùng để giới hạn quyền tối đa mà IAM user có thể có. Bài lab minh họa trường hợp user được gán quyền `AmazonEC2FullAccess`, nhưng vẫn bị giới hạn chỉ được quản trị EC2 trong Region được chỉ định thông qua permission boundary.

### 1. Giới thiệu

* Tìm hiểu IAM Permission Boundary và vai trò của nó trong việc giới hạn quyền tối đa cho IAM user hoặc group.
* Nắm khái niệm effective permissions: quyền thực tế của user là phần giao giữa identity-based policy và permission boundary.
* Hiểu lý do cần Permission Boundary để giảm rủi ro privilege escalation khi hệ thống có nhiều user và nhiều policy thay đổi liên tục.

### 2. Các bước chuẩn bị

* Chuẩn bị AWS Account có thể sử dụng IAM.
* Xác định bài lab sẽ thao tác chủ yếu trên IAM Management Console và kiểm thử quyền truy cập EC2 theo Region.

### 3. Tạo Policy Giới hạn

* Tạo policy `ec2-admin-restrict-region` để giới hạn quyền tối đa của user.
* Nội dung policy cho phép thao tác `ec2:*` nhưng chỉ khi request được thực hiện ở Region `ap-southeast-1`.
* Trạng thái thực hành hiện tại: đã làm được đến bước Create Policy và hiểu cách policy dùng condition `aws:RequestedRegion` để giới hạn phạm vi quyền.

### 4. Tạo IAM User Giới Hạn

* Bài lab hướng dẫn tạo IAM user `ec2-admin`, gán quyền `AmazonEC2FullAccess`, sau đó áp permission boundary `ec2-admin-restrict-region`.
* Phần này chỉ xem qua vì trong AWS Console có vài mục không thấy hoặc khác với ảnh/chỉ dẫn trong bài lab, nên không thể tiếp tục làm theo đúng từng bước hướng dẫn.

### 5. Kiểm tra IAM User Giới Hạn

* Phần kiểm thử dự kiến đăng nhập bằng user `ec2-admin`, vào EC2 ở Region Singapore `ap-southeast-1` để xác nhận quyền hoạt động bình thường.
* Sau đó chuyển sang Region Sydney `ap-southeast-2` để kiểm tra việc user bị chặn quyền EC2 do permission boundary.
* Phần này chưa thực hành trực tiếp, nhưng đã xem qua để hiểu permission boundary vẫn giới hạn quyền ngay cả khi user có policy quyền cao hơn.

### 6. Dọn dẹp tài nguyên

* Sau bài lab cần xóa IAM user `ec2-admin` và policy `ec2-admin-restrict-region`.
* Phần cleanup chưa thực hiện vì các bước tạo user và kiểm thử chưa được triển khai trực tiếp.

---

## Nội dung Lab 33

Lab 33 tập trung vào **mã hóa dữ liệu at rest với AWS KMS**, lưu trữ dữ liệu trên **Amazon S3**, ghi nhận hoạt động bằng **AWS CloudTrail** và truy vấn log bằng **Amazon Athena**.

* **1. Introduction**: Tìm hiểu vai trò của KMS, S3, CloudTrail và Athena trong bảo mật dữ liệu, lưu trữ và kiểm tra hoạt động.
* **2. Preparation steps**: Tạo policy/role, group và user để phân quyền thao tác với KMS, S3, CloudTrail, Athena.
* **3. Create Key Management Service**: Tạo KMS key để dùng làm khóa mã hóa dữ liệu.
* **4. Create Amazon S3**: Tạo bucket S3, bật mã hóa bằng KMS key và upload dữ liệu kiểm thử.
* **5. Create AWS CloudTrail and Amazon Athena**: Tạo trail để ghi log hoạt động, sau đó dùng Athena truy vấn dữ liệu log lưu trên S3.
* **6. Test and share encrypted data on S3**: Kiểm thử truy cập/chia sẻ file đã mã hóa để hiểu cách quyền KMS ảnh hưởng đến việc đọc dữ liệu.
* **7. Resource cleanup**: Dọn dẹp S3 bucket, KMS key, CloudTrail, Athena output và IAM resources sau khi hoàn thành.

---

## Kiến thức & kỹ năng đạt được

* Hiểu rõ hơn cách IAM policy condition giúp giới hạn quyền theo Region và Resource Tags.
* Biết cách tách quyền EC2 thành nhiều policy nhỏ theo từng nhóm hành động: đọc, tạo tag, tạo instance và quản lý instance.
* Nhận ra Resource Tags không chỉ dùng để quản lý tài nguyên mà còn có thể trở thành điều kiện kiểm soát truy cập.
* Hiểu vai trò của IAM Role và trust relationship trong quy trình assume role giữa IAM user và quyền quản trị EC2 giới hạn.
* Hiểu thêm cách IAM Permission Boundary giới hạn quyền tối đa của user, kể cả khi user được gán identity-based policy có quyền rộng hơn.
* Nắm được luồng mã hóa dữ liệu S3 bằng KMS, ghi log bằng CloudTrail và truy vấn log bằng Athena.

---

## Khó khăn gặp phải & Cách khắc phục

* **Lỗi khi update role policy**: Quá trình cập nhật policy/trust relationship cho IAM Role chưa thành công, khiến bài lab dừng trước phần switch role và kiểm thử policy.
* **Chưa kiểm thử được toàn bộ điều kiện IAM**: Vì role policy chưa cập nhật đúng, chưa thể xác nhận các case như Region bị chặn, tag không hợp lệ hoặc thao tác EC2 với tag `Team=Alpha`.
* **AWS Console khác với bài hướng dẫn Lab 30**: Khi thực hành có vài mục trong AWS Console không thấy hoặc khác với ảnh trong bài lab, nên chỉ làm được đến phần Create Policy và xem qua các bước còn lại để hiểu luồng hoạt động.
* **Hướng xử lý tiếp theo**: Kiểm tra lại JSON policy, ARN của IAM user, điều kiện MFA trong trust policy và danh sách policy đã attach vào role trước khi tiếp tục phần check policy.

---

## Bài học rút ra

* Khi dùng IAM condition, chỉ cần sai một key hoặc sai định dạng JSON policy thì role có thể không hoạt động như mong muốn.
* Việc chia nhỏ policy giúp dễ đọc và dễ debug hơn khi một quyền EC2 không chạy đúng.
* Cần kiểm tra kỹ trust relationship trước khi switch role, đặc biệt khi có điều kiện MFA.
* Permission Boundary không tự cấp quyền, mà chỉ đặt trần quyền tối đa cho user; quyền thực tế vẫn phụ thuộc vào cả identity-based policy và boundary.
* Khi mã hóa S3 bằng KMS, quyền truy cập file không chỉ phụ thuộc vào S3 policy mà còn phụ thuộc vào quyền sử dụng KMS key.

---

## Hình ảnh thực hành

> Lab 28 mới hoàn thành một phần và đang dừng ở lỗi update role policy, nên phần hình ảnh ghi nhận các bước đã thực hiện.

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
