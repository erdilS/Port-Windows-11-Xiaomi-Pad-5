<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Running Windows on the Xiaomi Pad 5

## Restoring the device in EDL mode
> This is done as a last resort when your device either only boots to EDL mode by itself, or if you are unable to restore it with other means

### Prerequisites
- A crypto wallet with $5 USDT

- [A Telegram account](https://telegram.org)

- [MrAuthTool 2.0](https://mrauthtool.com/)

- [Stock fastboot rom](https://xiaomifirmwareupdater.com/miui/nabu/)

### Setting up MrAuthTool
- Create a MrAuthTool account [here](https://mrauthtool.com/Sing_Up.php)
- Download **MR 2.0** on the MrAuthTool homepage, extract **Mr_Auth_Tool_2.0.exe** from the archive, and open it
- Sign into your account

### Buy credits
> Contact one of the authorized vendors listed on the MrAuthTool homepage on Telegram to buy credits.
>
> Don't hesitate to contact multiple people, because some may take a long time to respond.
> 
> You will need **5** credits to flash your device using this tool.

### Booting into EDL mode
> [!Note]
> If you're already in EDL mode, skip this step and continue with "Flashing your device"
- If your bootloader is unlocked and if you have access to fastboot mode, run ```fastboot oem edl``` to boot to EDL mode.

> If your bootloader is locked, or Android doesn't boot and you cannot access fastboot mode in any way, you will need to either remove the back of your device to short the EDL testpoints, or you will have to use an EDL cable
>
> (Not all EDL cables work and you may risk wasting money on one that won't, but this is probably still better than having to open your device).
- Look for a cable that has **V2** in its name, for example **Hydra V2 EDL Cable** or **V2 EDL Pro Cable**. Make sure it is for USB-C devices.
- Insert the cable into your device, then hold the button on the cable which may look like [this](https://t.me/nabuwoa/204867).
- It should boot you into EDL mode now.

### Flashing your device
- Download the stock fastboot rom for your device and select it in MrAuthTool.
- Press **flash**.
- Wait until it finishes flashing, then reboot.

## Finished!
























