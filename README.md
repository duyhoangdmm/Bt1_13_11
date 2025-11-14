# 🚀 Dự án Giao diện (UI) - Màn hình Đăng nhập & Đăng ký (Android)

Đây là dự án tập trung vào việc xây dựng giao diện (UI/Frontend) cho các màn hình cơ bản của một ứng dụng, bao gồm Đăng nhập và Đăng ký, sử dụng Android (Kotlin/Java) và Material Design.

## 📝 Phạm vi dự án (Project Scope)

Dự án này **chỉ tập trung vào phần Giao diện (UI)**. Các tính năng về logic, xác thực (authentication), hay gọi API **chưa** được cài đặt.

Mục tiêu là dựng lại (replicate) một bản thiết kế (mockup) cho trước một cách chính xác nhất.

## 📸 Hình ảnh Demo

| Màn hình Đăng nhập (Login) | Màn hình Đăng ký (Register) |
| :---: | :---: |
| <img src="https://github.com/user-attachments/assets/8c410afe-459f-437e-b8b1-92f2fdcb48fb" width="350"> | <img src="https://github.com/user-attachments/assets/97208c83-41d8-452d-92c6-9733b7189eb5" width="350"> |

## ✨ Tính năng Giao diện (UI Features) đã hoàn thành

* **Màn hình Đăng nhập:**
    * Bố cục `ConstraintLayout` phức tạp với background sóng (`ImageView`).
    * `EditText` tùy chỉnh cho Email và Password (có icon `drawableStart`).
    * Nút đăng nhập chính bằng `ImageButton`.
    * Nhóm 2 nút Social Login (Facebook, Google) với style `OutlinedButton`.
* **Điều hướng (Giả lập):**
    * Có `TextView` ("Are you new user? Register") để người dùng biết chỗ chuyển sang màn hình Đăng ký nhưng chưa code back_end nên chưa nhảy qua được
    
---

## 📈 Đánh giá & Bài học (Self-Evaluation)

Đây là phần đánh giá cá nhân về quá trình hoàn thành phần giao diện.

### 1. Khó khăn lớn nhất gặp phải
Khó khăn chính là tùy chỉnh `Button` (Nút) để giống hệt ảnh thiết kế, đặc biệt là khi làm việc với theme Material Design:

* **Vấn đề:** Dùng `android:background` với file XML `<shape>` không thể đè lên được style mặc định của `MaterialButton`.
* **Thử sai:** Chuyển sang `android:backgroundTint` nhưng nó chỉ *tô màu* (tint) lên nền, chứ không *thay thế* nền, dẫn đến kết quả sai.
* **Giải pháp:** Đã học được cách sử dụng **style chuẩn của Material Design**. Bằng cách áp dụng `style="@style/Widget.MaterialComponents.Button.OutlinedButton"` và dùng các thuộc tính `app:` (như `app:strokeColor`, `app:backgroundTint`, `app:cornerRadius`), ta có thể tùy chỉnh nút một cách chính xác mà vẫn giữ được hiệu ứng (ripple) của Material.

### 2. Bài học rút ra
* Hiểu rõ sự khác biệt giữa `android:background` (cũ) và `app:backgroundTint`, `app:strokeColor` (mới) của Material Components là rất quan trọng.
* Luôn ưu tiên tùy chỉnh bằng `style` và `theme` của Material trước khi cố gắng "đè" bằng drawable tùy chỉnh.
* Cần chú ý đến cảnh báo hỗ trợ tiếp cận (accessibility) và thêm `android:contentDescription` cho `ImageButton` để hỗ trợ trình đọc màn hình.
