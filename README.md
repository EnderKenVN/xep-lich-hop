# Xếp lịch họp nhóm

Công cụ web một tệp giúp nhóm sinh viên tìm khung giờ họp chung: nhập lịch bận của từng người, công cụ gợi ý 3 khung giờ có nhiều người rảnh nhất.

Sản phẩm dự thi **Kỹ năng CNTT và Ứng dụng AI – K21, FPT PolySchool TP.HCM**.

**Link truy cập:** https://enderkenvn.github.io/xep-lich-hop/

## Vấn đề
Mỗi thành viên có thời khóa biểu và việc làm thêm khác nhau, cả nhóm mất rất nhiều tin nhắn qua lại mới chốt được giờ họp.

## Tính năng
- Nhập lịch bận (ngày, từ giờ, đến giờ) cho tối đa 8 thành viên.
- Chọn thời lượng họp (1 đến 13 giờ), số người tối thiểu và người bắt buộc có mặt.
- Gợi ý 3 khung giờ tốt nhất, kèm danh sách người không rảnh.
- Bản đồ nhiệt số người rảnh theo từng giờ, đánh dấu 3 khung gợi ý.
- Sao chép tin nhắn mời họp để dán vào nhóm chat.
- Dữ liệu tự lưu trong trình duyệt (localStorage), không gửi đi đâu.

## Cách chạy
Không cần cài đặt hay API key. Mở `index.html` bằng trình duyệt, hoặc dùng bản demo trực tuyến. Bấm "Nạp dữ liệu mẫu" để xem ví dụ.

## Cơ chế hoạt động
1. Mỗi dòng lịch bận được kiểm tra (đúng tên, đúng ngày, giờ nguyên, giờ đến lớn hơn giờ từ); dòng lỗi không được tính.
2. Mỗi tuần chia thành 91 ô giờ (7 ngày x 13 giờ, từ 8h đến 21h); một người rảnh ở ô nào không có khoảng bận trùng.
3. Với thời lượng L giờ, thử mọi điểm bắt đầu trong từng ngày. Khung hợp lệ khi mọi người bắt buộc đều rảnh suốt L giờ và đủ số người tối thiểu.
4. Điểm = số người rảnh x 1000 - thứ tự trong tuần: nhiều người hơn thì thắng, bằng nhau thì khung sớm hơn thắng. Lấy 3 khung cao điểm nhất.

## AI được dùng ở đâu và kiểm tra thế nào
- Công cụ **không có tính năng AI chạy bên trong**: phần tìm khung giờ là thuật toán cố định, cùng dữ liệu luôn cho cùng kết quả.
- AI (Claude, Anthropic) được dùng để **hỗ trợ phát triển**: gợi ý ý tưởng, viết và chỉnh mã, kiểm thử.
- Cách kiểm tra: nhóm chạy với dữ liệu mẫu và lịch thật, đối chiếu kết quả với tính tay; công cụ kiểm tra từng dòng lịch bận nhập vào và báo lỗi nếu sai.

## Giới hạn
Tính theo giờ tròn, khung 8h đến 21h, lịch lặp giống nhau mỗi tuần, tối đa 8 thành viên, họp nằm trọn trong một ngày. Dữ liệu lưu riêng từng trình duyệt, chưa đồng bộ giữa các máy.

## Dữ liệu mẫu
5 thành viên và lịch bận trong dữ liệu mẫu do nhóm tự tạo, không có dữ liệu cá nhân thật.

## Nhóm thực hiện
- Lê Hoàng Phương
- Lê Diệu Tuyết Linh
- Bùi Khải Phúc Thịnh
