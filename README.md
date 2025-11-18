# 👟 Sneakery Store - Website Bán Giày Online

## 🚀 Hướng dẫn cài đặt (5 bước)

### 📥 **Bước 1: Tải code về máy và Chuyển sang nhánh hiện tại update/dev-pos**

```bash
git clone https://github.com/p1mp1m/sneakery-store
cd sneakery-store
git checkout update/dev-pos
```

### 🗄️ **Bước 2: Tạo Database**
*Chú ý: Nếu đang dùng db của Dev mới nhất sneakery-db thì không cần phải chạy bước này*

1. Mở **SQL Server Management Studio (SSMS)**
2. Kết nối với server: `localhost` (Authentication: Windows Authentication)
3. Mở và chạy file: `sneakery-database\1_CREATE_SCHEMA.sql` (nhấn F5)
4. Mở và chạy file: `sneakery-database\2_ADD_INDEXES.sql` (nhấn F5)
5. Mở và chạy file: `sneakery-database\3_ADD_CONSTRAINTS.sql` (nhấn F5)
6. Mở và chạy file: `sneakery-database\4_INSERT_DATA_PART1.sql` (nhấn F5)
7. Mở và chạy file: `sneakery-database\5_INSERT_DATA_PART2.sql` (nhấn F5)

✅ **Hoàn thành:** Database `sneakery_db` đã được tạo!
*Chú ý: Trong trường hợp DB của bạn đã tồn tại nó sẽ được tạo mới và cập nhật dữ liệu mới nhất*
---

### ⚙️ **Bước 3: Cấu hình Backend**

1. **Copy file cấu hình:**
Thêm sneakery-backend\src\main\resources\application.properties
*Đã có trong file zip chỉnh sửa theo cá nhân*

2. **Mở file:** `sneakery-backend/src/main/resources/application.properties`

3. **Sửa các biến môi trường:**
```properties
spring.datasource.username=${DB_USERNAME:YOUR_PASSWORD_HERE}
spring.datasource.password=${DB_PASSWORD:YOUR_JWT_SECRET_KEY_HERE}
```
*Ví dụ:*
```properties
spring.datasource.username=${DB_USERNAME:sa}
spring.datasource.password=${DB_PASSWORD:123456}
```
- Thay `YOUR_PASSWORD_HERE` bằng mật khẩu SQL Server của bạn
- Tạo JWT secret mới (dùng UUID generator online)
- Thay `YOUR_JWT_SECRET_KEY_HERE` bằng JWT secret mới tạo

```properties
app.jwt.secret=${JWT_SECRET:pr4A69n8RRGkZvDq56wfpxvjTE0cNF2SnmxgngH9nrQ=}
app.jwt.expiration-ms=${JWT_EXPIRATION_MS:86400000}

cloudinary.cloud-name=${CLOUDINARY_CLOUD_NAME:dpwvthh5z}
cloudinary.api-key=${CLOUDINARY_API_KEY:177993931929792}
cloudinary.api-secret=${CLOUDINARY_API_SECRET:tg22Fe3hUkyzB2Ivmfk3gbJjHsc}

spring.mail.username=${MAIL_USERNAME:aaa@gmail.com}
spring.mail.password=${MAIL_PASSWORD:aaa}
```
*Chú ý: Có thể dùng luôn tài khoản ví dụ trên*

4. **Cài đặt dependencies:**
*Cách 1: Dùng CMD*
```bash
cd sneakery-backend
mvn clean install
```
*Cách 2: Dùng IDE (IntelliJ/Eclipse)*
- Mở project `sneakery-backend` trong IDE
- Ấn nút *Run and Build* Maven Project

⏳ Chờ 2-5 phút để tải các thư viện...

---

### 🎨 **Bước 4: Cài đặt Frontend**

**Cài đặt dependencies:**
Trong CMD hoặc Terminal:
*Mở đường dẫn đến thư mục project*
*Ví dụ: cd C:User/LTT/Desktop/New/sneakery-store*
*Sau đó chạy lệnh*
```bash
cd sneakery-frontend
npm install
```

⏳ Chờ 2-5 phút để tải các thư viện...

---

### 🎮 **Bước 5: Chạy ứng dụng**

#### Chạy Backend:
Cách 1: Dùng IDE (IntelliJ/Eclipse)
- Mở project `sneakery-backend` trong IDE
- Ấn chạy class `SneakeryApplication.java` phía trên cùng

Cách 2: Dùng CMD
*Khuyên dùng cmd hoặc Terminal*
*Chuyển đến thư mục backend và chạy lệnh*
```bash
cd sneakery-backend
mvn spring-boot:run
```

✅ Khi thấy: `🚀 Sneakery Backend is running!`
              `📚 API Documentation: http://localhost:8080/swagger-ui.html` → Backend đã sẵn sàng!

#### Terminal 2 - Chạy Frontend:
*Khuyên dùng cmd hoặc Terminal*
*Khi đang trong cmd chạy lệnh npm install tiếp tục chạy*
```bash
cd sneakery-frontend
npm run dev
```

✅ Khi thấy: `Local: http://localhost:5173/` → Mở trình duyệt và truy cập!

---

## 🔑 Đăng nhập

Mở trình duyệt và vào: **http://localhost:5173**

### 👨‍💼 Tài khoản Admin:
```
Email:    admin@sneakery.com
Mật khẩu: password
```

### 👤 Tài khoản Khách hàng:
```
Email:    user1@example.com
Mật khẩu: password
```

---

<div align="center">

**✨ Chúc bạn setup thành công! ✨**

Made with ❤️ by Sneakery Team

![GitHub stars](https://img.shields.io/github/stars/p1mp1m/sneakery-store?style=social)
![GitHub forks](https://img.shields.io/github/forks/p1mp1m/sneakery-store?style=social)

</div>
