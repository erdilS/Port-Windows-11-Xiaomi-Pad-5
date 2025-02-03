<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Запуск Windows на Xiaomi Pad 5

## Повторне рутування Android
Цей розділ проведе вас через процес повторного рутування, коли MIUI/Hyper OS оновлюється та видаляє root

### Потрібні файли
- [```Образ відновлення```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [```Android platform-tools```](https://developer.android.com/studio/releases/platform-tools)

- [```Magisk.apk```](https://github.com/topjohnwu/Magisk/releases/latest)

### Перезавантажте планшет в **fastboot**
- Завантажте свій планшет у **fastboot**, утримуючи кнопку **зменшення гучності** під час перезавантаження

- Підключіть його до ПК/ноутбука за допомогою кабелю

### Завантажте модифіковане відновлення
> У режимі fastboot замініть `path\to\recovery.img` на фактичний шлях до образу відновлення
```cmd
fastboot boot fastboot\до\recovery.img
```

### Прошийте magisk
- Завантажте [`magisk.apk`](https://github.com/topjohnwu/Magisk/releases/latest) на свій ПК/ноутбук
> Замініть `path\to\magisk.apk` на фактичний шлях до magisk.apk
```cmd
adb push path\to\magisk.apk /tmp/magisk.zip && adb shell twrp install /tmp/magisk.zip
```

### Перезавантажте Android
> Якщо він не перезавантажується, перезавантажте вручну, натиснувши й утримуючи кнопку живлення
```cmd
adb reboot
```

### Завершення налаштування
- Налаштуйте свій пристрій, а потім завантажте та інсталюйте [Magisk](https://github.com/topjohnwu/Magisk/releases/latest), якщо його ще не встановлено.
- Відкрийте програму **Magisk** і дотримуйтесь інструкцій на екрані, потім ваш пристрій має перезавантажитися через кілька секунд.

### Оновіть boot.img у Windows C:\
- Перезавантажте назад до Android
- Відкрийте ```WOA Helper```
- Клацніть ```РЕЗЕРВНА КОПІЯ ЗАВАНТАЖУВАЛЬНОГО ОБРАЗУ``` > ```Windows```
- Готово

### Готово!
