---
title: "Tổng hợp phát hiện từ nhiều tài khoản AWS"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 3.2. </b> "
---

Khi kết hợp **AWS Security Hub** với **AWS Organizations**, bạn có thể tự động bật Security Hub cho toàn bộ các tài khoản trong tổ chức, bao gồm cả những tài khoản mới được tạo hoặc thêm vào sau này. Cách tiếp cận này giúp mở rộng phạm vi kiểm tra và thu thập phát hiện bảo mật, từ đó mang lại cái nhìn đầy đủ và chính xác hơn về trạng thái bảo mật tổng thể của tổ chức.

Thông qua việc sử dụng cơ chế **delegated administrator** của Security Hub cùng với cấu hình tập trung (central configuration), bạn có thể quản lý và theo dõi bảo mật một cách thống nhất trên nhiều dịch vụ AWS và giải pháp đối tác, trải rộng trên nhiều tài khoản và nhiều Region. Mô hình này đặc biệt phù hợp với các môi trường AWS quy mô lớn, nơi việc giám sát bảo mật phân tán theo từng tài khoản riêng lẻ sẽ gây khó khăn cho vận hành và phản ứng sự cố.

**Lưu ý cho người học**:  
Mặc dù trong workshop có đề cập rằng _“At this time, we are unable to demonstrate multi-account aggregation in this workshop”_, nhưng trong phần **Automated Security Response on AWS**, sơ đồ kiến trúc minh họa cho thấy các stack CloudFormation thực tế đã được triển khai trên nhiều tài khoản AWS khác nhau. Điều này phản ánh cách tiếp cận multi-account thường được áp dụng trong các môi trường sản xuất thực tế.
