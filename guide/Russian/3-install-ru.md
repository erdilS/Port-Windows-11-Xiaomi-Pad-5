<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Windows на Xiaomi Pad 5
>[!WARNING]
> **ПОЖАЛУЙСТА, НЕ ИСПОЛЬЗУЙТЕ УСТАРЕВШИЕ ВИДЕОГАЙДЫ НА YOUTUBE ИЛИ ЛЮБОЙ ДРУГОЙ ПЛАТФОРМЕ! ЭТИ ВИДЕО УСТАРЕЛИ, И ВЫ МОЖЕТЕ ОКИРПИЧИТЬ СВОЕ УСТРОЙСТВО, ИСПОЛЬЗУЯ ИХ! ЕСЛИ ВАМ ОЧЕНЬ НУЖЕН ВИДЕОГАЙД, ВОСПОЛЬЗУЙТЕСЬ ЭТИМ [НОВЫЙ ВИДЕОГАЙД](https://youtu.be/BbgTbTGbXYg) ОТ [ArtoSeVeN](https://www.youtube.com/channel/UCYjwfxlYlJ7Nnzv01oszQvA)**

## Установка

### Требования 
- `Мозг`

- [```Скрипт DriveLetterAssigner```](https://github.com/Misha803/My-Scripts/releases/tag/DriveLetterAssigner) (Отключите антивирус на время, система считает файл подозрительным)

- [```ARM64 Windows esd```](https://arkt-7.github.io/woawin/)

- [```Драйверы```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/Drivers)
  
### Загрузитесь в модифицированное рекавери чтобы начать установку Windows
> Замените **путь\к\recovery.img** на фактический путь к образу рекавери
```cmd
fastboot boot путь\к\recovery.img
```

#### Запустите msc
> Если скрипт попросит запустить его ещё раз, то так и сделайте
```cmd
adb shell msc
```
### Привяжите буквы к разделам WINNABU и ESPNABU 
> Запустите скрипт **DriveLetterAssigner V2.0** и нажмите **`Y`** на клавиатуре, чтобы автоматически назначить буквы **X** и **Y** для **WINNABU** и **ESPNABU**


### Установка Windows
> [!Important]
> Убедитесь, что вы используете **`CMD/Powershell`** от имени **администратора**

> Замените `<путь\к\install.esd>` на фактический путь install.esd (файл образа Windows который вы скачивали ранее) (он также может называться install.wim)

```cmd
dism /apply-image /ImageFile:<path\to\install.esd> /index:6 /ApplyDir:X:\
```

> Если вы получили `Error 87`, проверьте индекс вашего образа с помощью **`dism /get-imageinfo /ImageFile:<path\to\install.esd>`**, затем замените `index:6` номером индекса Windows 11 Pro в вашем образе

### Установка драйверов
> Распакуйте пакет драйверов и запустите `OfflineUpdater.cmd` 

> Если он попросит вас ввести букву, введите букву диска **WINNABU** (которая должна быть **X**), затем нажмите enter

#### Создайте файлы загрузчика Windows для EFI
> Если при копировании загрузочных файлов возникает ошибка, просто запустите скрипт [**```DriveLetterAssigner V2.0```**](https://github.com/Misha803/My-Scripts/releases/tag/DriveLetterAssigner) снова, он присвоит ESPNABU букву U. Затем снова запустите следующую команду, заменив Y на U
```cmd
bcdboot X:\Windows /s Y: /f UEFI
```

#### Удалите букву диска для ESPNABU, чтобы избежать появления фантомной буквы диска
> Если это не сработает, проигнорируйте это и перейдите к следующей команде. Этот фантомный диск исчезнет при следующей перезагрузке ПК.
```cmd
mountvol y: /d
```

### Перезагрузка в Android
```cmd
adb reboot
```

> Настройте своё устройство и двигайтесь к последнему шагу

## [Последний шаг: Настройка двойной загрузки](4-dualboot-ru.md)

