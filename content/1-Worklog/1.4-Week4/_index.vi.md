```md id="week4-final"
---
title: "Worklog Tuần 4"
date: 2026-05-12
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

## Mục tiêu tuần 4

* Tiếp tục nghiên cứu Module 04 – Lưu trữ trên AWS (Storage).
* Nắm được các giải pháp chuyển đổi dữ liệu lớn (Cold Data Transfer) với Snow Family.
* Hiểu mô hình lưu trữ lai (Hybrid Storage) thông qua AWS Storage Gateway.
* Nắm được các chiến lược Disaster Recovery và triển khai AWS Backup tập trung.
* Tiếp tục nghiên cứu chuyên sâu các AWS API đã tìm hiểu từ giai đoạn đầu thực tập nhằm phục vụ định hướng phát triển AWS Management Dashboard cho project nội bộ.

---

## Công việc đã thực hiện

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2 | Tìm hiểu lý thuyết Module 04-04 – Snow Family, AWS Storage Gateway, Chiến lược Disaster Recovery và AWS Backup | 12/05/2026 | 12/05/2026 | |
| 3 | Nghiên cứu lại và đào sâu AWS Cost Explorer API, Billing API và kiến trúc dashboard nhằm chuẩn bị cho giai đoạn triển khai project quản lý AWS | 13/05/2026 | 13/05/2026 | https://docs.aws.amazon.com/aws-cost-management/latest/APIReference/Welcome.html |
| 4 | Tiếp tục nghiên cứu IAM Management API, mô hình phân quyền và khả năng theo dõi tài nguyên AWS phục vụ định hướng xây dựng dashboard quản lý tập trung | 14/05/2026 | 14/05/2026 | https://docs.aws.amazon.com/IAM/latest/APIReference/Welcome.html |
| 5 | Nghiên cứu công nghệ ứng dụng (Prompt Engineering, BMAD) từ Event cộng đồng và các giải pháp tối ưu chi phí sử dụng AWS | 15/05/2026 | 15/05/2026 | [Bài Thu Hoạch Event 1](/4-eventparticipated/4.1-event1/) |
| 6 | Off vì bận việc cá nhân | 16/05/2026 | 16/05/2026 | |

---

## Kiến thức & kỹ năng đạt được

### 1. Snow Family – Chuyển đổi dữ liệu lớn (Cold Data Transfer)

* **Nắm được bài toán thực tế**: Hiểu rõ giới hạn của băng thông Internet khi cần di chuyển dữ liệu quy mô Petabyte đến Exabyte – lý do ra đời của Snow Family.
* **Đã nghiên cứu Snowball**: Thiết bị vật lý chứa tối đa **80 TB**; cần cài Snowball Client tại local để xác minh, nén và mã hóa dữ liệu trước khi thiết bị được vận chuyển về AWS Region lưu trên **S3** hoặc **Glacier**.
* **Đã nghiên cứu Snowball Edge**: Phiên bản nâng cấp với dung lượng tới **100 TB** và tích hợp sẵn tài nguyên tính toán (Compute) để xử lý dữ liệu ngay tại chỗ trước khi import vào AWS.
* **Đã nghiên cứu Snowmobile**: Giải pháp xe container vật lý cho di trú dữ liệu quy mô lên đến **100 PB**/xe, phù hợp cho các dự án di trú toàn bộ trung tâm dữ liệu ở quy mô Exabyte.

### 2. AWS Storage Gateway – Lưu trữ lai (Hybrid Storage)

* **Nắm được khái niệm cốt lõi**: Giải pháp kết hợp dung lượng lưu trữ On-premise với hạ tầng AWS cloud, tận dụng quy mô và chi phí hợp lý của cloud cho dữ liệu lớn có yêu cầu lưu giữ lâu dài.
* **Đã tìm hiểu File Gateway**: Ánh xạ thư mục On-premise lên **Amazon S3** qua giao thức **NFS/SMB**.
* **Đã tìm hiểu Volume Gateway**: Cung cấp lưu trữ dạng khối qua giao thức **iSCSI**; dữ liệu có thể snapshot và phục hồi khi cần Disaster Recovery.
* **Đã tìm hiểu Tape Gateway**: Cung cấp giao diện Virtual Tape Library (VTL) qua iSCSI, thay thế hệ thống băng từ vật lý với dữ liệu lưu trên S3 hoặc Glacier.

### 3. Chiến lược Disaster Recovery (DR)

* **Nắm được RTO & RPO**: Hiểu rõ RTO (Recovery Time Objective) và RPO (Recovery Point Objective) là hai yếu tố quan trọng để lựa chọn chiến lược DR phù hợp.
* **Đã phân tích 4 chiến lược DR trên AWS**:
  * Backup & Restore
  * Pilot Light
  * Low Capacity Active-Active
  * Full Capacity Active-Active

* Nhận thấy mức độ sẵn sàng, độ phức tạp và chi phí sẽ tăng dần khi yêu cầu RTO/RPO giảm xuống.

### 4. AWS Backup – Quản lý sao lưu tập trung

* **Nắm được vai trò dịch vụ**: AWS Backup giúp quản lý tập trung lịch backup, retention policy và theo dõi trạng thái sao lưu từ một giao diện duy nhất.
* **Đã xác định các tài nguyên hỗ trợ**: EBS, EC2, RDS, DynamoDB, EFS và Storage Gateway volumes đều có thể quản lý thống nhất thông qua Backup Plan.

---

### 5. Nghiên cứu AWS Management Dashboard – Kiến trúc & Cost Explorer API *(Day 3)*

* Tiếp tục nghiên cứu sâu hơn các AWS API đã được làm quen từ các tuần đầu thực tập nhằm phục vụ định hướng phát triển AWS Management Dashboard cho project nội bộ.
* Xác định bài toán thực tế: AWS Console có nhiều chức năng nhưng khá phức tạp khi quản lý nhiều user và tài nguyên; cần một dashboard tập trung giúp hiển thị chi phí, trạng thái tài nguyên và thông tin IAM User dễ theo dõi hơn.
* Đã tìm hiểu mô hình kiến trúc tổng quan gồm frontend hiển thị dữ liệu, backend xử lý request và lớp kết nối AWS SDK/API để phục vụ định hướng triển khai sau này.
* Nghiên cứu AWS Cost Explorer API:
  * Tìm hiểu API `GetCostAndUsage` để lấy dữ liệu chi phí theo thời gian.
  * Tìm hiểu khả năng phân nhóm dữ liệu theo service hoặc account.
  * Hiểu cơ chế phân quyền IAM cần thiết khi gọi Cost Explorer API.
* Tìm hiểu AWS Billing API và phân biệt nhóm API phục vụ phân tích chi phí với nhóm API quản lý billing tổng quan.
* Nghiên cứu thêm hướng trực quan hóa dữ liệu:
  * Biểu đồ xu hướng chi phí theo ngày/tháng.
  * Biểu đồ phân tích chi phí theo dịch vụ AWS.
  * Card tổng quan hiển thị mức sử dụng tài nguyên và chi phí hiện tại.
* Ghi nhận Cost Explorer không cập nhật dữ liệu theo thời gian thực nên cần lưu ý khi thiết kế dashboard.

### 6. Nghiên cứu IAM Management API & Định hướng Dashboard *(Day 4)*

* Tiếp tục nghiên cứu các IAM API đã tìm hiểu trước đó nhằm phục vụ module quản lý user cho dashboard.
* Tìm hiểu thêm:
  * API lấy danh sách IAM User.
  * API kiểm tra group và policy của user.
  * Kiểm tra trạng thái truy cập Console hoặc Programmatic Access.
* Nghiên cứu mô hình phân quyền dashboard:
  * Đã tìm hiểu nguyên tắc phân quyền read-only tối thiểu nhằm đảm bảo an toàn khi dashboard truy cập dữ liệu AWS.
  * Có tham khảo thêm cơ chế quản lý định danh tập trung trên AWS phục vụ định hướng mở rộng về sau.
* Tìm hiểu khả năng theo dõi trạng thái tài nguyên:
  * EC2 Instance status.
  * Metric cơ bản từ CloudWatch.
  * Trạng thái RDS và một số tài nguyên phổ biến.
* Định hướng triển khai dashboard:
  * Xây dựng backend trung gian để kết nối AWS SDK/API.
  * Xây dựng giao diện trực quan hóa chi phí và trạng thái tài nguyên.
  * Từng bước mở rộng thêm phần quản lý IAM User và monitoring.
* Đánh giá khó khăn kỹ thuật: Việc xử lý credential AWS an toàn và phân trang dữ liệu là những vấn đề cần được nghiên cứu kỹ trước khi triển khai thực tế.

### 7. Nghiên cứu công nghệ và tối ưu chi phí AWS từ Event cộng đồng *(Day 5)*

* Dựa trên nội dung tham gia buổi chia sẻ cộng đồng của AWS Study Group (vào Thứ 7 tuần 3), tiến hành nghiên cứu sâu hơn về các công nghệ được giới thiệu:
  * **Automated Prompt Engineering & Proptimizer Extension**: Tìm hiểu cách tối ưu hóa câu lệnh cho LLM, hỗ trợ nâng cao chất lượng code và hiệu suất làm việc khi tích hợp AI vào quy trình phát triển.
  * **Phương pháp BMAD (Build, Measure, Analyze, Deploy)**: Nghiên cứu áp dụng chu trình phát triển phần mềm hiện đại, đặc biệt là tầm quan trọng của việc đo lường và phân tích hệ thống.
* **Tối ưu chi phí AWS**: Nghiên cứu cách vận dụng các dịch vụ AWS với chi phí tiết kiệm nhất dựa trên các bài học kinh nghiệm từ cộng đồng. Tập trung vào việc tận dụng Free Tier, thiết lập ngân sách (AWS Budgets) và lựa chọn tài nguyên phù hợp với nhu cầu thực tế của project nội bộ nhằm giảm thiểu lãng phí.

---

## Khó khăn gặp phải & Cách khắc phục

* **Phân biệt các tầng chiến lược DR**: Pilot Light, Low Capacity và Full Capacity ban đầu dễ bị nhầm lẫn do định nghĩa khá gần nhau.
  * *Cách khắc phục*: Dùng RTO/RPO làm tiêu chí phân biệt chính để hiểu rõ từng mô hình.

* **Chọn đúng loại Storage Gateway**: Ba loại gateway có chức năng tương đối gần nhau.
  * *Cách khắc phục*: Ghi nhớ theo giao thức sử dụng:
    * NFS/SMB → File Gateway
    * iSCSI Block → Volume Gateway
    * iSCSI VTL → Tape Gateway

* **Phân biệt Cost Explorer API và Billing API**: Dễ nhầm lẫn khi tìm hiểu quyền IAM và phạm vi sử dụng của từng nhóm API.
  * *Cách khắc phục*: Đối chiếu IAM Actions với tài liệu AWS và kiểm tra lại policy theo từng nhóm quyền.

* **Xử lý credential an toàn cho dashboard backend**:
  * *Cách khắc phục*: Tìm hiểu cách lưu credential qua Environment Variables và định hướng sử dụng IAM Role khi triển khai thực tế.

---

## Bài học rút ra

* Khi băng thông mạng không đáp ứng được, Snow Family là giải pháp phù hợp cho việc di chuyển dữ liệu quy mô lớn.
* Lựa chọn chiến lược Disaster Recovery cần dựa trên RTO/RPO và ngân sách thực tế của hệ thống.
* AWS Backup giúp quản lý backup tập trung và hỗ trợ kiểm soát chi phí lưu trữ hiệu quả.
* Khi xây dựng hệ thống kết nối AWS API, nguyên tắc Least Privilege rất quan trọng để đảm bảo bảo mật và hạn chế lỗi phân quyền.
* Việc nghiên cứu kiến trúc và giới hạn của AWS API trước khi triển khai giúp định hướng thiết kế dashboard hợp lý và dễ mở rộng hơn trong tương lai.

---
