<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# 在 Xiaomi Pad 5 上安裝 Windows

## 更新驅動文件

### 請先準備下面的步驟

- [```Recovery```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)
  
- [```UEFI boot 映像```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v3.img)
  
- [```驅動文件```](https://github.com/map220v/MiPad5-Drivers/releases/latest)

### 請進入 Fastboot 模式, 並輸入以下命令來啟动到 Recovery
```cmd
fastboot boot <recovery.img>
```

#### 執行 msc 模式腳本
> 如果腳本提示您需要重新運行一次, 請重新執行下面的命令
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
> 您可以下载驱动程序[这里](https://github.com/map220v/MiPad5-Drivers/releases/latest)

> 如果它寫入 `"Automatic WINNABU detection failed! Enter Drive Letter manually"`，則鍵入 **`X`** 
```cmd
打开带有驱动程序的文件夹并运行 OfflineUpdater.cmd
```

### 重啟到 Bootloader
> 或者，如果您的 UEFI 已經刷新，只需使用 ```adb reboot``` 重新啟動即可
```cmd
adb reboot bootloader
```

### 刷入 UEFI boot 鏡像到當前激活的 slot
> 將 <uefi.img> 替換為 UEFI 映像的實際路徑
```cmd
fastboot flash boot <uefi.img>
```

## 完成
