<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Cài đặt Windows 11 lên Xiaomi Mi Pad 5

## Cập nhật các trình điều khiển (Drivers)

### Điều kiện tiên quyết

- [UEFI](../../../../releases/tag/1.0)
- [Mass storage mode script](../../../../releases/tag/1.0)
- [TWRP](../../../../releases/tag/1.0)
- [DriverUpdater](https://github.com/WOA-Project/DriverUpdater/releases/latest)
- [Drivers](https://github.com/map220v/MiPad5-Drivers)

#### Khởi động Recovery từ máy tính bằng CMD

```cmd
fastboot boot <recovery.img>
```

#### Tải script lên

```cmd
adb push msc.sh /sbin/
```

#### Thực thi lệnh

```cmd
adb shell msc.sh
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


### Cài đặt trình điều khiển thiết bị (gọi là Drivers)

> Thay thế `<nabudriversfolder>` bằng đường dẫn của thư mục Drivers

> Mở cmd với quyền Admin


```cmd
DriverUpdater.exe -d <nabudriversfolder>\definitions\Desktop\ARM64\Internal\nabu.txt -r <nabudriversfolder> -p X:
```


### Khởi động bằng Windows bootable UEFI image

```
fastboot flash boot <uefi.img>
```

## Hoàn tất!
