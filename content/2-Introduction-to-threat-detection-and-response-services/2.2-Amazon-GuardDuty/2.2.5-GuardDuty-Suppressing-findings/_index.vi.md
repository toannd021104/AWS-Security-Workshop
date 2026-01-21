---
title: "GuardDuty - Ẩn phát hiện"
date: "`r Sys.Date()`"
weight: 5
chapter: false
pre: " <b> 2.2.5 </b> "
---

#### Cấu hình quy tắc để ẩn các phát hiện không mong muốn từ công cụ đánh giá lỗ hổng

1. Từ bảng điều khiển **Amazon GuardDuty**, mở trang **Findings**.

2. Chọn nút **Suppress Findings**.

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.5-GuardDuty-Suppressing-findings/s2.png)

3. Quy tắc ẩn cần được xây dựng dựa trên hai tiêu chí lọc.  
   Tiêu chí đầu tiên sử dụng thuộc tính **Finding Type** với giá trị **Recon:EC2/Portscan**. Trong trường **Add filter criteria**, chọn **Finding Type**, nhập **"Recon:EC2/Portscan"**, sau đó chọn **Apply**.

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.5-GuardDuty-Suppressing-findings/s3.png)

4. Sau khi thêm bộ lọc đầu tiên, phần xem trước ở cuối trang sẽ hiển thị các phát hiện dự kiến bị ẩn bởi quy tắc này. Để tránh vô tình ẩn các phát hiện quan trọng, bạn cần bổ sung tiêu chí lọc thứ hai nhằm thu hẹp phạm vi áp dụng.

5. Tiêu chí lọc thứ hai dùng để xác định chính xác instance (hoặc các instance) đang chạy công cụ đánh giá lỗ hổng. Bạn có thể sử dụng **Instance image ID** hoặc **Tag value**, tuỳ theo cách nhận diện instance phù hợp.  
   Chọn **Add filter criteria** lần nữa, sau đó chọn **Instance Tag Value**, nhập **"Scanner"**, và chọn **Apply**.

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.5-GuardDuty-Suppressing-findings/s5.png)

6. Quan sát phần xem trước để xác nhận rằng chỉ có một phát hiện duy nhất sẽ bị ẩn bởi quy tắc này.

7. Trong trường **Name**, nhập **"VulnerabilityAssessmentTool"**.

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.5-GuardDuty-Suppressing-findings/s7.png)

1. Trong trường **Description**, nhập **"Suppress findings from Vulnerability Assessment Tool."**.

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.5-GuardDuty-Suppressing-findings/s8.png)

9. Chọn **Save** để lưu quy tắc ẩn phát hiện.
