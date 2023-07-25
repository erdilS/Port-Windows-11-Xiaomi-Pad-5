<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Cài đặt Windows 11 lên Xiaomi Mi Pad 5

## Các vấn đề


## Thiết bị chỉ vào được Android, không thể vào bootloader

### Điều kiện tiên quyết:

- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)

> **Cảnh báo** Có thể các bước sau đây chẳng giúp ích gì được bạn, bởi vì Xiaomi Pad 5 đã không có một custom recovery nào hoàn thiện để có thể cài đặt lên. Cũng như các thiết bị mới A/B nên chúng tôi cũng không có TWRP Installer zip,... và bạn sẽ không thể boot vào recovery tồn tại vì đã hỏng Fastboot. Nếu vạn đã cài đặt rom AOSP, có thể việc cài lại AOSP Recovery sẽ giúp bạn boot lại trực tiếp vào, vậy thì hãy thử các hướng dẫn sau. Nếu bạn đang dùng MIUI **không root**, hướng dẫn này chẳng giúp được gì đâu.

> Vì vậy, hãy tránh sử dụng nhãn ổ đĩa (disk labels) mà đã có dung lượng hoặc kí tự đặc biệt, và nếu có thể, chỉ nên dùng ESPNABU và WINNABU thôi, vì đã được test hàng triệu lần rồi nhé :>> Nếu bạn bị brick fastboot với disk labels và không root MIUI, bạn sẽ phải flash rom từ EDL bằng account có quyền, bạn sẽ phải trá giá vì đã không chịu đọc cảnh báo.


Vấn đề này do đã phân vùng với tên mà bootloader không xử lí được, để giải quyết:

- Boot vào recovery

- Kết nối máy tính bảng với PC

- Mở cmd trên PC

- Chạy lệnh ```adb shell```

- Chạy lệnh ```parted```

- Chạy lệnh ```print``` để liệt kê các phân vùng

- Nhìn xem phân vùng nào có dấu cách trong tên, ví dụ "Basic Data Partition" và ghi chú lại số volume của nó.

- Bây giờ, hãy chạy lệnh ```rm <số vol>```, ví dụ ```rm 99```


## fsa4480.sys BSOD trong lúc boot

- Mở driver folder

- Xoá đi ```components\QC8150\Device\DEVICE.SOC_QC8150.NABU\Drivers\USB``` folder

- Cài đặt lại driver

- Boot UEFI

- Sau khi boot, đọc driver và cài đặt lại driver một lần nữa

## Bật sạc nhanh và bật chế độ máy chủ USB

> **Cảnh báo nữa nè!** Nhớ là hãy cắm sạc trước khi boot, nếu không thì máy tính bảng sẽ không bao giờ sạc được nữa khi ở trong windows, và làm ơn đừng có tháo sạc hoặc thiết bị không bao giờ sạc được trừ khi bạn reboot và cắm bộ sạc.

> Sạc C đến C bằng thiết bị hỗ trợ PD đã được xác nhận đang hoạt động và bộ sạc 33W do xiaomi cung cấp cũng được xác nhận là đang hoạt động


- Flash cái này [UEFI](https://github.com/kmille36/TempStorage/blob/main/xiaomi-nabu.img?raw=true) bằng lệnh ```fastboot flash boot xiaomi-nabu.img```

- Update cái mới nhất [Drivers](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/blob/main/guide/driver-updating-selection.md)

- Sửa lại giá trị trong reg ```Computer\HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Enum\ACPI\QCOM0597\0\Device Parameters\RoleSwitchMode``` từ 3 thành 1 

- Khởi động lại Windows!

## Tôi đã tắt test mode và giờ không vào được Windows nữa

> **Lưu ý** **QUAN TRỌNG** Hãy chắc chắn bạn đã xem [Cái này](https://youtu.be/oHg5SJYRHA0) trước khi thử bất kì điều gì để tránh các rắc rối sau khi hoàn thành những điều sau đây

- Nhìn lại coi có tỉnh táo không, nhất là được chơi đồ trong lúc làm

- Xem coi có thất vọng về bản thân không, thật đáng thất vọng!

- OK, giờ làm theo tao nào

- Boot recovery image bằng lệnh ```fastboot boot <recovery.img>```

- Đẩy lệnh mass storage bằng ```adb push msc.sh /sbin/```

- Chạy lệnh mass storage với ```adb shell sh /sbin/msc.sh```

- Mở CMD bằng quyền Admin

- Gõ ```diskpart``` để bắt đầu diskpart (Shock dữ)

- Tìm tới ESP Volume bằng lệnh ```list volume```, lẽ ra tao phải được đặt tên là ESPNABU

- Giờ chọn ESP volume bằng lệnh ```select volume <number>```

- Gán kí tự cho ổ đĩa ```assign letter=y```

- Thoát khỏi diskpart ```exit```

- Chạy lại lệnh này để bật lại testmode ```bcdedit /store Y:\EFI\Microsoft\BOOT\BCD /set {default} testsigning on```

- Khởi động lại tablet vào bootloader và boot UEFI, lúc này Windows sẽ hoạt động trở lại
