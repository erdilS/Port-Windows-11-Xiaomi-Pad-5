<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Running Windows on the Xiaomi Pad 5

## Re-rooting Android

This section will guide you through the re-rooting process for when MIUI updates and removes root.

### Prerequisites
- [```Recovery Image```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)
  
- [```Android Platform Tools```](https://developer.android.com/studio/releases/platform-tools)

### Start recovery through the PC with the command
```cmd
fastboot boot <recovery.img>
```

### Make a backup of your existing boot image
```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/normal_boot.img" && adb pull /tmp/normal_boot.img
```

### Reboot back to Android
```cmd
adb reboot
```

### Patch boot 

- Copy the ```normal_boot.img``` file from the ```platform tools``` folder onto the tablet 

-  Open the Magisk app and click the ```Install``` button. Select ```Select and Patch a File``` option and find the ```normal_boot.img``` file that you copied to the tablet. Click the ```Let's Go``` button and wait for the patching process to complete.
  
- Copy the ```magisk_patched....img``` file from the ```Downloads``` folder on the tablet to the ```platform tools``` folder on your computer. 

- Reboot to fastboot
  
- Open command prompt in the platform tools folder 

### Flash patched boot 
 > Replace `<magisk_patched.img>` with the actual ```magisk_patched.img``` name/path.
```cmd
fastboot flash boot <magisk_patched.img>
```

### Update boot.img in Windows' C:\

- Reboot back to Android

- Open ```WOA Helper```

- Mount ```Windows```

- Open any file explorer and go to the ```Windows```  folder.

- Delete ```boot.img```

> [!NOTE]
> **The updated boot.img will automatically be generated in C:\ on the next reboot**

## Done
