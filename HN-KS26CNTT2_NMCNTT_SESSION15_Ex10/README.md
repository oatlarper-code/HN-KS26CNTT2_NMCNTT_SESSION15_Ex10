# 5.Yêu cầu đầu ra
1. Phần I.Phân tích và Đề xuất (Đa giải pháp)
- Input: 4 ban (Kỹ thuật, Thiết kế, Kinh doanh, Nhà đầu tư) với tổng số lượng (4-5 người cốt lõi), giao tiếp nội bộ, phân chia công việc, tương tác với đối tác ngoài trường, chuẩn bị bước vào giai đoạn nước rút với nhiều deadline dồn dập.
- Output: Trao đổi thông tin dễ dàng, không bị trôi tin nhắn quan trọng, dễ quản lý nhiệm vụ và kiểm soát lịch sử

||Giải pháp A|Giái pháp B|
|-|-|-|
Ưu điểm|Cả nhóm đã dùng, giao diện thân quen, free, không cần cài thêm, hỗ trợ gửi file, hình ảnh, ghim tin nhắn, tất cả đều có trên điện thoại cá nhân sẵn.| Phân channel chuyên đề (#thong-bao, #dev, #design, #kinh-doanh), reply in Thread giữ khung chat chính sạch sẽ, chuyển tin nhắn chat thành Task có Deadline bằng 1-click, tìm kiếm file và tin nhắn theo từ khóa, người gửi, kết hợp luôn Calendar, Docs, Video call trong 1 nền tảng.
Nhược điểm|Thông tin dễ bị trôi, không có tính chuyên nghiệp, tìm kiếm tài liệu khó khăn|Yêu cầu thời gian làm quen, một số đối tác không sử dụng nền tảng này
2. Phần II. So sánh và lựa chọn

|Tiêu chí nghiệp vụ|Giải pháp A|Giải pháp B
|-|-|-|
Tin nhắn bị trôi|❌Kém|✅Tốt
Quản lý công việc|❌Kém|✅Tốt
Giao diện người dùng|✅Tốt|⚠️Trung bình
Tìm kiếm|✅Tốt|✅Tốt
Giao tiếp bất đồng bộ|❌Kém|Tốt
- Lựa chọn: Sử dụng Lark Suite làm công cụ chính nội bộ còn Zalo làm công cụ phụ liên lạc đối tác
- Bẫy 1: Lark Suite có moblie app giúp thành viên làm việc ổn định
- Bẫy 2: Chi phí học tập trên Lark Suite không bị ảnh hưởng nhiều bởi Zalo chính là nguyên nhân trôi dữ liệu 
- Bẫy 3: Lập nhóm zalo riêng biệt dùng để giao tiếp với đối tác còn Lark Suite để lưu trữ dữ liệu nội bộ của đối tác
3. Phần III.Thiết kế và triển khai
```
CampusPay 
|
|-- 1. Dev (Ban Kỹ thuật)
|   |_API keys, thông tin khách hàng
|   |_Quyền đăng: Thành viên Ban kỹ thuật
|
|-- 2. Design (Ban thiết kế)
|   |_Thiết kế UI
|   |_Quyền đăng: Thành viên Ban thiết kế
|
|-- 3. Business (Ban kinh doanh)
|   |_Viết Business Plan 
|   |_Quyền đăng: Thành viên Ban kinh doanh
|
|-- 4. General (Nhóm chat chung)
    |_Trao đổi, chia sẻ
    |_Quyền đăng: tất cả thành viên trong nhóm

```
- Phạm vi áp dụng: chỉ được thông báo chung trên khi đưa tin quan trọng 
- Trả lời tin nhắn: sử dụng tính năng Reply in Thread để không bị trôi tin nhắn
- Hình phạt: sử dụng @all sai mục đích sẽ bị tính cờ đỏ và phạt theo quy định