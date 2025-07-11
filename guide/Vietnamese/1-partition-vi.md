<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Chạy Windows trên Xiaomi Pad 5

## Hướng dẫn cài đặt

### Chuẩn bị
- ```Unlocked bootloader``` - (Nếu bootloader đang khoá và chưa biết mở khoá làm sao thì xem [hướng dẫn này](unlock-bootloader-vi.md))

- ```🧠 Một cái đầu lạnh trước sóng gió của cuộc đời```

- ```Windows 10 trở lên, PC/Laptop```

- [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools)

- [```Bản mod của recovery image```](https://github.com/ArKT-7/twrp_device_xiaomi_nabu/releases/tag/mod-win)

### Lưu ý:
> [!NOTE]
> Bạn có thể chạy song song bất kỳ bản Android nào, bao gồm MIUI/Hyper OS hoặc bất kỳ custom ROM nào khác.

> [!Warning]
> Tất cả dữ liệu sẽ bị xoá, vui lòng **sao lưu** dữ liệu của bạn nếu cần.
> 
> TUYỆT ĐỐI KHÔNG KHỞI ĐỘNG LẠI MÁY TÍNH BẢNG nếu bạn nghĩ bạn làm sai, hãy yêu cầu trợ giúp trong [Telegram chat](https://t.me/nabuwoa)

### Mở CMD với quyền Administrator
> [!NOTE]
> Không biết bắt đầu từ đâu? Giải nén [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools), sau đó mở ```command prompt``` với quyền Admin và chạy lệnh sau, thay thế `"path\to\platform-tools"` bằng đường dẫn thực tế đến thư mục vừa tải (Android platform tools):
```cmd
cd "path\to\platform-tools"
```
> Sử dụng cửa sổ này trong suốt hướng dẫn. Đừng đóng nó.

> [!Note]
> Nếu thiết bị không hiện trong fastboot hoặc recovery mode, bạn sẽ phải cài đặt USB drivers [theo hướng dẫn này](troubleshooting-vi.md#device-is-not-recognized-in-fastboot-or-recovery)

#### Khởi động vào fastboot mode
- Khởi động vào **fastboot mode** bằng cách giữ nút **`giảm âm lương`**, đồng thời cáp phải luôn kết nối với máy tính.
- Hoặc bạn có thể chạy lệnh sau nếu bạn đang ở Android:
```cmd
adb reboot bootloader
```

### Khởi động vào modded recovery
> Trong lúc đang ở fastboot mode, thay thế `path\to\recovery.img` bằng đường dẫn thực tế đến recovery image và chạy lệnh:
```cmd
fastboot boot path\to\recovery.img
```

### Tạo bản sao lưu cho boot image hiện tại
```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/normal_boot.img" && adb pull /tmp/normal_boot.img
```

### Phân vùng thiết bị của bạn
> Có 2 cách để phân vùng thiết bị của bạn. Vui lòng chọn phương pháp bạn muốn sử dụng bên dưới.
 
> [!NOTE]
>
> ▶️ Nhấn để mở rộng menu
>
### Phương pháp 1: Phân vùng thủ công (chỉ sử dụng nếu bạn biết mình đang làm gì)

<details>
  <summary><strong>Nhấn vào đây để xem cách 1</strong></summary> 

#### Unmount data
> Bỏ qua bất kỳ lỗi nào nếu có và tiếp tục lệnh khác
```cmd
adb shell umount /dev/block/by-name/userdata
``` 

#### Resize bảng phân vùng
```cmd
adb shell sgdisk --resize-table 64 /dev/block/sda
```

### Chuẩn bị cho việc phân vùng
```cmd
adb shell parted /dev/block/sda
``` 

#### In bảng phân vùng hiện tại
> Các vùng sẽ được liệt kê, **userdata** sẽ là vùng cuối cùng trong danh sách
```cmd
print
``` 

#### Xoá bỏ userdata
> Thay **$** bằng con số của vùng **userdata**, thường thì là **31** (nhớ xem kỹ khi list vùng ở print)
```cmd
rm $
``` 

> [!NOTE]
> Note này của translator cho phần dưới:
> Bạn có thể chạy theo lệnh hướng dẫn mà không cần xem giải thích. Nếu bạn là một người nâng cao, bạn có thể đọc hiểu các lệnh này và tự thay thế các giá trị.

#### Tạo lại vùng userdata
> Thay **10.9GB** bằng start value của **userdata** trước đó mà chúng ta đã xoá (nhìn lại ở print)
>
> Thay **70GB** bằng end value mà bạn muốn **userdata** có (vùng của Android). Giả sử bạn muốn chia cho Android 59GB thì end value sẽ 70GB, ta lấy 59+10.9 = **70GB** (sử dụng số làm tròn, không cần chính xác tuyệt đối với end value)
```cmd
mkpart userdata ext4 10.9GB 70GB
``` 

#### Tạo phân vùng ESP
```cmd
mkpart esp fat32 70GB 70.3GB
> Thay **70GB** bằng end value của **userdata** (gõ print lần nữa để xem lại trước khi thay)
>
> Thay **70.3GB** bằng giá trị bạn đã sử dụng trước đó, thêm **0.3GB** vào đó (Phân vùng ESP sẽ có 300MB)
```cmd
mkpart esp fat32 70GB 70.3GB
``` 

#### Tạo phân vùng Windows
> Thay **70.3GB** bằng end value của **esp** (gõ print lần nữa để xem lại trước khi thay)
```cmd
mkpart win ntfs 70.3GB -0MB
``` 

#### Làm cho ESP bootable
> Sử dụng lệnh `print` để xem tất cả các phân vùng. Thay thế "$" bằng số phân vùng ESP của bạn, số này sẽ là **32**
```cmd
set $ esp on
``` 

#### Thoát chia vùng
```cmd
quit
``` 

### Định dạng các phân vùng Windows và ESP
> Đảm bảo rằng **win** thực sự có số phân vùng **33** bằng xem lại cái của lệnh `print` trước đó
```cmd
adb shell mkfs.ntfs -f /dev/block/sda33 -L WINNABU
``` 

> Đảm bảo rằng **esp** thực sự có số phân vùng **32** bằng xem lại cái của lệnh `print` trước đó
```cmd
adb shell mkfs.fat -F32 -s1 /dev/block/sda32 -n ESPNABU
```

### Sửa GPT
> Hoặc Windows có thể làm cho máy bạn đi bụi
```cmd
adb shell fixgpt
```

#### Khởi động lại thiết bị
> Nhằm đảm bảo Android vẫn bình thường
>
> Nếu nó không chạy, bạn hãy xoá hết dữ liệu máy tính bảng và khởi động lại (Factory reset)
```cmd
adb reboot
```

### [Bước kế tiếp: Root máy](/guide/Vietnamese/2-rootguide-vi.md)

----

</details>

### Phương pháp 2: Tự động phân vùng (khuyến nghị)

<details>
  <summary><strong>Nhấn vào đây để xem cách 2</strong></summary> 

### Chạy script phân vùng
> Thay **$** bằng số dung lượng bạn muốn Windows sử dụng (không thêm chữ GB, chỉ cần viết số)
>
> Nếu nó kêu 'run it again', bạn sợ à, chạy lại đi
```cmd
adb shell partition $
```

### [Bước kế tiếp: Root máy](/guide/Vietnamese/2-rootguide-vi.md)

</details>

----