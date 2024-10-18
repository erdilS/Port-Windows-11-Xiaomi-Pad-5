<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Windows на Xiaomi Pad 5
>[!WARNING]
> **ПОЖАЛУЙСТА, НЕ ИСПОЛЬЗУЙТЕ УСТАРЕВШИЕ ВИДЕОГАЙДЫ НА YOUTUBE ИЛИ ЛЮБОЙ ДРУГОЙ ПЛАТФОРМЕ! ЭТИ ВИДЕО УСТАРЕЛИ, И ВЫ МОЖЕТЕ ОКИРПИЧИТЬ СВОЕ УСТРОЙСТВО, ИСПОЛЬЗУЯ ИХ! ЕСЛИ ВАМ ОЧЕНЬ НУЖЕН ВИДЕОГАЙД, ВОСПОЛЬЗУЙТЕСЬ ЭТИМ [НОВЫЙ ВИДЕОГАЙД](https://www.youtube.com/watch?v=8Fl5AtHNH7M) ОТ [ArtoSeVeN](https://www.youtube.com/channel/UCYjwfxlYlJ7Nnzv01oszQvA)**

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
> Запустите скрипт **DriveLetterAssigner** и нажмите **`Y`** на клавиатуре, чтобы автоматически назначить буквы **X** и **Y** для **WINNABU** и **ESPNABU**


### Установка Windows
> [!Important]
> Убедитесь, что вы используете **`CMD/Powershell`** от имени **администратора**

> Замените `<путь\к\install.esd>` на фактический путь install.esd (файл образа Windows который вы скачивали ранее) (он также может называться install.wim)

```cmd
dism /apply-image /ImageFile:<path\to\install.esd> /index:6 /ApplyDir:X:\
```

> Если вы получили `Error 87`, проверьте индекс вашего образа с помощью **`dism /get-imageinfo /ImageFile:<path\to\install.esd>`**, затем замените `index:6` номером индекса Windows 11 Pro в вашем образе

### Копирование вашего boot.img в Windows
- Перетащите файл **rooted_boot.img** из папки **platform-tools** на диск **WINNABU** в проводнике Windows, затем переименуйте его в **boot.img** .

### Установка драйверов
- Распакуйте архив с драйверами, затем откройте файл `OfflineUpdater.cmd` (если появляется ошибка, запустите вместо этого `OfflineUpdaterFix.cmd`).

> Если он попросит вас ввести букву диска, введите букву диска **WINNABU** (которая должна быть **X**), затем нажмите enter

#### Создайте файлы загрузчика Windows для EFI
> Если при копировании загрузочных файлов возникает ошибка, снова запустите **DriveLetterAssigner**, затем выполните следующую команду ещё раз, заменив **Y** на **U**
```cmd
bcdboot X:\Windows /s Y: /f UEFI
```

#### Удалите букву диска для ESPNABU
> Если это не сработает, просто перейдите к следующей команде. Этот фантомный диск исчезнет при следующей перезагрузке компьютера.
```cmd
mountvol y: /d
```

### Перезагрузитесь в fastboot
```cmd
adb reboot bootloader
```

#### Загрузка в UEFI
> Замените `путь\к\nabu-uefi.img` фактическим путём к образу UEFI
```cmd
fastboot boot путь\к\nabu-uefi.img
```

### Перезагрузка в Android
Ваше устройство должно перезагрузиться само после +- 10 минут ожидания, после чего вы будете загружены  Android для выполнения последнего шага.


## [Последний шаг: Настройка двойной загрузки](4-dualboot-ru.md)

