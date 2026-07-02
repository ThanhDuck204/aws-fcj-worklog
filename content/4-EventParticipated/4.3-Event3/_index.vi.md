---
title: "Event 3"
date: 2026-06-20
weight: 3
chapter: false
pre: " <b> 4.3. </b> "
---
# Bài Thu Hoạch: Cuộc Thi AWS Certification Quiz

### Thông Tin Sự Kiện

| Thông tin | Chi tiết |
|---|---|
| **Tên sự kiện** | Cuộc thi AWS Certification Quiz |
| **Ngày & Giờ** | 20/06/2026 |
| **Hình thức** | Thi đấu đội (8 đội) |
| **Vai trò** | Người tham gia / Quan sát |
| **Chủ trì** | Cộng đồng AWS Study Group |

---

### Tổng Quan Sự Kiện

Cuộc thi AWS Certification Quiz là một cuộc thi kiến thức với 8 đội thi đấu với nhau để trả lời các câu hỏi về dịch vụ AWS cloud và các khái niệm cloud computing nói chung. Sự kiện được dẫn dắt bởi anh Thịnh, người đã cung cấp những thông tin chi tiết và kiến thức bổ sung quý giá về các khái niệm AWS trong suốt cuộc thi.

Khác với những buổi hội thảo hay chia sẻ thông thường, hôm nay là một cuộc thi thực sự, có tính cạnh tranh và gay cấn hơn nhưng cũng rất vui.

---

### Thể Thức Thi Đấu

Cuộc thi diễn ra qua nhiều vòng:

**Vòng loại**
8 đội cùng thi đấu với nhau. Các câu hỏi ở vòng này xoay quanh kiến thức AWS cơ bản. Các đội thể hiện trình độ kiến thức AWS rất khác nhau, có đội trả lời rất nhanh, có đội phải nghĩ lâu hơn.

**Bán kết**
Các đội đạt điểm cao nhất tiến vào vòng bán kết. Câu hỏi khó hơn, phức tạp hơn và đi sâu vào các dịch vụ AWS cụ thể. Độ khó tăng dần qua từng câu.

**Chung kết (hoãn lại)**
Do thời gian có hạn, vòng chung kết được hoãn lại sang tuần sau. Điều này cho các đội thêm thời gian chuẩn bị và học thêm, đồng thời cũng tạo sự háo hức cho trận chung kết.

Một điều thú vị là các đội thường dựa vào trực giác và dự đoán có cơ sở hơn là kiến thức kỹ thuật thuần túy. Anh em trong group vui gọi là "chơi hệ tâm linh". Chính vì thế cuộc thi thêm phần thú vị và khó đoán.

---

### Chủ Đề Chính Được Đề Cập

**1. Kiến thức chung về AWS**
Các dịch vụ AWS cốt lõi và trường hợp sử dụng, kiến thức cơ bản về cloud computing, best practices của AWS và cách tích hợp các dịch vụ.

**2. Tình huống AWS thực tế**
Các câu hỏi bao gồm nhiều tình huống thực tế, kiểm tra kỹ năng giải quyết vấn đề, hiểu biết về khả năng của dịch vụ AWS, chiến lược tối ưu chi phí và best practices về bảo mật.

**3. Phân quyền theo Resource vs Identity**
Một trong những câu hỏi thú vị và thực tế nhất tập trung vào ưu tiên phân quyền theo resource (resource-based policies) thay vì theo identity (identity-based policies).

Tại sao nên dùng Resource-Based Policies:
- Cross-Account Access: Dễ dàng cấp quyền truy cập tài nguyên từ các AWS account khác
- Quản lý tập trung: Phân quyền được định nghĩa trực tiếp trên tài nguyên
- Đơn giản hóa quản lý: Không cần sửa đổi policy của user/role
- Kiểm soát rõ ràng: Dễ dàng nhìn thấy ai có thể truy cập tài nguyên
- Không cần Assume Role: Truy cập trực tiếp mà không cần assume role

Các trường hợp sử dụng phổ biến: S3 Bucket Policies, SQS Queue Policies, SNS Topic Policies, Lambda Function Policies, KMS Key Policies.

Ví dụ: Khi bạn muốn cho phép nhiều account hoặc service truy cập S3 bucket, hiệu quả hơn là thêm bucket policy (resource-based) cho phép các account đó thay vì sửa IAM policy (identity-based) ở mỗi account.

**Identity-Based vs Resource-Based Policies:**
- Identity-Based Policies: Gắn vào IAM user, group, hoặc role. Kiểm soát identity có thể làm gì. Phải quản lý ở mỗi account.
- Resource-Based Policies: Gắn trực tiếp vào resource (S3, SQS, SNS...). Kiểm soát ai có thể truy cập resource. Quản lý tập trung trên resource.

Best Practice: Sử dụng resource-based policies khi cần cấp quyền cross-account hoặc muốn quản lý phân quyền tập trung.

---

### Kiến Thức Từ anh Thịnh

Trong suốt cuộc thi, anh Thịnh đã cung cấp thông tin bổ sung và ngữ cảnh giá trị cho mỗi câu hỏi:

