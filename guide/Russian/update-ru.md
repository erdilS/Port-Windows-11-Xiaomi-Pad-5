<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Запуск Windows на Xiaomi Pad 5

## Обновление драйверов

### Требования
- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)

- [Образ recovery](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [Образ UEFI](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v3.img)

- [Драйвера](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/Drivers)

### Загрузитесь в recovery
> Замените `путь\к\recovery.img` на действительный путь к recovery.img
```cmd
fastboot boot путь\к\recovery.img
```

#### Запустите msc
> Если скрипт попросит запустить его снова, то сделайте это 
```cmd
adb shell msc
```

### Diskpart
```cmd
diskpart
```

#### Выберите раздел Windows планшета
> Используйте `list volume`чтобы отобразить  замените "$" на номер WINNABU
```diskpart
select volume $
```

#### Привяжите букву X
```diskpart
assign letter x
```

#### Выйдите из diskpart
```diskpart
exit
```

### Установка драйверов
> [!Note]
> Этот процесс длится примерно 20 минут. Если будет идти дольше, просто ждите

- Распакуйте архив с драйверами, и запустите `OfflineUpdater.cmd` файл (если появляется ошибка, запустите`OfflineUpdaterFix.cmd`)

> если он попросит ввести букву диска, ввидите букву **WINNABU** (должна быть **X**), и нажмите enter

#### Перезагрузите ваше устройство
> Не забудьте также обновить образ UEFI в Android, иначе вы можете столкнуться с "синим экраном смерти" (BSoD) при последующей загрузке в Windows.
```cmd
adb reboot
```

## Готово!
