# Bài 2: Quản trị Tường lửa UFW cho Cụm Dịch vụ Multi-port

## 1. Mục tiêu
Thiết lập tường lửa UFW để bảo mật hệ thống máy chủ chạy nhiều cổng dịch vụ đồng thời. Hiểu cách cấu hình mở rộng cổng cho các cổng dịch vụ web và cô lập các cổng cơ sở dữ liệu.

## 2. Các bước cấu hình trên VPS

Các lệnh cấu hình UFW đã thực hiện:

```bash
# Khai báo các chính sách mặc định (chặn tất cả kết nối vào, cho phép kết nối ra)
sudo ufw default deny incoming
sudo ufw default allow outgoing

# Cho phép kết nối SSH (để quản trị)
sudo ufw allow 22/tcp

# Cho phép kết nối Web HTTP tiêu chuẩn (Nginx)
sudo ufw allow 80/tcp

# Cho phép cổng ứng dụng Spring Boot
sudo ufw allow 8082/tcp

# Kích hoạt UFW
sudo ufw enable
```

*Lưu ý: Cổng MySQL (3306/tcp) không được thêm vào danh sách allow nên sẽ tự động bị chặn từ Internet theo chính sách mặc định `deny incoming`.*

## 3. Kết quả kiểm tra

Đầu ra của lệnh kiểm tra trạng thái UFW:
```bash
sudo ufw status verbose
```

**Kết quả (Output):**
```text
(Học viên hãy copy kết quả hiển thị trên terminal sau khi chạy lệnh sudo ufw status verbose trên VPS và dán đè lên dòng chữ này)
```
