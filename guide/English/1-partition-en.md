<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Running Windows on the Xiaomi Pad 5

## Installation

### Partitioning your device

### Prerequisites

- [Recovery Image](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)

### Notes:
> **Warning** if you delete any partitions via diskpart later on or now windows will send a ufs command that gets misinterpreted which erase all your ufs
- All your data will be erased! Backup now if needed.
- These commands have been tested.
- Ignore `udevadm` warnings
- Do not run the same command twice
- On recovery, screen not working.
- DO NOT REBOOT YOUR TABLET if you think you made a mistake, ask for help in the [Telegram chat](https://t.me/nabuwoa)


#### ⚠️ Do not run all commands at once, execute them in order!

##### ⚠️ DO NOT MAKE ANY MISTAKE!!! YOU CAN BREAK YOUR DEVICE WITH THE COMMANDS BELOW IF YOU DO THEM WRONG!!!


#### Boot recovery through the PC with the command
```cmd
fastboot boot <recovery.img>
```
> If you already have TWRP installed, just hold the power and vol+ buttons at startup

#### Start ADB shell
```cmd
adb shell
```

#### Resize the partition table
> So that the Windows partitions can fit
```sh
sgdisk --resize-table 64 /dev/block/sda
```

#### Start parted
```sh
parted /dev/block/sda
```

#### Delete the `userdata` partition
> You can make sure that 31 is the userdata partition number by running
>  `print all`
```sh
rm 31
```

#### Create partitions
> If you get any warning message telling you to ignore or cancel, just type i and enter


<details>
<summary><b><strong>For 128GB models</strong></b></summary>

- Create the ESP partition (stores Windows bootloader data and EFI files)
```sh
mkpart esp fat32 10.9GB 11.4GB
```

- Create the main partition where Windows will be installed to
```sh
mkpart win ntfs 11.4GB 70.2GB
```

- Create Android's data partition
```sh
mkpart userdata ext4 70.2GB 126GB
```
  </summary>
</details>

<details>
<summary><b><strong>For 256GB models</strong></b></summary>

- Create the ESP partition (stores Windows bootloader data and EFI files)
```sh
mkpart esp fat32 10.9GB 11.4GB
```

- Create the main partition where Windows will be installed to
```sh
mkpart win ntfs 11.4GB 120.8GB
```

- Create Android's data partition
```sh
mkpart userdata ext4 120.8GB 254GB
```

  </summary>
</details>


#### Make ESP partiton bootable so the EFI image can detect it
```sh
set 31 esp on
```

#### Quit parted
```sh
quit
```
#### Reboot to bootloader
```sh
reboot bootloader
```

#### Boot to recovery
```cmd
fastboot boot <recovery.img>
```

#### Start adb shell again
```cmd
adb shell
```

#### Format partitions
-  Format the ESP partiton as FAT32
```sh
mkfs.fat -F32 -s1 /dev/block/bootdevice/by-name/esp -n ESPNABU
```

-  Format the Windows partition as NTFS
```sh
mkfs.ntfs -f /dev/block/bootdevice/by-name/win -L WINNABU
```

-  Format userdata
```sh
mke2fs -t ext4 /dev/block/bootdevice/by-name/userdata
```


#### Check if Android still starts
just restart the phone, and see if Android still works
If isn't boot or looping or animation, use MIUI recovery or other recoveries for wiping data.

### [Next step: Installing Windows](/guide/English/2-install-en.md)
