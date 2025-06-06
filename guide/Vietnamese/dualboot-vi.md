<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Chạy Windows trên Xiaomi Pad 5

## Khởi động kép Android và Windows một cách mượt mà, liền mạch.

### Chuẩn bị
- ```Một máy tính bảng đã root với Windows được cài đặt```

- [```Hình ảnh UEFI```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/UEFI)

- [```Ứng dụng WoA Helper```](https://github.com/n00b69/woa-helper/releases/tag/APK)

## Thiết lập ứng dụng khởi động kép
> Hướng dẫn này giả định rằng bạn đã root, nếu không, vui lòng làm theo [hướng dẫn root](2-rootguide-vi.md) trước

### Thiết lập - Android
- Tải xuống và cài đặt ứng dụng **WOA Helper**, sau đó mở nó và cấp quyền root.
- Tải xuống **Hình ảnh UEFI** và đặt nó vào thư mục có tên `UEFI` trong bộ nhớ trong của bạn.
- Mở ứng dụng WOA Helper và sử dụng **STA CREATOR** trong **WOA TOOLBOX**.
> [!Important]
> Nếu `/sdcard/Windows` trống, rom của bạn không hỗ trợ mounting và bạn sẽ phải tạo một bản sao lưu boot.img bên trong ứng dụng, sau đó sao chép nó thủ công vào Windows khi bạn khởi động vào đó (ví dụ bằng cách tải nó lên một nơi nào đó và sau đó tải xuống trong khi khởi động vào Windows). Điều này cũng áp dụng cho các tệp StA, cũng được tạo trong bộ nhớ trong của bạn.
>
> Làm điều tương tự nếu thư mục chỉ đọc.
- Nhấn nút **QUICKBOOT TO WINDOWS**.

### Thiết lập - Windows
> [!Tip]
> Nếu đây là lần đầu tiên bạn khởi động Windows và bạn muốn bỏ qua đăng nhập tài khoản Microsoft, hãy nhấn nút **I don't have internet** trên trang WiFi, sau đó khi được nhắc, hãy nhấn nút **Continue with limited setup**.
- Điều hướng đến `C:\sta` và tạo một lối tắt của **sta.exe** trên màn hình desktop của bạn, nếu chưa có sẵn

#### Khởi động vào Android
- Chạy lối tắt mới trên màn hình desktop của bạn (bạn cũng có thể ghim nó vào menu bắt đầu / thanh tác vụ của mình để dễ dàng truy cập)

#### Khởi động vào Windows
- Nhấn `QUICKBOOT TO WINDOWS` bên trong ứng dụng, hoặc sử dụng nút mới được tạo trong bảng điều khiển cài đặt nhanh của bạn

## Hoàn tất!

> [!TIP]
> Đừng quên kiểm tra trang [**```Ứng dụng và hướng dẫn hữu ích```**](Additional-materials-vi.md). Bạn sẽ tìm thấy hướng dẫn về cách kích hoạt Windows của mình, cũng như các thông tin hữu ích khác.