<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Chạy Windows trên Xiaomi Pad 5

## Phục hồi máy trong chế độ EDL

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
  <summary><strong>Flash bằng MiFlash</strong></summary>

## Flash bằng MiFlash

### Chuẩn bị
- [`Patched MiFlash Tool`](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/Files/MiFlashPatched.zip)

- [`Patched firehose (.elf) file`](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/Files/prog_ufs_firehose_sm7150_ddr.elf)

- `Đã giải nén` [`fastboot ROM for Nabu`](https://xiaomifirmwareupdater.com/hyperos/nabu/) 

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

#### Thành công!
Xiaomi Pad 5 của bạn bây giờ đã được reflash như ban đầu.