<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Running Windows on the Xiaomi Pad 5

## Resizing Windows partition after installation 

### Prerequisites
- ```Windows installed on nabu```

-  ```Brain```

- [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools)

- [```Modified recovery image```](https://github.com/ArKT-7/twrp_device_xiaomi_nabu/releases/tag/mod-win)

- [```Diskgenius app installed on your nabu```](https://www.diskgenius.com/download.php)

### Notes:
> [!Warning]
> These actions will cause wipe of all **Android** data so make a backup if needed, windows data will be kept!
> 
> DO NOT REBOOT YOUR TABLET if you think you made a mistake, ask for help in the [Telegram chat](https://t.me/nabuwoa)

### Flashing latest modded twrp:

#### Reboot to Android (using StA.exe)
- Flash your android boot.img (Reboot to Android) by running StA.exe shortcut on your desktop

#### Reboot into fastboot mode
- Boot your NABU into **fastboot mode** by holding down the **`volume down`** button while rebooting with a USB cable connected

#### Boot latest modded twrp
> Use platform tools cmd (you can open it by opening platform tools folder in explorer and typing `cmd` in explorer path)
> While in fastboot mode, replace `path\to\recovery.img` with the actual path of the recovery image
```cmd
fastboot boot "path\to\recovery.img"
```

#### Flash modded twrp you just booted 
Go to **`Advanced`** tab - **`Flash current twrp`** option 

#### Reboot
```cmd
adb reboot
```
> Alternatively use **`Reboot`** - **`System`** option in twrp

### Deleting userdata and resizing windows partition:
#### Reboot to Windows 
- Use **`QuickBoot`** button in WOA Helper app

#### Delete userdata
> [!WARNING]
> Do not delete/modify any other partition than that one described in the steps below!
> If you have any questions etc on this step please ask in [Telegram chat](https://t.me/nabuwoa) to avoid bricking your device

- Open **`Windows Disk Management`** app
- Find the big partition at the **end of drive 0** - userdata
- Delete it
- Add some GB you want to Windows partition by using **`Extend Volume`** option

### Creating new userdata and renaming it correctly:
#### Create new userdata using DiskGenius app
- Download and install DiskGenius app, then Open it
- Click **`Partition`** at the top - **`Create New Partition(N)`**
- Use Free space left to create new partition

#### Rename partition you just created
> [!IMPORTANT]
> This step is very important as by default Windows names the partition "Basic Data Partition", which contains spaces - This breaks fastboot!
- Select partition you just created (new userdata partition) from partitions list/blocks
- Click **`Partition`** at the top - **`Modify Partition Parameters(F11)`** 
- In **`Partition Name`** field carefully type **`userdata`**
- Click **`Ok`** - **`Yes`**
- Close DiskGenius app

#### Save changes
- Click **`Save All`** button from top panel
- Click **`Yes`** in the dialog

### Rebooting to Android and formatting data:
- Use StA.exe to reboot to Android
- When mi logo appears press and hold **`Volume +`** button to boot twrp you flashed earlier
- In twrp go to **`Wipe`** - **`Format Data`** - type **`Yes`**
- Go to **`Reboot`** - **`System`**
> If you couldn't format data via twrp you can use **`fastboot -w`** command in fastboot (connect nabu in fastboot to your PC and run this command via platform tools cmd)

### Done!
