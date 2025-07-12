<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Chạy Windows trên Xiaomi Pad 5

## Fix GPT để xài Windows 24H2 an toàn

### Chuẩn bị:
- [```Đã cài Windows```](selection-vi.md)

- [```Recovery image```](https://github.com/ArKT-7/twrp_device_xiaomi_nabu/releases/tag/mod-win)

- [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools)

> [!Important]
> Nếu bạn muốn sử dụng Windows 24H2 một cách an toàn, các bước này là cần thiết để tránh các vấn đề EDL.

> [!NOTE]
> Làm theo cái này sẽ không ảnh hưởng đến Android hoặc Windows của bạn.

### Khởi động vào fastboot mode
- Khởi động NABU của bạn vào **fastboot mode** bằng cách giữ nút **`giảm âm lượng`** trong khi cáp USB được kết nối
- Hoặc, nếu bạn đã bật USB debugging, hãy chạy lệnh bên dưới trong khi khởi động vào Android.
```cmd
adb reboot bootloader
```

### Khởi đôngj vào modified recovery
> Thay `path\to\recovery.img` bằng đường dẫn thực tế của **recovery.img** đã tải xuống
```cmd
fastboot boot path\to\recovery.img
```

### Fixing the GPT
> Làm một lần khi boot vào recovery đã chỉnh sửa
>
> Nếu nó yêu cầu bạn chạy lại, chạy lại đi, bạn sợ à
```cmd
adb shell fixgpt
```

### Khởi động lại thiết bị của bạn
```cmd
adb reboot
```

## ✅ Xong rồi nha! Windows 24H2 sẽ hoạt động an toàn.