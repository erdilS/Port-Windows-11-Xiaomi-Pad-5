<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Chạy Windows trên Xiaomi Pad 5

## Phục hồi máy trong chế độ EDL
> Hướng dẫn này bao gồm hai phương pháp để flash thiết bị của bạn, nếu phương pháp 1 không thành công, hãy sử dụng phương pháp 2

### Nhập chế độ EDL
> Có hai phương pháp để khởi động Xiaomi Pad 5 của bạn vào **chế độ EDL**. Sử dụng phương pháp nào phù hợp với bạn.

> [!NOTE]
>
> ▶️ Nhấn để mở rộng menu.

<details>
  <summary><strong>Phương pháp 1: Mở khoá bootloader</strong></summary>

> Nếu bootloader của bạn đã được mở khoá, chỉ cần chạy lệnh sau trong **fastboot mode**
```cmd
fastboot oem edl
```

</details>

<details>
  <summary><strong>Phương pháp 2: Locked bootloader or unbootable device</strong></summary>

- Cắm một **cáp EDL** (nếu bạn có) vào thiết bị của mình và nhấn nút trên cáp để khởi động vào **EDL mode**.
> Các cáp EDL bạn mua online được, nhưng để chạy được thì phải bao gồm V2 trong tên, ví dụ **Hydra V2 EDL Cable**.
- Ngoài ra, bạn có thể **short the test points** (cần mở nắp lưng của thiết bị).

</details>

### Kiểm tra mọi thứ ô-kê chưa
- Mở **Device Manager** trên PC của bạn và tìm kiếm một thiết bị mới, chẳng hạn như **Qualcomm HS-USB QDLoader 9008**.
- Nếu thiết bị được đặt tên là **QUSB_BULK_CID** và/hoặc có cảnh báo màu vàng ⚠️ trong **Device Manager**, bạn cần cài đặt/cập nhật driver.
- Để làm điều này, hãy tải xuống và giải nén tệp **[QUD.zip](https://github.com/n00b69/woa-betalm/releases/download/Qfil/QUD.zip)**, chọn thiết bị có lỗi trong Device Manager, chọn **Update drivers**, sau đó chọn thư mục **QUD** mà bạn đã giải nén.

> [!NOTE]
>
> ▶️ Nhấn để mở rộng menu.

<details>
  <summary><strong>Phương pháp 1: Cách miễn phí</strong></summary>

## Phương pháp 1: Đồ chùa

### Chuẩn bị
- [`Patched MiFlash Tool`](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/MiFlashPatched.zip)

- [`Patched firehose (.elf) file`](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/prog_ufs_firehose_sm7150_ddr.elf)

- `Đã giải nén` [`fastboot ROM for Nabu`](http://xmfirmwareupdater.com/miui/nabu/) 

### Chuẩn bị trước các files quan trọng
- Giải nén **fastboot ROM** cho Xiaomi Pad 5 của bạn.
- Giải nén tệp **MiflashPatched.zip** mà bạn đã tải xuống trước đó.
- Sao chép tệp **firehose (.elf)** từ thư mục **MiflashPatched.zip** vào thư mục **images** bên trong **fastboot ROM** đã giải nén của bạn, ghi đè lên tệp hiện có.

#### Mở MiFlash Tool
- Điều hướng đến thư mục **MiFlash** bên trong **MiflashPatched.zip** đã giải nén.
- Khởi động **XiaoMiFlash.exe** với quyền quản trị.

### Flashing the ROM
- Nhấn nút **Select** trong **MiFlash** và chọn thư mục nơi bạn đã giải nén **fastboot ROM** của mình (thư mục mà bạn đã thay thế tệp **firehose.elf**).
- Trong công cụ **MiFlash**, đảm bảo rằng tùy chọn **"Clean All"** đã được chọn.
- Nhấn **Refresh** trong **MiFlash** để xác minh kết nối với thiết bị của bạn.
- Sau khi xác nhận thiết bị của bạn đã được phát hiện và tùy chọn **"Clean All"** đã được chọn, nhấn **Flash** để bắt đầu quá trình flash.

> [!Important]
> Nếu bạn thấy bất kỳ lỗi nào không biến mất sau 2 phút, hãy khởi động lại thiết bị vào **EDL mode** một lần nữa, sau đó nhấn **Refresh** và **Flash** lại để thử lại.

#### Khởi động lại thiết bị
- Sau khi quá trình flash hoàn tất, nhấn nút **Reboot** để khởi động lại thiết bị.

</details>

<details>
  <summary><strong>Phương pháp 2: Cách trả phí</strong></summary>

## Phương pháp 2: Flash trả phí qua công cụ HXRU

### Chuẩn bị
- `$3 USDT` và một ví tiền điện tử để mua tín dụng (một số tài khoản ngân hàng Nga cũng được chấp nhận)

- `Tài khoản Telegram` để liên lạc với hỗ trợ HXRU

- [`MiFlash HXRU Tool`](https://hxrutool.net/tool/Xiaomi_Auth_Tool_v9.0.0.5_mtk.zip)

- [`Stock fastboot ROM for Nabu`](http://xmfirmwareupdater.com/miui/nabu/)
### Thiết lập công cụ HXRU
- Tạo một tài khoản trên **[HXRU dashboard](https://dashboard.hxrutool.com/Register)**.
- Tải xuống và giải nén công cụ **MiFlash HXRU**.

#### Mua tín dụng
- Liên hệ với **@hxruofficial** trên Telegram để mua **5 tín dụng** (khoảng **$3**). Bạn cần những tín dụng này để tiếp tục quá trình flash thiết bị của mình.

### Flashing your device
- Mở **XiaoMiFlash.exe** và cấp quyền quản trị cho nó.
- Tải xuống fastboot rom gốc cho thiết bị của bạn (nên có phần mở rộng .tgz) và mở nó. Bên trong sẽ có một tệp .tar. Giải nén nội dung của tệp .tar này vào bất kỳ thư mục nào.
- Nhấn nút **select** trong **XiaoMiFlash** và chọn thư mục này.
- Nhấn **flash**.
- Nếu bạn nhận được lỗi `write time out`, hãy giữ nút **power** + **volume down** trong khoảng 30 giây để khởi động lại EDL. Sau đó nhấn nút **flash** một lần nữa.
- Sau vài giây, một cửa sổ đăng nhập sẽ xuất hiện. Nhập thông tin tài khoản HRXU của bạn vào đây và nhấn **Request Auth Flashing**.

#### Khởi động lại thiết bị
- Sau khi nó hiển thị **flash done**, hãy khởi động lại thiết bị của bạn bằng cách giữ nút **power** trong khoảng 14 giây.

</details>

### Reflashing your rom with MiFlash
> [!Warning]
> Đống tools này sẽ flash rom về 1 slot. Nếu thiết bị của bạn chuyển đổi slot, nó sẽ khởi động lại vào EDL một lần nữa.
- Khởi động lại vào fastboot mode.
- Flash lại fastboot rom lần thứ hai bằng cách sử dụng **MiFlash** hoặc với tệp **flash_all.bat** trong rom.
- Khởi động lại sau khi quá trình flash hoàn tất.

#### Thành công!
Xiaomi Pad 5 của bạn bây giờ đã được reflash như ban đầu.