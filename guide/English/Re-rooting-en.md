<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Running Windows on the Xiaomi Pad 5

## Re-rooting Android
This section will guide you through the re-rooting process for when MIUI/Hyper OS updates and removes root.

### Prerequisites
- [```Recovery Image```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)
  
- [```Android Platform Tools```](https://developer.android.com/studio/releases/platform-tools)

- [```Magisk.apk```](https://github.com/topjohnwu/Magisk/releases/latest)
  
### Reboot to **fastboot** 
- Boot your NABU into **fastboot** by holding down the **`volume down`** button during reboot

- Connect it to your PC/Laptop using a cable

### Boot the modded recovery
> While in fastboot mode, replace `path\to\recovery.img` with the actual path of the recovery image
```cmd
fastboot boot path\to\recovery.img
```

### Flash magisk 
- Download [`magisk.apk`](https://github.com/topjohnwu/Magisk/releases/latest) onto your PC/Laptop 
> Replace `path\to\magisk.apk` with the actual path of the magisk.apk
```cmd
adb push path\to\magisk.apk /tmp/magisk.zip && adb shell twrp install /tmp/magisk.zip
```

#### Reboot into Android
> If it doesn't boot, reboot manually by press and hold power button
```cmd
adb reboot
```

### Finishing setup
- Set up your device, then download and install [Magisk](https://github.com/topjohnwu/Magisk/releases/latest), if it isn't already installed.
- Open the **Magisk** app and follow the instructions on the screen, and your device should reboot after a few seconds.


### Update boot.img in Windows' C:\
- Reboot back to Android
- Open ```WOA Helper```
- Click ```BACKUP BOOT IMAGE``` > ```Windows```
- Done

## Finished!















