<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Useful apps and instructions for Windows on Xiaomi pad 5

## Disabling USB host mode
> [!Warning]
> Unpowered USB devices will stop working

Run [restore_default_usb.reg](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/USBHost/restore_default_usb.reg), then restart the tablet.

To re-enable USB host mode, run [force_usb_host.reg](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/USBHost/force_usb_host.reg), then restart the tablet.

## Disable secureboot
> If you want to be able to update drivers without a PC

[Guide to disabling secureboot](/guide/English/disable-secureboot-en.md)

## Install ```Microsoft Office```/```Microsoft 365```

### Download Office iso 

- Download this [file](https://mega.nz/file/hjAiSL4T#G7kOKpsUFpyL2UW9RQmY2e96urcQW5xZKdc7ciaNOy8) to tablet
  
### Install Office from iso

- Right-click on the iso file and select Mount to open it in explorer

- Double-click on ```Office Tool Plus.exe``` to start the installation wizard
  
- In the window that appears, click `Yes`
  
- Wait for the installation to complete
  
### Activate Office 

- Activate it using massgrave script:

> Open `PowerShell` and type: 

  ```powershell 
irm https://massgrave.dev/get | iex 
```

- When a window appears, select 2

- On next page select 1

- Wait for the activation to complete

- Enjoy using Office!

 ## Activate Windows

> Open PowerShell and type: 

  ```powershell 
irm https://massgrave.dev/get | iex 
```
> When a window appears, select 1

 ## How to use Flashlight 

 - Download [Flashlight.7z](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/flashlight_fix.7z) and unzip to any folder

> Run flashlight.exe to enable flashlight 

> Press any key to disable it



