# TRUYEN_KI_SO

🧩 1. MÔ TẢ ỨNG DỤNG
Ứng dụng gồm 2 phần:

Client (Người gửi): Tải file lên, tạo cặp khóa RSA, ký hash file bằng private key, gửi chữ ký + public key + tên file đến server.

Server (Người nhận): Nhận file, hash, chữ ký và public key → xác thực chữ ký để đảm bảo tính toàn vẹn và xác minh người gửi.

🗂️ 2. CẤU TRÚC THƯ MỤC
├── main.py                     # Backend Flask + Socket.IO
├── templates/
│   ├── index.html              # Trang giới thiệu chung
│   ├── client.html             # (Chưa gửi) - Giao diện gửi file
│   └── server.html             # Giao diện xác thực (người nhận)
├── uploads/                    # Nơi lưu file tạm


🔁 3. QUY TRÌNH HOẠT ĐỘNG
💻 Client (Người gửi)
Tải file lên.

Tạo khóa RSA (public/private).

Tạo hash SHA256 từ file.

Ký hash bằng private key → tạo chữ ký số.

Gửi chữ ký + public key + hash + tên file đến Server.

🖥️ Server (Người nhận)
Nhận các thông tin từ client.

Tạo lại hash từ file.

Giải mã chữ ký bằng public key.

So sánh kết quả:

✅ Nếu khớp → chữ ký hợp lệ.

❌ Nếu không khớp → chữ ký sai hoặc dữ liệu bị thay đổi.

⚙️ 4. CÁCH CHẠY ỨNG DỤNG
✅ Bước 1: Cài đặt thư viện
bash
Sao chép
Chỉnh sửa
pip install flask flask-socketio cryptography
✅ Bước 2: Chạy ứng dụng
bash
Sao chép
Chỉnh sửa
python main.py
✅ Bước 3: Truy cập trình duyệt
🌐 http://localhost:5000/ → Giao diện giới thiệu

🌐 http://localhost:5000/client → (nếu có client.html) Giao diện gửi file

🌐 http://localhost:5000/server → Giao diện xác thực file

5.Hỉnh Ảnh Minh Họa Web
![image](https://github.com/user-attachments/assets/387c752d-24e4-4adb-b0f0-1010e97c2820)
![image](https://github.com/user-attachments/assets/ba8b3775-a6b2-492d-af62-2a673098c89d)
![image](https://github.com/user-attachments/assets/27c6f206-c330-41d3-bf3c-8b5918500fb7)
