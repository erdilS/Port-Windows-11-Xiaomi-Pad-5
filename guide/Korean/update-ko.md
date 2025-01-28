<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Xiaomi Pad 5 에서 윈도우 구동

## 드라이버 업데이트

### 준비물
- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)

- [맞춤화된 리커버리 이미지](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [UEFI 이미지](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/UEFI)

- [드라이버](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/Drivers)

### Boot back into the modded recovery
> Replace `path\to\recovery.img` with the actual path of the recovery image
```cmd
fastboot boot path\to\recovery.img
```

#### Execute the msc script
> If it asks you to run it once again, do so
```cmd
adb shell msc
```

### Diskpart
```cmd
diskpart
```

#### Select the Windows volume of the tablet
> Use `list volume` to find it, replace "$" with the actual number of **WINNABU**
```diskpart
select volume $
```

#### Assign the letter X
```diskpart
assign letter x
```

#### Exit diskpart
```diskpart
exit
```

### 드라이버 설치
> [!Note]
> This process will take +- 20 minutes. Do not worry, this is normal.

- Unpack the driver archive, then open the `OfflineUpdater.cmd` file (if an error shows up, run `OfflineUpdaterFix.cmd` instead)

> If it asks you to enter a letter, enter the drive letter of **WINNABU** (which should be **X**), then press enter

#### Reboot your device
> Make sure to also change the UEFI image in Android, otherwise you may face a "blue screen of death" (BSoD) when booting Windows later.
```cmd
adb reboot
```

## 끝!












