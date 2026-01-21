---
title: "GuardDuty - Thông báo"
date: "`r Sys.Date()`"
weight: 7
chapter: false
pre: " <b> 2.2.7 </b> "
---

#### Cấu hình SNS topic

1. Truy cập dịch vụ **Amazon SNS** tại: https://console.aws.amazon.com/sns/v3/home

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.5-Security-Hub-Notifications/s1.png)

2. Trong thanh điều hướng bên trái, chọn **Topics**.

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.5-Security-Hub-Notifications/s2.png)

3. Chọn **Create topic**.

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.5-Security-Hub-Notifications/s3.png)

1. Chọn loại **Standard**.

2. Nhập tên topic là **"guardduty-findings"**.

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.7-GuardDuty-Notifications/s5.png)

6. Giữ nguyên các thiết lập mặc định còn lại và chọn **Create topic** ở cuối trang để tạo topic.

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.7-GuardDuty-Notifications/s6.png)

#### Đăng ký theo dõi SNS topic

1. Từ trang chi tiết của topic **guardduty-findings**, chọn **Create subscription**.

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.7-GuardDuty-Notifications/s7.png)

1. Trong trang **Create subscription**, tại mục **Protocol**, chọn **email**.

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.7-GuardDuty-Notifications/s8.png)

1. Tại mục **Endpoint**, nhập địa chỉ email bạn muốn sử dụng để nhận thông báo trong workshop này. Bạn có thể huỷ đăng ký sau khi workshop kết thúc.

2. Chọn **Create subscription**.

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.7-GuardDuty-Notifications/s10a.png)

11. Kiểm tra hộp thư của địa chỉ email vừa nhập. Trong vài phút, bạn sẽ nhận được email xác nhận đăng ký.

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.7-GuardDuty-Notifications/s11.png)

12. Trong email, chọn **Confirm subscription** để xác nhận. Thao tác này sẽ mở một trang xác nhận trên trình duyệt.

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.7-GuardDuty-Notifications/s12.png)

#### Tạo EventBridge rule để gửi phát hiện đến SNS topic

13. Sau khi đã đăng ký thành công SNS topic, bạn có thể cấu hình để tự động gửi phát hiện đến topic này. Tạo một EventBridge rule để lắng nghe các sự kiện từ GuardDuty. Truy cập **Amazon EventBridge** tại: https://console.aws.amazon.com/events/home

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.5-Security-Hub-Notifications/s13.png)

14. Chọn **Create rule** ở bên phải, đảm bảo loại **EventBridge Rule** được chọn.

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.5-Security-Hub-Notifications/s14.png)

1. Trong trang **Define rule detail**, đặt tên rule là **"guardduty-findings"**, sau đó chọn **Next**.

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.7-GuardDuty-Notifications/s15.png)

1. Trong trang **Build event pattern**, cuộn xuống phần **Event pattern** và chọn **Edit pattern** ở góc dưới bên phải.

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.7-GuardDuty-Notifications/s16.png)

1. Dán mẫu sự kiện (JSON) sau. Mẫu này dùng để bắt các sự kiện GuardDuty có mức độ nghiêm trọng cao (tương ứng CRITICAL).

```js
{
  "source": ["aws.guardduty"],
  "detail-type": ["GuardDuty Finding"],
  "detail": {
    "severity": [
      4, 4.0, 4.1, 4.2, 4.3, 4.4, 4.5, 4.6, 4.7, 4.8, 4.9,
      5, 5.0, 5.1, 5.2, 5.3, 5.4, 5.5, 5.6, 5.7, 5.8, 5.9,
      6, 6.0, 6.1, 6.2, 6.3, 6.4, 6.5, 6.6, 6.7, 6.8, 6.9,
      7, 7.0, 7.1, 7.2, 7.3, 7.4, 7.5, 7.6, 7.7, 7.8, 7.9,
      8, 8.0, 8.1, 8.2, 8.3, 8.4, 8.5, 8.6, 8.7, 8.8, 8.9
    ]
  }
}
```

18. Chọn **Next**.

19. Trong trang **Select target(s)**, từ menu thả xuống **Select a target**, chọn **SNS topic**.

20. Sau đó, từ menu thả xuống **Topic**, chọn **guardduty-findings**.
    ![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.7-GuardDuty-Notifications/s20.png)

21. Chọn **Next**.

22. Trong trang **Configure tags - optional**, chọn **Next**.

23. Trong trang **Review and create**, chọn **Create rule**. Hãy chú ý đến email của bạn trong phần còn lại của workshop.
    ![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.7-GuardDuty-Notifications/s23.png)
