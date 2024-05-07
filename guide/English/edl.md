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
> You will need **5** credits to flash your device using this tool.

### Flashing your device
- Boot into EDL mode on your device.
> [!Note]
> If your bootloader is unlocked, you can run ```fastboot oem edl``` while in fastboot mode. Otherwise you need to open your device and short the testpoints.
- Download the stock fastboot rom for your device and select it in MrAuthTool.
- Press **flash**.
- Wait until it finishes flashing, then reboot.

## Finished!
























