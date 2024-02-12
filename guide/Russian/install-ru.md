<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Windows на Xiaomi Pad 5
> [!WARNING]
> **ПОЖАЛУЙСТА, НЕ ИСПОЛЬЗУЙТЕ УСТАРЕВШИЕ ВИДЕОГИДЫ НА YOUTUBE ИЛИ ЛЮБОЙ ДРУГОЙ ПЛАТФОРМЕ! ЭТИ ВИДЕО УСТАРЕЛИ, И ВЫ МОЖЕТЕ ЗАБЛОКИРОВАТЬ СВОЕ УСТРОЙСТВО, ИСПОЛЬЗУЯ ИХ! ЕСЛИ ВАМ НУЖЕН ВИДЕОГИД, ВОСПОЛЬЗУЙТЕСЬ ЭТИМ [НОВЫЙ ВИДЕОГИД](https://www.youtube.com/watch?v=rGPbdFq7gKs) ОТ [ArtoSeVeN](https://www.youtube.com/channel/UCYjwfxlYlJ7Nnzv01oszQvA)**


## Установка

### Требования

- [ARM образ Windows](https://uupdump.net/)
  
- [Образ UEFI](https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/images/xiaomi-nabu_20240212-V2.img)
  
- [Драйверы](https://github.com/map220v/MiPad5-Drivers/releases/latest)

### Перезапустите рекавери чтобы начать установку Windows

```cmd
fastboot boot <recovery.img>
```

#### Запустите msc
> Если скрипт попросит запустить его ещё раз, то так и сделайте

```cmd
adb shell msc
```

### Привязка букв к разделам
  

#### Запустите Менеджер дисков Windows

> Как только планшет определился как диск

```cmd
diskpart
```


#### Привязка буквы  `X` к разделу Windows

#### Выберите Windows раздел планшета
> Используйте команду `list volume` чтобы найти разделы "WINNABU" и "ESPNABU"

```diskpart
select volume <number>
```

#### Привяжите букву X
```diskpart
assign letter=x
```

### Привязка буквы  `Y`  к разделу ESP

#### Выберите ESP раздел планшета
> Используйте команду `list volume` чтобы найти его, обычно это последний раздел

```diskpart
select volume <number>
```

#### Привяжите букву Y

```diskpart
assign letter=y
```

#### Закройте diskpart
```diskpart
exit
```

  
  

### Установка Windows
> [!NOTE]
> **Теперь запустите командную строку от имени администратора**

> Замените `<path/to/install.wim>` действительным путём к файлу `install.wim`, который расположен в папке `sources` внутри вашего ISO. Вы можете получить его, смонтировав образ или разархивировав его

> Он также может называться **install.esd.** Измените путь соответственно.
```cmd
dism /apply-image /ImageFile:<path/to/install.wim> /index:1 /ApplyDir:X:\
```

### Установка драйверов

> Вы можете скачать драйвера [тут](https://github.com/map220v/MiPad5-Drivers/releases/latest)

> Когда он попросит вас "Enter Drive letter...", введите **X:**

> Не запускайте его от имени администратора, при необходимости он запросит права администратора.


```cmd
 Откройте папку с драйверами и заустите OfflineUpdater.cmd
```

### Создайте файлы загрузчика Windows для EFI

```cmd
bcdboot X:\Windows /s Y: /f UEFI
```
## Удалите букву диска для ESPNABU, чтобы избежать появления фантомной буквы диска

```cmd
mountvol y: /d
```

## Запуск Windows

### Создайте резервную копию текущего ядра Android

> [!NOTE]
> **Теперь вернитесь в командную строку platform tools**
```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/boot.img"
```

### Скопируйте РК на компьютер

```cmd
adb pull /tmp/boot.img
```
### Перезапустите планшет в fastboot

```cmd
adb reboot bootloader
```

### Скачайте и прошейте образ UEFI 
> Скачайте [образ UEFI](https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/images/xiaomi-nabu_20240115.img)
```cmd
fastboot flash boot <путь к образу UEFI>
```
## Перезагрузитесь в Windows
```cmd
fastboot reboot
```
> [!NOTE]
> При первой загрузке Windows он не увидит никаких сетей Wi-Fi, просто перезагрузите его, удерживая нажатой кнопку питания, а после перезагрузки, когда вы попытаетесь подключиться к своей сети и увидите "мороженое", нажмите "повторить попытку" 7 раз

### Загрузка в Android
> Прошейте скопированное ранее ядро в fastboot

```cmd
fastboot flash boot boot.img
```

## Готово!
> Вы можете присоедениться к нашему [чату в Telegram](https://t.me/nabuwoa) что-бы получать последние новости проекта 
### [Последний шаг: Настройка двойной загрузки](dualboot-ru.md)
