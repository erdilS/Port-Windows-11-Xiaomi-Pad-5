<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Cài đặt Windows 11 lên Xiaomi Mi Pad 5

## Hướng dẫn cài đặt

## Cài đặt Windows

### Điều kiện tiên quyết

- [Windows trên ARM image](https://uupdump.net/)
- [UEFI image](/images/)
- [DriverUpdater](https://github.com/WOA-Project/DriverUpdater/releases/latest)
- [Drivers (Trình điều khiển thiết bị)](https://github.com/map220v/MiPad5-drivers)

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

> Thay `<nabudriversfolder>` bằng đường dẫn thực tế của folder Drivers

```cmd
driverupdater.exe -d <nabudriversfolder>\definitions\Desktop\ARM64\Internal\nabu.txt -r <nabudriversfolder> -p X:
```

### Tạo windows bootloader tới EFI

```cmd
bcdboot X:\Windows /s Y: /f UEFI
```

###  Cho phép không kí Driver

> Nếu không làm, đừng hỏi sao bị BSOD nhé

```cmd
bcdedit /store Y:\EFI\Microsoft\BOOT\BCD /set {default} testsigning on
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

### Nhận dạng panel của bạn

```cmd
adb shell panel
```


### Reboot vào bootloader 

```cmd
adb reboot bootloader
```

### Tải và flash UEFI image
> Tải image cho Panel [Huaxing](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/blob/main/images/xiaomi-nabu_huaxing.img?raw=1&plain=1) hoặc [Tianma](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/blob/main/images/xiaomi-nabu_tianma.img?raw=1&plain=1)

```cmd
fastboot flash boot <path to image>
```

### Boot trở lại vào Android
> Dùng backup boot của bạn và flash từ fastboot

```cmd
fastboot flash boot boot.img
```

## Xong rồi!
