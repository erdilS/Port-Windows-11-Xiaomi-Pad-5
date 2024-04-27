<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Полезные приложения и инструкции для Windows на Xiaomi pad 5

## Hide D drive (modem partition)
> [!NOTE]
> Это рекомендовано так как этот диск не следует модифицировать, в то время как некоторые приложения могут пытаться записать в него

- Откройте командную строку и запустите ```diskpart```
- Выполните ```list volume``` чтобы просмотреть все доступные тома
- Выберите диск который имеет букву D используя ```select volume $```, замените "$" номером тома
- Удалите букву используя ```remove letter d```
- Выйдите из diskpart при помощи ```exit```

#### Готово!


## Disabling USB host mode
> [!Warning]
> Unpowered USB devices will stop working

Запустите [USB Host Control](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/USBHost) чтобы включить/выключить режим USB host и подтвердите что вы хотите включить/выключить USB host mode 

#### Готово!

## Отключить безопасную загрузку 
> Если вы хотите иметь возможность обновлять драйверы без ПК 

[Руководство по отключению SecureBoot ](/guide/Russian/disable-secureboot-ru.md)

## Установка Microsoft Office

- Скачайте этот [файл](https://drive.google.com/file/d/1-i-0RraTSgwxqQSWal3uYWCen1TjK6d3/view?usp=drivesdk) на планшет  
  
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

