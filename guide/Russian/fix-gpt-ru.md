<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Запуск Windows на Xiaomi Pad 5

## Исправление GPT для безопасного использования Windows 24H2

### Предварительные условия:
- [```Установленная Windows```](selection-ru.md)

- [```образ Recovery```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [```platform tools```](https://developer.android.com/studio/releases/platform-tools)

> [!Important]
> Если вы хотите безопасно использовать Windows 24H2, выполните следующие действия, чтобы избежать проблем с EDL.
> 
> Это никак не повлияет на вашу установку Android или Windows.

### Загрузка в fastboot
- Загрузите ваш NABU в режим fastboot, удерживая нажатой кнопку "Уменьшение громкости" + "питание", или запустите приведенную ниже команду во время загрузки в Android.
```cmd
adb reboot bootloader
```

#### Загрузка в модифицированый Recovery
> Замените `path\to\recovery.img` на фактический путь к загруженному файлу **recovery.img**
```cmd
fastboot boot path\to\recovery.img
```

### Исправление GPT
> После загрузки в Recovery
>
> Если он попросит вас запустить его еще раз, сделайте это
```cmd
adb shell fixgpt
```

#### перезагрузка устройства
```cmd
adb reboot
```

## ✅ Готово! Теперь можно безопасно использовать Windows 24H2. С наступающим Новым Годом вас!
