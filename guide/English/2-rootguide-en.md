<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Running Windows on the Xiaomi Pad 5

## Rooting your tablet
> [!NOTE]
> **If you are already rooted just skip this step and go to the next page**

### Prerequisites
- ```Brain```

- [```Magisk.apk```](https://github.com/topjohnwu/Magisk/releases/latest)

### Flash magisk 
- Download [`magisk.apk`](https://github.com/topjohnwu/Magisk/releases/latest)
 to your PC/Laptop 
> Replace `path\to\magisk.apk` with the actual path of the magisk.apk
```cmd
adb push path\to\magisk.apk /tmp && adb shell twrp install /tmp/magisk.apk
```

### Reboot into Android
> If it doesn't, boot into stock recovery and perform a **factory reset** there
```cmd
adb reboot
```

### Set up your Android
- Just setup your Android as usual, connect to Wi-Fi etc

### Finishing setup
- Download and install [Magisk app](https://github.com/topjohnwu/Magisk/releases/latest) on the tablet
- Open the **Magisk** app again.
- Follow the instructions on the screen, and your device should reboot after a few seconds.

### [Next step: Installing Windows](/guide/English/3-install-en.md)

