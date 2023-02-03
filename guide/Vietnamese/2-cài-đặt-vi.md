# Cài đặt Windows

### Khởi động lại vào chế độ recovery để bắt đầu cài đặt Windows

```cmd
fastboot boot <recovery.img>
```

### Đẩy tập lệnh msc qua /sbin

```cmd
adb push msc.sh /sbin/
```

### Thực thi tập lệnh msc

```cmd
adb shell sh /sbin/msc.sh
```

## Gán ký tự chữ cái cho ổ đĩa
  

#### Khởi động trình quản lý đĩa của Windows

> Một khi Xiaomi Pad 5 được phát hiện dưới dạng đĩa

```cmd
diskpart
```


### Gán ký tự `X` cho Windows volume

#### Chọn Windows volume trên điện thoại của bạn
> Sử dụng `list volume` để tìm, nó là những volume có tên "WINNABU" và "ESPNABU"

```diskpart
select volume <number>
```

#### Gán kí tự X
```diskpart
assign letter=x
```

### Gán kí tự `Y` cho esp volume

#### Chọn esp volume trên điện thoại của bạn
> Sử dụng `list volume` để tìm, nó thường là cái cuối cùng

```diskpart
select volume <number>
```

#### Gán kí tự Y

```diskpart
assign letter=y
```

### Thoát diskpart:
```diskpart
exit
```

  
  

## Cài đặt

> Thay thế `<path/to/install.wim>` bằng đường dẫn install.wim của bạn,

> `install.wim` nằm trong thư mục sources bên trong ISO
> Bạn có thể lấy nó bằng cách mount ra windows explore hoặc giải nén nó ra

```cmd
dism /apply-image /ImageFile:<path/to/install.wim> /index:1 /ApplyDir:X:\
```

# Cài đặt Drivers

> Thay thế `<nabudriversfolder>` bằng vị trí của thư mục trình điều khiển

```cmd
driverupdater.exe -d <nabudriversfolder>\definitions\Desktop\ARM64\Internal\nabu.txt -r <nabudriversfolder> -p X:
```

  

# Tạo tệp Windows bootloader cho EFI

```cmd
bcdboot X:\Windows /s Y: /f UEFI
```

  
  

# Cho phép các drivers chưa được ký

>Nếu bạn không làm bước này sẽ dẫn tới màn hình xanh

```cmd
bcdedit /store Y:\EFI\Microsoft\BOOT\BCD /set {default} testsigning on
```

# Khởi động vào Windows

### Tạo bản sao lưu hình ảnh khởi động hiện có của bạn

```cmd
adb shell "dd if=/dev/block/bootdevice/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/boot.img"
```

##### Đẩy sao lưu vào máy tính

```cmd
adb pull /tmp/boot.img
```

### Khởi động vào bootloader 

```cmd
adb reboot bootloader
```

### Flash hình ảnh uefi từ TWRP

```cmd
fastboot flash boot boot-nabu.img
```

# Khởi động lại vào Android
> Sử dụng image khởi động sao lưu của bạn và flash từ fastboot

```cmd
fastboot flash boot boot.img
```

# Đã xong!
