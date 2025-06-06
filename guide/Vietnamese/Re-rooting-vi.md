<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Chạy Windows trên Xiaomi Pad 5

## Re-rooting Android
Phần này sẽ hướng dẫn bạn quy trình khôi phục quyền root khi MIUI/Hyper OS cập nhật và bị mất root.

### Chuẩn bị
- [```Recovery Image```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)
  
- [```Android Platform Tools```](https://developer.android.com/studio/releases/platform-tools)

- [```Magisk.apk```](https://github.com/topjohnwu/Magisk/releases/latest)

### Khởi động vào **fastboot**
- Khởi động NABU của bạn vào **fastboot** bằng cách giữ nút **`giảm âm lượng`** trong khi khởi động lại

- Kết nối máy với PC/Laptop của bạn bằng cáp

### Khởi động vào recovery đã chỉnh sửa
> Trong chế độ fastboot, thay thế `path\to\recovery.img` bằng đường dẫn thực tế của hình ảnh recovery
```cmd
fastboot boot path\to\recovery.img
```

### Flash magisk
- Tải xuống [`magisk.apk`](https://github.com/topjohnwu/Magisk/releases/latest) vào PC/Laptop của bạn
> Thay thế `path\to\magisk.apk` bằng đường dẫn thực tế của magisk.apk
```cmd
adb push path\to\magisk.apk /tmp/magisk.zip && adb shell twrp install /tmp/magisk.zip
```

#### Khởi động lại vào Android
> Nếu nó không khởi động, hãy khởi động lại bằng cách nhấn và giữ nút nguồn
```cmd
adb reboot
```

### Hoàn tất thiết lập
- Thiết lập thiết bị của bạn, sau đó tải xuống và cài đặt [Magisk](https://github.com/topjohnwu/Magisk/releases/latest), nếu nó chưa được cài đặt.
- Mở ứng dụng **Magisk** và làm theo hướng dẫn trên màn hình, và thiết bị của bạn sẽ khởi động lại sau vài giây.


### Cập nhật boot.img trong C:\
- Khởi động lại vào Android
- Mở ```WOA Helper```
- Nhấn ```BACKUP BOOT IMAGE``` > ```Windows```
- Xong

## Hoàn tất!