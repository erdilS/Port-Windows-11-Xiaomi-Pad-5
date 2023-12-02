<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Running Windows on the Xiaomi Pad 5

## Installation

### Partitioning your device

### Prerequisites

- [Recovery Image](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)

### Notes:
> [!Warning]\
> if you delete any partitions via diskpart later on or now windows will send a ufs command that gets misinterpreted which erase all your ufs
> All your data will be erased! Backup now if needed.
> 
> These commands have been tested.
> 
> Ignore `udevadm` warnings
> 
>  Do not run the same command twice
> 
> On recovery, screen not working.
> 
> DO NOT REBOOT YOUR TABLET if you think you made a mistake, ask for help in the [Telegram chat](https://t.me/nabuwoa)
>
> 
> Do not run all commands at once, execute them in order!
>
> YOU CAN BREAK YOUR DEVICE WITH THE COMMANDS BELOW IF YOU DO THEM WRONG!


#### Boot recovery through the PC with the command
```cmd
fastboot boot <recovery.img>
```
##### Run the partitioning script

> If it asks you to run it once again, do so

> This is **optional** but you can **set custom sizes using this script**

> To set custom sizes do ```adb shell partition [TARGET WINDOWS SIZE IN GB]```

> Make sure you do not add GB at the end, just the number

```cmd
adb shell partition
```

#### Check if Android still starts
Just restart the phone, and see if Android still works


## [Next step: Installing Windows](guide/English/2-install-en.md)
