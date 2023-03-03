<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Chạy Windows trên Xiaomi Pad 5

## Cập nhật Driver

### Điều kiện tiên quyết

- [UEFI](../../../../releases/tag/1.0)
- [Mass storage mode script](../../../../releases/tag/1.0)
- [TWRP](../../../../releases/tag/1.0)
- [DriverUpdater](https://github.com/WOA-Project/DriverUpdater/releases/latest)
- [Drivers](https://github.com/map220v/MiPad5-Drivers)

#### Vào recovery thông qua PC với lệnh

```cmd
fastboot boot <recovery.img>
```

## Đẩy script

```cmd
adb push msc.sh /sbin/
```

### Thực thi script

```cmd
adb shell sh /sbin/msc.sh
```

## Gán kí tự cho ổ đĩa

#### Khởi động trình quản lí đĩa của Windows

> Một khi Pad 5 được phát hiện là đĩa

```cmd
diskpart
```


### Gán `x` cho Windows volume

#### Chọn Windows volume trên điện thoại
> Dùng `list volume` để tìm, nó thường là cái ở cuối

```diskpart
select volume <number>
```

#### Gán kí tự x
```diskpart
assign letter=x
```

### Thoát diskpart:
```diskpart
exit
```


# Cài đặt Drivers

> Thay thế `<nabudriversfolder>` bằng đường dẫn tới thư mục drivers

> Mở cmd với quyền quản trị viên

```cmd
driverupdater.exe -d <nabudriversfolder>\definitions\Desktop\ARM64\Internal\nabu.txt -r <nabudriversfolder> -p X:
```


##### Khởi động với Windows bootable UEFI image #####

```
fastboot flash boot <uefi.img>
```


# Đã hoàn thành!
