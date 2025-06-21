<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Chạy Windows trên Xiaomi Pad 5

## Cập nhật drivers

### Chuẩn bị
- [`ADB & Fastboot`](https://developer.android.com/studio/releases/platform-tools)

- [`Modified recovery image`](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [```DriveLetterAssigner Tool```](https://github.com/Misha803/My-Scripts/releases/tag/DriveLetterAssigner)

- [`UEFI image`](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/UEFI)

- [`Drivers`](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/Drivers)

### Khởi động vào chế độ recovery đã chỉnh sửa
> Thay thế `path\to\recovery.img` bằng đường dẫn thực tế của recovery
```cmd
fastboot boot path\to\recovery.img
```

#### Thực thi script msc
> Nếu nó yêu cầu bạn chạy lại, hãy làm như vậy
```cmd
adb shell msc
```

### Gán ký tự cho WINNABU
> [!NOTE]
> Bạn có thể bỏ qua bước này nếu WINNABU đã có ký tự ổ đĩa được gán

> Chạy **DriveLetterAssigner** và nhấp vào **`Assign Drive Letter X to Windows Volume Only`** để tự động gán ký tự **X** cho **WINNABU**

### Cài đặt drivers
> [!Note]
> Quá trình này sẽ mất từ 3 đến 6 giờ. Đừng lo lắng, điều này là bình thường.

- Giải nén tệp driver, sau đó mở tệp `OfflineUpdater.cmd` (nếu xuất hiện lỗi, hãy chạy `OfflineUpdaterFix.cmd` thay thế)

> Nếu nó yêu cầu bạn nhập một ký tự, hãy nhập ký tự ổ đĩa của **WINNABU** (nên là **X**), sau đó nhấn enter

#### Khởi động lại thiết bị của bạn
> [!Warning]
> Hãy chắc chắn cũng thay đổi UEFI trong Android, nếu không bạn có thể gặp phải "màn hình xanh chết chóc" (BSoD) khi khởi động Windows sau này.
```cmd
adb reboot
```

## Hoàn tất!