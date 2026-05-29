---
title: "Worklog Tuần 6"
date: 2026-05-25
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

## Mục tiêu tuần 6

* Tiếp tục hoàn thành các bài lab còn lại của Module 05 liên quan đến IAM, EC2 và quản lý quyền truy cập theo điều kiện.
* Tìm hiểu cách dùng IAM Policy, IAM Role và Resource Tags để giới hạn quyền thao tác với EC2.
* Thực hành Lab 28: quản lý quyền truy cập EC2 bằng Resource Tags thông qua IAM Services.
* Tìm hiểu Lab 30: giới hạn quyền IAM user bằng IAM Permission Boundary.
* Thực hành Lab 33: mã hóa dữ liệu S3 bằng AWS KMS và theo dõi hoạt động bằng CloudTrail, Athena.
* Nghiên cứu Lab 44: IAM Role & Condition, tập trung vào assume role và điều kiện truy cập theo IP/thời gian.
* Nghiên cứu Lab 48: cấp quyền cho ứng dụng truy cập AWS service bằng IAM Role thay vì dùng access key trực tiếp.
* Sau khi xử lý nốt phần lab Module 05 trong ngày thứ 4, bắt đầu học Module 06-01 về các khái niệm nền tảng database.
* Tiếp tục học lý thuyết Module 06, tập trung vào Amazon Redshift và Amazon ElastiCache để hiểu nhóm dịch vụ phân tích dữ liệu và tối ưu hiệu năng ứng dụng.

---

## Công việc đã thực hiện

