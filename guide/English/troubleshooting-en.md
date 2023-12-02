<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Running Windows on the Xiaomi Pad 5

## Troubleshooting Issues


## Device can boot into android but not bootloader

### Prerequisites:

- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)

> [!WARNING]
 Probably these steps won't help you because Xiaomi Pad 5 doesn't have a fully working custom recovery to flash it to device. Also like most of newer A/B devices we don't have a TWRP Installer zip etc. and you can't boot existing recovery image because of broken fastboot. If you have already installed AOSP rom, probably it has a preinstalled AOSP recovery and you can boot it directly, so you can follow these steps. If you have unrooted MIUI, this steps won't help you.
>
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

> [!WARNING]
>  Make sure any registry edits are done on the Mi Pad 5 itself

> [!NOTE]
> C to C charging with a PD supported device has been confirmed working and the 33W charger provided by Xiaomi is also confirmed to be working

 Download  [Script from Misha803](https://t.me/droidscripts/22)

## I have disabled test mode and now my tablet will not boot into Windows

> [!IMPORTANT]
>  Make sure you watch [This video](https://youtu.be/oHg5SJYRHA0) before attempting to do anything to avoid anymore trouble

- Take a good look at yourself

- Realise how much of a disappointment you are

- Follow whats below

- Boot the recovery image with ```fastboot boot <recovery.img>```

- Push the mass storage script with ```adb push msc.sh /sbin/```

- Run the mass storage script with ```adb shell sh /sbin/msc.sh```

- Open cmd as admin

- Type ```diskpart``` to start diskpart (shocker)

- Find the ESP Volume with ```list volume```, i should be the one named ESPNABU

- Select the ESP volume with ```select volume <number>```

- Assign the letter with ```assign letter=y```

- Exit diskpart with ```exit```

- Run this command to re enable testmode ```bcdedit /store Y:\EFI\Microsoft\BOOT\BCD /set {default} testsigning on```

- Reboot the tablet into bootloader and boot your UEFI image and Windows should boot

## Bootllop after switching to Android 

> Run fastboot

> fastboot set_active other

-fastboot flash boot <boot.img>

-fastboot reboot
