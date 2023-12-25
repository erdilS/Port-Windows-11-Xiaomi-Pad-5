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

## Включить зарядку и OTG 

> [!WARNING]
>  Убедитесь что все изменения в реестре сделаны на Mi pad 5

> [!NOTE]
> Подтверждена работоспособность зарядки C-to-C с помощью устройства с поддержкой PD, а также подтверждена работоспособность зарядного устройства мощностью 33 Вт, предоставленного Xiaomi

- Скачайте  [Скрипт от Misha803](https://t.me/droidscripts/22) что бы легко включить это 
 
- или используйте традиционный метод - в редакторе рекстра, измените значение параметра ```RoleSwitchMode``` С ```3``` на ```1```: ```Computer\HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Enum\ACPI\QCOM0597\0\Device Parameters```. 


