<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Запуск Windows на Xiaomi Pad 5

## Установка

### Предварительные условия
- ```Мозг```

- [```DriveLetterAssigner```](https://github.com/Misha803/My-Scripts/releases/tag/DriveLetterAssigner)
  
- [```ARM Windows ESD```](https://arkt-7.github.io/woawin/)
    
- [```Драйвера```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/Drivers)

- [```Образ UEFI```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/UEFI)

### Опять загрузитесь в модифицированный рекавери
> Замените `путь\к\recovery.img` на актуальный путь к **recovery.img**
```cmd
fastboot boot путь\к\recovery.img
```

### Выполните msc
> Скрипт может попросить вас запустить его еще раз. В таком случае, выполните эту же команду заново.
```cmd
adb shell msc
```

### Назначьте буквы WINNABU и ESPNABU
> Откройте скрипт **DriveLetterAssigner** и нажмите букву `Y` на вашей клавиатуре для автоматического присвоения букв **X** и **Y** для **WINNABU** и **ESPNABU**
### Установка Windows
> [!Important]
> Убедитесь, что вы используете командную строку от имени администратора

> [!Important]
> По соображениям производительности рекомендуется использовать Windows 11 24H2 (сборки, начинающиеся с 261XX, например 26100.2454)

> Замените `путь\к\install.esd` на фактический путь к **install.esd** (он также может называться install.wim или 22631.2861.XXXXXXX.esd)

```cmd
dism /apply-image /ImageFile:path\to\install.esd /index:6 /ApplyDir:X:\
```

> Если вы получаете `Error 87`, проверьте индекс вашего образа с помощью `dism / get -imageinfo /ImageFile: path \to \install .esd`, затем замените `index: 6` фактическим номером индекса **Windows 11 Pro** в вашем образе.

### Копирование вашего boot.img в Windows
- Перетащите файл **root_boot.img** из папки **platform-tools** на диск **WINNABU** в проводнике Windows, затем переименуйте его в **boot.img**.

### Установка драйверов
- Распакуйте архив с драйверами, затем откройте файл `OfflineUpdater.cmd` (если появляется ошибка, запустите вместо него `OfflineUpdaterFix.cmd `)

> Если он попросит вас ввести букву, введите букву диска **WINNABU** (которая должна быть **X**), затем нажмите enter

#### Создание файлов загрузчика Windows
> Если при копировании загрузочных файлов возникает ошибка, запустите **DriveLetterAssigner** еще раз, затем снова запустите следующую команду, заменив **Y** на **U**
```cmd
bcdboot X:\Windows /s Y: /f UEFI
```

#### Удалите букву диска для ESPNABU
> Если это не сработает, проигнорируйте это и перейдите к следующей команде. Этот фантомный диск исчезнет при следующей перезагрузке компьютера.
```cmd
mountvol y: /d
```

### Перезагрузка в fastboot
```cmd
adb reboot bootloader
```

#### Загрузка в UEFI
> Замените `путь\к\nabu-uefi.img` на актуальный путь к образу UEFI
```cmd
fastboot boot path\to\nabu-uefi.img
```

### Перезагрузка в Android
> Ваше устройство должно перезагрузиться само по себе после +- 10 минут, после чего вы загрузитесь в Android для последнего шага.

## [Последний шаг: Настройка двойной загрузки](/guide/Russian/4-dualboot-ru.md)



