- Kiến thức kỹ thuật: Các khái niệm áp dụng như thế nào trong môi trường production
- Lỗi thường gặp: Những cạm bẫy cần tránh khi triển khai AWS services
- Best practices: Các phương pháp chuẩn trong ngành về kiến trúc AWS
- Cân nhắc chi phí: Các giải pháp khác nhau ảnh hưởng đến chi phí AWS như thế nào
- Vấn đề bảo mật: Các khía cạnh bảo mật của cấu hình AWS

Cách tiếp cận học tập mà anh Thịnh chia sẻ cũng rất thực tế: hiểu thay vì học vẹt, tập trung vào khái niệm hơn là học thuộc lòng, và luôn đặt câu hỏi tại sao thay vì chỉ nhớ những gì làm theo.

---

### Bài Học Chính

**1. Quản lý phân quyền AWS**
Hiểu sâu về resource-based vs identity-based policies, biết khi nào sử dụng từng loại policy, nắm được mô hình cross-account access và best practices bảo mật cho phân quyền.

**2. Kiến thức AWS thực tế**
Tình huống thực tế có giá trị hơn kiến thức lý thuyết đơn thuần. Hiểu tương tác giữa các service là rất quan trọng, và chi phí cũng như bảo mật phải được xem xét trong mọi quyết định.

**3. Kỹ năng thi đấu đội**
Tư duy nhanh dưới áp lực, giải quyết vấn đề theo nhóm, dự đoán chiến lược khi không chắc chắn, và học hỏi từ cách tiếp cận của đội khác.

**4. Học tập liên tục**
AWS rất rộng và không ngừng phát triển. Sự kiện cộng đồng cung cấp cơ hội học tập quý giá. Câu hỏi thực tế tiết lộ khoảng trống kiến thức cần cải thiện.

---

### Suy Ngẫm Cá Nhân

**Về chuyên môn**
Cuộc thi này cho thấy một số lĩnh vực mình cần cải thiện: kiến trúc phân quyền cần hiểu sâu hơn về IAM và resource policies, cần biết cách các AWS service khác nhau hoạt động cùng nhau, và cần chuyển đổi kiến thức lý thuyết sang tình huống thực tế tốt hơn.

**Trải nghiệm thi đấu**
Thi dưới áp lực thời gian cho thấy hiểu biết thực sự của mình. Có những câu tưởng biết mà khi bị hỏi lại không trả lời được ngay. Cuộc thi cũng phơi bày những lĩnh vực cần học thêm. Quan sát cách đội khác giải quyết vấn đề cũng là một cách học hiệu quả.

**Giá trị cộng đồng**
Phần giải thích bổ sung của anh Thịnh là vô cùng giá trị. Học từ câu trả lời và lý luận của đội khác cũng rất bổ ích. Sự kiện giúp kết nối với những người đam mê AWS khác, tạo thêm động lực để học AWS sâu hơn.

**Về "hệ tâm linh"**
Các đội thường dựa vào dự đoán có học và trực giác nhiều hơn là kiến thức thuần túy. Nghe buồn cười nhưng thực ra lại chứng minh một số điều: hiểu biết nền tảng vững chắc cho phép trực giác tốt, kinh nghiệm AWS xây dựng nhận dạng mẫu, và sự tự tin trong dự đoán có cơ sở là kỹ năng quý giá. Thêm vào đó, làm việc nhóm có thể bù đắp cho khoảng trống kiến thức cá nhân.

---

### Kế Hoạch Hành Động

**Học tập ngay**
- Tìm hiểu sâu về IAM Policies, đặc biệt là resource-based vs identity-based policies
- Học các mô hình và best practices cho cross-account access
- Hiểu cách các AWS service khác nhau tương tác với nhau
- Thực hành với các vấn đề kiến trúc AWS thực tế

**Phát triển dài hạn**
- Cân nhắc chuẩn bị cho chứng chỉ AWS
- Xây dựng dự án sử dụng các AWS service khác nhau
- Tiếp tục tham gia sự kiện AWS Study Group
- Chia sẻ kiến thức học được với thành viên nhóm

**Chuẩn bị thi chung kết**
- Ôn tập các chủ đề khó cho vòng chung kết tuần sau
- Tập trung vào các chủ đề thách thức
- Làm qua các câu hỏi thực hành AWS certification
- Thảo luận phương pháp và chiến lược với nhóm

---

### Đánh Giá Sự Kiện

(5/5)

Thể thức thi đấu xuất sắc khiến việc học trở nên vui và hấp dẫn. Kiến thức của anh Thịnh mang lại giá trị to lớn vượt xa các câu hỏi quiz. Các câu hỏi dựa trên tình huống thực tế rất phù hợp với việc sử dụng AWS thực tế. Cách tiếp cận "dựa vào trực giác" của các đội mang lại sự hài hước và giảm căng thẳng.

### Một Số Hình Ảnh Tại Sự Kiện

![AWS Certification Quiz - Khoảnh khắc thi đấu 1](/images/Event/event3_1.jpg)

![AWS Certification Quiz - Khoảnh khắc thi đấu 2](/images/Event/event3_2.jpg)

![AWS Certification Quiz - Toàn cảnh sự kiện](/images/Event/event3_3.jpg)
