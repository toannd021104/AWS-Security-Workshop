---
title: "GuardDuty - Kế hoạch bảo vệ"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 2.2.3 </b> "
---

#### Điều kiện tiên quyết

Đảm bảo EC2 instance đã được gán **SSM Management Role**. Để biết cách gắn instance profile cho EC2 instance, tham khảo tài liệu tại:  
https://docs.aws.amazon.com/systems-manager/latest/userguide/setup-instance-permissions.html#attach-instance-profile

#### S3 Protection trong Amazon GuardDuty

1. Truy cập trang **S3 Protection** trong mục **Protection plans** của bảng điều khiển GuardDuty.

2. Kiểm tra và xác nhận rằng **S3 Protection** đã được bật.

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.3-GuardDuty-Protection-plans/s2.png)

#### EKS Protection trong Amazon GuardDuty

3. Truy cập trang **EKS Protection** trong mục **Protection plans** của bảng điều khiển GuardDuty.

4. Đảm bảo rằng **EKS Audit Log Monitoring** đang được bật.  
   Lưu ý: Trải nghiệm cấu hình **GuardDuty EKS Runtime Monitoring** hiện được quản lý như một phần của tính năng **Runtime Monitoring** mới.

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.3-GuardDuty-Protection-plans/s4.png)

#### Runtime Monitoring trong Amazon GuardDuty

5. Truy cập trang **Runtime Monitoring** trong mục **Protection plans** của bảng điều khiển GuardDuty.

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.3-GuardDuty-Protection-plans/s5.png)

1. Xác nhận rằng **Runtime Monitoring** đã được bật, đồng thời cấu hình **Automated agent configuration** cho từng môi trường Amazon EKS, AWS Fargate (chỉ ECS) và Amazon EC2.

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.3-GuardDuty-Protection-plans/s6.png)

1. Trong trang **Runtime Monitoring**, chuyển sang tab **Runtime coverage**. Hãy quan sát mục **Coverage statistics**.  
   Nội dung chi tiết không nằm trong phạm vi workshop này, bạn có thể tìm hiểu thêm về cách thiết lập Runtime Monitoring tại:  
   https://docs.aws.amazon.com/guardduty/latest/ug/runtime-monitoring.html

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.3-GuardDuty-Protection-plans/s7a.png)

_Lưu ý_: Nếu **Coverage status** của EC2 Instance là _unhealthy_ và trường **Issue** hiển thị **"No Agent Reporting"** hoặc các lỗi liên quan đến SSM

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.3-GuardDuty-Protection-plans/errorSSM.png)

nguyên nhân có thể do không cài đặt được SSM agent trên EC2 instance. Bạn có thể xác minh bằng cách kiểm tra file `/var/log/amzn-guardduty-agent` trên instance (Amazon Linux 2, Amazon Linux 2023). Tham khảo thêm tại:  
https://docs.aws.amazon.com/guardduty/latest/ug/gdu-assess-coverage-ec2.html#ec2-runtime-monitoring-coverage-issues-troubleshoot

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.3-GuardDuty-Protection-plans/s7b.png)

#### Malware Protection cho EC2 trong Amazon GuardDuty

8. Truy cập trang **Malware Protection** trong mục **Protection plans** của bảng điều khiển GuardDuty.

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.3-GuardDuty-Protection-plans/s8.png)

9. GuardDuty tự động kích hoạt quét malware khi phát hiện một finding cho thấy có dấu hiệu mã độc trên EC2 instance hoặc workload container. Đảm bảo rằng tuỳ chọn **GuardDuty-initiated malware scan** đã được bật.

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.3-GuardDuty-Protection-plans/s9.png)

Dưới đây là ví dụ một số lần quét malware trên EC2:

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.3-GuardDuty-Protection-plans/s9b.png)

Khi theo dõi chi tiết một lần quét thông qua **Scan ID**:

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.3-GuardDuty-Protection-plans/s9c.png)

_Tệp EICAR-Test_ là tệp dùng để kiểm tra khả năng phát hiện mối đe doạ và không phải là virus thực sự.

10. Cuộn xuống và bật tuỳ chọn **Retain scanned snapshots when malware is detected**.

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.3-GuardDuty-Protection-plans/s10.png)

#### RDS Protection trong Amazon GuardDuty

11. Truy cập trang **RDS Protection** trong mục **Protection plans** của bảng điều khiển GuardDuty.

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.3-GuardDuty-Protection-plans/s11.png)

12. Đảm bảo rằng **RDS Login Activity Monitoring** đã được bật.

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.3-GuardDuty-Protection-plans/s12.png)

#### Lambda Protection trong Amazon GuardDuty

13. Truy cập trang **Lambda Protection** trong mục **Protection plans** của bảng điều khiển GuardDuty.

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.3-GuardDuty-Protection-plans/s13.png)

14. Xác nhận rằng **Lambda Network Activity Monitoring** đang được bật.

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.3-GuardDuty-Protection-plans/s14.png)
