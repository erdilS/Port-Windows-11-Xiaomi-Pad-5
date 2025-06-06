<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Chạy Windows trên Xiaomi Pad 5

## Hướng dẫn cài đặt

### Chuẩn bị
- ```🧠 Một cái đầu lạnh trước sóng gió của cuộc đời```

- [```DriveLetterAssigner Tool```](https://github.com/Misha803/My-Scripts/releases/tag/DriveLetterAssigner)
  
- [```ARM Windows ESD```](https://arkt-7.github.io/woawin/)
    
- [```Drivers```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/Drivers)

- [```UEFI image```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/UEFI)

### Khởi động vào modded recovery
> Thay `path\to\recovery.img` bằng đường dẫn thực của file recovery
```cmd
fastboot boot path\to\recovery.img
```

### Thực thi msc
> Nếu nó yêu cầu bạn chạy lại, bạn sợ à, chạy lại tiếp cho mình
```cmd
adb shell msc
```

### Gắn nhãn cho WINNABU và ESPNABU
> Chạy **DriveLetterAssigner** và nhấp **`YES`** để tự động gán nhãn **X** và **Y** cho **WINNABU** và **ESPNABU**

### Cài đặt Windows
> [!Important]
> Hãy chắc chắn rằng bạn đang chạy CMD/Powershell với quyền **Administrator**

> [!Important]
> Vì lý do hiệu suất, nên sử dụng Windows 11 24H2 (các bản dựng bắt đầu bằng 261XX, chẳng hạn như 26100.2454)

> Thay `path\to\install.esd` bằng đường dẫn thực của file install.esd (nó cũng có thể được đặt tên là install.wim hoặc 22631.2861.XXXXXXX.esd)

```cmd
dism /apply-image /ImageFile:path\to\install.esd /index:6 /ApplyDir:X:\
```

> Nếu thấy lỗi `Error 87`, hãy kiểm tra index của image với lệnh `dism /get-imageinfo /ImageFile:path\to\install.esd`, sau đó thay `index:6` bằng số index thực tế của **Windows 11 Pro** trong image của bạn

### Chép file boot.img vào Windows
- Kéo thả **rooted_boot.img** từ thư mục **platform-tools** vào ổ đĩa **WINNABU** trong Windows Explorer, sau đó đổi tên thành **boot.img**.

### Cài đặt Drivers
- Giải nén driver đã tải trước đó, sau đó mở file `OfflineUpdater.cmd` (nếu có lỗi xuất hiện, hãy chạy `OfflineUpdaterFix.cmd` thay thế)

> Nếu nó yêu cầu bạn nhập một ký tự, hãy nhập ký tự ổ đĩa của **WINNABU** (nên là **X**), sau đó nhấn enter

#### Tạo các file bootloader cho Windows
> Nếu có lỗi xảy ra khi sao chép các file boot, hãy chạy lại **DriveLetterAssigner**, sau đó chạy lại lệnh sau, thay **Y** bằng **U**
```cmd
bcdboot X:\Windows /s Y: /f UEFI
```

#### Xoá nhãn cho ESPNABU
> Nếu điều này không hoạt động, hãy bỏ qua và chuyển sang lệnh tiếp theo. Ổ đĩa ảo này sẽ biến mất vào lần khởi động lại PC tiếp theo của bạn.
```cmd
mountvol y: /d
```

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

## [Bước cuối cùng: Thiết lập dualboot](/guide/Vietnamese/dualboot-selection-vi.md)
