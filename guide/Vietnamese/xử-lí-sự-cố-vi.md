<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Chạy Windows trên Xiaomi Pad 5

## Khắc phục sự cố


## Khắc phục sự cố

### Điều kiện tiên quyết:

- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)

> **Cảnh báo** Có thể các bước này sẽ không giúp ích gì cho bạn vì Xiaomi Pad 5 không có khôi phục tùy chỉnh hoạt động hoàn toàn để flash nó vào thiết bị. Cũng giống như hầu hết các thiết bị A / B mới hơn, chúng tôi không có zip TWRP Installer, v.v. và bạn không thể khởi động hình ảnh khôi phục hiện có vì fastboot bị hỏng. Nếu bạn đã cài đặt ROM AOSP, có lẽ nó đã cài đặt sẵn khôi phục AOSP và bạn có thể khởi động trực tiếp, vì vậy bạn có thể làm theo các bước sau. Nếu bạn chưa root MIUI, các bước này sẽ không giúp ích gì cho bạn.

> Vì vậy, vui lòng tránh sử dụng nhãn đĩa có chứa khoảng trắng và ký tự đặc biệt, và nếu có thể, chỉ cần sử dụng nhãn ESPNABU và WINNABU đã được kiểm tra hàng triệu lần. Nếu bạn mắc kẹt ở fastboot với nhãn đĩa và bạn đã unrooted MIUI, bạn phải flash rom thông qua EDL với tài khoản được ủy quyền và bạn phải trả tiền cho nó.


Điều này được gây ra bởi các phân vùng có tên ổ đĩa mà bộ nạp khởi động không thể xử lý, để khắc phục nó:

- Khởi động vào recovery

- Kết nối điện thoại với PC

- Mở cmd trên PC

- Chạy ```adb shell```

- Chạy ```parted```

- Chạy ```print``` để liệt kê tất cả các phân vùng

- Tìm các phân vùng có khoảng trắng trong tên v.d "Basic Data Partition" và lưu ý số thứ tự của phân vùng

- Bây giờ chạy ```rm <vol number>``` v.d ```rm 99```


## fsa4480.sys BSOD khi khởi động

- Mở thư mục driver

- Loại bỏ thư mục ```components\QC8150\Device\DEVICE.SOC_QC8150.NABU\Drivers\USB```

- Cài đặt lại driver

- Khởi động UEFI

- Sau khi khởi động, hãy đọc driver và cài đặt lại driver một lần nữa
