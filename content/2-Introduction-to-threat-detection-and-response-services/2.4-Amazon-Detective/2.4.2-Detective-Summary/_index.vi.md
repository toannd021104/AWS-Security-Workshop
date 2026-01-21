---
title: "Detective - Tóm tắt"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 2.4.2 </b> "
---

Trang **Summary** trong Amazon Detective đóng vai trò là điểm khởi đầu quan trọng để xác định các thực thể cần được điều tra, dựa trên những hoạt động đã diễn ra trong vòng 24 giờ gần nhất. Thông qua trang này, bạn có thể nhanh chóng nhận diện các thực thể liên quan đến những hành vi bất thường cụ thể, từ đó định hướng quá trình phân tích và truy vết nguyên nhân.

Để truy cập trang Summary, trong bảng điều hướng của Detective, chọn **Summary**. Trang này cũng sẽ được hiển thị mặc định khi bạn mở bảng điều khiển Amazon Detective lần đầu tiên.

Từ trang Summary, bạn có thể xác định các thực thể thỏa mãn một hoặc nhiều tiêu chí sau:

- Các thực thể liên quan đến những cuộc điều tra cho thấy dấu hiệu của sự kiện bảo mật tiềm ẩn do Detective phát hiện.
- Các thực thể tham gia vào hoạt động xuất phát từ những vị trí địa lý mới chưa từng được quan sát trước đó.
- Các thực thể thực hiện số lượng lệnh gọi API lớn nhất trong khoảng thời gian theo dõi.
- Các EC2 instance có lưu lượng mạng cao nhất.
- Các cụm container có số lượng container lớn nhất.

Mỗi bảng thông tin trên trang Summary đều cho phép bạn chuyển trực tiếp sang chi tiết của một thực thể cụ thể để tiếp tục điều tra sâu hơn.

Khi làm việc với trang Summary, bạn có thể điều chỉnh **phạm vi thời gian** để quan sát hoạt động trong bất kỳ khoảng 24 giờ nào thuộc 365 ngày trước đó. Khi bạn thay đổi thời điểm **bắt đầu**, thời điểm **kết thúc** sẽ tự động được cập nhật thành 24 giờ sau mốc thời gian đã chọn, giúp việc so sánh và phân tích trở nên nhất quán.

Amazon Detective cho phép truy cập dữ liệu sự kiện lịch sử trong tối đa một năm. Các dữ liệu này được trình bày thông qua hệ thống trực quan hóa, thể hiện sự thay đổi về loại hình và khối lượng hoạt động theo thời gian, đồng thời liên kết trực tiếp với các phát hiện từ Amazon GuardDuty. Cách tiếp cận này giúp bạn dễ dàng nhận biết xu hướng, bất thường và mối liên hệ giữa các sự kiện bảo mật trong quá trình điều tra.
