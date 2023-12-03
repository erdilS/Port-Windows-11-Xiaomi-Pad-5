<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# 在 Xiaomi Pad 5 上安裝 Windows

## 恢復原廠分區表並刪除 Windows

### 在什麽時候需要這樣做 ?

如果您想要刪除 Windows, 請參考本篇而不是手動嘗試恢復分區表, 這樣可以避免人為錯誤, *本篇僅用於刪除 Windows*
> 如果您需要重新鎖定 Bootloader, 您的磁盤分區必須為原廠狀態, 且需要回到原廠固件

### 請先準備下面的文件
- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)
- [gpt_both0.bin](../../../../releases/tag/1.0)

### 還原 GPT 分區表
> 使用 gpt_both0.bin 路徑取代下面命令裏的 ```<gpt_both0.bin>```。
```cmd
fastboot flash partition:0 <gpt_both0.bin>
```

### 格式化 Userdata 分區以避免在啟動畫面卡住, 並還原 FS 大小
```cmd
fastboot -w
```