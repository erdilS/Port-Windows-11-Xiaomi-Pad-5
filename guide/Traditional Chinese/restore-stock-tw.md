<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# 在 Xiaomi Pad 5 上執行 Windows

## 解除安裝

### 為何需要這樣做？

如果您想要解除安裝 Windows，就使用本指南而非手動刪除分割區，這樣可以避免人為錯誤，這一部完整的指南僅用於解除安裝。

如果您想要重新鎖定您的 Bootloader，您的磁碟分割表格必須是原廠狀態。

### 先決條件

- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)
- [gpt_both0.bin](../../../../releases/tag/1.0)

### 還原 GPT
> 使用 gpt_both0.bin 檔案路徑取代 ```<gpt_both0.bin>```。

```cmd
fastboot flash partition:0 <gpt_both0.bin>
```

### 清除 Userdata 以避免開機迴圈並還原 FS 大小
```cmd
fastboot -w
```
