<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# 在 Xiaomi Pad 5 上安裝 Windows

## 更新驅動文件

### 請先準備下面的步驟
- [UEFI boot 映像](../../../../releases/tag/1.0)
- [TWRP](../../../../releases/tag/1.0)
- [驅動更新工具](https://github.com/WOA-Project/DriverUpdater/releases/latest)
- [驅動文件](https://github.com/map220v/MiPad5-Drivers)

### 請進入 Fastboot 模式, 並輸入以下命令來啟动到 Recovery
```cmd
fastboot boot <recovery.img>
```

#### 執行 msc 模式腳本
```cmd
adb shell msc
```

### 重新分配驅動器號

#### 啟動 Windows 磁碟管理員
> 請確認您的 Xiaomi Pad 5 被 Windows 識別為磁碟
```cmd
diskpart
```

#### 確認分區掛載情況
> 如果「WINNABU」分區已經被掛載在 X, 那麽請直接退出 Diskpart 並繼續

#### 選中平板上的 Windows 分區
> 使用 `list volume` 以找到名為「WINNABU」的分區
```diskpart
select volume <number>
```

#### 分配 Windows 分區到 `X` 盤
> 如果您遇到錯誤「指定的磁碟機代號已在使用中，因此無法指定」, 請重啟您的電腦 (不是平板電腦) 並打開 Diskpart 再試一次
```diskpart
assign letter=x
```

#### 離開 Diskpart
```diskpart
exit
```

### 安裝驅動程式
> 以解壓出來的驅動文件夾位置取代 `<nabudriversfolder>`
```cmd
DriverUpdater.exe -d <nabudriversfolder>\definitions\Desktop\ARM64\Internal\nabu.txt -r <nabudriversfolder> -p X:
```

### 重啟到 Bootloader
```cmd
adb reboot bootloader
```

### 刷入 UEFI boot 鏡像到當前激活的 slot
```cmd
fastboot flash boot <UEFI.img>
```

## 完成
