<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Running Windows on the Xiaomi Pad 5

## Uninstallation

### Why is this needed?

If you want to uninstall windows this is used instead of deleting partitions manually to avoid human error + writing a whole dedicated guide to just uninstalling.

If you want to relock your bootloader you'll need your partition table to be stock.

### Prerequisites

- [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools)
  
- [```Recovery Image```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

#### Boot the modded recovery
```cmd
fastboot boot <recovery.img>
```

#### Restore the partition layout
> [!Warning]
> This will wipe your Android files. Backup first if needed.
```cmd
adb shell restore
```

### Reboot to Android 
```cmd
adb reboot 
```
## Done!
