<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On Xiaomi Pad 5">

# Запуск Windows на Xiaomi Pad 5

## Руководство по двойной загрузке (DualbootKernelPatcher)
> Ниже перечислены два способа, первый из которых требует прав суперпользователя, а второй — нет. Используйте тот способ, который вам больше нравится, так как оба они выполняют одну и ту же функцию.

### Предварительные требования (способ 1: требуется root-доступ)
- [Приложение WOA Helper](https://github.com/n00b69/woa-helper/releases/tag/APK)

### Настройка — Android
- Скачайте и установите приложение **WOA Helper**, затем откройте его и предоставьте ему root-доступ.
- Откройте **WOA Toolbox**, затем нажмите кнопку **DUALBOOT KERNEL PATCHER**. 
- Дождитесь завершения, затем перезагрузите устройство.

#### Загрузка в Windows
- Закройте **магнитный чехол** и перезагрузите (или включите) устройство.

#### Загрузка в Android
- Откройте **магнитный чехол** и перезагрузите (или включите) устройство.

## Готово!


### Предварительные условия (способ 2: не требует прав суперпользователя)
- [Модифицированный образ recovery](https://github.com/ArKT-7/twrp_device_xiaomi_nabu/releases/tag/mod-win)

- [Magiskboot](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/magiskboot.exe)

- [DualBoot Kernel Patcher](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/DualBootKernelPatcher.zip)

- [.fd файл](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/nabu.fd)

### Открытие CMD от имени администратора
> Откройте командную строку от имени **администратора**, затем выполните приведенную ниже команду, заменив `путь\к\platform-tools` на фактический путь к папке с платформенными инструментами, например **C:\platform-tools**.
>
> Не закрывайте это окно. Оно понадобится вам на протяжении всего руководства.
```cmd
cd путь\к\platform-tools
```

### Загрузите модифицированное recovery
> В режиме fastboot  замените `путь\к\файлу\recovery.img` на фактический путь к файлу recovery.img
```cmd
fastboot boot путь\к\файлу\recovery.img
```

#### Создайте резервную копию загрузочного образа
> Это создаст резервную копию загрузочного образа в текущем каталоге (например, `C:\platform-tools`).
```cmd
adb pull /dev/block/by-name/boot_a boot.img
```

#### Настройка необходимых файлов
- Скачайте **magiskboot.exe** и переместите его в папку `platform-tools`. 
- Скачайте **DualBootKernelPatcher.zip** и извлеките папку **DualBootKernelPatcher** в папку `platform-tools`. 
- Скачайте **nabu.fd** и переместите его в папку `platform-tools`. 

### Распаковка загрузочного образа
> Убедитесь, что **boot.img** находится в папке `platform-tools`.
```cmd
./magiskboot unpack boot.img
```

### Исправление загрузочного образа
```cmd
./DualBootKernelPatcher\bin\Windows\DualBootKernelPatcher-x86_64.exe ./kernel ./nabu.fd ./output ./DualBootKernelPatcher\Config\DualBoot.Sm8150.cfg ./DualBootKernelPatcher\ShellCode\ShellCode.Nabu.bin
```

### Переименование файла ядра
- Удалите или переименуйте файл **kernel** в папке `platform-tools`, затем переименуйте файл **output** в `kernel`

### Переупаковка загрузочного образа
> Это позволит переупаковать исправленный загрузочный образ в новый файл под названием **new_boot.img**
```cmd
./magiskboot repack boot.img
```

### Перезагрузка в режиме fastboot
```cmd
adb reboot bootloader
```

### Прошиваем рутированный загрузочный образ
> Замените `путь_к_новому_загрузочному_образу.img` на фактический путь к образу
```cmd
fastboot flash boot_a путь_к_новому_загрузочному_образу.img
```
```cmd
fastboot flash boot_b путь_к_новому_загрузочному_образу.img
```

#### Перезагружаем устройство
```cmd
fastboot reboot
```

#### Загрузка в Windows
- Закройте **магнитный чехол** и перезагрузите (или включите) устройство.

#### Загрузка в Android
- Откройте **магнитный чехол** и перезагрузите (или включите) устройство.

## Готово!
