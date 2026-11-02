# PHÂN TÍCH SỰ CỐ KỸ THUẬT CAREPULSE

## PHẦN 1: PHÂN TÍCH VẤN ĐỀ

**1. Bốn điểm sai trong bản giải trình:**

- **DNS:** Có nhiệm vụ chuyển tên miền thành địa chỉ IP của máy chủ.
- **TCP/TLS:** Phải thiết lập kết nối TCP và mã hóa TLS trước khi truyền dữ liệu HTTPS.
- **HTTP:** Mã 404 là không tìm thấy tài nguyên, mã 500 là lỗi xử lý phía máy chủ.
- **DOM:** Sửa nội dung trong Tab Elements chỉ thay đổi giao diện tạm thời, không sửa dữ liệu trên Database.

**2. Vì sao phải trả về mã 500?**

Khi Database hoặc Backend bị lỗi, máy chủ không thể xử lý yêu cầu nên cần trả về mã 500. Nếu trả về 404, bệnh nhân có thể hiểu nhầm rằng hồ sơ xét nghiệm đã bị xóa, gây lo lắng và mất niềm tin vào hệ thống.

## PHẦN 2: SỬA LỖI VÀ HOÀN THIỆN GIẢI PHÁP

**3. Quy trình HTTP Request gồm 4 bước:**

- **Bước 1 - DNS:** Chuyển tên miền CarePulse thành địa chỉ IP máy chủ.
- **Bước 2 - TCP/TLS:** Thiết lập kết nối và mã hóa dữ liệu HTTPS
