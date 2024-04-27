<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Корисні програми та інструкції для Windows на Xiaomi Pad 5


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



## Вимкнення безпечного завантаження 
> Якщо ви хочете мати можливість оновлювати драйвери без ПК 

[Інструкція з вимкнення безпечного завантаження](/guide/Ukrainian/disable-secureboot-uk.md)

## Встановіть Microsoft Office

- Завантажте цей [файл](https://drive.google.com/file/d/1-i-0RraTSgwxqQSWal3uYWCen1TjK6d3/view?usp=drivesdk) до планшета
  
- Вимкніть Windows Defender, щоб уникнути будь-яких перешкод під час встановлення
  
- Клацніть правою кнопкою миші на файлі iso і виберіть "змонтувати", щоб відкрити його в провіднику

- Двічі клацніть на AUTORUN.exe, щоб запустити майстер встановлення
  
- Виберіть мову та компоненти, які потрібно встановити, а потім натисніть кнопку "Почати встановлення"
  
- Дочекайтеся завершення установки і активації

- Знову ввімкніть Windows Defender

- Насолоджуйтесь Microsoft Office!

## Активація Windows

> Відкрийте PowerShell і введіть: 

```cmd
irm https://massgrave.dev/get | iex 
```
> Коли з'явиться вікно, виберіть 1

## Ліхтарик

- Завантажте [Flashlight.7z](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/flashlight_fix.7z) і розпакуйте в будь-яку папку

- Запустіть flashlight.exe, щоб увімкнути ліхтарик

- Натисніть будь-яку клавішу, щоб вимкнути його