| Ngày | Công việc | Kết quả | Tài liệu | Ghi chú |
|---|---|---|---|---|
| 26/05/2026 | Thực hành Lab 28 và tìm hiểu Lab 30. | Lab 28 hoàn thành khoảng một nửa; Lab 30 làm được phần Create Policy và xem qua các phần còn lại. | [Lab 28 - EC2 Service Access Management with Resource Tags through IAM Services](https://000028.awsstudygroup.com/) <br> [Lab 30 - IAM Permission Boundary](https://000030.awsstudygroup.com/vi/1-introduce/) | Lab 28 lỗi update role policy; Lab 30 có vài mục Console không thấy/khác hướng dẫn. |
| 26/05/2026 | Thực hành Lab 33: Encrypt at rest with AWS KMS. | Tạo IAM resources, KMS key, S3 bucket mã hóa KMS, CloudTrail, Athena và kiểm thử chia sẻ dữ liệu mã hóa. | [Lab 33 - Encrypt at rest with AWS KMS](https://000033.awsstudygroup.com/1-introduce/) | Hoàn thành các bước chính. |
| 27/05/2026 | Hoàn thành nốt phần lab Module 05 còn lại và bắt đầu học Module 06-01. | Nghiên cứu Lab 44, Lab 48 để hoàn tất nhóm lab Module 05; sau đó học video Database Concepts review để nắm nền tảng trước khi đi vào các dịch vụ database trên AWS. | [Lab 44 - IAM Role & Condition](https://000044.awsstudygroup.com/vi/1-iam-intro/) <br> [Lab 48 - Cấp quyền cho ứng dụng với IAM Role](https://000048.awsstudygroup.com/vi/1-prepare/) <br> [Module 06-01 - Database Concepts review](https://www.youtube.com/watch?v=OOD2RwWuLRw&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=217) | Lab 44/48 chỉ nghiên cứu vì cần nhiều IAM resources, EC2/S3 và có rủi ro quyền hoặc chi phí. |
| 29/05/2026 | Tiếp tục tìm hiểu lý thuyết Module 06 qua video Module 06-03: Redshift - ElastiCache. | Nắm được vai trò của Amazon Redshift trong data warehouse/OLAP, kiến trúc MPP, columnar storage, Redshift Spectrum; đồng thời hiểu Amazon ElastiCache dùng Redis/Memcached để caching dữ liệu, giảm tải database và tăng hiệu năng ứng dụng. | [Module 06-03 - Redshift - ElastiCache](https://www.youtube.com/watch?v=UvdiRW34aNI&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=219&t=145s) | Tập trung học lý thuyết, ghi chú kiến trúc và use case; chưa triển khai lab thực hành để tránh phát sinh tài nguyên. |
| 30/05/2026 | Nghỉ vì lý do cá nhân. | Không có hoạt động học tập. |  | Nghỉ cá nhân. |

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

## Nội dung Lab 44

Lab 44 tập trung vào **IAM Role & Condition**, giúp hiểu cách IAM user assume role và cách dùng trust policy condition để giới hạn quyền truy cập theo IP hoặc thời gian.

* **1. Giới thiệu về IAM**: Ôn lại IAM, request tới AWS service, chứng thực request và quá trình assume role.
* **2. Tạo IAM Group**: Tạo group `ec2-rds-admin-group` có quyền quản trị EC2/RDS.
* **3. Tạo IAM User**: Tạo các user như `EC2-admin-user`, `RDS-admin-user`, `Group-user`, `No-permission-user` và kiểm tra quyền từng user.
* **4. Cấu hình Role Condition**: Tạo role `lab44-RoleFullAccess`, cấu hình switch role và thêm condition để giới hạn truy cập theo IP/thời gian.
* **5. Dọn dẹp tài nguyên**: Xóa role, IAM users và user group sau khi kết thúc bài lab.

**Lý do chỉ nghiên cứu**: Bài lab yêu cầu tạo nhiều IAM user, gán quyền quản trị EC2/RDS và tạo role có `AdministratorAccess`; ngoài ra phần kiểm thử có thể cần tạo EC2/RDS. Vì vậy em chỉ đọc hiểu luồng hoạt động để tránh rủi ro cấp quyền quá rộng, cấu hình nhầm IAM và phát sinh tài nguyên không cần thiết.

---

## Nội dung Lab 48

Lab 48 tập trung vào cách **cấp quyền cho ứng dụng truy cập AWS service bằng IAM Role**, so sánh cách dùng access key với cách gắn IAM Role vào EC2 để ứng dụng upload file lên S3 an toàn hơn.

* **1. Chuẩn bị**: Tạo EC2 instance và S3 bucket làm môi trường cho ứng dụng upload object.
* **2. Sử dụng access key**: Tạo IAM user, access key/secret access key và dùng trong ứng dụng Python để upload file lên S3.
* **3. IAM Role trên EC2**: Tạo IAM Role, gắn role vào EC2 và để ứng dụng truy cập S3 thông qua temporary credentials thay vì hardcode key.
* **4. Dọn dẹp tài nguyên**: Xóa S3 bucket, EC2 instance, IAM user và IAM role sau khi hoàn thành.

**Lý do chỉ nghiên cứu**: Bài lab cần tạo EC2, S3 bucket, IAM user, access key và IAM Role. Em chỉ nghiên cứu để tránh phát sinh tài nguyên, tránh quản lý access key không cần thiết và giảm rủi ro lộ credential trong quá trình thử nghiệm.

---

## Nội dung Module 06-01

Video **Database Concepts review** thuộc chuỗi AWS First Cloud Journey, tập trung ôn các khái niệm database nền tảng trước khi học Amazon RDS, Aurora, ElastiCache và Redshift.

* **Database, Primary Key, Foreign Key**: Hiểu cơ sở dữ liệu là hệ thống lưu trữ thông tin có cấu trúc/bán cấu trúc; primary key định danh bản ghi, foreign key liên kết dữ liệu giữa các bảng.
* **Index và Partitioning**: Index giúp tăng tốc truy vấn đọc nhưng có thể tăng chi phí ghi/lưu trữ; partitioning chia bảng lớn thành các phần nhỏ để tối ưu truy vấn.
* **Log và Buffer**: Log hỗ trợ khôi phục, đồng bộ dữ liệu; buffer dùng RAM để tăng tốc truy cập dữ liệu thường dùng.
* **RDBMS và NoSQL**: RDBMS dùng bảng, SQL và normalization; NoSQL linh hoạt schema, dễ mở rộng ngang, gồm key-value, document, wide-column và graph.
* **OLTP và OLAP**: OLTP phục vụ giao dịch nhanh, cập nhật liên tục; OLAP phục vụ phân tích dữ liệu lịch sử trong data warehouse.

---

## Nội dung Module 06-03

Video **Redshift - ElastiCache** giới thiệu hai dịch vụ AWS managed service quan trọng trong Module 06: **Amazon Redshift** cho phân tích dữ liệu quy mô lớn và **Amazon ElastiCache** cho caching nhằm tối ưu hiệu năng ứng dụng.

### 1. Amazon Redshift

* **Tổng quan**: Amazon Redshift là dịch vụ data warehouse được quản lý bởi AWS, phù hợp với Big Data và các truy vấn OLAP phức tạp. Redshift dùng lõi PostgreSQL nhưng được tối ưu cho workload phân tích thay vì giao dịch OLTP.
* **Kiến trúc MPP**: Redshift sử dụng kiến trúc Massively Parallel Processing, trong đó Leader Node nhận truy vấn, lập kế hoạch và tổng hợp kết quả; Compute Nodes chịu trách nhiệm xử lý, lưu trữ và đọc dữ liệu theo từng phần được phân phối.
* **Columnar storage**: Dữ liệu được lưu theo cột thay vì theo dòng. Cách lưu trữ này phù hợp với truy vấn phân tích vì hệ thống chỉ cần đọc các cột liên quan, giúp giảm lượng dữ liệu phải scan và tăng tốc các truy vấn tổng hợp.
* **SQL và công cụ kết nối**: Redshift hỗ trợ SQL cùng các driver phổ biến như JDBC/ODBC, giúp kết nối với các BI tools hoặc SQL clients quen thuộc.
* **Tối ưu chi phí và hiệu năng**: Có thể dùng transient/cloned cluster để tăng năng lực xử lý trong giai đoạn nhu cầu cao. Ngoài ra, Redshift Spectrum cho phép truy vấn dữ liệu trực tiếp từ Amazon S3 mà không cần load toàn bộ dữ liệu vào cluster, giúp giảm chi phí lưu trữ và mở rộng phạm vi phân tích.

### 2. Amazon ElastiCache

* **Tổng quan**: Amazon ElastiCache là dịch vụ managed cache của AWS, hỗ trợ hai engine chính là Redis và Memcached để lưu dữ liệu trong RAM với độ trễ thấp.
* **Vị trí trong kiến trúc ứng dụng**: ElastiCache thường được đặt giữa application layer và database layer. Ứng dụng đọc dữ liệu thường xuyên từ cache trước, chỉ truy vấn database khi cache miss, từ đó giảm tải cho database.
* **Hiệu năng**: Vì dữ liệu được lưu trong bộ nhớ, cache giúp tăng tốc các thao tác đọc/ghi thường gặp, đặc biệt với dữ liệu được truy cập lặp lại như session, profile, cấu hình, kết quả truy vấn hoặc dữ liệu dashboard.
* **Quản lý node**: ElastiCache hỗ trợ phát hiện và thay thế node bị lỗi, giúp giảm phần vận hành hạ tầng so với tự dựng cache cluster.
* **Caching logic**: Dịch vụ chỉ cung cấp hạ tầng cache; developer vẫn phải quyết định dữ liệu nào cần cache, TTL bao lâu, khi nào invalidate cache và xử lý cache miss như thế nào. Đây là phần quan trọng để tránh dữ liệu stale hoặc cache không đem lại hiệu quả.

### 3. Định hướng học tiếp

* Ôn lại SQL cơ bản để hiểu rõ hơn cách truy vấn dữ liệu trong RDS, Redshift và các hệ thống data warehouse.
* Tìm hiểu thêm Amazon RDS, Database Migration Service (DMS) và Schema Conversion Tool (SCT) để nắm quy trình vận hành và migration database trên AWS.
* Tham khảo thêm các sách như **Database Internals** và **The Data Warehouse Toolkit** để hiểu sâu hơn về cơ chế lưu trữ, query processing và thiết kế data warehouse.

---

## Kiến thức & kỹ năng đạt được

* Hiểu rõ hơn cách IAM policy condition giúp giới hạn quyền theo Region và Resource Tags.
* Biết cách tách quyền EC2 thành nhiều policy nhỏ theo từng nhóm hành động: đọc, tạo tag, tạo instance và quản lý instance.
* Nhận ra Resource Tags không chỉ dùng để quản lý tài nguyên mà còn có thể trở thành điều kiện kiểm soát truy cập.
* Hiểu vai trò của IAM Role và trust relationship trong quy trình assume role giữa IAM user và quyền quản trị EC2 giới hạn.
* Hiểu thêm cách IAM Permission Boundary giới hạn quyền tối đa của user, kể cả khi user được gán identity-based policy có quyền rộng hơn.
* Nắm được luồng mã hóa dữ liệu S3 bằng KMS, ghi log bằng CloudTrail và truy vấn log bằng Athena.
* Hiểu thêm cách trust policy condition giới hạn assume role theo IP và thời gian trong IAM.
* Hiểu vì sao IAM Role trên EC2 an toàn hơn việc hardcode access key trong ứng dụng.
* Củng cố nền tảng database để chuẩn bị học các dịch vụ AWS Database như RDS, Aurora, ElastiCache và Redshift.
* Hiểu vai trò của Amazon Redshift trong bài toán data warehouse, OLAP và phân tích dữ liệu lớn.
* Nắm được kiến trúc MPP của Redshift với Leader Node, Compute Node và cách dữ liệu được xử lý song song.
* Phân biệt row-based storage và columnar storage, từ đó hiểu vì sao columnar storage phù hợp cho truy vấn phân tích.
* Hiểu cách Redshift Spectrum hỗ trợ truy vấn dữ liệu trên Amazon S3 mà không cần nạp toàn bộ dữ liệu vào cluster.
* Hiểu vai trò của Amazon ElastiCache trong việc caching dữ liệu bằng Redis/Memcached để giảm tải database và cải thiện độ trễ ứng dụng.
* Nhận ra caching logic là trách nhiệm của developer, bao gồm chọn dữ liệu để cache, đặt TTL và invalidate cache đúng thời điểm.

---

## Khó khăn gặp phải & Cách khắc phục

* **Lỗi khi update role policy**: Quá trình cập nhật policy/trust relationship cho IAM Role chưa thành công, khiến bài lab dừng trước phần switch role và kiểm thử policy.
* **Chưa kiểm thử được toàn bộ điều kiện IAM**: Vì role policy chưa cập nhật đúng, chưa thể xác nhận các case như Region bị chặn, tag không hợp lệ hoặc thao tác EC2 với tag `Team=Alpha`.
* **AWS Console khác với bài hướng dẫn Lab 30**: Khi thực hành có vài mục trong AWS Console không thấy hoặc khác với ảnh trong bài lab, nên chỉ làm được đến phần Create Policy và xem qua các bước còn lại để hiểu luồng hoạt động.
* **Không thực hành Lab 44 trực tiếp**: Bài lab dùng nhiều IAM user, quyền admin và có thể tạo EC2/RDS khi kiểm thử, nên chỉ nghiên cứu để tránh rủi ro phân quyền và chi phí.
* **Không thực hành Lab 48 trực tiếp**: Bài lab cần tạo EC2/S3 và access key, nên chỉ nghiên cứu để tránh phát sinh chi phí và rủi ro credential.
* **Module 06-03 chủ yếu là lý thuyết kiến trúc**: Redshift và ElastiCache có nhiều khái niệm mới như MPP, columnar storage, cache invalidation và cache miss, nên cần ghi chú lại theo từng use case để tránh nhầm giữa data warehouse, database giao dịch và cache.
* **Hướng xử lý tiếp theo**: Kiểm tra lại JSON policy, ARN của IAM user, điều kiện MFA trong trust policy và danh sách policy đã attach vào role trước khi tiếp tục phần check policy.

---

## Bài học rút ra

* Khi dùng IAM condition, chỉ cần sai một key hoặc sai định dạng JSON policy thì role có thể không hoạt động như mong muốn.
* Việc chia nhỏ policy giúp dễ đọc và dễ debug hơn khi một quyền EC2 không chạy đúng.
* Cần kiểm tra kỹ trust relationship trước khi switch role, đặc biệt khi có điều kiện MFA.
* Permission Boundary không tự cấp quyền, mà chỉ đặt trần quyền tối đa cho user; quyền thực tế vẫn phụ thuộc vào cả identity-based policy và boundary.
* Khi mã hóa S3 bằng KMS, quyền truy cập file không chỉ phụ thuộc vào S3 policy mà còn phụ thuộc vào quyền sử dụng KMS key.
* Khi cấu hình assume role, trust relationship quan trọng không kém permission policy vì nó quyết định ai được phép sử dụng role và trong điều kiện nào.
* Với ứng dụng chạy trên EC2, nên ưu tiên IAM Role để lấy temporary credentials thay vì lưu access key lâu dài trong code hoặc trên máy chủ.
* Trước khi chọn dịch vụ database trên AWS, cần hiểu workload thuộc OLTP hay OLAP và dữ liệu phù hợp RDBMS hay NoSQL.
* Redshift phù hợp cho phân tích dữ liệu và truy vấn OLAP, không nên xem nó như database giao dịch thay thế RDS.
* Columnar storage giúp truy vấn phân tích hiệu quả hơn vì chỉ đọc các cột cần thiết, đặc biệt khi tính tổng hợp hoặc lọc trên một số trường.
* ElastiCache giúp tăng tốc hệ thống nhưng không tự giải quyết toàn bộ bài toán hiệu năng; hiệu quả phụ thuộc nhiều vào cách thiết kế caching strategy trong ứng dụng.
* Khi dùng cache, cần luôn nghĩ đến vòng đời dữ liệu: dữ liệu nào được cache, cache trong bao lâu, khi nào làm mới và cách xử lý khi cache không còn đúng.

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
