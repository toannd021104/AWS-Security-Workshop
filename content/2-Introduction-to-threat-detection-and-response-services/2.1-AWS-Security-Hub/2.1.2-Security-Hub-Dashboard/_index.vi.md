---
title: "Security Hub - Bảng điều khiển"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 2.1.2 </b> "
---

#### Security Hub summary

1. Truy cập trang **Summary** của Security Hub tại liên kết sau:  
   [AWS Security Hub summary page](https://console.aws.amazon.com/securityhub/home?#/summary)

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.2-Security-Hub-Dashboard/s1.png)

2. Ở phần đầu trang, xem tiện ích **Security standards**. Khu vực này hiển thị điểm số bảo mật tổng quan gần nhất của tài khoản cũng như điểm số theo từng tiêu chuẩn Security Hub. Điểm số bảo mật nằm trong khoảng từ 0–100%, phản ánh tỷ lệ các kiểm soát đã **Passed** so với tổng số kiểm soát đang được bật.

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.2-Security-Hub-Dashboard/s2.png)

3. Dành một vài phút để quan sát các insight được hiển thị trên trang Summary. Bạn có thể xác định những tài nguyên nào trong tài khoản đang phát sinh nhiều kiểm tra bảo mật nhất hay không. Một trong các tiện ích cung cấp cái nhìn tổng hợp về các tài nguyên tạo ra nhiều phát hiện nhất, được phân loại theo từng loại tài nguyên.

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.2-Security-Hub-Dashboard/s3.png)
![VPC](/images/2/2.1-AWS-Security-Hub/2.1.2-Security-Hub-Dashboard/s3b.png)

4. Cuộn xuống để xem các biểu đồ trong phần **Most common threat type** và **Software vulnerabilities with exploits**. Các biểu đồ này giúp bạn nắm được những mối đe doạ phổ biến và các lỗ hổng phần mềm đang được tổng hợp trong tài khoản.

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.2-Security-Hub-Dashboard/s4.png)

Xem chi tiết các phát hiện được gửi từ AWS GuardDuty. Chọn một phát hiện bất kỳ để xem thông tin chi tiết hơn:

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.2-Security-Hub-Dashboard/s5.png)

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.2-Security-Hub-Dashboard/s6.png)
![VPC](/images/2/2.1-AWS-Security-Hub/2.1.2-Security-Hub-Dashboard/s7.png)
