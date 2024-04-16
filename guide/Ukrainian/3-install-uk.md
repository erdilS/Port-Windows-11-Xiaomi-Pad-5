<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Запуск Windows на Xiaomi Pad 5
> [!WARNING]
> **БУДЬ ЛАСКА, НЕ ВИКОРИСТОВУЙТЕ ЗАСТАРІЛІ ВІДЕОГІДИ НА YOUTUBE АБО БУДЬ-ЯКІЙ ІНШІЙ ПЛАТФОРМІ! ЦІ ВІДЕО ЗАСТАРІЛИ, І ВИ МОЖЕТЕ ЗАБЛОКУВАТИ СВІЙ ПРИСТРІЙ, ВИКОРИСТОВУЮЧИ ЇХ! ЯКЩО ВАМ ПОТРІБЕН ВІДЕОГІД, СКОРИСТАЙТЕСЯ ЦИМ [НОВИЙ ВІДЕОГІД](https://youtu.be/BbgTbTGbXYg) від [ArtoSeVeN](https://www.youtube.com/channel/UCYjwfxlYlJ7Nnzv01oszQvA)**

## Встановлення Windows

### Необхідні файли
- [```Windows ARM esd```](https://worproject.com/esd) (вибирати - Version:  ```11 ``` Build:  ```22631.2861``` Architecture:  ```ARM64``` Edition:  ```CLIENT``` Language:  ```виберіть свою мову```)
  
- [```Драйвери```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/Drivers)

### Завантажте відновлення, щоб розпочати встановлення Windows
```cmd
fastboot boot <recovery.img>
```

#### Запустіть msc
> Якщо він попросить запустити його ще раз, то так і зробіть
```cmd
adb shell msc
```

### Запуск diskpart
> Коли ваш Xiaomi Pad 5 визначився як диск
```cmd
diskpart
```

#### Вибір розділа Windows у планшеті
> Використовуйте `list volume` для того, щоб знайти розділ Windows, він називається "WINNABU"
```diskpart
select volume <номер>
```

#### Призначення літери `X`
```diskpart
assign letter x
```

#### Вибір розділа ESP в телефоні
> Використовуйте `list volume` для того, щоб знайти розділ ESP, він назвається "ESPNABU"
```diskpart
select volume <номер>
```

#### Призначення літери `Y`
```diskpart
assign letter y
```

#### Вихід із diskpart:
```diskpart
exit
```

### Встановлення Windows
> Замінити `<path\to\install.esd>` із фактичним шляхом до install.esd (його також можна назвати install.wim) 
```cmd
dism /apply-image /ImageFile:<path\to\install.esd> /index:6 /ApplyDir:X:\
``` 

> Якщо ви отримуєте помилкуa `Error 87`, перевірте індекс вашого зображення за допомогою `dism /get-imageinfo /ImageFile:<path\to\install.esd>`, потім замініть `index:6` на фактичний номер індексу Windows 11 Pro у вашому зображенні 

### Встановлення драйверів
> Якщо він пише `"Automatic WINNABU detection failed! Enter Drive Letter manually"`, введіть **`X`**
```cmd
 Відкрийте папку драйверів і запустіть OfflineUpdater.cmd
```
> If any errors appear under **Installing App Packages**, ignore them and continue

#### Створіть файли завантажувача Windows
> Якщо під час копіювання завантажувальних файлів виникає помилка, перевірте `diskpart`, щоб перевірити, чи є в ESPNABU літера Y. Якщо це не так, додайте будь-яку іншу літеру (наприклад, K) і замініть Y у наведеній нижче команді на зазначену літеру відповідно
```cmd
bcdboot X:\Windows /s Y: /f UEFI
```

### Видаліть букву диска для ESPNABU, щоб уникнути появи фантомної літери диска
```cmd
mountvol y: /d
```

### Reboot to Android
```cmd
adb reboot
```

> Set up your device, then go to the last step

## [Останній крок: Налаштування подвійного завантаження](dualboot-uk.md)















