<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Running Windows on the Xiaomi Pad 5

## Disabling secureboot
> [!Important]
> Follow this guide only if you want to disable secureboot.

### Prerequisites
- ```Brain```

- [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools)

- [```Recovery Image```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [```UEFI image (Secureboot off)```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-NoSecureboot-v3.img)

## Pros and cons of secureboot
> By default, secureboot is enabled in this guide

##### Pros and cons of secureboot
- √ No watermark on homescreen
- √ Apps that do not work with Test Mode will work
- √ You can update big versions (e.g 22h2 to 23h2) in Windows update directly
- × You cannot install unsigned drivers

##### Pros and cons of secureboot disabled
- √ You can install unsigned drivers
- × Test mode watermark on homescreen
- × Some apps/games with anti-cheat software may not work
- × You cannot update big versions (e.g 22h2 to 23h2) through Windows Update

## Disabling secureboot

#### Make a backup of your rooted boot image
> You will need this to return to Android, but you can skip this step if you've already made a backup

Use the `Backup Android boot` function in the WOA Helper app, or boot to the modded recovery and run
```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/rooted_boot.img" && adb pull /tmp/rooted_boot.img
```

#### Boot to the recovery
> Replace <path\to\recovery> with the actual path of the recovery image
```cmd
fastboot boot <path\to\recovery.img>
```

#### Activate mass storage mode
> Once the Xiaomi Pad 5 has booted into the modded recovery
```cmd
adb shell msc
```

#### Start the Windows disk manager
> Once the Xiaomi Pad 5 is detected as a disk
```cmd
diskpart
```

#### Select the esp volume of the tablet
> Use `list volume` to find it, it's the one named "ESPNABU"
```diskpart
select volume <number>
```

#### Assign the letter Y
```diskpart
assign letter y
```

#### Exit diskpart
```diskpart
exit
```

#### Modify the bootloader files
> To enable test signing
```cmd
bcdedit /store Y:\EFI\Microsoft\BOOT\BCD /set "{default}" testsigning on
```

#### Removing SiPolicy
> Assuming you are disabling secureboot on an existing install, you need to delete this file or the system will not boot
```cmd
del Y:\EFI\Microsoft\Boot\SiPolicy.p7b
```

#### Remove the drive letter for ESPNABU
> If this does not work, ignore it and skip to the next command. This phantom drive will disappear the next time you reboot your PC.
```cmd
mountvol y: /d
```

#### Reboot to fastboot
```cmd
adb reboot bootloader
```

#### Flashing the UEFI
> Make sure you use the no secureboot UEFI from this page, replace <path\to\uefi-NoSecureboot-v3.img> with the actual path to the UEFI image
```cmd
fastboot flash boot <path\to\uefi-NoSecureboot-v3.img>
```

> [!Important]
> Make sure to also replace your old UEFI in the UEFI folder in your internal storage of Android, so you don't accidentally flash it the next time you try to switch to Windows from Android

#### Reboot to Windows
```cmd
fastboot reboot
```

## Finished!



















