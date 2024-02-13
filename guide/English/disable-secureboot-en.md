<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Running Windows on the Xiaomi Pad 5

## Disabling secureboot
> [!Important]
> Follow this guide only if you want to disable secureboot.

### Prerequisites
- ```Brain```

- [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools)

- [```Recovery Image```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [```UEFI image (Secureboot off)```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-noSB-v2.img)

## Pros and cons of secureboot
> By default, secureboot is enabled in this guide

##### Pros of secureboot
- No watermark on homescreen
- Apps that do not work with Test Mode will work

##### Cons of secureboot
- Watermark on homescreen
- PC is required to update drivers
- SOME applications may not run due to Test Mode

## Disabling secureboot

#### Make a backup of your rooted boot image
> You will need this to return to Android, but you can skip this step if you've already made a backup

Use the `Backup Android boot` function in the WOA Helper app, or boot to fastboot and run

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
bcdedit /store Y:\EFI\Microsoft\BOOT\BCD /set {default} testsigning on
```

#### Removing SiPolicy
> Assuming you are disabling secureboot on an existing install, you need to delete this file or the system will not boot

SiPolicy.p7b in esp:/EFI/Microsoft/Boot/

#### Removing disk letters
> So that phantom drives don't stay there after disconnecting the tablet. If it does not work, you can skip this step. These phantoms drives will disappear after rebooting your PC

#### Reboot to fastboot
```cmd
adb reboot bootloader
```

#### Flashing the UEFI
> Make sure you use the no secureboot UEFI from this page, replace <path\to\uefi-noSB-v2.img> with the actual path to the UEFI image
```cmd
fastboot flash uefi <path\to\uefi-noSB-v2.img>
```

#### Reboot to Windows
```cmd
fastboot reboot
```

## Finished!



















