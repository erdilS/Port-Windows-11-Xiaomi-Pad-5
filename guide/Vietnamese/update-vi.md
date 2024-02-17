<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Cài đặt Windows 11 lên Xiaomi Mi Pad 5

## Cập nhật các trình điều khiển (Drivers)

### Điều kiện tiên quyết

- [```Recovery```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)
  
- [```UEFI image```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v3.img)
  
- [```Drivers```](https://github.com/map220v/MiPad5-Drivers/releases/latest)

#### Khởi động Recovery từ máy tính bằng CMD

```cmd
fastboot boot <recovery.img>
```

#### Thực thi lệnh
> Nếu nó yêu cầu bạn chạy nó một lần nữa, hãy làm như vậy
```cmd
adb shell msc
```

### Gán Kí tự cho ổ đĩa

#### Khởi động Windows disk manager

> Duy nhất Pad 5 được nhận là một ổ đĩa

```cmd
diskpart
```


### Gán `X` cho Windows volume

#### Chọn Windows volume cho máy tính bảng
> Sử dụng `list volume` để tìm kiếm, chỉ duy nhất có một "WINNABU"

```diskpart
select volume <number>
```

#### Gán kí tự X
```diskpart
assign letter=x
```

#### Thoát khỏi diskpart
```diskpart
exit
```

### Cài Drivers

> Bạn có Thể tải Xuống Trình Điều khiển [tại đây](https://github.com/map220v/MiPad5-Drivers/releases/latest)

> nếu nó ghi `"Automatic WINNABU detection failed! Enter Drive Letter manually"`, nhập **`X`**  
```cmd
Mở thư mục Với Trình Điều Khiển và chạy OfflineUpdater.cmd
```
### Khởi động bằng Windows bootable UEFI image
 Hoặc nếu UEFI của bạn đã được flashed, chỉ cần khởi động lại với ```adb reboot```
```
fastboot flash boot <uefi.img>
```

## Hoàn tất!
