<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Cài đặt Windows 11 lên Xiaomi Mi Pad 5

## Hướng dẫn cài đặt

## Cài đặt Windows

### Điều kiện tiên quyết

- [Windows trên ARM image](https://uupdump.net/)
- [UEFI image](https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/images/xiaomi-nabu_secureboot-v2.img)
- [Drivers](https://github.com/map220v/MiPad5-Drivers/releases/latest)


### Boot vào recovery để tiếp tục cài Windows

```cmd
fastboot boot <recovery.img>
```


#### Thực thi msc script

```cmd
adb shell msc
```

### Gán kí tự cho ổ đĩa
  

#### Khởi động Windows disk manager (Windows trình quản lí ổ đĩa)

> Duy nhất Xiaomi Pad 5 được nhận diện là ổ đĩa

```cmd
diskpart
```


#### Gán `X` cho ổ Windows

#### Chọn ổ Windows của máy tính bảng
> Dùng lệnh `list volume` để kiếm, thường nó tên là "WINNABU"

```diskpart
select volume <number>
```

#### Gán kí tự X
```diskpart
assign letter=x
```

### Gán `Y` cho ổ ESP

#### Chọn ổ esp volume của tablet
> Dùng lệnh `list volume` để kiếm, thường nó tên là "ESPNABU"

```diskpart
select volume <number>
```

#### Gán kí tự Y

```diskpart
assign letter=y
```

#### Thoát diskpart
```diskpart
exit
```

  
  

### Cài đặt

> Thay `<path/to/install.wim>` bằng đường dẫn thực tế của `install.wim`.

> `install.wim` nằm ở mục source folder, bên trong file ISO
> Bạn có thể kiếm nó bằng cách giải nén file ISO

```cmd
dism /apply-image /ImageFile:<path/to/install.wim> /index:1 /ApplyDir:X:\
```

### Cài Drivers

> Bạn có Thể tải Xuống Trình Điều khiển [tại đây](https://github.com/map220v/MiPad5-Drivers/releases/latest)

```cmd
Mở thư mục Với Trình Điều Khiển và chạy OfflineUpdater.cmd
```
### Tạo windows bootloader tới EFI

```cmd
bcdboot X:\Windows /s Y: /f UEFI
```


## Boot vào Windows

### Tạo backup cho file boot hiện hành

```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/boot.img"
```

### Đẩy file backup lên máy tính

```cmd
adb pull /tmp/boot.img
```


### Reboot vào bootloader 

```cmd
adb reboot bootloader
```

### Tải và flash UEFI image
> Tải XUỐNG [HÌNH ẢNH UEFI](https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/images/xiaomi-nabu_secureboot-v2.img)
```cmd
fastboot flash boot <path to image>
```

### Boot trở lại vào Android
> Dùng backup boot của bạn và flash từ fastboot

```cmd
fastboot flash boot boot.img
```

## Xong rồi!
