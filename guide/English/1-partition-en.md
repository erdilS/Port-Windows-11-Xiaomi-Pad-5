<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Running Windows on the Xiaomi Pad 5

## Installation

### Prerequisites
- ```Unlocked bootloader``` - (If your bootloader is locked and you don't know how to unlock it use [this](unlock-bootloader-en.md) guide)

-  ```Brain```

- ```Windows 10(or higher) PC/Laptop```

- [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools)

- [```Modified recovery image```](https://github.com/Kumar-Jy/Windows-in-NABU-Without-PC/releases/tag/Modded-TWRP-Recovery)

### Notes:
> [!NOTE]
> You can use any Android for dualboot - MIUI/Hyper OS or any custom ROM

> [!Warning]
> All your data will be erased! Back up now if needed.
> 
> DO NOT REBOOT YOUR TABLET if you think you made a mistake, ask for help in the [Telegram chat](https://t.me/nabuwoa)

### Opening CMD as an administrator
> [!NOTE]
> Don't know how to start? Unzip the downloaded [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools), then open ```command prompt``` as an administrator and run the following command, replacing `"path\to\platform-tools"` with the actual path of the platform tools folder
```cmd
cd "path\to\platform-tools"
```
> Use this window throughout the entire guide. Do not close it.

> [!Note]
> If your device is not detected in fastboot or recovery mode, you'll have to install USB drivers [using this guide](troubleshooting-en.md#device-is-not-recognized-in-fastboot-or-recovery)

#### Reboot into fastboot mkde
- Boot your NABU into **fastboot mode** by holding down the **`volume down`** button while rebooting with a USB cable connected
- Alternatively, run the below command while booted in Android
```cmd
adb reboot bootloader
```

### Boot the modded recovery
> While in fastboot mode, replace `path\to\recovery.img` with the actual path of the recovery image
```cmd
fastboot boot path\to\recovery.img
```

### Make a backup of your existing boot image
```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/normal_boot.img" && adb pull /tmp/normal_boot.img
```

### Partitioning your device
> There are two methods to partition your device. Please select the method you would like to use below.
 
> [!NOTE]
>
> ▶️ Click to expand the menu.

### Method 1: Automatic partitioning (recommended)

<details>
  <summary><strong>Click here for method 1</strong></summary> 

### Run the partitioning script
> Replace **$** with the amount of storage you want Windows to have (do not add GB, just write the number)
> 
> If it asks you to run it once again, do so
```cmd
adb shell partition $
```

### [Next step: Rooting your device](/guide/English/2-rootguide-en.md)

</details>

----

### Method 2: Manual partitioning (use it only if you know what you're doing)

<details>
  <summary><strong>Click here for method 2</strong></summary> 

#### Unmount data
> Ignore any possible errors and continue
```cmd
adb shell umount /dev/block/by-name/userdata
``` 

#### Resizing the partition table
```cmd
adb shell sgdisk --resize-table 64 /dev/block/sda
```

### Preparing for partitioning
```cmd
adb shell parted /dev/block/sda
``` 

#### Printing the current partition table
> Parted will print the list of partitions, **userdata** should be the last partition in the list
```cmd
print
``` 

#### Removing userdata
> Replace **$** with the number of the **userdata** partition, which should be **31**
```cmd
rm $
``` 

#### Recreating userdata
> Replace **10.9GB** with the former start value of **userdata** which we just deleted
>
> Replace **70GB** with the end value you want **userdata** to have. In this example your available usable space in Android will be 70GB-10.9GB = **59GB**
```cmd
mkpart userdata ext4 10.9GB 70GB
``` 

#### Creating ESP partition
> Replace **70GB** with the end value of **userdata**
>
> Replace **70.3GB** with the value you used before, adding **0.3GB** to it
```cmd
mkpart esp fat32 70GB 70.3GB
``` 

#### Creating Windows partition
> Replace **70.3GB** with the end value of **esp**
```cmd
mkpart win ntfs 70.3GB -0MB
``` 

#### Making ESP bootable
> Use `print` to see all partitions. Replace "$" with your ESP partition number, which should be **32**
```cmd
set $ esp on
``` 

#### Exit parted
```cmd
quit
``` 

### Formatting Windows and ESP partitions
> Ensure that **win** actually has partition number **33** by scrolling up to the output of the `print` command
```cmd
adb shell mkfs.ntfs -f /dev/block/sda33 -L WINNABU
``` 

> Ensure that **esp** actually has partition number **32** by scrolling up to the output of the `print` command
```cmd
adb shell mkfs.fat -F32 -s1 /dev/block/sda32 -n ESPNABU
```

### Fixing the GPT
> Or Windows may brick your device
```cmd
adb shell fixgpt
```

#### Reboot your device
> To check if Android still starts
>
> If it doesn't, reboot into stock recovery and perform a factory reset there
```cmd
adb reboot
```

### [Next step: Rooting your device](/guide/English/2-rootguide-en.md)

----

</details>





























