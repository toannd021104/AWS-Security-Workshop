---
title: "Detective - Nhóm phát hiện"
date: "`r Sys.Date()`"
weight: 5
chapter: false
pre: " <b> 2.4.5 </b> "
---

Nhóm phát hiện bảo mật (Finding Groups) trong Amazon Detective cho phép bạn xem xét và phân tích nhiều hoạt động có liên quan đến cùng một sự cố bảo mật tiềm ẩn. Thay vì điều tra từng phát hiện bảo mật một cách rời rạc, Detective giúp gom các phát hiện nghiêm trọng – đặc biệt là từ Amazon GuardDuty – vào các nhóm có ngữ cảnh chung, từ đó hỗ trợ việc xác định nguyên nhân gốc rễ một cách hiệu quả hơn.

Trong thực tế, khi một tác nhân đe dọa cố gắng xâm nhập vào môi trường AWS, chúng thường không thực hiện một hành động đơn lẻ mà tiến hành một chuỗi các hành vi liên tiếp. Chuỗi hành động này có thể tạo ra nhiều phát hiện bảo mật khác nhau, xuất hiện ở các thời điểm khác nhau và liên quan đến nhiều thực thể khác nhau. Nếu các phát hiện này được xem xét riêng lẻ, rất dễ dẫn đến việc đánh giá sai mức độ nghiêm trọng của sự cố hoặc bỏ sót mối liên hệ quan trọng giữa chúng.

Amazon Detective giải quyết bài toán này bằng cách áp dụng kỹ thuật phân tích đồ thị để suy luận mối quan hệ giữa các phát hiện bảo mật và các thực thể liên quan, sau đó tự động nhóm chúng lại. Cách tiếp cận này giúp hình thành một bức tranh tổng thể về sự cố, thay vì chỉ nhìn thấy từng mảnh thông tin rời rạc. Do đó, các nhóm phát hiện bảo mật thường được khuyến nghị sử dụng như điểm khởi đầu cho quá trình điều tra.

Detective phân tích dữ liệu từ các phát hiện bảo mật và liên kết chúng với những phát hiện khác có khả năng liên quan, dựa trên các tài nguyên hoặc thuộc tính chung mà chúng chia sẻ. Ví dụ, các phát hiện phát sinh từ cùng một phiên IAM role, hoặc bắt nguồn từ cùng một địa chỉ IP, có khả năng cao là thuộc về cùng một hoạt động nền. Việc điều tra theo nhóm như vậy mang lại nhiều giá trị, ngay cả trong những trường hợp mối liên hệ được suy luận không hoàn toàn chính xác, bởi nó vẫn cung cấp thêm ngữ cảnh cho nhà phân tích bảo mật.

Bên cạnh các phát hiện bảo mật, mỗi nhóm còn bao gồm các thực thể liên quan, chẳng hạn như tài nguyên AWS, địa chỉ IP bên ngoài, hoặc các user agent. Những thực thể này đóng vai trò bổ sung ngữ cảnh, giúp làm rõ cách thức và phạm vi của sự cố bảo mật.

Sau khi một phát hiện GuardDuty ban đầu được tạo và được xác định là có liên quan đến các phát hiện khác, Amazon Detective sẽ tự động hình thành một nhóm phát hiện bảo mật bao gồm toàn bộ các phát hiện và thực thể liên quan. Quá trình này thường được hoàn tất trong vòng tối đa 48 giờ kể từ khi phát hiện ban đầu xuất hiện.
