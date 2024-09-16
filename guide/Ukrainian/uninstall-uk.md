<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Запуск Windows на Xiaomi Pad 5

## Видалення Windows

### Навіщо це потрібно?

Якщо ви хочете видалити Windows, це використовується замість видалення розділів вручну, щоб уникнути людської помилки.

Якщо ви хочете повторно заблокувати завантажувач, вам знадобиться, щоб таблиця розділів була стандартною.

### Необхідні файли

- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)

- [```Образ відновлення```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

#### Перехід в Android
> Перейдіть в Android перед початком процесу видалення

#### Перезавантажтесь в fastboot
- Завантажте свій планшет у режим **fastboot**, утримуючи кнопку **зменшення гучності** під час перезавантаження

- Підключіть його до ПК/ноутбука за допомогою кабелю

#### Завантажте модифіковане відновлення
> Відкрийте вікно CMD у папці `platform-tools`, а потім (поки ваш планшет у режимі fastboot) запустіть
```cmd
fastboot boot шлях\до\recovery.img
```

#### Відновлення схему розділу
> [!Warning]
> Ця операція видалить ваші дані в Android. Спершу створіть резервну копію, якщо потрібно.
```cmd
adb shell restore
```

### Перезавантажтесь в Android
```cmd
adb reboot
```

> [!Note]
> Якщо ви перезавантажилися в MIUI Recovery, виконайте такі дії:
> 1. Виберіть "Wipe Data" -> "Wipe All Data"
> 2. Після успішного видалення даних натисніть "Back to Main Menu".
> 3. Натисніть "Reboot"
> 4. Планшет перезавантажиться в систему

### Готово!
