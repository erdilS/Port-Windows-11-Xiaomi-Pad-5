<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

## Запуск Windows на Xiaomi Pad 5

> [!WARNING]
> **БУДЬ ЛАСКА, НЕ ВИКОРИСТОВУЙТЕ ЗАСТАРІЛІ ВІДЕОГІДИ НА YOUTUBE АБО БУДЬ-ЯКІЙ ІНШІЙ ПЛАТФОРМІ! ЦІ ВІДЕО ЗАСТАРІЛИ, І ВИ МОЖЕТЕ ЗАБЛОКУВАТИ СВІЙ ПРИСТРІЙ, ВИКОРИСТОВУЮЧИ ЇХ! ЯКЩО ВАМ ПОТРІБЕН ВІДЕОГІД, СКОРИСТАЙТЕСЯ ЦИМ [НОВИЙ ВІДЕОГІД](https://youtu.be/BbgTbTGbXYg) від [ArtoSeVeN](https://www.youtube.com/channel/UCYjwfxlYlJ7Nnzv01oszQvA)**

## Встановлення Windows

## Початок

### Необхідні файли
  
- [```Образ UEFI```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v3.img)

- [```Windows ARM esd```](https://worproject.com/esd) (вибирати - Version:  ```11 ``` Build:  ```22631.2861``` Architecture:  ```ARM64``` Edition:  ```CLIENT``` Language:  ```виберіть свою мову```)
  
- [```Драйвери```](https://github.com/map220v/MiPad5-Drivers/releases/latest)

### Завантажте відновлення, щоб розпочати встановлення Windows

```cmd
fastboot boot <recovery.img>
```

### Запустіть msc
> Якщо він попросить запустити його ще раз, то так і зробіть

```cmd
adb shell msc
```

## Призначте літери розділам

### Запуск diskpart

> Коли ваш Xiaomi Pad 5 визначився як диск

```cmd
diskpart
```

### Призначення літери `X` розділу Windows

#### Вибір розділа Windows у планшеті
> Використовуйте `list volume` для того, щоб знайти розділ Windows, він називається "WINNABU"

```diskpart
select volume <номер>
```

#### Призначення літери `X`
```diskpart
assign letter x
```

### Призначення літери `Y` розділу ESP

#### Вибір розділа ESP в телефоні
> Використовуйте `list volume` для того, щоб знайти розділ ESP, він назвається "ESPNABU"

```diskpart
select volume <номер>
```

#### Призначення літери `Y`

```diskpart
assign letter y
```

### Вихід із diskpart:
```diskpart
exit
```

## Встановлення Windows
> Замінити `<path\to\install.esd>` із фактичним шляхом до install.esd (його також можна назвати install.wim) 

```cmd
dism /apply-image /ImageFile:<path\to\install.esd> /index:6 /ApplyDir:X:\
``` 

> Якщо ви отримуєте помилкуa `Error 87`, перевірте індекс вашого зображення за допомогою `dism /get-imageinfo /ImageFile:<path\to\install.esd>`, потім замініть `index:6` на фактичний номер індексу Windows 11 Pro у вашому зображенні 

### Скопіюйте файл boot.img у Windows 

> Це знадобиться для завантаження Android пізніше 
```cmd
adb shell cp /dev/block/bootdevice/by-name/boot /win/boot.img
```

### Встановлення драйверів

> Ви можете завантажити драйвери [тут](https://github.com/map220v/MiPad5-Drivers/releases/latest)

> Якщо він пише `"Automatic WINNABU detection failed! Enter Drive Letter manually"`, введіть **`X`**

```cmd
 Відкрийте папку драйверів і запустіть OfflineUpdater.cmd
```

## Створіть файли завантажувача Windows
> Якщо під час копіювання завантажувальних файлів виникає помилка, перевірте `diskpart`, щоб перевірити, чи є в ESPNABU літера Y. Якщо це не так, додайте будь-яку іншу літеру (наприклад, K) і замініть Y у наведеній нижче команді на зазначену літеру відповідно
```cmd
bcdboot X:\Windows /s Y: /f UEFI
```
## Видаліть букву диска для ESPNABU, щоб уникнути появи фантомної літери диска

```cmd
mountvol y: /d
```

## Завантаження у Windows

### Зробіть резервну копію поточного завантажувального розділа
> [!NOTE]
> **Тепер поверніться до командного рядка platform tools**
```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/rooted_boot.img" && adb pull /tmp/rooted_boot.img
```

### Завантажте відновлення

```cmd
adb reboot bootloader
```

### Завантажте та прошийте UEFI
> Завантажити [Образ UEFI](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v3.img)
```cmd
fastboot flash boot <шлях до образу>
```

### Перезавантажтесь у Windows
```cmd
fastboot reboot
```

> [!NOTE]
> Під час першого завантаження Windows він не побачить жодних мереж Wi-Fi, просто перезавантажте його, утримуючи кнопку живлення, а після перезавантаження, коли ви спробуєте підключитися до своєї мережі та побачите "морозиво", натисніть "повторити спробу" 7 разів

## Завантаження Android
Після налаштування Windows натисніть кнопку перезапуску в Windows (не вимкнення), а потім, коли вона перезапуститься, утримуйте `зменшення гучності` + `ввімкнення` щоб перезавантажитися назад в режим швидкого завантаження
> Використовуйте свій резервний завантажувальний образ і прошийте його в fastboot, щоб повернутися до Android

```cmd
fastboot flash boot rooted_boot.img
```
```cmd
fastboot reboot
```
## Готово!
> Ви можете приєднатися до нашого [Telegram chat](https://t.me/nabuwoa) щоб отримувати новини про проект
## [Останній крок: Налаштування подвійного завантаження](dualboot-uk.md)
