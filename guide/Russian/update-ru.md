<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Запуск Windows на Xiaomi Pad 5

## Обновление драйверов

### Требования
- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)

- [Образ recovery](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [Образ UEFI](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/UEFI)

- [Драйвера](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/Drivers)

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

### Diskpart
```cmd
diskpart
```

#### Выберите раздел Windows планшета
> Используйте `list volume`, чтобы отобразить разделы, затем замените "$" на номер раздела **WINNABU**
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
> Этот процесс длится примерно 20 минут. Если он будет идти дольше, просто ждите

- Распакуйте архив с драйверами, и запустите `OfflineUpdater.cmd` файл (если появляется ошибка, запустите`OfflineUpdaterFix.cmd`)

> Если он попросит ввести букву диска, введите букву **WINNABU** (должна быть **X**) и нажмите enter

#### Перезагрузите ваше устройство
> Не забудьте также обновить образ UEFI в Android, иначе вы можете столкнуться с "синим экраном смерти" (BSoD) при последующей загрузке в Windows.
```cmd
adb reboot
```

## Готово!

## Обновление UEFI 
> [!Warning]
> Если вы переходите от более старой версии UEFI, выпущенной до 2 февраля 2025 года, к UEFI-V4, вам потребуется обновить драйверы. Это можно сделать с помощью [гайда по обновлению драйверов](update-ru.md).
> 
> Учтите, что следующий релиз драйверов будет работать, только если вы переустановите Windows с новыми драйверами и UEFI, поэтому есть смысл переустановить Windows сейчас.

### Требования 
- [```WOA Helper```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/woahelper.apk)
  
- [```Последняя версия UEFI```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/nabu-uefi-v4.img)

## Замените старый UEFI на новый
> Если вы ещё не настроили двойную загрузку, то выполните [настройку двойной загрузки](dualboot-ru.md), что бы настроить WOA Helper правильно
- Загрузитесь в Android
- Откройте папку `UEFI` во внутренней памяти Android 
- Удалите старый UEFI
- Поместите новый UEFI в эту папку

## Готово, перезагружайтесь в Windows и наслаждайтесь  

> [!NOTE]
> Если вы столкнулись с BSOD или ваша Windows не загружается должным образом, убедитесь, что вы используете последние версии драйверов. При необходимости обновите их.
