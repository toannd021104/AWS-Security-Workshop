---
title: "Security Hub - Tổng quan"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 2.1.1 </b> "
---

#### Tiêu chuẩn bảo mật

1. Truy cập trang [AWS Security Hub Summary](https://console.aws.amazon.com/securityhub/home?#/summary).

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.1-security-hub-overview/s1.png)  
![VPC](/images/2/2.1-AWS-Security-Hub/2.1.1-security-hub-overview/s1b.png)  
![VPC](/images/2/2.1-AWS-Security-Hub/2.1.1-security-hub-overview/s1c.png)

2. Tại trang **Summary**, bạn có thể quan sát các tiêu chuẩn bảo mật đang được kích hoạt trong tài khoản, cùng với số lượng kiểm soát đạt và không đạt đối với từng tiêu chuẩn. Phần trăm hiển thị phản ánh tỷ lệ các kiểm soát ở trạng thái **Passed** so với tổng số kiểm soát có trạng thái **Passed** hoặc **Failed**.

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.1-security-hub-overview/s2.png)

3. Từ menu điều hướng bên trái, chọn **Security standards**.

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.1-security-hub-overview/s3.png)

4. Các tiêu chuẩn bảo mật này đã được cấu hình và bật sẵn thông qua CloudFormation khi môi trường workshop được triển khai.

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.1-security-hub-overview/s4.png)

5. Chọn một tiêu chuẩn để xem chi tiết. Nhấn **View results** để kiểm tra tiêu chuẩn **NIST Special Publication 800-53 Revision 5**.

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.1-security-hub-overview/s5.png)

#### Kiểm soát bảo mật

6. Ở phần đầu trang, bạn có thể lọc danh sách kiểm soát theo trạng thái như **Passed**, **Failed**, **Disabled**, v.v. Ngoài ra, có thể tìm kiếm nhanh một kiểm soát cụ thể bằng ô **Filter all enabled controls**. Thực hiện lọc theo **ID** và nhập **EC2.13**.

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.1-security-hub-overview/s6.png)

7. Chọn kiểm soát **Security groups should not allow ingress from 0.0.0.0/0 to port 22**. Danh sách hiển thị các tài nguyên đã được đánh giá theo kiểm soát này cùng trạng thái hiện tại của từng tài nguyên. Bạn sẽ thấy cả các tài nguyên **FAILED** và **PASSED**.

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.1-security-hub-overview/s7.png)

8. Mỗi kiểm soát trong Security Hub đều đi kèm hướng dẫn khắc phục. Ở đầu trang, chọn **Remediation instructions link** để mở tài liệu hướng dẫn trong một tab mới.

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.1-security-hub-overview/s8.png)

#### Điều tra tài nguyên cấu hình không đúng

1. Quay lại trang chi tiết của kiểm soát bảo mật. Với một tài nguyên đang ở trạng thái **FAILED**, tại cột **Investigate**, chọn **Config rule**. Thao tác này sẽ dẫn bạn sang AWS Config để xem lịch sử cấu hình của tài nguyên hoặc quy tắc đã thực hiện việc đánh giá.

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.1-security-hub-overview/s9.png)

2. Chọn **Configuration timeline** để mở dòng thời gian cấu hình của security group trong AWS Config. Tại đây, bạn có thể xác định thời điểm tài nguyên trở nên không tuân thủ bằng cách xem các sự kiện theo mốc thời gian. Có thể mở rộng từng sự kiện để xem chi tiết.

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.1-security-hub-overview/s10.png)

3. Mở rộng mục **CloudTrail Event** trong danh sách sự kiện.

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.1-security-hub-overview/s11.png)

4. Trong phần **View event**, chọn **CloudTrail** để xem chi tiết sự kiện đã được ghi nhận. AWS CloudTrail theo dõi và lưu lại các hoạt động trong tài khoản AWS, hỗ trợ việc phân tích, kiểm toán và xử lý sự cố.

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.1-security-hub-overview/s12.png)

#### Kiểm soát hợp nhất

1. Quay lại Security Hub và mở trang **General settings** từ menu điều hướng.  
   https://console.aws.amazon.com/securityhub/home?#/settings/general

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.1-security-hub-overview/s13.png)

2. Tại đầu trang, xác nhận rằng hai tuỳ chọn **Auto-enable new controls in enabled standards** và **Consolidated control findings** đang được bật.

3. Chọn **Controls** trong menu điều hướng. Trang này hiển thị toàn bộ danh sách kiểm soát ở dạng hợp nhất, giúp bạn dễ dàng theo dõi số lượng kiểm soát đang đạt, không đạt hoặc ở trạng thái khác. Khi sử dụng phát hiện hợp nhất, các kiểm soát xuất hiện trong nhiều tiêu chuẩn sẽ không tạo ra các phát hiện trùng lặp, từ đó giảm số lượng phát hiện và tránh nhầm lẫn khi phân tích.

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.1-security-hub-overview/s15.png)

#### Insights

1. Trong menu điều hướng bên trái, chọn **Insights**.

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.1-security-hub-overview/s16.png)

2. Tại ô tìm kiếm, nhập **"severity"** và chọn insight **24. Severity by counts of findings**.

![VPC](/images/2/2.1-AWS-Security-Hub/s17.png)

3. Security Hub cung cấp nhiều insight được quản lý sẵn mà người dùng không thể chỉnh sửa hoặc xoá. **24. Severity by counts of findings** là một ví dụ điển hình. Dành thời gian xem tổng quan số lượng phát hiện theo mức độ nghiêm trọng trong môi trường. Chọn một **Severity Label** (ví dụ **Critical**) để xem chi tiết các phát hiện tương ứng.

![VPC](/images/2/2.1-AWS-Security-Hub/s18.png)
