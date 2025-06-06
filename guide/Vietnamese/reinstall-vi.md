<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Chạy Windows trên Xiaomi Pad 5

## Hướng dẫn cài đặt lại
Nếu bạn không thích phiên bản Windows của mình hoặc bạn đã làm hỏng cài đặt Windows của mình, hoặc bất kỳ điều gì khác, bạn có thể chỉ cần cài đặt lại Windows. May mắn thay, quy trình này rất dễ dàng.

> [!IMPORTANT]
> Cân nhắc, điều này sẽ xóa tất cả các tệp Windows của bạn. Nếu bạn muốn sao lưu bất kỳ tệp nào trong số đó, bạn có thể gắn (mount) Windows bằng ứng dụng [WOA Helper](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/woahelper.apk) và sao chép thủ công bất kỳ tệp nào bạn muốn giữ lại

### Chuẩn bị
- ```Đã có Windows và phân vùng boot``` (*Chưa có hả bà thơ? [Quuay lại và giả vờ chưa thấy gì hết nghee](/guide/Vietnamese/1-partition-vi.md)*)

- [```Recovery Image```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools)

#### Khởi động vào fastboot mode
- Khởi động NABU của bạn vào **fastboot mode** bằng cách giữ nút **`giảm âm lượng`** trong khi khởi động lại với cáp USB
- Hoặc, nếu bạn đã bật USB debugging, hãy chạy lệnh bên dưới trong khi khởi động vào Android.
```cmd
adb reboot bootloader
```

### Khởi động modified recovery
> Thay thế `path\to\recovery.img` bằng đường dẫn thực tế của recovery đã chỉnh sửa
```cmd
fastboot boot path\to\recovery.img
```

### Định dạng lại phân vùng
> Nếu nó yêu cầu bạn chạy lại, hãy chạy lại đi, bạn sợ à
```cmd
adb shell format
```

## [Tiếp thôi: Cài lại Windows](/guide/Vietnamese/3-install-vi.md)
