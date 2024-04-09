<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Running Windows on the Xiaomi Pad 5

## Troubleshooting Issues

## I can't move files to the Windows folder from Android 

If you are unable to move files to the Windows folder, it means you shut down Windows instead of restarting it. To fix this issue, boot back to Windows and use restart, then as it restarts boot to fastboot and use it to return to Android

##### Done!

## Charging in Windows does not work
> [!WARNING]
> Do not use a powered USB hub with host mode enabled, this can potentially break your device. If you use a powered USB hub, please use the [disable USB host mode guide](/guide/English/Additional-materials-en.md#Disabling-USB-host-mode)

Charging in Windows only works on specific cables. Cables that have been known to work are the original Poco X3 Pro cable (identified by the additional orange/red pin in the USB-A port), and the Nimaso 100W USB-C to USB-C fast charging cable.

##### Done!

## Device can boot into Android but not bootloader

### Prerequisites:
- [Android platform tools](https://developer.android.com/studio/releases/platform-tools)

- [SHRP Recovery](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/SHRP.img)

> [!Important]
> This will only work if you are rooted. If you aren't, the only way to recover is to flash your device with EDL using [MrAuthTool](https://mrauthtool.com/)

- Remove the **UEFI** image from the UEFI folder in your internal storage, then place the **SHRP recovery** image here
- Press `QUICKBOOT TO WINDOWS` in the WOA Helper app
- Once booted into the recovery, connect your device to your PC and run:
```cmd
adb shell parted /dev/block/sda
```
- Run ```print``` to list all partitions
- Look for partitions that have spaces in the names e.g "Basic Data Partition" and note their volume number
- Remove this partition with ```rm $```, replacing **$** with the volume number
- Run ```quit```
- Run ```adb reboot bootloader```, and when you see the **FASTBOOT** logo on your screen, flash your Android boot image with ```fastboot flash boot_a path\to\boot.img```
- You may have to do the same for **boot_b** if your device does not boot, or if it boots back to the recovery

> [!Note]
> Make sure you replace the recovery image in the UEFI folder with the UEFI file again

##### Done!

## fsa4480.sys BSOD on boot
- Open driver folder

- Remove the ```<DriverPackageFile Path="$(mspackageroot)\components\QC8150\Device\DEVICE.SOC_QC8150.NABU\Drivers\USB" Name="fsa4480.inf" ID="fsa4480"/>``` line from NABU.xml

- Reinstall the driver

- Boot UEFI
> [!NOTE]
> If you are still getting a BSOD, use the `reinstall` guide and use this driver package 

##### Done!

## Bootloop after switching to Android 
- Boot to fastboot

- ```fastboot set_active other```

- ```fastboot flash boot <boot.img>```

- ```fastboot reboot```

##### Done!

















