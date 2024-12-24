<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Running Windows on the Xiaomi Pad 5

## Rooting your tablet
> [!NOTE]
> **If you are already rooted just skip this step and go to the next page**

### Prerequisites
- ```Brain```
  
- [```Modified recovery image```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [```Magisk app```](https://github.com/topjohnwu/Magisk/releases/latest)

### Install magisk app
- Just install downloaded [Magisk app](https://github.com/topjohnwu/Magisk/releases/latest) on the tablet

### Reboot into fastboot
```cmd
adb reboot bootloader
```

### Boot the modded recovery again
> Replace `path\to\recovery.img` with the actual path of the recovery image
```cmd
fastboot boot path\to\recovery.img
```

### Flash magisk 
- Download [`magisk.apk`](https://github.com/topjohnwu/Magisk/releases/latest)
 to your PC/Laptop 
> Replace `path\to\magisk.apk` with the actual path of the magisk.apk
```cmd
adb push path\to\magisk.apk /tmp && adb shell twrp install /tmp/magisk.apk
```

### Reboot into Android
```cmd
adb reboot
```

### Finishing setup
- Open the **Magisk** app again.
- Follow the instructions on the screen, and your device should reboot after a few seconds.

### [Next step: Installing Windows](/guide/English/3-install-en.md)

