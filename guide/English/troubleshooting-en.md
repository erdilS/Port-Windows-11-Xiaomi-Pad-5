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

## Enabling fast charging and enabling USB host mode

> **Warning!** Please plug the charger in before boot otherwise the tablet will not charge at all in windows, also please do not unplug the charger or rles the device wont charge unless you reboot and you have the charger plugged in.

> C to C charging with a PD supported device has been confirmed working and the 33W charger provided by xiaomi is also confirmed to be working


- Flash this [UEFI](https://github.com/kmille36/TempStorage/blob/main/xiaomi-nabu.img?raw=true) by using ```fastboot flash boot xiaomi-nabu.img```

- Update to latest [Drivers](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/blob/main/guide/driver-updating-selection.md)

- Modifying the following value in regedit ```Computer\HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Enum\ACPI\QCOM0597\0\Device Parameters\RoleSwitchMode``` change the value from 3 to 1 

- Restart Windows!

## I have disabled test mode and now my tablet will not boot into windows

- Take a good look at yourself

- Realise how much of a dissapointment you are

- Follow whats below

- Boot the recovery image with ```fastboot boot <recovery.img>```

- Push the mass storage script with ```adb push msc.sh /sbin/```

- Run the mass storage script with ```adb shell sh /sbin/msc.sh```

- Open cmd as admin

- Type ```diskpart``` to start diskpart (shocker)

- Find the ESP Volume with ```list volume```, i should be the one named ESPNABU

- Select the esp volume with ```select volume <number>```

- Assign the letter with ```assign letter=y```

- Exit diskpart with ```exit```

- Run this command to re enable testmode ```bcdedit /store Y:\EFI\Microsoft\BOOT\BCD /set {default} testsigning on```

- Reboot the tablet into bootloader and boot your UEFI image and windows should boot
