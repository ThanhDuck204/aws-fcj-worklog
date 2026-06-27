---
title: "Worklog Tuần 9"
date: 2026-06-15
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

## Mục tiêu tuần 9

* Hoàn thiện các thay đổi kiến trúc đã thống nhất ở tuần trước.
* Review code với nhóm và sửa các điểm chưa ổn.
* Tối ưu hiệu suất hệ thống ở những phần ảnh hưởng trực tiếp đến trải nghiệm.
* Hoàn thành Module 6 và ghi lại các quyết định thiết kế chính.
* Chuẩn bị phần việc tiếp theo cho sprint mới.

---

## Công việc đã thực hiện

| Ngày | Công việc | Kết quả | Tài liệu | Ghi chú |
|---|---|---|---|---|
| 15/06/2026 | Hoàn thiện cải tiến kiến trúc và rà lại các thay đổi chính. | Cập nhật lại kiến trúc dự án theo hướng đã thống nhất. Các phần liên quan đến xử lý dữ liệu, service layer, mock service và luồng tích hợp AWS được làm rõ hơn để nhóm dễ tiếp tục phát triển. | [AWS Study Group YouTube](https://www.youtube.com/@AWSStudyGroup) <br> [Cloud Journey](https://cloudjourney.awsstudygroup.com/) <br> [GitHub Worklog](https://github.com/NTL0210/FACJ_Worklog) | Hoàn thiện & tối ưu |
| 16/06/2026 | Code review với nhóm, tối ưu hiệu suất và hoàn thành Module 6. | Thực hiện peer code review, ghi nhận các điểm cần chỉnh trong cách tổ chức code và xử lý dữ liệu. Tối ưu lại một số phần xử lý để giảm thao tác dư. Hoàn thành Module 6 và bổ sung ghi chú về lựa chọn database/AWS services cho dự án. | [AWS Study Group YouTube](https://www.youtube.com/@AWSStudyGroup) <br> [Cloud Journey](https://cloudjourney.awsstudygroup.com/) <br> [Discord Lamentum](https://discord.gg/yjFh7dNq) <br> [GitHub Worklog](https://github.com/NTL0210/FACJ_Worklog) | Review code & hoàn thành Module 6 |
| 17/06/2026 | Làm việc dự án nhóm và chuẩn bị cho sprint tiếp theo. | Tích hợp các thay đổi kiến trúc vào công việc chung, đồng bộ với nhóm về các bước tiếp theo và chuẩn bị nội dung cần làm cho sprint mới. Các phần còn mở được ghi chú lại để tránh bỏ sót khi chia task. | [AWS Study Group YouTube](https://www.youtube.com/@AWSStudyGroup) <br> [Cloud Journey](https://cloudjourney.awsstudygroup.com/) <br> [Discord Lamentum](https://discord.gg/yjFh7dNq) <br> [GitHub Worklog](https://github.com/NTL0210/FACJ_Worklog) | Tích hợp & lập kế hoạch |
| 19/06/2026 | Nghỉ - lý do cá nhân. | Không có hoạt động học tập. | Không có | Nghỉ cá nhân |
| 20/06/2026 | Tiếp tục làm dự án nhóm. Nhận góp ý, tìm lỗi và cải thiện chức năng. | Sửa các lỗi được ghi nhận và cải thiện chức năng dựa trên góp ý của nhóm. | [GitHub Worklog](https://github.com/NTL0210/FACJ_Worklog) | Cải thiện dự án |
| 21/06/2026 | Lên công ty tham gia Event 3. | Tham gia sự kiện của công ty, kết nối với đồng nghiệp và học hỏi từ các buổi chia sẻ. | [Thư viện ảnh Event 3](#thu-vien-anh-event-3) | Sự kiện công ty |

---

## Ghi chú trong tuần

Tuần này tập trung vào hoàn thiện hơn là mở thêm nhiều tính năng. Sau khi review code, nhóm có thêm vài điều chỉnh nhỏ để code dễ đọc và dễ bảo trì hơn.

Việc hoàn thành Module 6 cũng giúp mình nhìn lại lựa chọn database trong dự án rõ hơn. DynamoDB vẫn phù hợp với hướng MVP hiện tại, nhưng các kiến thức về RDS, Aurora, Redshift và ElastiCache giúp mình hiểu khi nào cần cân nhắc thêm dịch vụ khác.

Cuối tuần, mình tiếp tục làm dự án — nhận góp ý từ nhóm, tìm lỗi và cải thiện chức năng. Đây là cơ hội tốt để hoàn thiện dần sản phẩm dựa trên thực tế sử dụng.

Chủ nhật, mình lên công ty tham gia Event 3. Đây là dịp để kết nối với đồng nghiệp và học hỏi những kinh nghiệm thực tế từ các buổi chia sẻ.

---

## Khó khăn gặp phải

* Khi tích hợp các thay đổi kiến trúc, cần đảm bảo code, tài liệu và phần mock data không bị lệch nhau.
* Code review phát hiện một số chỗ tổ chức code chưa thật sự dễ đọc, cần chỉnh lại để nhóm bảo trì thuận lợi hơn.
* Tối ưu hiệu suất phải chọn đúng điểm đang ảnh hưởng đến trải nghiệm, tránh mất thời gian tối ưu những phần chưa cần thiết.
* Sau khi học xong Module 6, cần phân biệt rõ use case của DynamoDB, RDS, Aurora, Redshift và ElastiCache để không chọn dịch vụ theo cảm tính.
* Nhận góp ý từ nhóm đồng nghĩa với việc liên tục tìm và sửa lỗi, cần theo dõi cẩn thận những gì đã thay đổi.

---

## Kiến thức rút ra

* Code review giúp phát hiện lỗi nhỏ và thống nhất style làm việc trong nhóm.
* Tối ưu hiệu suất nên bắt đầu từ những phần đang dùng nhiều nhất, không cần tối ưu lan man.
* Ghi lại quyết định thiết kế giúp nhóm dễ hiểu vì sao chọn hướng triển khai hiện tại.
* Module 6 hỗ trợ tốt cho việc so sánh DynamoDB, RDS và các dịch vụ dữ liệu khác trong AWS.
* Liên tục tìm và sửa lỗi từ góp ý của nhóm là cách tốt để nâng cao chất lượng sản phẩm từng bước một.
* Sự kiện công ty là dịp quý giá để học hỏi kinh nghiệm thực tế và mở rộng mạng lưới quan hệ chuyên môn.

---

## Thư viện ảnh Event 3

![Event 3 - Ảnh 1](/images/Event/event3_1.jpg)

![Event 3 - Ảnh 2](/images/Event/event3_2.jpg)

![Event 3 - Ảnh 3](/images/Event/event3_3.jpg)
