<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Running Windows on the Xiaomi Pad 5

## Troubleshooting Issues


## Device can boot into android but not bootloader

### Prerequisites:

- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)

> **Warning** Probably these steps won't help you because Xiaomi Pad 5 doesn't have a fully working custom recovery to flash it to device. Also like most of newer A/B devices we don't have a TWRP Installer zip etc. and you can't boot existing recovery image because of broken fastboot. If you have already installed AOSP rom, probably it has a preinstalled AOSP recovery and you can boot it directly, so you can follow these steps. If you have unrooted MIUI, this steps won't help you.

> So please avoid to use disk labels which contains spaces and special characters, and if it is possible just use ESPNABU and WINNABU labels which are tested for a million times. If you brick fastboot with disk labels and you have unrooted MIUI, you have to flash rom via EDL with authorized account and you have to pay for it.


This is caused by partitions with volume names the bootloader cannot handle, to fix this:

- Boot to recovery

- Connect phone to PC

- Open cmd on PC

- Run ```adb shell```

- Run ```parted```

- Run ```print``` to list all partitions

- Look for partitions that have spaces in the names e.g "Basic Data Partition" and note their volume number

- Now run ```rm <vol number>``` e.g ```rm 99```


## fsa4480.sys BSOD on boot

- Open driver folder

- Remove the ```components\QC8150\Device\DEVICE.SOC_QC8150.NABU\Drivers\USB``` folder

- Reinstall the driver

- Boot UEFI

- After it boots, readd the driver and reinstall the driver again

## How to Charging and USB guide:

- Flash this UEFI into boot in fast boot mode: https://github.com/kmille36/TempStorage/blob/main/xiaomi-nabu.img?raw=true

- Update to latest Drivers: https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/blob/main/guide/driver-updating-selection.md

- Tested with C to C charging (with PD support), Xiaomi 33W charge work (already tested)

*You need to plug in charger before windows bootup, otherwise it will not charging... (please keep cable plugged in, if u unplug it will not charge until you shutdown windows and plug in charge before bootup).*

- Also USB type C Apdater work by modify value in Computer\HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Enum\ACPI\QCOM0597\0\Device Parameters (RoleSwitchMode 3 to 1). Then restart windows!

