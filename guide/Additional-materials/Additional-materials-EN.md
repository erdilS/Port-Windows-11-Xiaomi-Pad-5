<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Useful apps and instructions for Windows on Xiaomi pad 5

## Microsoft Office

- Download this [file](https://drive.google.com/file/d/1st8xVpxtJbe2GVTEZrC_RNumKllR97Hp/view?usp=sharing) to tablet 
  
- Turn off Windows Defender to avoid any interference with the installation
  
- Right-click on the iso file and select Mount to open it in explorer

- Double-click on AUTORUN.exe to start the installation wizard
  
- Choose the language and the components you want to install, and then click Start installation
  
- Wait for the installation and activation to complete

- Turn on Windows Defender again 

- Enjoy using Office!

 ## Activate Windows

> Open PowerShell and type: 

  ```cmd
irm https://massgrave.dev/get | iex 
```
> When a window appears, select 1

 ## How to use Flashlight 

 - Download [Flashlight.7z](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/flashlight_fix.7z) and unzip to any folder

> Run flashlight.exe to enable flashlight 

> Press any key to disable it


## Enabling fast charging and enabling USB host mode

> [!WARNING]
>  Make sure any registry edits are done on the Mi Pad 5 itself

> [!NOTE]
> C to C charging with a PD supported device has been confirmed working and the 33W charger provided by Xiaomi is also confirmed to be working

- Download  [Script from Misha803](https://t.me/droidscripts/22) to easy enable it
 
- or use traditional method - In the registry editor, change the value of the parameter ```RoleSwitchMode``` from ```3``` to ```1```: ```Computer\HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Enum\ACPI\QCOM0597\0\Device Parameters```. 
