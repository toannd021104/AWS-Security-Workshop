---
title: "Detective - Tổng quan"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 2.4.1 </b> "
---

#### Detective - Tổng quan

Amazon Detective là dịch vụ hỗ trợ phân tích và điều tra bảo mật, giúp các nhóm an ninh nhanh chóng xác định nguyên nhân gốc rễ của các hành vi bất thường hoặc rủi ro bảo mật tiềm ẩn trong môi trường AWS. Dịch vụ này tự động thu thập dữ liệu nhật ký từ các tài nguyên AWS và áp dụng các kỹ thuật như học máy, phân tích thống kê và lý thuyết đồ thị để xây dựng một tập dữ liệu được liên kết, từ đó hỗ trợ quá trình điều tra bảo mật một cách trực quan và hiệu quả hơn.

Amazon Detective giúp đơn giản hóa đáng kể quy trình điều tra sự cố, cho phép các đội bảo mật rút ngắn thời gian phân tích và đưa ra kết luận chính xác hơn. Các bộ dữ liệu đã được tổng hợp sẵn, kèm theo thông tin ngữ cảnh và tóm tắt, giúp người dùng nhanh chóng hiểu được bản chất và mức độ nghiêm trọng của các vấn đề bảo mật có thể xảy ra. Detective lưu trữ dữ liệu đã tổng hợp trong tối đa một năm và cung cấp các hình ảnh trực quan thể hiện sự thay đổi về loại hình cũng như khối lượng hoạt động theo từng giai đoạn thời gian, đồng thời liên kết các thay đổi này với các phát hiện bảo mật liên quan. Dịch vụ không yêu cầu chi phí trả trước; người dùng chỉ trả phí dựa trên số lượng sự kiện được phân tích, mà không cần cài đặt thêm phần mềm hay kích hoạt các hệ thống ghi log bổ sung.

Amazon Detective trích xuất và xử lý các sự kiện theo dòng thời gian, chẳng hạn như hoạt động đăng nhập, các lệnh gọi API và lưu lượng mạng, từ nhiều nguồn dữ liệu khác nhau bao gồm AWS CloudTrail, Amazon Virtual Private Cloud (Amazon VPC) Flow Logs, các phát hiện từ Amazon GuardDuty, AWS Security Hub và nhật ký kiểm toán (audit logs) của Amazon Elastic Kubernetes Service (Amazon EKS). Trên cơ sở đó, Detective xây dựng một biểu đồ hành vi dựa trên học máy, cung cấp cái nhìn tương tác và thống nhất về cách các tài nguyên hoạt động và tương tác với nhau theo thời gian. Thông qua việc khám phá biểu đồ hành vi này, bạn có thể phân tích các sự kiện bảo mật như đăng nhập thất bại, lệnh gọi API bất thường hoặc lưu lượng mạng đáng ngờ, từ đó hỗ trợ xác định nguyên nhân cốt lõi của các phát hiện bảo mật trên AWS.

Trong thực tế, các tác nhân đe dọa thường thực hiện một chuỗi hành động liên tiếp khi tìm cách xâm nhập vào môi trường AWS, dẫn đến việc tạo ra nhiều phát hiện bảo mật trên các tài nguyên khác nhau. Amazon Detective giới thiệu khái niệm _nhóm tìm kiếm_ (investigation groups), là tập hợp các phát hiện bảo mật và tài nguyên có liên quan đến cùng một sự cố tiềm ẩn, giúp bạn điều tra chúng một cách tổng thể thay vì xử lý từng phát hiện riêng lẻ. Cách tiếp cận này giúp giảm đáng kể thời gian phân loại và điều tra sự cố. Bạn có thể bắt đầu quá trình phân tích bằng cách xem các nhóm tìm kiếm để có cái nhìn toàn diện hơn về sự kiện, đồng thời sử dụng các hình ảnh trực quan tương tác và khả năng mô tả chuỗi sự kiện bằng ngôn ngữ tự nhiên thông qua AI tổng hợp để hiểu rõ hơn bối cảnh và diễn biến của sự cố bảo mật.
