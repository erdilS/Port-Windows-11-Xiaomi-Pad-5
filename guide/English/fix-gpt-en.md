<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Running Windows on the Xiaomi Pad 5

## Fix the GPT to use Windows 24H2 safely

### Prerequisites:
- [```Already installed Windows```](selection-en.md)

- [```Recovery image```](https://github.com/ArKT-7/twrp_device_xiaomi_nabu/releases/tag/mod-win)

- [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools)

> [!Important]
> If you want to use Windows 24H2 safely, these steps are required to avoid EDL issues.

> [!NOTE]
> Doing this will not affect your Android or Windows install.

### Reboot into fastboot mode
- Boot your NABU into **fastboot mode** by holding down the **`volume down`** button while rebooting with a USB cable connected
- Or, if you have USB debugging enabled, run the below command while booted into Android.
```cmd
adb reboot bootloader
```

### Boot into the modified recovery
> Replace `path\to\recovery.img` with the actual path of the downloaded **recovery.img**
```cmd
fastboot boot path\to\recovery.img
```

### Fixing the GPT
> Once booted into the recovery image
>
> If it asks you to run it again, do so
```cmd
adb shell fixgpt
```

### Reboot your device
```cmd
adb reboot
```

## ✅ Done! Windows 24H2 can now safely be used.























