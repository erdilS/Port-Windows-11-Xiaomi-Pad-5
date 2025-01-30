<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Useful apps and instructions for Windows on Xiaomi pad 5

### List of supported apps/games
> These are by no means comprehensive lists, they do however list apps/games that have been tested by the community

- [Renegade Google Sheets list](https://docs.google.com/spreadsheets/d/1XYuoySgYQE0HL573sA-0RGMX7I4lt5rWJuQ8Z8yRJNY/edit?usp=drivesdk)

- [ARM Repo (native ARM software)](https://armrepo.ver.lt/)

- [News & supported applications](https://windowsonarm.org/)

#### Finished!


### Disable adaptive brightness
- Open Windows 11 Settings by pressing **`Win + I`** or by right-clicking the Start button and selecting "Settings".
- Navigate to the **`System`** section from the left sidebar.
- Select **`Display`** within the System settings.
- In the **`Brightness`** section, you'll see two options:
**```1. Change brightness automatically when lighting changes:```**
> Turn this option off by toggling the switch to the **`Off`** position.
 **```2. Change brightness based on content:```**
> Turn this option off by selecting **`Off`** from the dropdown menu.

#### Finished!


### Toggling USB host mode
> [!Warning]
> Disable USB host mode if you use a powered USB hub, as this can irreversibly damage your device. If you don't use a powered USB hub, enable USB host mode or you will not be able to use any USB devices.

- Run [USB Host Control](https://github.com/Misha803/My-Scripts/releases/tag/USB-Host-Mode-Control) to enable/disable USB host mode, then confirm that you want to disable/enable USB host mode.
- If USB host mode is currently enabled and USB does not work, turn it off, then back on.

#### Finished!


### Install Microsoft Office
- Go to [Gravesoft's Office installer page](https://gravesoft.dev/office_c2r_links).
- Download the installer that fits your purposes. Make sure you select `Online x64`.
- Open the `setup.exe` and follow any instructions provided within.

#### Finished!


### Activate Windows / Office
- Follow the instructions by Massgravel [here](https://github.com/massgravel/Microsoft-Activation-Scripts)

#### Finished!


### Making the keyboard float
> [!WARNING]  
> Make sure these steps are done on the device running Windows, not your computer!

- Open CMD as an administrator and run ```reg delete HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\Scaling /v MonitorSize```
- Press `y` then enter.
- Reboot your device.

##### Finished!

