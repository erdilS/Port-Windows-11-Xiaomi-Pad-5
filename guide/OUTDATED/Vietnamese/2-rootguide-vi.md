<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Chạy Windows trên Xiaomi Pad 5

## Root máy tính bảng
> [!NOTE]
> **Nếu bạn đã root, hãy bỏ qua bước này và chuyển sang trang tiếp theo**

### Chuẩn bị
- ```🧠 Một cái đầu lạnh trước sóng gió của cuộc đời```

- [```Magisk.apk```](https://github.com/topjohnwu/Magisk/releases/latest)

### Flash magisk 
- Tải [`magisk.apk`](https://github.com/topjohnwu/Magisk/releases/latest) xuống PC/Laptop của bạn
> Thay `path\to\magisk.apk` bằng đường dẫn thực của file magisk.apk
```cmd
adb push path\to\magisk.apk /tmp/magisk.zip
adb shell twrp install /tmp/magisk.zip
```

#### Khởi động vào Android
> Nếu nó không khởi động, hãy khởi động vào stock recovery và thực hiện **factory reset** ở đó
```cmd
adb reboot
```

### Hoàn tất thiết lập
- Setup máy ngon lành đi, sau đó tải xuống và cài đặt [Magisk](https://github.com/topjohnwu/Magisk/releases/latest), nếu nó chưa được cài đặt.
- Mở ứng dụng **Magisk** và làm theo hướng dẫn trên màn hình, thiết bị của bạn sẽ khởi động lại sau vài giây.

### Sao lưu boot.img đã root
> Khởi động vào recovery đã chỉnh sửa, sau đó chạy lệnh bên dưới

> [!NOTE]
> Chạy lệnh này trong **Command Prompt (CMD)**. Lệnh không hoạt động trong PowerShell.
```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/rooted_boot.img" && adb pull /tmp/rooted_boot.img
```

### [Bước kế tiếp: Cài đặt Windows](/guide/Vietnamese/3-install-vi.md)