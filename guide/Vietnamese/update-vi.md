<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Chạy Windows trên Xiaomi Pad 5

> [!CAUTION]
> Hướng dẫn này **không предназначен để cập nhật driver lên phiên bản 2601.19**.  
> Việc sử dụng cho phiên bản này có thể gây lỗi hoặc làm hệ thống không ổn định.

## Cập nhật drivers

### Chuẩn bị
- [`ADB & Fastboot`](https://developer.android.com/studio/releases/platform-tools)

- [`Modified recovery image`](https://github.com/ArKT-7/twrp_device_xiaomi_nabu/releases/tag/mod-win)

- [```DriveLetterAssigner Tool```](https://github.com/Misha803/My-Scripts/releases/tag/DriveLetterAssigner)

- [`UEFI image & Drivers`](https://github.com/remtrik-stuff/MiPad5-Windows-Releases/releases)
> Để tải xuống, hãy cuộn xuống cuối trang, tìm tệp cần thiết và nhấp vào tệp đó để bắt đầu tải xuống.


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

### Khởi động vào fastboot
```cmd
adb reboot bootloader
```

#### Khởi động vào UEFI
> Thay `path\to\nabu-uefi.img` bằng đường dẫn thực của file UEFI
```cmd
fastboot boot path\to\nabu-uefi.img
```

### Khởi động vào Android
> Thiết bị của bạn sẽ tự động khởi động lại sau khoảng 10 phút chờ đợi, sau đó bạn sẽ được khởi động vào Android, và chúng ta đến bước cuối cùng.

## [Thiết lập dualboot](/guide/Vietnamese/dualboot-selection-vi.md)

