<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Chạy Windows trên Xiaomi Pad 5

## Hướng dẫn gỡ cài đặt

### Tại sao cần gỡ cài đặt?
> Nếu bạn muốn khóa lại bootloader của mình, bạn sẽ cần bảng phân vùng của mình trở về trạng thái ban đầu.

> [!Warning]
> **Tất cả dữ liệu của bạn sẽ bị xóa! Hãy sao lưu ngay nếu cần.**

### Chuyển sang Android
> Nếu lần khởi động cuối cùng của bạn là Windows, hãy chuyển sang Android trước khi bắt đầu quá trình gỡ cài đặt

#### Khởi động vào chế độ fastboot
- Khởi động NABU của bạn vào **fastboot mode** bằng cách giữ nút **`giảm âm lượng`** trong khi khởi động lại với cáp USB
- Hoặc, nếu bạn đã bật USB debugging, hãy chạy lệnh bên dưới trong khi khởi động vào Android.
```cmd
adb reboot bootloader
```cmd
adb reboot bootloader
```

> [!NOTE]
>
> ▶️ Nhấn vào đây để mở rộng menu.

<details>
  <summary><strong>Phương pháp 1 - Gỡ cài đặt bằng adb shell restore</strong></summary>

### Chuẩn bị
- [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools)

- [```Modified Recovery Image```](https://github.com/ArKT-7/twrp_device_xiaomi_nabu/releases/tag/mod-win)

#### Khởi động recovery đã chỉnh sửa
> Mở một cửa sổ CMD bên trong thư mục platform-tools, sau đó (trong khi máy tính bảng của bạn đang ở chế độ fastboot) chạy:
```cmd
fastboot boot path\to\recovery.img
```

### Khôi phục bố cục phân vùng
> [!Warning]
> Cái này sẽ xóa tất cả dữ liệu Android của bạn. Hãy sao lưu trước nếu cần.

```cmd
adb shell restore
```

#### Khởi động vào Android
```cmd
adb reboot 
```

## Done!

</details>

<details>
  <summary><strong>Phương pháp 2 - Gỡ cài đặt trong fastboot</strong></summary>

### Chuẩn bị
- [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools)

- [```gpt_both0.bin```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/gpt_both0.bin)

### Khôi phục bảng phân vùng
> Thay thế ```path\to\gpt_both0.bin``` bằng đường dẫn đến tệp gpt_both0.bin.
```cmd
fastboot flash partition:0 path\to\gpt_both0.bin
```

#### Xóa userdata
> Để tránh bootloop và khôi phục kích thước FS
```cmd
fastboot -w
```

#### Khởi động vào Android
```cmd
fastboot reboot
```

## Hoàn tất!

</details>

<details>
  <summary><strong>Phương pháp 3 - Gỡ cài đặt bằng "Nabu Fastboot Tool"</strong></summary>

### Chuẩn bị
 `Một `**`cáp`**` để kết nối `**`Xiaomi Pad 5`**` của bạn với `**`thiết bị khác`**

 **`Bất kỳ thiết bị nào khác (Android, Windows, Mac hoặc Linux)`**

### Kết nối với Fastboot Tool trên trang web
- Mở **[Nabu Fastboot Tool](https://arkt-7.github.io/nabu/)** trong trình duyệt của bất kỳ thiết bị nào.
- Nhấp vào nút **`Connect Device Fastboot`**.
- Chọn **`Android`** từ danh sách xuất hiện và **`cho phép`** quyền truy cập.

### Định dạng và Khôi phục phân vùng
- Cuộn xuống phần **`Format/wipe make Partition Stock`**.
- Trong hộp nhập, gõ **`format`**.
- Cuối cùng, nhấp vào nút **`Format/Wipe`** và nhấn **`OK`** khi một thông báo cảnh báo xuất hiện.
- Khi quá trình định dạng hoàn tất, một thông báo thành công sẽ xuất hiện. Nhấp **`OK`** để đóng thông báo.
- Cuộn lên và nhấp vào nút **`Reboot Device`** để khởi động lại thiết bị của bạn.

## Hoàn tất!

</details>

> [!NOTE]
> Nếu thiết bị của bạn **khởi động lại vào recovery** sau khi gỡ cài đặt Windows, hãy thực hiện các hành động sau:
> 1. Chọn **Wipe Data/Factory reset**
> 2. **Wipe All Data**
> 3. Sau khi dữ liệu đã được xóa thành công, nhấp vào Back
> 4. Nhấp vào **Reboot**
> 5. Khởi động lại vào System