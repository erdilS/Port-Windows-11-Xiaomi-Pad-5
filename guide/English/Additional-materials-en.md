<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Useful apps and instructions for Windows on Xiaomi pad 5

### List of supported apps/games
This is by no means a comprehensive list, it simply lists apps/games that have been tested by the community
[The link can be found here](https://docs.google.com/spreadsheets/d/1XYuoySgYQE0HL573sA-0RGMX7I4lt5rWJuQ8Z8yRJNY/edit?usp=drivesdk)

You can also find a list of dedicated ARM software [at this link](https://armrepo.ver.lt/)

#### Finished!

## Hide D drive (modem partition)
> [!NOTE]
> This is recommended because this drive should not be modified, while some applications may try to write to it

- Open a command prompt window and run ```diskpart```
- Run ```list volume``` to see all available volumes
- Select the disk that has letter D with ```select volume $```, replacing "$" with the volume number
- Remove the letter with ```remove letter d```
- Exit diskpart with ```exit```

#### Finished!


## Disabling USB host mode
> [!Warning]
> Unpowered USB devices will stop working

Run [USB Host Control](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/USBHost) to enable/disable USB host mode and  confirm that you want to disable/enable USB host mode 

#### Finished!


## Disable secureboot
> If you want to be able to update drivers without a PC

[Guide to disabling secureboot](/guide/English/disable-secureboot-en.md)

#### Finished!


## Install Microsoft Office / Microsoft 365
- Download this [ISO file](https://drive.google.com/file/d/1-i-0RraTSgwxqQSWal3uYWCen1TjK6d3/view?usp=drivesdk) to the tablet
- Right-click on the iso file and select Mount to open it in explorer
- Double-click on ```Office Tool Plus.exe``` to start the installation wizard
- In the window that appears, click `Yes`
- Wait for the installation to complete

#### Finished!


## Activate Windows / Office
Follow the instructions by Massgravel [here](https://github.com/massgravel/Microsoft-Activation-Scripts)

#### Finished!


## How to use the Flashlight 
 - Download [Flashlight.7z](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/flashlight_fix.7z) and unzip to any folder
> Run flashlight.exe to enable the flashlight 
> Press any key to disable it

#### Finished!




















