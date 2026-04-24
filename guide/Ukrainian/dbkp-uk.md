<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Запуск Windows на Xiaomi Pad 5

## Інструкція з подвійного завантаження (DualbootKernelPatcher)
> Нижче наведено два методи: перший потребує root, другий — ні. Використовуйте той, який вам підходить, обидва роблять одне й те саме.

> [!Warning]
> DualBoot Kernelpatcher наразі не працює у 50% користувачів (Windows не завантажується). Якщо це стосується вас, відновіть оригінальний boot.img і скористайтеся [методом WOA Helper](/guide/Ukrainian/4-dualboot-uk.md) для подвійного завантаження Windows і Android.

### Вимоги (метод 1: потрібен root)
- [Додаток WOA Helper](https://github.com/n00b69/woa-helper/releases/tag/APK)

### Налаштування - Android
- Завантажте та встановіть додаток **WOA Helper**, відкрийте його та надайте root доступ.
- Відкрийте **WOA Toolbox**, натисніть кнопку **DUALBOOT KERNEL PATCHER** і виберіть потрібний варіант (подвійне завантаження через **магнітний чохол** або через **кнопки гучності**).
- Зачекайте завершення, потім перезавантажте пристрій.

#### Завантаження Windows
- Закрийте **магнітний чохол** і перезавантажте (або увімкніть) пристрій.

#### Завантаження Android
- Відкрийте **магнітний чохол** і перезавантажте (або увімкніть) пристрій.

## Готово!


### Вимоги (метод 2: root не потрібен)
- [Модифікований образ recovery](https://github.com/ArKT-7/twrp_device_xiaomi_nabu/releases/tag/mod-win)

- [Magiskboot](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/Files/magiskboot.exe)

- [DualBoot Kernel Patcher](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/Files/DualBootKernelPatcher.zip)

- [.fd файл](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/Files/nabu.fd)

### Відкриття CMD від імені адміністратора
> Відкрийте CMD від імені **адміністратора**, потім виконайте команду нижче, замінивши `path\to\platform-tools` на фактичний шлях до папки platform-tools, наприклад **C:\platform-tools**.
>
> Не закривайте це вікно — воно знадобиться протягом усього гайду.
```cmd
cd path\to\platform-tools
```

### Завантаження модифікованого recovery
> В режимі fastboot замініть `path\to\recovery.img` на фактичний шлях до образу recovery
```cmd
fastboot boot path\to\recovery.img
```

#### Резервна копія образу boot
> Це збереже образ boot у поточній папці (наприклад `C:\platform-tools`).
```cmd
adb pull /dev/block/by-name/boot_a boot.img
```

#### Підготовка необхідних файлів
- Завантажте **magiskboot.exe** і перемістіть його в папку `platform-tools`.
- Завантажте **DualBootKernelPatcher.zip** і розпакуйте папку **DualBootKernelPatcher** у папку `platform-tools`.
- Завантажте **nabu.fd** і перемістіть його в папку `platform-tools`.

### Розпакування образу boot
> Переконайтесь що **boot.img** знаходиться в папці `platform-tools`.
```cmd
magiskboot unpack boot.img
```

### Патчинг образу boot
```cmd
DualBootKernelPatcher\bin\Windows\DualBootKernelPatcher-x86_64.exe kernel nabu.fd output DualBootKernelPatcher\Config\DualBoot.Sm8150.cfg DualBootKernelPatcher\ShellCode\ShellCode.Nabu.bin
```

### Перейменування файлу ядра
- Видаліть або перейменуйте файл **kernel** у папці `platform-tools`, потім перейменуйте файл **output** на `kernel`

### Перепакування образу boot
> Це перепакує патчений образ boot у новий файл **new_boot.img**
```cmd
magiskboot repack boot.img
```

### Перезавантаження в fastboot
```cmd
adb reboot bootloader
```

### Прошивка патченого образу boot
> Замініть `path\to\new_boot.img` на фактичний шлях до образу
```cmd
fastboot flash boot_a path\to\new_boot.img
```
```cmd
fastboot flash boot_b path\to\new_boot.img
```

#### Перезавантажте пристрій
```cmd
fastboot reboot
```

#### Завантаження Windows
- Закрийте **магнітний чохол** і перезавантажте (або увімкніть) пристрій.

#### Завантаження Android
- Відкрийте **магнітний чохол** і перезавантажте (або увімкніть) пристрій.

## Готово!