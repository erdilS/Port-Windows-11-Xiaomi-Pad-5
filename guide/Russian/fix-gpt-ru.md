<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Запуск Windows на Xiaomi Pad 5

## Исправление GPT для безопасного использования Windows 24H2

### Требования:
- [```Уже установленная Windows```](selection-ru.md)

- [```Образ реквавери```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [```platform tools```](https://developer.android.com/studio/releases/platform-tools)

> [!Важно]
> Если вы хотите безопасно использовать Windows 24H2, выполните следующие действия, чтобы избежать проблем с EDL.

> [!NOTE]
> Это никак не повлияет на установленные Android или Windows.

### Загрузка в fastboot
- Загрузите NABU в **fastboot**, удерживая нажатой кнопку **`уменьшения громкости`** во время перезагрузки с подключенным USB-кабелем

### Загрузка в модифицированый рекавери
> Замените `путь\к\recovery.img` на фактический путь к загруженному файлу **recovery.img**
```cmd
fastboot boot путь\к\recovery.img
```

### Исправление GPT
> После загрузки в recovery
>
> Скрипт может попросить вас запустить его еще раз. В таком случае, выполните эту же команду заново.
```cmd
adb shell fixgpt
```

### Перезагрузка устройства
```cmd
adb reboot
```

## ✅ Готово! Теперь можно безопасно использовать Windows 24H2.
