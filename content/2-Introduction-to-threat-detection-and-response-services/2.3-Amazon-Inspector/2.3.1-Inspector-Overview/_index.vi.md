---
title: "Inspector - Tổng quan"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 2.3.1 </b> "
---

#### Inspector

Amazon Inspector là dịch vụ quản lý lỗ hổng bảo mật hoạt động liên tục, thực hiện quét các workload trên AWS nhằm phát hiện lỗ hổng phần mềm cũng như các rủi ro liên quan đến khả năng tiếp xúc mạng ngoài ý muốn. Chỉ với một vài thao tác trong AWS Management Console, bạn có thể kích hoạt và sử dụng Amazon Inspector cho toàn bộ các tài khoản trong AWS Organizations. Sau khi được bật, Inspector tự động phát hiện các Amazon Elastic Compute Cloud (EC2) instance, container image lưu trữ trong Amazon Elastic Container Registry (ECR) cũng như được sử dụng trong các công cụ CI/CD, và các AWS Lambda function ở quy mô lớn, đồng thời bắt đầu đánh giá các tài nguyên này dựa trên những lỗ hổng đã được biết đến.

Amazon Inspector tính toán điểm rủi ro chi tiết cho từng phát hiện bằng cách kết hợp thông tin CVE với các yếu tố ngữ cảnh như khả năng truy cập mạng và mức độ có thể bị khai thác. Điểm rủi ro này được sử dụng để ưu tiên xử lý các lỗ hổng nghiêm trọng nhất, qua đó nâng cao hiệu quả của quá trình khắc phục. Toàn bộ các phát hiện được tập trung trong bảng điều khiển Amazon Inspector và đồng thời được gửi sang AWS Security Hub và Amazon EventBridge để phục vụ tự động hóa các quy trình phản ứng. Đối với container image, các lỗ hổng được phát hiện cũng sẽ được gửi trực tiếp đến Amazon ECR để chủ sở hữu tài nguyên có thể theo dõi và xử lý. Amazon Inspector hỗ trợ các nhóm bảo mật và đội ngũ phát triển, ở mọi quy mô, đạt được mức độ bảo mật và tuân thủ hạ tầng một cách toàn diện trong môi trường AWS.

![VPC](/images/2/2.3/2.3.1/s1.png)
