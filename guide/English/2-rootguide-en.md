<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Running Windows on the Xiaomi Pad 5

## Rooting your tablet
> [!NOTE]
> **If you are already rooted, skip this step and go to the next page**

### Prerequisites
- ```Brain```

- [```Magisk.apk```](https://github.com/topjohnwu/Magisk/releases/latest)

### Flash magisk 
- Download [`magisk.apk`](https://github.com/topjohnwu/Magisk/releases/latest) onto your PC/Laptop 
> Replace `path\to\magisk.apk` with the actual path of the magisk.apk
```cmd
adb push path\to\magisk.apk /tmp/magisk.zip && adb shell twrp install /tmp/magisk.zip
```

#### Reboot into Android
> If it doesn't boot, renoot into stock recovery and perform a **factory reset** there
```cmd
adb reboot
```

### Finishing setup
- Set up your device, then download and install [Magisk](https://github.com/topjohnwu/Magisk/releases/latest), if it isn't already installed.
- Open the **Magisk** app and follow the instructions on the screen, and your device should reboot after a few seconds.

### Back up your rooted boot.img
> Reboot into the modified recovery image, then run the below command
```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/rooted_boot.img" && adb pull /tmp/rooted_boot.img
```

### [Next step: Installing Windows](/guide/English/3-install-en.md)





































