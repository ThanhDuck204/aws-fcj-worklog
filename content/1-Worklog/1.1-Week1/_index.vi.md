---
title: "Worklog Tuần 1"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---

### Mục tiêu tuần 1:

* Làm quen với môi trường thực tập và các thành viên trong First Cloud Journey.
* Hiểu được các khái niệm cơ bản về Cloud Computing và AWS.
* Biết cách sử dụng AWS Console, CLI và làm quen với các dịch vụ chính.
* Nắm được các nguyên tắc bảo mật và quản lý chi phí khi sử dụng AWS.
* Hiểu được cách AWS định hướng thiết kế hệ thống thông qua Well-Architected Framework.

---

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2 | - Làm quen với các thành viên FCJ, tìm nhóm học tập để trao đổi <br> - Đọc nội quy, quy định của đơn vị thực tập <br> - Tìm hiểu Cloud Computing và AWS Global Infrastructure <br>&emsp; + Cloud Computing (on-demand, pay-as-you-go) <br>&emsp; + Lợi ích: tối ưu chi phí, linh hoạt, dễ mở rộng <br>&emsp; + AWS gồm Region, AZ, Edge Location <br> - Tìm hiểu tổng quan Well-Architected Framework (6 trụ cột) <br> - Tạo tài khoản AWS Free Tier và thêm thẻ Visa | 20/04/2026 | 20/04/2026 | https://cloudjourney.awsstudygroup.com/ <br> https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html |
| 3 | - Tìm hiểu AWS Management Console <br>&emsp; + Không sử dụng Root User cho công việc hằng ngày <br>&emsp; + Đăng nhập bằng IAM User <br> - Tìm hiểu AWS CLI và SDK <br>&emsp; + Cấu hình Access Key, Secret Key <br>&emsp; + Hiểu cách CLI hoạt động <br> - Tìm hiểu các gói AWS Support và cách tạo support case | 21/04/2026 | 21/04/2026 | https://cloudjourney.awsstudygroup.com/ <br> https://www.youtube.com/watch?v=95quNuhvMT0 |
| 4 | - Thiết lập bảo mật tài khoản AWS <br>&emsp; + Bật MFA cho Root User <br>&emsp; + Tạo Admin Group và Admin User <br>&emsp; + Gán quyền AdministratorAccess <br>&emsp; + Kiểm tra đăng nhập IAM <br> - Tìm hiểu cách xử lý lỗi xác thực tài khoản và liên hệ support khi cần | 22/04/2026 | 22/04/2026 | https://www.youtube.com/watch?v=1dG5xutGbr4 <br> https://www.youtube.com/watch?v=b9pK1oG534Q <br> https://www.youtube.com/watch?v=69iKhwI7k2Y |
| 5 | - Đọc tài liệu và thực hành lab tổng hợp <br>&emsp; + VPC, Subnet, Route Table <br>&emsp; + Security Group <br>&emsp; + EC2 và IAM <br>&emsp; + RDS và AWS Budgets <br> - Thực hành các lab tương ứng <br> - Thực hiện cleanup toàn bộ tài nguyên sau khi hoàn thành | 23/04/2026 | 23/04/2026 | https://cloudjourney.awsstudygroup.com/ <br> https://000007.awsstudygroup.com/vi/3-usage-budget/ |
| 6 | - Tìm hiểu cách ứng dụng kết nối với database trên cloud <br> - Thực hành lab Database <br>&emsp; + Kết nối database <br>&emsp; + Thêm dữ liệu <br>&emsp; + Truy vấn dữ liệu <br> - Cài đặt và tìm hiểu Kiro <br> - **Tìm hiểu lý thuyết Module 02 – Networking & Security (VPC, Subnet, SG, NACL)** | 24/04/2026 | 24/04/2026 | https://cloudjourney.awsstudygroup.com/ <br> https://www.youtube.com/watch?v=uAQCm4sm_1c |

---

### Kết quả đạt được tuần 1:

---

* **Nắm vững nền tảng Cloud Computing và AWS:**
  * Hiểu rõ sự khác biệt giữa mô hình **On-Premise** và **Cloud Computing**, đặc biệt là lợi thế của Cloud về khả năng mở rộng và tối ưu chi phí.
  * Nắm được bản chất của mô hình **on-demand** và **pay-as-you-go**, từ đó nhận thức được việc sử dụng tài nguyên không kiểm soát có thể dẫn đến phát sinh chi phí ngoài ý muốn.
  * Hiểu cấu trúc hạ tầng toàn cầu của AWS:
    * **Region**: khu vực triển khai chính
    * **Availability Zone (AZ)**: đảm bảo tính sẵn sàng cao
    * **Edge Location**: tối ưu độ trễ khi phân phối nội dung
  * Bước đầu biết cách lựa chọn Region phù hợp với người dùng tại Việt Nam (ưu tiên Singapore) nhằm tối ưu độ trễ và chi phí.

---

* **Hiểu tư duy thiết kế hệ thống theo AWS Well-Architected Framework:**
  * Nắm được 6 trụ cột cốt lõi và vai trò của từng trụ trong việc xây dựng hệ thống:
    * Operational Excellence
    * Security
    * Reliability
    * Performance Efficiency
    * Cost Optimization
    * Sustainability
  * Hiểu rằng việc thiết kế hệ thống không chỉ tập trung vào chạy được mà còn phải đảm bảo:
    * Khả năng mở rộng (Scalability)
    * Khả năng chịu lỗi (Fault Tolerance)
    * Tối ưu chi phí (Cost-aware design)
  * Nhận thức được tầm quan trọng của việc:
    * **Decoupling hệ thống** thay vì thiết kế monolithic
    * Ưu tiên sử dụng **Managed Services** để giảm tải vận hành
    * Không over-provision tài nguyên, thay vào đó sử dụng Auto Scaling

