<<<<<<< HEAD
# Smart Locker System with Face Recognition

Hệ thống tủ khóa thông minh với nhận diện khuôn mặt, bao gồm backend API và Flutter mobile app.

## 🏗️ Kiến trúc hệ thống

```
locker_id/
├── backend/          # FastAPI Backend
│   ├── api/         # API routes
│   ├── config/      # Database config
│   ├── models/      # Data models
│   └── main.py      # Main server
└── frontend/        # Flutter App
    └── locker_app/  # Mobile application
```

## 🚀 Cách chạy hệ thống

### 1. Backend Setup

```bash
cd backend

# Tạo virtual environment
python -m venv venv

# Kích hoạt virtual environment
# Trên macOS/Linux:
source venv/bin/activate
# Trên Windows:
# venv\Scripts\activate

# Cài đặt dependencies
pip install -r requirements_simple.txt

# Chạy server
python main_simple.py
```

Server sẽ chạy tại: http://localhost:8000

### 2. Flutter App Setup

```bash
cd frontend/locker_app

# Cài đặt dependencies
flutter pub get

# Chạy app
flutter run
```

## 📱 Tính năng chính

### Backend APIs

1. **Face Registration** (`POST /api/face/register`)
   - Đăng ký khuôn mặt của chủ nhân
   - Lưu trữ encoding khuôn mặt

2. **Face Verification** (`POST /api/face/verify`)
   - Xác thực khuôn mặt
   - So sánh với khuôn mặt đã đăng ký

3. **Locker Unlock** (`POST /api/face/unlock-locker`)
   - Mở khóa tủ bằng nhận diện khuôn mặt
   - Kết hợp verification + unlock

### Flutter App

1. **Camera Integration**
   - Chụp ảnh khuôn mặt
   - Real-time camera preview
   - Face scanning animation

2. **Face Registration**
   - Nút "Register Face" để đăng ký khuôn mặt
   - Upload ảnh lên server

3. **Face Recognition**
   - Nút "Unlock with Face Recognition"
   - Gửi ảnh lên server để verify
   - Hiển thị kết quả match/unmatch

## 🔧 API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/face/register` | Đăng ký khuôn mặt |
| POST | `/api/face/verify` | Xác thực khuôn mặt |
| POST | `/api/face/unlock-locker` | Mở khóa tủ bằng khuôn mặt |
| GET | `/api/face/status` | Kiểm tra trạng thái service |
| DELETE | `/api/face/unregister` | Xóa đăng ký khuôn mặt |

## 📊 Logging

### Backend Logs
- ✅ Face registered successfully for user: owner
- ✅ Face verification successful for user: owner
- 🔓 Locker 12 unlocked successfully for user: owner
- ❌ Face verification failed for user: owner

### Flutter App Logs
- 🔍 Face verification response: {...}
- ✅ FACE MATCH DETECTED - Locker unlocked successfully!
- ❌ Face verification failed: No face detected

## 🛠️ Cấu hình

### Backend Configuration
- **Port**: 8000
- **Host**: 0.0.0.0 (cho phép kết nối từ bên ngoài)
- **Database**: SQLite (file-based)
- **Face Storage**: In-memory (demo) / Database (production)

### Flutter App Configuration
- **Backend URL**: http://localhost:8000/api/face
- **Locker ID**: 12 (có thể thay đổi)
- **User ID**: "owner" (default)

## 🔒 Bảo mật

**Lưu ý**: Đây là phiên bản demo đơn giản. Trong production cần:

1. **Authentication**: JWT tokens
2. **Database**: PostgreSQL/MySQL thay vì SQLite
3. **Face Storage**: Encrypted storage
4. **HTTPS**: SSL/TLS encryption
5. **Rate Limiting**: Prevent abuse
6. **Input Validation**: Sanitize inputs

## 🐛 Troubleshooting

### Backend Issues
1. **Port already in use**: Thay đổi port trong `run_server.py`
2. **Face recognition not working**: Kiểm tra `face-recognition` library
3. **Database errors**: Xóa file `smart_locker.db` để reset

### Flutter Issues
1. **Camera permission**: Kiểm tra quyền camera trong Settings
2. **Network error**: Kiểm tra backend URL và kết nối mạng
3. **Build errors**: Chạy `flutter clean && flutter pub get`

## 📝 Ghi chú

- Hệ thống sử dụng `face-recognition` library dựa trên dlib
- Khuôn mặt được encode thành 128-dimensional vectors
- Tolerance mặc định: 0.6 (có thể điều chỉnh)
- Demo sử dụng in-memory storage cho đơn giản

## 🤝 Đóng góp

1. Fork repository
2. Tạo feature branch
3. Commit changes
4. Push to branch
5. Tạo Pull Request

## 📄 License

MIT License - xem file LICENSE để biết thêm chi tiết.
=======
# lock-id
>>>>>>> 7a6c8379004526dd8fb0af2df0d3fabc3e9c0310
