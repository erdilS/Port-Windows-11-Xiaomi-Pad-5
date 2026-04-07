<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Running Windows on the Xiaomi Pad 5

## Reinstallation
If you don't like your Windows version or you've bricked your Windows install, or anything else, you would probably just reinstall Windows. Thankfully this process is very easy.

> [!IMPORTANT]
> Quite obviously, this will erase all of your Windows files. If you'd like to back up any of them, you can do so by mounting Windows using the [WOA Helper](https://github.com/n00b69/woa-helper/releases/tag/APK) app and manually copying any files you wish to keep

> [!Warning]
> Make sure you have Android boot.img flashed before proceeding, if you have uefi.img flashed and don't have boot.img backup of your current Android ROM, you may need to extract it from your ROM package, if you're on HyperOS/MIUI, you can download rooted via magisk with TWRP inbuilt boot.img for your version of HyperOS/MIUI [Here](https://github.com/ArKT-7/nabu/releases/tag/Nabu-boot-with-twrp)

### Prerequisites
- ```Existing Windows and boot partitions``` (*If not met, [go back and just pretend this guide never existed](/guide/English/1-partition-en.md)*)

- [```Recovery Image```](https://github.com/ArKT-7/twrp_device_xiaomi_nabu/releases/tag/mod-win)

- [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools)

#### Reboot into fastboot mode
- Boot your NABU into **fastboot mode** by holding down the **`volume down`** button while rebooting with a USB cable connected
- Or, if you have USB debugging enabled, run the below command while booted into Android.
```cmd
adb reboot bootloader
```

### Boot modified recovery
> Replace `path\to\recovery.img` with the actual path of the modded recovery image
```cmd
fastboot boot path\to\recovery.img
```

### Back up your boot.img
```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/rooted_boot.img" && adb pull /tmp/rooted_boot.img
```

### Format the partitions
> If it asks you to run it once again, do so
```cmd
adb shell format
```

## [Next step: Reinstalling Windows](/guide/English/3-install-en.md)
