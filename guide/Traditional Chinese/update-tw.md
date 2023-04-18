<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# 在 Xiaomi Pad 5 上執行 Windows

## 驅動程式更新

### 先決條件

- [UEFI](../../../../releases/tag/1.0)
- [大型存放模式指令碼](../../../../releases/tag/1.0)
- [TWRP](../../../../releases/tag/1.0)
- [驅動程式更新程式](https://github.com/WOA-Project/DriverUpdater/releases/latest)
- [驅動程式](https://github.com/map220v/MiPad5-Drivers)

#### 透過電腦命令列啟動 Recovery

```cmd
fastboot boot <recovery.img>
```

#### 推入指令碼

```cmd
adb push msc.sh /sbin/
```

#### 執行指令碼

```cmd
adb shell msc.sh
```

### 指派代號至磁碟

#### 啟動 Windows 磁碟管理員

> 一旦 Xiaomi Pad 5 被偵測為一個磁碟

```cmd
diskpart
```


### 指派 `X` 至 Windows 磁碟區

#### 選取平板電腦的 Windows 磁碟區
> 使用 `list volume` 以找到它，其名為「WINNABU」

```diskpart
select volume <number>
```

#### 指派代號 X
```diskpart
assign letter=x
```

#### 離開 Diskpart
```diskpart
exit
```


### 安裝驅動程式

> 以驅動程式資料夾位置取代 `<nabudriversfolder>`

> 以系統管理員身分開啟 CMD


```cmd
DriverUpdater.exe -d <nabudriversfolder>\definitions\Desktop\ARM64\Internal\nabu.txt -r <nabudriversfolder> -p X:
```


### 以可開機至 Windows 的 UEFI 映像開機

```
fastboot flash boot <uefi.img>
```

## 完成！
