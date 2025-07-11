<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Chạy Windows trên Xiaomi Pad 5

## Hướng dẫn Dualboot (DualbootKernelPatcher)
> Có hai phương pháp được liệt kê dưới đây, phương pháp đầu tiên yêu cầu root, phương pháp thứ hai thì không. Sử dụng phương pháp nào phù hợp nhất với bạn, vì cả hai đều thực hiện cùng một việc.

### Chuẩn bị (phương pháp 1: yêu cầu root)
- [WOA Helper app](https://github.com/n00b69/woa-helper/releases/tag/APK)

> [!NOTE]
> Dịch giả note cho ai chưa biết: **magnetic case** là cái ốp có từ tính, đóng lại thì máy tắt, mở ra thì máy bật.

### Thiết lập - Android
- Tải xuống và cài đặt ứng dụng **WOA Helper**, sau đó mở nó và cấp quyền root.
- Mở **WOA Toolbox**, sau đó nhấn nút **DUALBOOT KERNEL PATCHER** và chọn tùy chọn bạn muốn sử dụng (dualboot bằng **magnetic case**, hoặc với **volume buttons**).
- Chờ cho đến khi hoàn tất, sau đó khởi động lại thiết bị của bạn.

#### Khởi động vào Windows - cách Magnetic Case
- Đóng **magnetic case** và khởi động lại (hoặc bật) thiết bị của bạn.

#### Khởi động vào Windows - cách Volume button
- Khởi động lại (hoặc bật) thiết bị của bạn và giữ bất kỳ **nút âm lượng** nào khi bạn thấy biểu tượng mở khóa hoặc logo Aloha (hình chữ V ngược).

#### Khởi động vào Android
- Mở **magnetic case** và khởi động lại (hoặc bật) thiết bị của bạn.
- Nếu bạn đang sử dụng phương pháp **nút âm lượng**, chỉ cần không nhấn bất kỳ nút âm lượng nào trong khi khởi động thiết bị.

## Hoàn tất!


### Chuẩn bị (phương pháp 2: không yêu cầu root)
- [Modified recovery image](https://github.com/ArKT-7/twrp_device_xiaomi_nabu/releases/tag/mod-win)

- [Magiskboot](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/magiskboot.exe)

- [DualBoot Kernel Patcher](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/DualBootKernelPatcher.zip)

- [.fd file (magnetic case method](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/nabu.fd)

- [.fd file (volume button method](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/nabuVolumebuttons.fd)

### Mở CMD với quyền admin
> Mở CMD với quyền **administrator**, sau đó chạy lệnh bên dưới, thay thế `path\to\platform-tools` bằng đường dẫn thực tế đến thư mục platform-tools, ví dụ **C:\platform-tools**.
>
> Không đóng cửa sổ này. Bạn sẽ cần sử dụng nó trong suốt hướng dẫn này.
```cmd
cd path\to\platform-tools
```

### Khởi động vào modded recovery
> Trong chế độ fastboot, thay thế `path\to\recovery.img` bằng đường dẫn thực tế đến recovery image
```cmd
fastboot boot path\to\recovery.img
```

#### Sao lưu boot image
> This will back up your boot image in the current directory (for example `C:\platform-tools`).
```cmd
adb pull /dev/block/by-name/boot_a boot.img
```

#### Thiết lập các tệp cần thiết
- Tải xuống **magiskboot.exe** và di chuyển nó vào thư mục `platform-tools`.
- Tải xuống **DualBootKernelPatcher.zip** và giải nén thư mục **DualBootKernelPatcher** vào thư mục `platform-tools`.
- Tải xuống **nabu.fd** và di chuyển nó vào thư mục `platform-tools`.

### Giải nén boot image của bạn
> Đảm bảo rằng **boot.img** nằm trong thư mục `platform-tools`.
```cmd
magiskboot unpack boot.img
```

### Vá boot image
```cmd
DualBootKernelPatcher\bin\Windows\DualBootKernelPatcher-x86_64.exe kernel nabu.fd output DualBootKernelPatcher\Config\DualBoot.Sm8150.cfg DualBootKernelPatcher\ShellCode\ShellCode.Nabu.bin
```

### Đổi tên tệp kernel
- Xóa hoặc đổi tên tệp **kernel** trong thư mục `platform-tools`, sau đó đổi tên tệp **output** thành `kernel`

### Đóng gói lại boot image của bạn
> Điều này sẽ đóng gói lại boot image đã vá của bạn vào một tệp mới có tên **new_boot.img**
```cmd
magiskboot repack boot.img
```

### Khởi động vào fastboot
```cmd
adb reboot bootloader
```

### Áp dụng patched boot image
> Thay `path\to\new_boot.img` bằng đường dẫn thực tế đến tệp
```cmd
fastboot flash boot_a path\to\new_boot.img
```
```cmd
fastboot flash boot_b path\to\new_boot.img
```

#### Khởi động lại máy
```cmd
fastboot reboot
```

#### Khởi động vào Windows - cách Magnetic Case
- Đóng **magnetic case** và khởi động lại (hoặc bật) thiết bị của bạn.

#### Khởi động vào Windows - cách Volume button
- Khởi động lại (hoặc bật) thiết bị của bạn và giữ bất kỳ **nút âm lượng** nào khi bạn thấy biểu tượng mở khóa hoặc logo Aloha (hình chữ V ngược).

#### Khởi động vào Android
- Mở **magnetic case** và khởi động lại (hoặc bật) thiết bị của bạn.
- Nếu bạn đang sử dụng phương pháp **nút âm lượng**, chỉ cần không nhấn bất kỳ nút âm lượng nào trong khi khởi động thiết bị.

## Hoàn tất!