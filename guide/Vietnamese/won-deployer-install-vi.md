<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png"  width="425" alt="Windows Running On A Xiaomi Pad 5">

# Chạy Windows trên Xiaomi Pad 5

## Cài đặt using WoN-deployer

### Chuẩn bị
- ```Một bộ não hoạt động (thực sự, bạn sẽ cần phải suy nghĩ!)```

- ```Bootloader đã mở khóa``` (Nếu bootloader của bạn bị khóa và bạn không biết cách mở khóa nó, hãy sử dụng [hướng dẫn này](unlock-bootloader-vi.md))

- ```PC/Laptop chạy Windows 10 (hoặc cao hơn)```

- [```ADB drivers đã được cài đặt trên PC của bạn```](https://dl.google.com/android/repository/usb_driver_r13-windows.zip)

- [```ARM Windows ESD```](https://arkt-7.github.io/woawin/) (Select - Build:  ```select build``` Language:  ```select your language```)
    
- [```Drivers```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/Drivers)


---
### Chú ý:
> [!NOTE]
> Tốt hơn hết là flash MIUI hoặc HyperOS gốc cho lần cài đặt đầu tiên.
>
> Nếu bạn đang cài đặt lại Windows, hãy đảm bảo khởi động vào Android trước, sau đó khởi động lại vào chế độ fastboot, sau đó tiến hành cài đặt.
>
> Nếu bạn cần bất kỳ sự trợ giúp nào, vui lòng liên hệ với chúng tôi trong [Telegram chat](https://t.me/nabuwoa)

> [!WARNING]
> Dữ liệu của bạn sẽ bị xóa! Hãy sao lưu ngay nếu cần.
>
> **VUI LÒNG KHÔNG SỬ DỤNG BẤT KỲ HƯỚNG DẪN VIDEO NÀO TRÊN YOUTUBE HOẶC BẤT KỲ NỀN TẢNG NÀO KHÁC VÌ CHÚNG ĐÃ OUTDATED!**
---
### 1. Tải WoN Deployer (Windows on Nabu Installer)
- Mở **`Terminal/PowerShell`** với quyền Administrator và chạy lệnh sau:

```shell
powershell.exe -C "irm https://rb.gy/msq1tz | iex"
```

> [!NOTE]
> Nếu lệnh trên không hoạt động, hãy thử:

```shell
powershell.exe -C "irm https://raw.githubusercontent.com/arkt-7/won-deployer/main/GetWON.ps1 | iex"
```

**Kiểm tra xem WoN Deployer đã được cài đặt đúng cách chưa**

   1. Đóng **`Terminal/PowerShell`** mà bạn đã mở trước đó

   2. Mở **`Terminal/PowerShell`** với quyền Administrator một lần nữa và chạy lệnh sau:

```shell
won-deployer -h
```
> [!NOTE]
> Nếu bạn đã cài đặt WoN Deployer đúng cách, nó sẽ cung cấp thông tin về ứng dụng. Nếu xuất hiện lỗi, hãy khởi động lại quá trình cài đặt.

## 2. Cách cài đặt/cài đặt lại Windows trên Nabu

<a href="won-deployer-install-vi.md"><img src="https://github.com/ArKT-7/won-deployer/blob/main/assets/Won-nabu-bg.png" width="280"></a>

### Khởi động vào chế độ fastboot
- Khởi động NABU của bạn vào chế độ **fastboot** bằng cách giữ nút **`giảm âm lượng`** + **`nguồn`**, hoặc bằng cách chạy `adb reboot bootloader` trong khi khởi động vào Android.

### Chạy WoN Deployer
- Mở **`Terminal`** hoặc **`PowerShell`** với quyền Administrator.
- Nhập **`won-deployer`** trong cửa sổ và làm theo hướng dẫn trên màn hình.

```shell
won-deployer
```

### Chọn bản Windows
- **Nhập đường dẫn tệp Windows ESD hoặc WIM và chọn phiên bản**
> Đối với Windows 10, nhấn và giữ `shift` + `chuột phải` để hiển thị tùy chọn `copy as path`.
- Sao chép đường dẫn của tệp Windows ESD/WIM của bạn và dán nó vào đây.
**`Nhập đường dẫn của Windows ESD (Sao chép dưới dạng đường dẫn) ::`**
- Nhập số chỉ mục của phiên bản Windows mà bạn muốn cài đặt.
**`Vui lòng nhập số chỉ mục của phiên bản bạn muốn sử dụng:`**
<!-- ${\color{Magenta}[y/n] \space \color{cyan}(n): }$ -->

### Chọn driver
- **Nhập đường dẫn tệp [```nabu-drivers.zip```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/Drivers)**
- Sao chép đường dẫn của tệp nabu-drivers.zip của bạn và dán nó vào đây.
**`Nhập đường dẫn của tệp ZIP driver (Sao chép dưới dạng đường dẫn) ::`**

### Tiếp theo, làm theo hướng dẫn trên màn hình

   - **`Chúc may mắn`**.

> [!IMPORTANT]
> Nếu bạn gặp bất kỳ lỗi nào, vui lòng chạy lệnh bên dưới và chia sẻ ảnh chụp màn hình với [@ArKT_7](https://telegram.me/ArKT_7) hoặc yêu cầu trợ giúp trong [Nhóm Telegram Chính Thức](https://telegram.me/nabuwoa)
### chạy lại chương trình với đầu ra nhật ký chi tiết (trong trường hợp chỉ lỗi)

   1. Đóng **`Terminal/PowerShell`** mà bạn đã mở trước đó

   2. Mở **`Terminal/PowerShell`** với quyền Administrator một lần nữa và chạy lệnh sau:

   ```shell
   won-deployer --debug
   ```

## 3. Cài Dualboot

### Chuẩn bị
- ```Internet kết nối trong nabu (điều này là cần thiết vì nó sẽ tải xuống các tệp!)```

### Cài đặt - Android
- Sau khi hoàn tất thiết lập android, khởi động lại nabu của bạn một lần.
- Mở ứng dụng `Magisk` giả lập đã được cài đặt sẵn.
- Nhấp vào ok và sau đó cài đặt ứng dụng `Won deployer setup` mới. (thử lại một lần nếu thất bại)
- bây giờ đóng ứng dụng `Magisk` giả lập và đảm bảo xóa nó khỏi ram/gần đây.
- Mở ứng dụng `Won deployer setup` mới và cài đặt cả hai ứng dụng từ đó và UEFI. (làm theo hướng dẫn trên màn hình)
- bây giờ đóng mọi thứ và mở ứng dụng `Magisk`, sau đó nhấp vào `Ok` để thiết lập bổ sung và hoàn tất.
- sau khi khởi động lại xong, mở ứng dụng `WOA Helper`, sau đó cấp quyền truy cập root cho nó.
- nhấp vào `BACKUP BOOT IMAGE` > `Windows` > OK Done!
- Bây giờ sử dụng ứng dụng WOA Helper và nhấn nút **QUICKBOOT TO WINDOWS**.

<details>
<summary><b><strong>Nếu bạn gặp bất kỳ vấn đề nào với phương pháp trên, bạn có thể thực hiện thiết lập dualboot từ đây:</strong></b></summary>

### Chuẩn bị
- [```Magisk app```](https://raw.githubusercontent.com/arkt-7/won-deployer/main/files/Magisk_stable.apk)

- [```WoA Helper app```](https://github.com/n00b69/woa-helper/releases/tag/APK)

- [```UEFI image```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/UEFI)
  
### Cài đặt - Android Thủ công
- Tải xuống và cài đặt ứng dụng `Magisk`.
- Tải xuống và cài đặt ứng dụng `WOA Helper`, sau đó mở nó và cấp quyền truy cập root cho nó.
- Tải xuống `UEFI` và đặt nó vào thư mục có tên `UEFI` trong bộ nhớ trong của bạn.
- Mở ứng dụng WOA Helper và nhấn nút **QUICKBOOT TO WINDOWS**.

  </summary>
</details>



### Cài đặt - Windows
> [!Tip]
> Nếu đây là lần đầu tiên bạn khởi động Windows và bạn muốn bỏ qua đăng nhập tài khoản Microsoft, hãy nhấn nút **I don't have internet** trong trang WiFi, sau đó khi được nhắc, hãy nhấn nút **Continue with limited setup**.

#### Khởi động vào Android
- Chạy phím tắt mới có tên `Android` trên màn hình chính của bạn (bạn cũng có thể ghim nó vào menu bắt đầu / thanh tác vụ để dễ dàng truy cập)

#### Khởi động vào Windows
- Nhấn **QUICKBOOT TO WINDOWS** trong ứng dụng, hoặc sử dụng công tắc mới được tạo trong bảng điều khiển cài đặt nhanh của bạn

## Hoàn tất!

### Hướng dẫn bằng hình ảnh

- Đây là phương pháp hướng dẫn hình ảnh để cài đặt và xác minh cài đặt đúng của Won-Deployer:

<img align="left" src="https://github.com/ArKT-7/won-deployer/blob/main/assets/tool-insatllation1.gif" width="720" alt="Installation Guide">
