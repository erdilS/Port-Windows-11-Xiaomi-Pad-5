<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Running Windows on the Xiaomi Pad 5

## Installation

### Prerequisites
- ```Unlocked bootloader``` - (If your bootloader is locked and you don't know how to unlock it use [this](unlock-bootloader-en.md) guide)

-  ```Brain```

- ```Windows 10(or higher) PC/Laptop```

- [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools)

- [```Modified recovery image```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

### Notes:
> [!NOTE]
> You can use any Android for dualboot - MIUI/Hyper OS or any custom ROM

> [!Warning]
> All your data will be erased! Back up now if needed.
> 
> DO NOT REBOOT YOUR TABLET if you think you made a mistake, ask for help in the [Telegram chat](https://t.me/nabuwoa)

### Opening CMD as an administrator
> [!NOTE]
> Don't know how to start? Unzip the downloaded [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools), then open ```command prompt``` as an administrator and run the following command, replacing `"path\to\platform-tools"` with the actual path of the platform tools folder
```cmd
cd "path\to\platform-tools"
```
> Use this window throughout the entire guide. Do not close it.

> [!Note]
> If your device is not detected in fastboot or recovery mode, you'll have to install USB drivers [using this guide](troubleshooting-en.md#device-is-not-recognized-in-fastboot-or-recovery)

#### Reboot into fastboot mkde
- Boot your NABU into **fastboot mode** by holding down the **`volume down`** button while rebooting with a USB cable connected
- Alternatively, run the below command while booted in Android
```cmd
adb reboot bootloader
```

### Boot the modded recovery
> While in fastboot mode, replace `path\to\recovery.img` with the actual path of the recovery image
```cmd
fastboot boot path\to\recovery.img
```

### Partitioning your device
> Replace **$** with the amount of storage you want Windows to have (do not add GB, just write the number)
> 
> If it asks you to run it once again, do so
```sh
adb shell partition $
```

### Make a backup of your existing boot image
```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/normal_boot.img" && adb pull /tmp/normal_boot.img
```

#### Check if Android still starts
> Reboot to check if Android still works.
```cmd
adb reboot
```

> [!NOTE]
> If it doesn't boot into Android, reboot into fastboot mode and run `fastboot -w`, or boot into stock recovery and perform a **factory reset**

### [Next step: Rooting your device](/guide/English/2-rootguide-en.md)
