<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Windows на Xiaomi Pad 5

## Удаление

Если вы хотите удалить Windows, используйте данный упрощенный метод вместо ручного удаления разделов чтобы исключить риск ошибки.

Если вы хотите заблокировать загрузчик обратно, убедитесь что таблица разделов находится в заводском состоянии.

### Требования

- [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools)

- [```Recovery Image```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

#### Переключитесь на Android
> Переключитесь на Android перед началом процесса удаления

#### Перезагрузитесь в режим fastboot
- Загрузите планшет в режим **fastboot**, удерживая кнопку **`уменьшения громкости`** во время перезагрузки

- Подключите его к ПК/ноутбуку с помощью кабеля

#### Загрузите модифицированное recovery
> Откройте окно CMD в папке platform-tools, затем (пока планшет находится в режиме fastboot) запустите
```cmd
fastboot boot path\to\recovery.img
```

#### Восстановите разметку раздела
> [!Warning]
> Это сотрет ваши файлы Android. Сначала сделайте резервную копию, если необходимо.
```cmd
adb shell restore
```

### Перезагрузите в Android
```cmd
adb reboot
```

> [!NOTE]
> Если вы перезагрузились в MIUI Recovery, выполните следующие действия:
> 1. Выберите Wipe Data
> 2. Wipe All Data
> 3. После успешного удаления данных нажмите Back To Main Menu
> 4. Нажмите Reboot
> 5. Перезагрузите в System

## Готово!
