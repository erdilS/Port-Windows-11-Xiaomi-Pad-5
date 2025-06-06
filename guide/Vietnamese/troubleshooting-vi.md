<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Chạy Windows trên Xiaomi Pad 5

## Cẩm nang khắc phục sự cố

## Tôi không thể di chuyển tệp vào thư mục Windows từ Android

Nếu bạn hong thể chuyển file tới Windows, có nghĩa là bạn đã tắt Windows thay vì khởi động lại. Để sủa lỗi này, hãy khởi động vào Windows và nhấn nút restart, sau đó khi nó khởi động vào fastboot, hãy dùng fastboot để trở về Android.

##### Hoàn tất!
## Không nhận dạng được thiết bị trong fastboot hoặc recovery
> Có nghĩa là bạn chưa cài đặt (đúng) driver USB
- Tải [QUD.zip](https://github.com/n00b69/woa-betalm/releases/download/Qfil/QUD.zip) về và giải nén nó.
- Mở Device Manager và tìm một thiết bị không xác định hoặc thiết bị có lỗi có thể được gọi là **Android**, **ADB Interface**, hoặc **QUSB_BULK**.
- Nhấp chuột phải vào thiết bị này, chọn "Update Drivers" > "Browse files", sau đó chọn **QUD folder** mà bạn đã giải nén trước đó.

##### Hoàn tất!

## Sạc trong Windows không hoạt động
> [!WARNING]
> Không được sử dụng một bộ chia USB có nguồn với chế độ host được bật, điều này có thể làm hỏng thiết bị của bạn. Nếu bạn sử dụng một hub USB có nguồn, vui lòng sử dụng [hướng dẫn tắt chế độ host USB](/guide/Vietnamese/Additional-materials-vi.md#Disabling-USB-host-mode)

Sạc trong Windows chỉ hoạt động với các cáp cụ thể. Các cáp đã được biết là hoạt động bao gồm cáp gốc Poco X3 Pro (được xác định bởi chân cam/đỏ bổ sung trong cổng USB-A), cáp Nimaso 100W USB-C sang USB-C, cáp Samsung USB-C sang USB-C.

##### Hoàn tất!

## NABU trong fastboot không nhận diện được bởi PC/Laptop của tôi, tôi nên làm gì?
- Tải [**`QUD.zip`**](https://github.com/n00b69/woa-betalm/releases/download/Qfil/QUD.zip) về và giải nén nó.
- Mở Device Manager và tìm một thiết bị không xác định hoặc thiết bị có lỗi có thể được gọi là Android hoặc QUSB_BULK.
- Nhấp chuột phải vào thiết bị này, chọn **```Update Drivers```** → **`Browse files`**, sau đó chọn thư mục QUD mà bạn đã giải nén trước đó.

##### Hoàn tất!


## Thiết bị có thể khởi động vào Android và/hoặc Windows nhưng không vào bootloader

### Yêu cầu:
- [Termux](https://play.google.com/store/apps/details?id=com.termux)

- [Android platform tools](https://developer.android.com/studio/releases/platform-tools)

- [SHRP Recovery](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/SHRP.img)

#### Nếu bạn có quyền truy cập vào Android:
- Cài đặt **Termux** và cấp quyền root cho nó.
- Cài đặt **tsu** và **parted** bằng cách sử dụng hai lệnh này, nhấn `Y` nếu nó yêu cầu bạn xác nhận:
```cmd
pkg install tsu
```
```cmd
pkg install parted
```
- Chạy lệnh bên dưới để mở parted:
```cmd
parted /dev/block/sda
```
- Chạy ```print``` để liệt kê tất cả các phân vùng.
- Tìm các phân vùng có độ dài hơn 16 ký tự, ví dụ "Basic Data Partition" và ghi lại số hiệu của chúng.
- Đổi tên phân vùng này bằng lệnh ```name $ test```, thay thế **$** bằng số hiệu phân vùng và thay thế **test** bằng tên bạn muốn đặt cho phân vùng.
- Chạy lệnh ```quit```.

##### Hoàn tất!


#### Nếu bạn có quyền truy cập vào Windows:
- Đổi tên **C:\boot.img** thành **C:\bootb.img**.
- Tải hình ảnh **SHRP recovery** về, đổi tên thành **boot.img**, và đặt nó vào `C:\`.
- Chạy lối tắt **Switch to Android** hoặc **Android** để flash và khởi động vào SHRP recovery.
- Khi đã khởi động vào recovery, kết nối thiết bị của bạn với PC và chạy:
```cmd
adb shell parted /dev/block/sda
```
- Chạy ```print``` để liệt kê tất cả các phân vùng.
- Tìm các phân vùng có độ dài hơn 16 ký tự, ví dụ "Basic Data Partition" và ghi lại số hiệu của chúng.
- Đổi tên phân vùng này bằng lệnh ```name $ test```, thay thế **$** bằng số hiệu phân vùng và thay thế **test** bằng tên bạn muốn đặt cho phân vùng.
- Chạy lệnh ```quit```.
- Chạy lệnh ```adb reboot bootloader```, và khi bạn thấy logo **FASTBOOT** trên màn hình, hãy flash hình ảnh boot Android của bạn bằng lệnh ```fastboot flash boot_a path\to\boot.img```.
- Bạn có thể phải làm tương tự cho **boot_b** nếu thiết bị của bạn không khởi động, hoặc nếu nó khởi động lại vào recovery.

> [!important]
> Đảm bảo đặt hình ảnh UEFI trở lại thư mục UEFI, hoặc nếu bạn đã sử dụng phương pháp Windows, hãy đặt boot.img vào C:\

##### Hoàn tất!

## fsa4480.sys BSOD on boot
- Mở thư mục driver

- Xóa dòng ```<DriverPackageFile Path="$(mspackageroot)\components\QC8150\Device\DEVICE.SOC_QC8150.NABU\Drivers\USB" Name="fsa4480.inf" ID="fsa4480"/>``` từ NABU.xml

- Cài đặt lại driver

- Khởi động UEFI
> [!NOTE]
> Nếu bạn vẫn gặp BSOD, hãy sử dụng hướng dẫn `cài đặt lại` và sử dụng gói driver này

##### Hoàn tất!

## Bootloop sau khi chuyển sang Android
- Khởi động vào fastboot

- ```fastboot set_active other```

- ```fastboot flash boot <boot.img>```

- ```fastboot reboot```

##### Hoàn tất!

















