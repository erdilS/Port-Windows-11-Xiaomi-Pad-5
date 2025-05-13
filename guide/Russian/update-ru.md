<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Запуск Windows на Xiaomi Pad 5

## Обновление драйверов

### Требования
- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)

- [Образ recovery](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [Образ UEFI](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/UEFI)

- [Драйверы](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/Drivers)

> [!CAUTION]
> **❗️ОБНОВЛЕНИЕ ДРАЙВЕРОВ ДО ВЕРСИИ v2501.27 ВОЗМОЖНО ТОЛЬКО ЧЕРЕЗ WININSTALLER И ЗАЙМЁТ 3.5 ЧАСА❗️**
> **❗️УБЕДИТЕСЬ, ЧТО ВАША БАТАРЕЯ ЗЯРЯЖЕНА❗️**
> 
> [**Руководство по переустановке**](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/blob/main/guide/Russian/reinstall-ru.md)
> 
> [**Руководство по обновлению**](https://github.com/Kumar-Jy/Windows-in-NABU-Without-PC/blob/main/guide/Russian/DriverUpdate-ru.md)
>
> **❗️РЕКОМЕНДУЕТСЯ ПЕРЕУСТАНОВКА, ПОСКОЛЬКУ СЛЕДУЮЩЕЕ ОБНОВЛЕНИЕ ПОТРЕБУЕТ ПОВТОРНОЙ УСТАНОВКИ, ЕСЛИ ВЫ ОБНОВЛЯЛИСЬ С БОЛЕЕ СТАРЫХ ДРАЙВЕРОВ❗️**

### Загрузитесь в recovery
> Замените `путь\к\recovery.img` на действительный путь к recovery.img
```cmd
fastboot boot путь\к\recovery.img
```

#### Запустите msc
> Если скрипт попросит запустить его снова, то выполните его ещё раз
```cmd
adb shell msc
```

### Назначьте WINNABU букву диска 
> [!NOTE]
> Вы можете пропустить этот шаг, если у WINNABU уже есть назначенная буква

> Запустите **DriveLetterAssigner** и нажмите **`Assign Drive Letter X to Windows Volume Only`** чтобы автоматически назначить букву **X** для **WINNABU**

### Установка драйверов 
> [!Note]
> Обновление займёт от 3 до 6 часов, не волнуйтесь, это нормально. 

- Распакуйте архив с драйверами, затем откройте файл `OfflineUpdater.cmd` (если появляется ошибка, запустите вместо него `OfflineUpdaterFix.cmd `)

> Если он попросит вас ввести букву, введите букву диска **WINNABU** (которая должна быть **X**), затем нажмите enter

#### Перезагрузите ваше устройство
> [!Warning]
> Также убедитесь, что вы обновили образ UEFI в Android, иначе вы можете столкнуться с "blue screen of death" (BSoD) при загрузке в Windows.
```cmd
adb reboot
```

## Готово!
