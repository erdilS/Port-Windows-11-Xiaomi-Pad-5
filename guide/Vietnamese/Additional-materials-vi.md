<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Chạy Windows trên Xiaomi Pad 5

### List apps/games được hỗ trợ
> Đây không phải là danh sách đầy đủ, nhưng là tổng hợp các ứng dụng/trò chơi đã được cộng đồng thử nghiệm và xác nhận hoạt động.

- [Renegade Google Sheets list](https://docs.google.com/spreadsheets/d/1XYuoySgYQE0HL573sA-0RGMX7I4lt5rWJuQ8Z8yRJNY/edit?usp=drivesdk)

- [ARM Repo (native ARM software)](https://armrepo.ver.lt/)

- [News & supported applications](https://windowsonarm.org/)

#### Hoàn tất!


### Tắt adaptive brightness
- Mở Windows 11 Settings bằng cách nhấn **`Win + I`** hoặc nhấp chuột phải vào nút Start và chọn "Settings".
- Điều hướng đến phần **`System`** từ thanh bên trái.
- Chọn **`Display`** trong cài đặt System.
- Trong phần **`Brightness`**, bạn sẽ thấy hai tùy chọn:
**```1. Change brightness automatically when lighting changes:```**
> Tắt tùy chọn này bằng cách chuyển công tắc sang vị trí **`Off`**.
 **```2. Change brightness based on content:```**
> Tắt tùy chọn này bằng cách chọn **`Off`** từ menu dropdown.

#### Hoàn tất!

### Thiết lập Android boot.img auto-flashing

>[!NOTE]
> Setup Android boot.img auto-flashing trên Windows boot hoặc khi pin thấp (<15%) để tránh tình trạng pin chết khi uefi.img đã được flash.

- Tải xuống **boot.img auto-flasher** [here](https://github.com/Misha803/My-Scripts/releases/tag/boot.img-Auto-Flasher).
- Chạy nó, nhấp vào nút **INSTALL**, chọn thời điểm nào nên tự động flash Android boot.img (trên Windows boot/Pin thấp) và chờ quá trình cài đặt hoàn tất.

#### Hoàn tất!

### Sử dụng USB host mode
> [!Warning]
> Tắt USB host mode nếu bạn sử dụng một bộ chia USB có nguồn điện, vì điều này có thể gây hư hỏng thiết bị của bạn. Nếu bạn không sử dụng một bộ chia USB có nguồn điện, hãy bật USB host mode hoặc bạn sẽ không thể sử dụng bất kỳ thiết bị USB nào.

- Chạy [USB Host Control](https://github.com/Misha803/My-Scripts/releases/tag/USB-Host-Mode-Control) để bật/tắt USB host mode, sau đó xác nhận rằng bạn muốn tắt/bật USB host mode.
- Nếu USB host mode hiện đang được bật và USB không hoạt động, hãy tắt nó đi, sau đó bật lại.

#### Hoàn tất!


### Cài đặt Microsoft Office
- Truy cập [trang cài đặt Office của Gravesoft](https://gravesoft.dev/office_c2r_links).
- Tải xuống trình cài đặt phù hợp với nhu cầu của bạn. Hãy chắc chắn rằng bạn chọn `Online x64`.
- Mở `setup.exe` và làm theo bất kỳ hướng dẫn nào được cung cấp bên trong.

#### Hoàn tất!


### Kích hoạt Windows / Office
- Làm theo hướng dẫn của Massgravel [tại đây](https://github.com/massgravel/Microsoft-Activation-Scripts)

#### Hoàn tất!

## Tôi có thể cập nhật Windows của mình bằng cách sử dụng Windows Update hoặc ISO không?
- ✅ **Có!** Bạn có thể cài đặt bất kỳ bản cập nhật nào xuất hiện trong Windows Update và bạn cũng có thể sử dụng hình ảnh ISO cho việc này.

## Tôi có thể cập nhật Android sau khi cài đặt Windows không?
- ✅ **Có!** Bạn có thể cập nhật Android bằng bất kỳ cách nào, chỉ cần lưu ý sử dụng [hướng dẫn Re-rooting Android](Re-rooting-vi.md) sau khi cập nhật.