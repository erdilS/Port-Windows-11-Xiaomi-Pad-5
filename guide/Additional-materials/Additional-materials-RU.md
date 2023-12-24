<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Полезные приложения и инструкции для Windows на Xiaomi pad 5

## Установка Microsoft Office

- Скачайте этот [файл](https://drive.google.com/file/d/1st8xVpxtJbe2GVTEZrC_RNumKllR97Hp/view?usp=sharing) на планшет  
  
- Отключите защитник Windows, чтобы избежать каких-либо проблем при установке
  
- Щелкните правой кнопкой мыши на iso-файле и выберите "Смонтировать", чтобы открыть его в проводнике

- Дважды щелкните на AUTORUN.exe, чтобы запустить мастер установки
  
- Выберите язык и приложения, которые вы хотите установить, а затем нажмите кнопку "Начать установку"
  
- Дождитесь завершения установки и активации

- Снова включите защитник Windows

- Наслаждайтесь использованием Office!

 ## Активация Windows

> Откройте PowerShell и введите: 

  ```cmd
irm https://massgrave.dev/get | iex 
```
> В открывшемся окне выберите 1 

 ## Использование фонарика 

 - Скачайте [Flashlight.7z](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/flashlight_fix.7z) и распакуйте в любую папку

> Запустите flashlight.exe что-бы включить фонарик

> Нажмите любую клавишу что-бы выключить его

## Enabling charging and USB host mode

> [!WARNING]
>  Make sure any registry edits are done on the Mi Pad 5 itself

> [!NOTE]
> C to C charging with a PD supported device has been confirmed working and the 33W charger provided by Xiaomi is also confirmed to be working

- Download  [Script from Misha803](https://t.me/droidscripts/22) to easy enable it
 
- Or use traditional method - In the registry editor, change the value of the parameter ```RoleSwitchMode``` from ```3``` to ```1```: ```Computer\HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Enum\ACPI\QCOM0597\0\Device Parameters```. 


