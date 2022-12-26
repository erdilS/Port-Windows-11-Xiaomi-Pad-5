This step is required so that we make partitions where our Windows installation will be

## Notes:
> **Warning** if you delete any partitions via diskpart later on or now windows will send a ufs command that gets misinterpreted which erase all your ufs
- All your data will be erased! Backup now if needed.
- These commands have been tested.
- Ignore `udevadm` warnings
- Do not run the same command twice
- On TWRP, screen not working.
- DO NOT REBOOT YOUR PHONE if you think you made a mistake, ask for help in the [Telegram chat](https://t.me/nabuwoa)

#### Boot TWRP recovery through the PC with the command
```cmd
fastboot boot <twrp.img>
```
> If you already have TWRP installed, just hold the power and vol+ buttons at startup

#### Unmount all partitions
```cmd
adb shell twrp unmount /data
```

## Push parted to /tmp/
> For reparting the partitions
```cmd
adb push parted /tmp/
```

## Start the ADB shell
```cmd
adb shell
```

### Resize the partition table
> So that the Windows partitions would fit
```sh
sgdisk --resize-table 64 /dev/block/sda
```

### Fixing parted permissions
```sh
chmod 755 /tmp/parted
```

### Start parted
```sh
/tmp/parted /dev/block/sda
```


### Delete the `userdata` partition
> You can make sure that 31 is the userdata partition number by running
>  `print all`
```sh
rm 31
```

### Create partitions
> If you get any warning message telling you to ignore or cancel, just type i and enter

#### For 128Gb models: If you have 128 GB model, please contact me on [Telegram chat](https://t.me/nabuwoa)


#### For 256Gb models:

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


### Make ESP partiton bootable so the EFI image can detect it
```sh
set 31 esp on
```

### Quit parted
```sh
quit
```

### Reboot to TWRP

### Start the shell again on your PC
```cmd
adb shell
```

### Format partitions
-  Format the ESP partiton as FAT32
```sh
mkfs.fat -F32 -s1 /dev/block/bootdevice/by-name/esp -n ESPNABU
```

-  Format the Windows partition as NTFS
```sh
mkfs.ntfs -f /dev/block/bootdevice/by-name/win -L WINNABU
```

-  Format the userdata
```sh
mke2fs -t ext4 /dev/block/bootdevice/by-name/userdata
```

### Check if Android still starts
just restart the phone, and see if Android still works


## [Next step: Install Windows](/guide/English/2-install-en.md)
