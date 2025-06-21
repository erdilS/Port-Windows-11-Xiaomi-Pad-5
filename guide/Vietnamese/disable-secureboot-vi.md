<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Chạy Windows trên Xiaomi Pad 5

## Tắt secureboot
> [!Important]
> Chỉ làm theo khi bạn thực sự cần tắt secureboot, vì nó có thể gây ra một số vấn đề không mong muốn.

### Chuẩn bị
- ```🧠 Một cái đầu lạnh trước sóng gió của cuộc đời```

- [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools)

- [```Recovery Image```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [```UEFI image (Secureboot off)```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/XXXnabu-NoSecureboot-v4.img)

## Lợi và hại của secureboot
> By default, secureboot is enabled in this guide

##### Lợi và hại của secureboot
- √ Không có watermark trên màn hình chính
- √ Các ứng dụng không hoạt động với Test Mode sẽ hoạt động
- √ Bạn có thể cập nhật các phiên bản lớn (ví dụ 22h2 đến 23h2) trong Windows update trực tiếp
- × Bạn không thể cài đặt các driver "lậu"

##### Lợi và hại của secureboot bị tắt
- √ Bạn có thể cài đặt các driver "lậu"
- × Watermark chế độ thử nghiệm trên màn hình chính
- × Một số ứng dụng/trò chơi có phần mềm chống gian lận có thể không hoạt động
- × Bạn không thể cập nhật các phiên bản lớn (ví dụ 22h2 đến 23h2) thông qua Windows Update

## Tắt secureboot

#### Tạo một bản backup root image
> Bạn sẽ cần cái này để quay lại Android, nhưng bạn có thể bỏ qua bước này nếu bạn đã tạo một bản sao lưu

Sử dụng chức năng `Backup Android boot` trong ứng dụng WOA Helper, hoặc khởi động vào recovery đã chỉnh sửa và chạy
```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/rooted_boot.img" && adb pull /tmp/rooted_boot.img
```

#### Khởi động vào recovery
> Thay thế <path\to\recovery> bằng đường dẫn thực tế đến recovery image
```cmd
fastboot boot <path\to\recovery.img>
```

#### Kích hoạt chế độ lưu trữ
> Khi Xiaomi Pad 5 đã khởi động vào recovery đã chỉnh sửa
```cmd
adb shell msc
```

#### Khởi động trình quản lý đĩa Windows
> Khi Xiaomi Pad 5 được phát hiện như một đĩa
```cmd
diskpart
```

#### Chọn phân vùng esp của máy tính bảng
> Sử dụng `list volume` để tìm, nó là phân vùng có tên "ESPNABU"
```diskpart
select volume <number>
```

#### Gán nhãn Y
```diskpart
assign letter y
```

#### Thoát diskpart
```diskpart
exit
```

#### Sửa các tệp bootloader
> Để kích hoạt chế độ thử nghiệm
```cmd
bcdedit /store Y:\EFI\Microsoft\BOOT\BCD /set "{default}" testsigning on
```

#### Xóa SiPolicy
> Giả sử bạn đang tắt secureboot trên một cài đặt hiện có, bạn cần xóa tệp này hoặc máy sẽ thành cục gạch
```cmd
del Y:\EFI\Microsoft\Boot\SiPolicy.p7b
```

#### Gỡ nhãn cho ESPNABU
> Nếu không chạy cũng chả sao, kệ nó và làm lệnh sau. Cái ổ đĩa ảo này sẽ biến mất vào lần khởi động lại PC tiếp theo của bạn.
```cmd
mountvol y: /d
```

#### Khởi động vào fastboot
```cmd
adb reboot bootloader
```

#### Flashing the UEFI
> Đảm bảo bạn sử dụng UEFI không có secureboot từ trang này, thay thế `<path\to\uefi-NoSecureboot-v3.img>` bằng đường dẫn thực tế đến tệp UEFI
```cmd
fastboot flash boot <path\to\uefi-NoSecureboot-v3.img>
```

> [!Important]
> Đảm bảo bạn cũng thay thế UEFI cũ của bạn trong thư mục UEFI trong bộ nhớ trong của Android, để bạn không vô tình flash nó lần sau khi cố gắng chuyển sang Windows từ Android

#### Khởi động lại vào Windows
```cmd
fastboot reboot
```

## Hoàn tất!


















