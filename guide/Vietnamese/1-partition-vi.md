<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Cài đặt Windows 11 lên Xiaomi Mi Pad 5

## Cài đặt

### Phân vùng cho thiết bị

### Điều kiện tiên quyết

- [Recovery Image](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)

### Chú ý nha:
> [!WARNING]
>  Nếu bạn vô tình xoá bất kì phân vùng vào bằng kí tự diskpart hoặc windows sẽ gửi một lệnh ufs rằng có gì đó sai sai làm bạn bị xoá hết file ufs.
>
> Dữ liệu của bạn sẽ bị xoá sạch! Hãy backup từ bây giờ nếu cần thiết.
> 
> Những lệnh sử dụng ở đây đều đã được thử nghiệm thành công
> 
> Bỏ qua cảnh báo `udevadm`
> 
> TUYỆT ĐỐI KHÔNG khởi động lại máy tính bảng, nếu cần hỗ trợ hãy hỏi tại [Telegram chat](https://t.me/nabuwoa)
>
>
> TUYỆT ĐỐI KHÔNG copy toàn bộ lệnh rồi làm 1 lần duy nhất. Câu lệnh sẽ cần thời gian để chạy nên không được làm thế đâu!
>
> KHÔNG ĐƯỢC SAI LẦM. MỘT CÂU LỆNH SAI CÓ THỂ KHIẾN MÁY BẠN KHÔNG BAO GIỜ HOẠT ĐỘNG TRỞ LẠI!!!


#### Boot recovery từ PC bằng lệnh
```cmd
fastboot boot <recovery.img>
```
##### Chạy tập lệnh phân vùng

> Nếu nó yêu cầu bạn chạy nó một lần nữa, hãy làm như vậy

> Đây là **tùy chọn** nhưng bạn có thể **đặt kích thước tùy chỉnh bằng cách sử dụng tập lệnh này**

> Để đặt kích thước tùy chỉnh, hãy thực hiện  ```adb shell partition [NHẮM MỤC TIÊU KÍCH THƯỚC WINDOWS TÍNH BẰNG GB]```

> Đảm bảo rằng bạn không thêm GB ở cuối, chỉ số

```cmd
adb shell partition
```


### Make a backup of your existing boot image

```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/normal_boot.img" && adb pull /tmp/normal_boot.img
```


#### Check if Android still starts
> just see if Android still works
If isn't boot or looping on animation, use MIUI recovery or other recoveries for wiping data.

```cmd
adb reboot
```

### [Bước tiếp theo: Get root](/guide/Vietnamese/2-rootguide-vi.md)
