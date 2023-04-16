<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# 在 Xiaomi Pad 5 上執行 Windows

## 安裝

## 安裝 Windows

### 先決條件

- [Windows on ARM 映像](https://uupdump.net/)
- [UEFI 映像](../../../../releases/tag/1.0)
- [大型存放模式指令碼](../../../../releases/tag/1.0)
- [驅動程式更新程式](https://github.com/WOA-Project/DriverUpdater/releases/latest)
- [驅動程式](https://github.com/map220v/MiPad5-drivers)

### 開機回到 Recovery 以開始安裝 Windows

```cmd
fastboot boot <recovery.img>
```

#### 推入 msc 指令碼至 /sbin

```cmd
adb push msc.sh /sbin/
```

#### 執行 msc 指令碼

```cmd
adb shell sh /sbin/msc.sh
```

### 指派磁碟代號
  

#### 啟動 Windows 磁碟管理員

> 一旦 Xiaomi Pad 5 被偵測為一個磁碟

```cmd
diskpart
```


#### 指派 `X` 至 Windows 磁碟區

#### 選取平板電腦的 Windows 磁碟區
> 使用 `list volume` 以找到它，其名為「WINNABU」

```diskpart
select volume <number>
```

#### 指派代號 X
```diskpart
assign letter=x
```

### 指派 `Y` 至 ESP 磁碟區

#### 選取平板電腦的 ESP 磁碟區
> 使用 `list volume` 以找到它，其名為「ESPNABU」

```diskpart
select volume <number>
```

#### 指派代號 Y

```diskpart
assign letter=y
```

#### 離開 DiskPart
```diskpart
exit
```

  
  

### 安裝

> 使用實際 install.wim 路徑取代 `<path/to/install.wim>`，

> `install.wim` 位於您的 ISO 中的原始資料夾，可透過掛接或擷取取得

```cmd
dism /apply-image /ImageFile:<path/to/install.wim> /index:1 /ApplyDir:X:\
```

### 安裝驅動程式

> 以驅動程式資料夾位置取代 `<nabudriversfolder>`

```cmd
driverupdater.exe -d <nabudriversfolder>\definitions\Desktop\ARM64\Internal\nabu.txt -r <nabudriversfolder> -p X:
```

  

### 為 EFI 建立 Windows Bootloader 檔案

```cmd
bcdboot X:\Windows /s Y: /f UEFI
```

  
  

### 允許未簽署的驅動程式

> 如果您不這樣做，將會出現藍色當機畫面

```cmd
bcdedit /store Y:\EFI\Microsoft\BOOT\BCD /set {default} testsigning on
```


## 開機至 Windows

### 為您的現有 Boot 映像製作備份

```cmd
adb shell "dd if=/dev/block/bootdevice/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/boot.img"
```

### 提取備份至電腦

```cmd
adb pull /tmp/boot.img
```

### 重新開機至 Bootloader

```cmd
adb reboot bootloader
```

### 從 TWRP 刷新 UEFI 映像

```cmd
fastboot flash boot boot-nabu.img
```

### 開機回到 Android
> 使用您的備份開機映像並從 Fastboot 刷新

```cmd
fastboot flash boot boot.img
```

## 完成！
