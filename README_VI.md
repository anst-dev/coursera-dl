# Hướng dẫn sử dụng cs-dlp (Tiếng Việt)

Đây là công cụ hỗ trợ tải video và tài liệu từ Coursera (fork của coursera-dl), đã được cài đặt và cấu hình sẵn trên máy của bạn.

## 1. Cấu hình đã thiết lập
File cấu hình: `coursera-dl.conf`
Hiện tại đã được thiết lập các thông số sau:
- **Xác thực (CAUTH)**: Đã nhập mã token xác thực.
- **Phụ đề**: Tiếng Anh (`en`).
- **Chế độ tải**: Hỗ trợ tiếp tục tải khi bị gián đoạn (`--resume`).
- **Định dạng loại bỏ**: Không tải file HTML (`--ignore-formats html`).
- **Chất lượng video**: 720p.

## 2. Cách sử dụng

Mở PowerShell tại thư mục này và chạy lệnh theo cú pháp:

```powershell
python cs_dlp/main.py [tên-khóa-học]
```

### Cách lấy tên khóa học (slug)
Tên khóa học là phần nằm sau `https://www.coursera.org/learn/` trên thanh địa chỉ trình duyệt.
Ví dụ:
- Link: `https://www.coursera.org/learn/machine-learning`
- Tên khóa học: `machine-learning`

### Các ví dụ lệnh

**Tải một khóa học:**
```powershell
python cs_dlp/main.py machine-learning
```

**Tải nhiều khóa học cùng lúc:**
```powershell
python cs_dlp/main.py course-1 course-2
```

**Chỉ tải tài liệu (không tải video):**
Thêm tham số `--ignore-formats mp4`
```powershell
python cs_dlp/main.py --ignore-formats mp4 machine-learning
```

**Tải thêm phụ đề tiếng Việt (nếu có):**
Ghi đè cấu hình mặc định bằng cách thêm tham số:
```powershell
python cs_dlp/main.py --subtitle-language en,vi machine-learning
```

## 3. Khắc phục sự cố thường gặp

- **Lỗi xác thực (401 Unauthorized)**:
  Mã CAUTH trong file `coursera-dl.conf` có thể đã hết hạn. Bạn cần lấy mã mới từ trình duyệt (cookie `CAUTH`) và cập nhật lại vào file `coursera-dl.conf`.

- **Không tìm thấy khóa học**:
  Đảm bảo bạn đã **đăng ký (Enroll)** vào khóa học đó trên Coursera bằng tài khoản tương ứng với mã CAUTH.

- **Lỗi không tìm thấy lệnh**:
  Đảm bảo bạn đang đứng đúng thư mục chứa source code và chạy lệnh bắt đầu bằng `python cs_dlp/main.py`.
