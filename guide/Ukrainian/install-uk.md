<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

## Запуск Windows на Xiaomi Pad 5

> [!WARNING]
> **БУДЬ ЛАСКА, НЕ ВИКОРИСТОВУЙТЕ ЗАСТАРІЛІ ВІДЕОГІДИ НА YOUTUBE АБО БУДЬ-ЯКІЙ ІНШІЙ ПЛАТФОРМІ! ЦІ ВІДЕО ЗАСТАРІЛИ, І ВИ МОЖЕТЕ ЗАБЛОКУВАТИ СВІЙ ПРИСТРІЙ, ВИКОРИСТОВУЮЧИ ЇХ! ЯКЩО ВАМ ПОТРІБЕН ВІДЕОГІД, СКОРИСТАЙТЕСЯ ЦИМ [НОВИЙ ВІДЕОГІД](https://www.youtube.com/watch?v=rGPbdFq7gKs) від [ArtoSeVeN](https://www.youtube.com/channel/UCYjwfxlYlJ7Nnzv01oszQvA)**


## Установка

## Установка Windows

### Передумова

- [Образ Windows на ARM](https://uupdump.net/)
  
- [Образ UEFI](https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/images/xiaomi-nabu_20240115.img)
  
- [Драйвері](https://github.com/map220v/MiPad5-Drivers/releases/latest)

### Завантажте відновлення, щоб розпочати встановлення Windows

```cmd
fastboot boot <recovery.img>
```


### запустити msc
> Якщо скрипт попросить запустити його ще раз, то так і зробіть

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
assign letter=x
```

### Призначення літери `Y` розділу ESP

#### Вибір розділа ESP в телефоні
> Використовуйте `list volume` для того, щоб знайти розділ ESP, він назвається "ESPNABU"

```diskpart
select volume <номер>
```

### Призначення літери `Y`

```diskpart
assign letter=y
```

### Вихід із diskpart:
```diskpart
exit
```


## Встановлення
> [!NOTE]
> **Тепер запустіть командний рядок від імені адміністратора**

> Замініть `<path/to/install.wim>` дійсним шляхом до install.wim,
> `install.wim` знаходиться в теці sources всередині вашого iso

> Ви можете отримати цей файл розпакувавши або смонтувавши його

> Він також може називатися **install.esd.** Змініть шлях відповідно.


```cmd
dism /apply-image /ImageFile:<path/to/install.wim> /index:1 /ApplyDir:X:\
```


### Встановлення драйверів

> Ви можете завантажити драйвери [тут](https://github.com/map220v/MiPad5-Drivers/releases/latest)

> Коли він попросить вас " Enter Drive letter...", ввівши **`X:`**


> Не запускайте його від імені адміністратора, при необхідності він запитає права адміністратора.
```cmd
 Відкрийте папку драйверів і запустіть OfflineUpdater.cmd
```

# Створіть файли завантажувача Windows

```cmd
bcdboot X:\Windows /s Y: /f UEFI
```
## Видаліть букву диска для ESPNABU, щоб уникнути появи фантомної літери диска

```cmd
mountvol y: /d
```

# Завантажтеся у Windows

### Зробіть резервну копію поточного загрузочного розділа
> [!NOTE]
> **Тепер поверніться до командного рядка platform tools**
```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/boot.img"
```

##### Скопіюйте резервну копію на компьютер

```cmd
adb pull /tmp/boot.img
```

### Завантажте відновлення

```cmd
adb reboot bootloader
```

### Завантажте та прошийте зображення UEFI
> Завантажити [зображення UEFI](https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/images/xiaomi-nabu_20240115.img)
```cmd
fastboot flash boot <шлях до зображення>
```
## Перезавантажтесь у Windows
```cmd
fastboot reboot
```
> [!NOTE]
> Під час першого завантаження Windows він не побачить жодних мереж Wi-Fi, просто перезавантажте його, утримуючи кнопку живлення, а після перезавантаження, коли ви спробуєте підключитися до своєї мережі та побачите "морозиво", натисніть "повторити спробу" 7 разів

# Завантажте Android
> Використовуйте резервну копію завантажувального образу та прошийте з швидкого завантаження

```cmd
fastboot flash boot boot.img
```

# Готово!
> Ви можете приєднатися до нашого [Telegram chat](https://t.me/nabuwoa) щоб отримувати новини про проект
### [Останній крок: Налаштування подвійного завантаження](dualboot-uk.md)
