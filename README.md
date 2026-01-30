# StudentMS (studentms)

Ngắn gọn: hệ thống quản lý học sinh PHP (dùng XAMPP / MySQL).

**Cấu trúc**
- `studentms/` — mã nguồn front-end và admin.
- `create_database.sql` — script tạo CSDL (`studentmsdb`) và các bảng cần thiết.

**Yêu cầu**
- XAMPP (Apache + MySQL)
- PHP 7.x/8.x (tùy host)

**Cài đặt nhanh (Windows, XAMPP)**
1. Đặt toàn bộ thư mục vào `C:\xampp\htdocs\` (đã có sẵn trong workspace).
2. Bật Apache và MySQL trong XAMPP Control Panel.

**Tạo/nhập CSDL**
- Bằng phpMyAdmin:
  1. Mở http://localhost/phpmyadmin
  2. Chọn Import → chọn file `create_database.sql` → Go

- Bằng MySQL CLI (XAMPP mặc định user `root` không có mật khẩu):
```bash
cd C:\xampp\htdocs\qlhs
mysql -u root < create_database.sql
```

**Kết nối**
- File cấu hình DB: `studentms/includes/dbconnection.php` và `studentms/admin/includes/dbconnection.php` — mặc định sử dụng:
  - Host: `localhost`
  - User: `root`
  - Password: `` (rỗng)
  - Database: `studentmsdb`

**Tài khoản mặc định**
- Admin mẫu được chèn trong script: `Administrator` / mật khẩu `admin` (chưa hash). Thay đổi ngay sau khi cài.

**Ghi chú bảo mật & vận hành**
- Đổi mật khẩu MySQL nếu triển khai công khai.
- Hash mật khẩu Admin/Student (ví dụ `password_hash()`), hiện script chèn mật khẩu thô cho demo.
- Kiểm tra quyền thư mục upload cho thư mục chứa ảnh và file bài tập tải lên.

**Muốn tôi làm tiếp**
- Thay `admin` bằng mật khẩu đã hash và cập nhật script.  
- Chạy import trên máy của bạn và kiểm tra trang đăng nhập.  

