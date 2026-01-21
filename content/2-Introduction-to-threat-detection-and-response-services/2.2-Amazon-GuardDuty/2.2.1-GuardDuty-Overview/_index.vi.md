---
title: "GuardDuty - Tổng quan"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 2.2.1 </b> "
---

#### GuardDuty - Tổng quan

Amazon GuardDuty là dịch vụ phát hiện mối đe doạ hoạt động liên tục, có nhiệm vụ giám sát và nhận diện các hành vi độc hại cũng như truy cập trái phép trong toàn bộ môi trường AWS của bạn. GuardDuty kết hợp nhiều kỹ thuật như học máy (ML), phát hiện bất thường và nhận diện phần mềm độc hại, đồng thời khai thác dữ liệu từ cả các nguồn AWS gốc và các nguồn tình báo bảo mật của bên thứ ba uy tín. Cách tiếp cận này giúp bảo vệ hiệu quả tài khoản AWS, khối lượng công việc và dữ liệu của bạn.

GuardDuty có khả năng phân tích quy mô rất lớn, xử lý hàng chục tỷ sự kiện đến từ nhiều nguồn dữ liệu AWS khác nhau, bao gồm nhật ký AWS CloudTrail, Amazon Virtual Private Cloud (Amazon VPC) Flow Logs và DNS query logs. Ngoài ra, dịch vụ còn giám sát các sự kiện dữ liệu của Amazon Simple Storage Service (Amazon S3), sự kiện đăng nhập Amazon Aurora, cũng như hoạt động runtime của Amazon Elastic Kubernetes Service (Amazon EKS), Amazon Elastic Compute Cloud (Amazon EC2) và Amazon Elastic Container Service (Amazon ECS), bao gồm cả các workload container không máy chủ chạy trên AWS Fargate.

GuardDuty cung cấp khả năng phát hiện mối đe doạ chính xác đối với các tài khoản có dấu hiệu bị xâm nhập — những tình huống thường khó nhận biết kịp thời nếu không có cơ chế giám sát liên tục gần thời gian thực. Ví dụ, GuardDuty có thể phát hiện các hành vi bất thường như truy cập tài nguyên AWS từ vị trí địa lý lạ vào thời điểm không phổ biến trong ngày. Đối với các tài khoản có truy cập theo lập trình, GuardDuty còn phát hiện các lời gọi API bất thường, chẳng hạn như nỗ lực vô hiệu hoá CloudTrail để che giấu hoạt động, hoặc tạo snapshot cơ sở dữ liệu từ các địa chỉ IP độc hại.

GuardDuty liên tục thu thập, giám sát và phân tích dữ liệu sự kiện của tài khoản AWS và các workload thông qua CloudTrail, VPC Flow Logs và DNS logs. Bạn không cần triển khai hay vận hành thêm phần mềm bảo mật hoặc hạ tầng bổ sung cho các chức năng bảo vệ cơ bản. Khi kết hợp nhiều tài khoản AWS trong cùng một tổ chức, GuardDuty cho phép tổng hợp các phát hiện mối đe doạ thay vì phải xử lý riêng lẻ từng tài khoản. Điều này giúp giảm đáng kể khối lượng công việc thu thập, phân tích và liên kết dữ liệu, cho phép bạn tập trung vào việc phản ứng nhanh với sự cố, duy trì mức độ an toàn cho tổ chức và tiếp tục mở rộng cũng như đổi mới trên nền tảng AWS.

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.1-GuardDuty-Overview/s1.png)
