### Phần 1: Phân tích lỗi sai 

1\. Mất trắng dữ liệu khi lỗi hệ thống (Rủi ro cao nhất) Ổ `C:\` là phân vùng hệ thống. Khi Windows bị lỗi (màn hình xanh, lỗi Win) cần phải format và cài lại hệ điều hành, toàn bộ dữ liệu trong ổ `C:\` — bao gồm thư mục `System32` — sẽ bị xoá sạch hoàn toàn.

2\. Vi phạm nguyên tắc bảo mật và quyền hệ thống (System Security) Thư mục `C:\Windows\System32` chứa các file thực thi hệ thống cốt lõi. Luôn lưu dữ liệu cá nhân vào đây gây rủi ro vô tình xóa/ghi đè file hệ thống. Đồng thời, thao tác tạo/sửa file tại đây yêu cầu quyền `Administrator`, dẫn đến việc các công cụ như VS Code hay Python Script có thể bị chặn truy cập (lỗi `PermissionError / Access Denied`).

3\. Sai lầm về hiệu năng SSD/HDD Nét tốc độ của SSD/HDD phụ thuộc vào chuẩn ổ cứng và chuẩn giao tiếp (NVMe/SATA), không phụ thuộc vào việc file nằm ở phân vùng `C:\` hay `D:\`. Lưu file ở `D:\` không làm giảm tốc độ đọc/ghi của file code.

### Phần 2: Đề xuất cây thư mục chuẩn (File Tree)

Chuyển toàn bộ dữ liệu sang Ổ D:\\ (Dữ liệu), đặt tên theo chuẩn kebab-case hoặc snake\_case (viết liền không dấu, dùng dấu gạch ngang/gạch dưới thay cho khoảng trắng).

D:\\ptit-documents/ nhap-mon-cntt/session-01/ session-02/bai1.py  
