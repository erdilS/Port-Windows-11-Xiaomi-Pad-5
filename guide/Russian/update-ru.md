<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Запуск Windows на Xiaomi Pad 5

## Обновление драйверов

### Что нужно
- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)

- [Иодифицированное recovery](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [образ UEFI](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v3.img)

- [Драйвера](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/Drivers)

### Загрузитесь в recovery
> Вместо `path\to\recovery.img` напишите настоящие нахождение recovery.img
```cmd
fastboot boot path\to\recovery.img
```

#### Выполните MSC скрипт
> если вас просят повторить ещё раз, сделайте это 
```cmd
adb shell msc
```

### Diskpart
```cmd
diskpart
```

#### Выберите сколько хотите выделить места на диске для Windows
> Используйте `list volume` замените "$" на то, сколько хотите выделить ГБ для **WINNABU**
```diskpart
select volume $
```

#### Отметьте этот раздел буквой X
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

- Распакуйте архив с драйверами, и запустите `OfflineUpdater.cmd` файл (если будет ошибка, запустите`OfflineUpdaterFix.cmd`)

> если скажет ввести букву вашего диска, то ввидите её **WINNABU** (это буква **X**), и нажмите enter

#### Перезагрузите ваше устройство
> Не забудьте также изменить образ UEFI в Android, иначе вы можете столкнуться с "синим экраном смерти" (BSoD) при последующей загрузке Windows.
```cmd
adb reboot
```

## Готово!
