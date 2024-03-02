<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Running Windows on the Xiaomi Pad 5

## Troubleshooting Issues

## Charging in Windows does not work
> [!WARNING]
> Do not use a powered USB hub with host mode enabled, this can potentially break your device. If you use a powered USB hub, please use the [disable USB host mode guide](/guide/English/Additional-materials-en.md#disabling-usb-host-mode)

Charging in Windows only works on specific cables. Cables that have been known to work are the original Poco X3 Pro cable (identified by the additional orange/red pin in the USB-A port), and the Nimaso 100W USB-C to USB-C fast charging cable.


## Device can boot into Android but not bootloader

### Prerequisites:

- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)

> [!WARNING]
 Probably these steps won't help you because Xiaomi Pad 5 doesn't have a fully working custom recovery to flash it to device. Also like most of newer A/B devices we don't have a TWRP Installer zip etc. and you can't boot existing recovery image because of broken fastboot. If you have already installed AOSP rom, probably it has a preinstalled AOSP recovery and you can boot it directly, so you can follow these steps. If you have unrooted MIUI, this steps won't help you.
>
> So please avoid to use disk labels which contains spaces and special characters, and if it is possible just use ESPNABU and WINNABU labels which are tested for a million times. If you brick fastboot with disk labels and you have unrooted MIUI, you have to flash rom via EDL with authorized account and you have to pay for it.


This is caused by partitions with volume names the bootloader cannot handle, to fix this:

- Boot to recovery

- Connect tablet to PC

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


## Bootloop after switching to Android 

- Run fastboot

- ```fastboot set_active other```

- ```fastboot flash boot <boot.img>```

- ```fastboot reboot```
