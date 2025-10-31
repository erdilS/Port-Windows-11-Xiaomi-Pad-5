<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Chạy Windows trên Xiaomi Pad 5

## Mở Bootloader: Hướng dẫn từng bước cho HyperOS/MIUI

### Chuẩn bị
- [`📲 Mi Community App(only for HyperOS/MIUI 14)`](https://apkpure.net/xiaomi-community/com.mi.global.bbs/download).

- [`🔧 Mi Unlock Tool`](https://miuirom.xiaomi.com/rom/u1106245679/6.5.224.28/miflash_unlock-en-6.5.224.28.zip).

- [`🛠️ HyperSploit (bypass method)`](https://github.com/TheAirBlow/HyperSploit/releases/latest/download/HyperSploit-Windows.exe).

> [!WARNING]
>
> Sao lưu Data: Mở khoá bootloader sẽ xóa tất cả dữ liệu trên thiết bị của bạn. Hãy chắc chắn sao lưu dữ liệu quan trọng trước khi tiếp tục.

### Bật chế độ Nhà phát triển
- **Cho HyperOS:**
  - Vào **Settings → My device → Detailed info and specs → OS version**.
  - Nhấn nhiều lần vào phiên bản OS cho đến khi các tùy chọn nhà phát triển được kích hoạt (bạn sẽ thấy một thông báo bật lên).

- **Cho MIUI:**
  - Vào **Settings → About phone → MIUI version**.
  - Nhấn nhiều lần vào phiên bản MIUI cho đến khi các tùy chọn nhà phát triển được kích hoạt (bạn sẽ thấy một thông báo bật lên).

### Bật OEM Unlocking và USB Debugging
- Vào **Settings → Additional settings → Developer options**.
- Bật **OEM unlocking** và **USB debugging**.

### Phương pháp mới (Cho HyperOS/MIUI 14)
<details>
  <summary><strong>Nhấn để mở</strong></summary>

  <details>
   <summary><strong>Phương pháp 1: Dùng HyperSploit Bypass (Khuyến nghị) </strong></summary>

**Cách này sẽ Bypass daily quota limit trong khi áp dụng trong ứng dụng Mi Community.**

### Áp dụng để mở khóa (HyperSploit)
- Chạy **HyperSploit-Windows.exe** với quyền Administrator.
- Khi được nhắc trên thiết bị của bạn, hãy nhấn **OK** để cho phép USB debugging.
- Làm theo hướng dẫn trên màn hình trong cửa sổ **HyperSploit**. Khi được yêu cầu **cố gắng liên kết tài khoản**:
- Vào **Settings → Additional settings → Developer options → Mi Unlock status**.
- Nhấp vào **Add account and device**, sau khi thêm thành công, HyperSploit sẽ xác nhận với **Successfully binded**

  </details>
  
  <details>
    <summary><strong>Phương pháp 2: Sử dụng Mẹo Thời Gian </strong></summary>

**Nếu thiết bị của bạn là phiên bản toàn cầu, bạn có thể đăng ký mở khóa bootloader vào một thời điểm cụ thể.**
- Xiaomi cho phép **2.000 thiết bị mở khóa hàng ngày**.
- Thời gian đặt lại cho giới hạn hàng ngày này là **7 PM theo giờ Moscow**.

### Áp dụng để mở khóa
- Đồng bộ hóa thời gian địa phương của bạn với **7 PM theo giờ Moscow** và sẵn sàng vào thời điểm này - thời gian là rất quan trọng.
- Mở ứng dụng **Xiaomi Community**, đặt nó thành Global và đăng nhập bằng cùng một tài khoản như trên thiết bị của bạn.
- Đi tới tab **"Me"**, nhấp vào **"Unlock bootloader,"** sau đó nhấp vào **"Apply"**.
- Khi được cấp quyền truy cập, hãy đi tới **Settings → Additional settings → Developer options → Mi Unlock status**.
- Nhấp vào **Add account and device**, sau khi thêm thành công, bạn sẽ thấy **Added Successfully**.

  </details>
  
</details>

### Phương pháp thông thường (cho MIUI 13 và trước đó)
<details>
  <summary><strong>Nhấn để mở</strong></summary>

### Liên kết tài khoản Mi
- Vào **Settings** > **Additional settings** > **Developer options** > **Mi Unlock status**.
- Nhấp vào **Add your Mi Account**. Sau khi thêm thành công, bạn sẽ thấy **Added Successfully**.

</details>

### Mở khóa Bootloader
- Mở **Mi Flash Unlock Tool** và đăng nhập bằng cùng một tài khoản Mi.
- Khởi động thiết bị của bạn vào **fastboot mode** và kết nối với PC.
- Sử dụng Mi Unlock Tool trên PC để mở khóa bootloader.
- Nếu xuất hiện lỗi thời gian chờ `có thể là 168 giờ/7 ngày`, hãy đóng mọi thứ, đợi cho đến khi thời gian kết thúc, sau đó lặp lại bước này.

> [!NOTE]
> Thời gian chờ trong Mi Unlock Tool có thể khác với những gì được mô tả trong hướng dẫn này.
>
> Trong thời gian chờ, không được đặt lại thiết bị của bạn hoặc đăng xuất khỏi tài khoản Xiaomi của bạn.


### Credits & Acknowledgements
- **Hướng dẫn này đã được kiểm tra và xác nhận bởi** [@ArKT_7](https://t.me/ArKT_7)  **GitHub:** [@ArKT-7](https://github.com/ArKT-7)