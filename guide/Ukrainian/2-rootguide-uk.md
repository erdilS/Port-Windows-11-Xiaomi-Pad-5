<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Running Windows on the Xiaomi Pad 5

## Отримання root 
> [!NOTE]
> **Якщо у вас уже є root, просто пропустіть цей крок і перейдіть до наступної сторінки**

### Передумови
- Мозок
  
- [```Magisk.apk```](https://github.com/topjohnwu/Magisk/releases/latest)

### Прошивка Magisk
- Завантажте [`magisk.apk`](https://github.com/topjohnwu/Magisk/releases/latest) на свій ПК/ноутбук
> Замініть `path\to\magisk.apk` на фактичний шлях до magisk.apk
```cmd
adb push path\to\magisk.apk /tmp/magisk.zip && adb shell twrp install /tmp/magisk.zip
```

#### Перезавантажте Android
> Якщо він не завантажується, перезавантажтеся у стандартне відновлення та виконайте там **Wipe data**
```cmd
adb reboot
```

### Завершення налаштування
- Налаштуйте свій пристрій, а потім завантажте та інсталюйте [Magisk](https://github.com/topjohnwu/Magisk/releases/latest), якщо він ще не встановлений
- Відкрийте програму **Magisk** і дотримуйтесь інструкцій на екрані, потім ваш пристрій має перезавантажитися через кілька секунд

### Зробіть резервну копію вашого root.img
> Перезавантажтеся у TWRP, а потім виконайте наведену нижче команду
```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/rooted_boot.img" && adb pull /tmp/rooted_boot.img
```

### [Наступний крок: Встановлення Windows](/guide/Ukrainian/3-install-uk.md)

