<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Windows на Xiaomi Pad 5
>[!WARNING]
> **ПОЖАЛУЙСТА, НЕ ИСПОЛЬЗУЙТЕ УСТАРЕВШИЕ ВИДЕОГАЙДЫ НА YOUTUBE ИЛИ ЛЮБОЙ ДРУГОЙ ПЛАТФОРМЕ! ЭТИ ВИДЕО УСТАРЕЛИ, И ВЫ МОЖЕТЕ ОКИРПИЧИТЬ СВОЕ УСТРОЙСТВО, ИСПОЛЬЗУЯ ИХ! ЕСЛИ ВАМ ОЧЕНЬ НУЖЕН ВИДЕОГАЙД, ВОСПОЛЬЗУЙТЕСЬ ЭТИМ [НОВЫЙ ВИДЕОГАЙД](https://youtu.be/BbgTbTGbXYg) ОТ [ArtoSeVeN](https://www.youtube.com/channel/UCYjwfxlYlJ7Nnzv01oszQvA)**

## Установка

### Требования 

- `Мозг`

- - [```Скрипт DriveLetterAssigner```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/DriveLetterAssigner.V1.0.exe)

- [```ARM64 Windows esd```](https://worproject.com/esd) (Выберите - Version:  ```11``` Build:  ```22631.2861``` Architecture:  ```ARM64``` Edition:  ```CLIENT``` Language:  ```Выберите ваш язык```)

- [```Драйверы```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/Drivers)
  
### Перезапустите рекавери чтобы начать установку Windows
```cmd
fastboot boot <recovery.img>
```

#### Запустите msc
> Если скрипт попросит запустить его ещё раз, то так и сделайте
```cmd
adb shell msc
```
### Привяжите буквы к разделам WINNABU и ESPNABU 

#### Просто запустите скрипт [```DriveLetterAssigner```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/DriveLetterAssigner.V1.0.exe) и нажмите `Y` на вашей клавиатуре 
> Скрипт автоматически привяжет буквы X и Y к разделам Windows и ESP планшета


### Установка Windows
> Замените `<путь\к\install.esd>` существующим путём к install.esd (он может также называться install.wim)
```cmd
dism /apply-image /ImageFile:<путь\к\install.esd> /index:6 /ApplyDir:X:\
```

> если вы получили `Ошибка 87`, проверьте индекс вашего образа используя `dism /get-imageinfo /ImageFile:<путь\к\install.esd>`, затем замените `index:6` существующим номером индекса Windows 11 Pro в вашем образе 


### Установка драйверов
> Распакуйте пакет драйверов, затем откройте файл `OfflineUpdater.cmd` 

> Введите букву диска **WINNABU**, должна быть X, затем нажмите Enter

> Если в разделе **Installing App Packages** появятся какие-либо ошибки, проигнорируйте их и продолжайте

#### Создайте файлы загрузчика Windows для EFI
> Если при копировании загрузочных файлов возникает ошибка, откройте `diskpart', чтобы проверить, есть ли у ESPNABU буква Y. Если это не так, добавьте любую другую букву (например, K) и замените Y в приведенной ниже команде на указанную букву соответственно
```cmd
bcdboot X:\Windows /s Y: /f UEFI
```

#### Удалите букву диска для ESPNABU, чтобы избежать появления фантомной буквы диска
```cmd
mountvol y: /d
```

### Перезагрузка в Android
```cmd
adb reboot
```

> Настройте свое устройство и двигайтесь к последнему шагу

## [Последний шаг: Настройка двойной загрузки](dualboot-ru.md)



















