<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Запуск Windows на Xiaomi Pad 5
> [!WARNING]
> **БУДЬ ЛАСКА, НЕ ВИКОРИСТОВУЙТЕ ЗАСТАРІЛІ ВІДЕОГІДИ НА YOUTUBE АБО БУДЬ-ЯКІЙ ІНШІЙ ПЛАТФОРМІ! ЦІ ВІДЕО ЗАСТАРІЛИ, І ВИ МОЖЕТЕ ЗЛАМАТИ СВІЙ ПРИСТРІЙ, ВИКОРИСТОВУЮЧИ ЇХ! ЯКЩО ВАМ ПОТРІБЕН ВІДЕОГІД, СКОРИСТАЙТЕСЯ ЦИМ [НОВИЙ ВІДЕОГІД](https://youtu.be/BbgTbTGbXYg) від [ArtoSeVeN](https://www.youtube.com/channel/UCYjwfxlYlJ7Nnzv01oszQvA)**

## Встановлення Windows

### Необхідні файли
- [```Windows ARM esd```](https://arkt-7.github.io/woawin/)

- [```DriveLetterAssinger```](https://github.com/Misha803/My-Scripts/releases/tag/DriveLetterAssigner)  

- [```Драйвери```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/Drivers)

- [```UEFI образ```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v3.img)

### Завантажте відновлення, щоб розпочати встановлення Windows
```cmd
fastboot boot <recovery.img>
```

#### Запустіть msc
> Якщо він попросить запустити його ще раз, то так і зробіть
```cmd
adb shell msc
```

### Призначення літер для WINNABU і ESPNABU
> Відкрийте сценарій DriveLetterAssigner і натисніть Y на вашій клавіатурі для автоматичного призначення літер X і Y розділам WINNABU і ESPNABU

### Встановлення Windows
> [!Important]
> Переконайтесь що запустили cmd/PowerShell від імені **адміністратора**
>
> Замініть `path\to\install.esd` фактичним шляхом до install.esd (він також може називатися install.wim або 22631.2861.XXXXXXX.esd) 
```cmd
dism /apply-image /ImageFile:path\to\install.esd /index:6 /ApplyDir:X:\
``` 

> Якщо ви отримуєте помилку `Error 87`, перевірте індекс вашого образу за допомогою `dism /get-imageinfo /ImageFile:path\to\install.esd`, потім замініть `index:6` на фактичний номер індексу Windows 11 Pro у вашому образі 

### Копіювання boot.img у Windows
- Перетягніть **rooted_boot.img** із папки **platform-tools** у розділ **WINNABU** у провіднику Windows, а потім перейменуйте його на **boot.img**.

### Встановлення драйверів
> Якщо ви маєте помилку `"Automatic WINNABU detection failed! Enter Drive Letter manually"`, введіть **`X`**
```cmd
 Відкрийте папку драйверів і запустіть OfflineUpdater.cmd
```
> Якщо відображаються помилки під **Installing App Packages**, ігноруйте їх і продовжуйте

#### Створіть файли завантажувача Windows
> Якщо під час копіювання завантажувальних файлів виникає помилка, знову запустіть **DriveLetterAssigner**, а потім знову виконайте наведену нижче команду, замінивши Y на U
```cmd
bcdboot X:\Windows /s Y: /f UEFI
```

### Видаліть букву диска для ESPNABU, щоб уникнути появи фантомної літери диска
```cmd
mountvol y: /d
```

### Перезавантажте планшет в fastboot
```cmd
adb reboot bootloader
```

#### Завантажтесь з UEFI
> Замініть `path\to\nabu-uefi.img` на фактичний шлях до образу UEFI
```cmd
fastboot boot fastboot\до\nabu-uefi.img
```

### Перезавантажтесь в Android
Ваш пристрій має перезавантажитися самостійно через +- 10 хвилин очікування, після чого ви завантажитеся в Android для останнього кроку.

## [Останній крок: Налаштування подвійного завантаження](4-dualboot-uk.md)