---

* **Hiểu và hình thành tư duy quản lý chi phí trên AWS:**
  * Nhận thức rõ rủi ro của mô hình pay-as-you-go khi không kiểm soát tài nguyên.
  * Xác định được các nguyên nhân phổ biến gây phát sinh chi phí:
    * Quên tắt EC2 instance
    * Không xóa RDS hoặc snapshot
    * Sử dụng tài nguyên ngoài Free Tier
  * Thực hành sử dụng **AWS Budgets** để:
    * Thiết lập ngưỡng cảnh báo chi phí
    * Theo dõi mức sử dụng theo thời gian
  * Hình thành thói quen:
    * **Luôn cleanup tài nguyên sau khi hoàn thành lab**
    * Kiểm tra tài nguyên trước khi kết thúc phiên làm việc
  * Bước đầu sử dụng công cụ **Kiro** để hỗ trợ:
    * Tạo checklist kiểm tra tài nguyên
    * Tự động hóa một phần quy trình rà soát chi phí

---

* **Nắm được các nguyên tắc bảo mật cơ bản trong AWS:**
  * Hiểu rõ rủi ro khi sử dụng **Root User** và lý do không dùng trong công việc hằng ngày.
  * Đã thực hiện:
    * Bật **MFA** cho Root User
    * Tạo **IAM User** và **IAM Group**
    * Gán quyền thông qua Group thay vì trực tiếp cho User
  * Hiểu và áp dụng nguyên tắc **Least Privilege** trong cấp quyền.
  * Nhận thức được bảo mật trong Cloud là **trách nhiệm chia sẻ (Shared Responsibility Model)** giữa AWS và người dùng.

---

* **Hiểu cách AWS Support hoạt động và xử lý sự cố cơ bản:**
  * Nắm được các gói Support và phạm vi hỗ trợ của từng gói.
  * Biết cách tạo **Support Case** khi gặp sự cố.
  * Có khả năng tự xử lý một số lỗi cơ bản liên quan đến xác thực và quyền truy cập.

---

* **Làm quen với AWS Console, CLI và SDK:**
  * Sử dụng AWS Management Console để tạo và quản lý tài nguyên.
  * Cấu hình thành công AWS CLI và hiểu cách CLI tương tác với AWS thông qua API.
  * Thực hiện được một số lệnh cơ bản để thao tác tài nguyên.
  * Hiểu vai trò của **AWS SDK** trong việc tích hợp AWS vào ứng dụng thực tế.

---

* **Hoàn thành các lab và hiểu mối liên hệ giữa các dịch vụ:**
  * Triển khai được kiến trúc cơ bản gồm:
    * **VPC**: thiết lập network
    * **Subnet**: phân chia public/private
    * **EC2**: triển khai compute
    * **RDS**: quản lý database
  * Hiểu mối quan hệ giữa các thành phần:
    * EC2 hoạt động trong Subnet thuộc VPC
    * Security Group kiểm soát truy cập instance
    * RDS kết nối với application thông qua network
  * Thực hành:
    * Kết nối database
    * Thêm và truy vấn dữ liệu
  * Sau khi hoàn thành lab, đã thực hiện cleanup toàn bộ tài nguyên để tránh phát sinh chi phí.

---

* **Nắm vững Module 02 – Networking & Security (điểm nổi bật trong tuần):**
  * Hiểu cách xây dựng kiến trúc mạng trong AWS thông qua VPC.
  * Phân biệt rõ:
    * **Public Subnet**: có thể truy cập Internet
    * **Private Subnet**: không truy cập trực tiếp Internet
  * Nắm vững vai trò của các thành phần:
    * **Internet Gateway (IGW)**: kết nối VPC với Internet
    * **NAT Gateway**: cho phép Private Subnet truy cập Internet theo chiều ra
    * **Route Table**: định tuyến traffic
    * **VPC Endpoint**: kết nối nội bộ tới dịch vụ AWS
  * Hiểu rõ cơ chế bảo mật:
    * **Security Group (Stateful)**: kiểm soát ở cấp instance
    * **NACL (Stateless)**: kiểm soát ở cấp subnet
  * Phân tích được luồng traffic:
    * Public EC2 ↔ Internet
    * Private EC2 → NAT → Internet
  * Làm quen với mô hình mở rộng:
    * **VPC Peering**
    * **Transit Gateway**
  * Nhận thức được rằng thiết kế network là nền tảng quan trọng để đảm bảo:
    * Bảo mật hệ thống
    * Khả năng mở rộng
    * Tính ổn định của ứng dụng

---

### Một số hình ảnh thực hành:

![Setup](/images/Worklog-weak1/setup-virtual-mfa-device.png)

![Create](/images/Worklog-weak1/create-admin-group-and-admin-user.png)

![Done Budget](/images/Worklog-weak1/done-all-lab-budget.png)

![Done All](/images/Worklog-weak1/done-all-5-labs-get-100-credit-aws.png)
