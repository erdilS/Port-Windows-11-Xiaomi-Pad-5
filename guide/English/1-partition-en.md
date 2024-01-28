<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Running Windows on the Xiaomi Pad 5

## Installation



### Prerequisites
- Brain
- [Recovery Image](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)

### Notes:
> [!Warning]\
> if you delete any partitions via diskpart later on or now windows will send a ufs command that gets misinterpreted which erase all your ufs
> 
> All your data will be erased! Backup now if needed.
> 
> These commands have been tested.
> 
> Ignore `udevadm` warnings
> 
>  Do not run the same command twice
> 
> DO NOT REBOOT YOUR TABLET if you think you made a mistake, ask for help in the [Telegram chat](https://t.me/nabuwoa)
>
> Do not run all commands at once, execute them in order!
>
> **PLEASE DON'T USE OUTDATED VIDEO GUIDES ON YOUTUBE OR ANY OTHER PLATFORM! THESE VIDEOS ARE OUTDATED AND YOU CAN BRICK YOUR DEVICE USING IT! IF YOU NEED A VIDEO GUIDE, USE THIS [NEW VIDEO GUIDE](https://www.youtube.com/watch?v=rGPbdFq7gKs) FROM [ArtoSeVeN](https://www.youtube.com/channel/UCYjwfxlYlJ7Nnzv01oszQvA)**


### Partitioning your device

#### Boot recovery through the PC with the command
```cmd
fastboot boot <recovery.img>
```
#### Partitioning your device

> If it asks you to run it once again, do so

> This is **optional**, but you can also **set custom sizes (by default, it splits the storage in half)**

> To set custom sizes do ```adb shell partition [TARGET WINDOWS SIZE IN GB]```

> Make sure you do not add GB at the end, just the number

```cmd
adb shell partition
```

#### Check if Android still starts
just restart the tablet, and see if Android still works
If isn't boot or looping or animation, use MIUI recovery or other recoveries for wiping data.


### [Next step: Installing Windows](/guide/English/2-install-en.md)
