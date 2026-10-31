<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Windows на Xiaomi Pad 5

## Отключение SecureBoot 
> [!WARNING]
> В последний выпуск драйверов и UEFI [v2608.03](https://github.com/remtrik-stuff/MiPad5-Windows-Releases/releases/tag/2608.03) входит образ UEFI с отключённым Secure Boot. Если вы используете более старую версию драйверов, используйте соответствующий ей образ UEFI с отключённым Secure Boot. Не смешивайте версии UEFI и драйверов.

> [!IMPORTANT]
> Следуйте этому руководству, только если хотите отключить Secure Boot.

### Требования
- ```Мозг```

- [```Android platform-tools```](troubleshooting-ru.md#adb-fastboot-not-recognized-ru)

- [```Образ рекавери```](https://github.com/ArKT-7/twrp_device_xiaomi_nabu/releases/tag/mod-win)

- [```Образ UEFI с отключённым Secure Boot```](https://github.com/remtrik-stuff/MiPad5-Windows-Releases/releases/download/2608.03/MiPad5.UEFI-v2608.03_nSB.img)

## Плюсы и минусы SecureBoot
> По умолчанию, SecureBoot включен в этом гайде

##### Плюсы и минусы SecureBoot
- [x] Отсутствие водяного знака на рабочем столе
- [x] Приложения, которые не работают в тестовом режиме, будут работать
- [x] Вы можете установить крупные обновления (например, с 24H2 на 25H2) непосредственно в центре обновления Windows
- [ ] Вы не сможете установить неподписанные драйверы

##### Плюсы и минусы отключения SecureBoot
- [x] Вы можете устанавливать неподписанные драйверы
- [ ] Водяной знак тестового режима на рабочем столе
- [ ] Некоторые приложения/игры с анти-читерским ПО могут не работать
- [ ] Вы не сможете установить крупные обновления (например, с 24H2 до 25H2) через центр обновления Windows

## Отключение SecureBoot

#### Создайте резервную копию рутированного boot-образа.
> Она вам понадобится для возврата к Android, но вы можете пропустить этот шаг, если уже создали резервную копию.

Используйте функцию `РЕЗЕРВНОЕ КОПИРОВАНИЕ BOOT ОБРАЗА` в приложении WOA Helper или загрузитесь в модифицированное recovery и выполните команду

> [!NOTE]
> Выполните эту команду в **командной строке (CMD)**. В PowerShell она не работает.
```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/rooted_boot.img" && adb pull /tmp/rooted_boot.img
```

#### Загрузитесь в recovery
> Замените `путь\к\recovery.img` на фактический путь к образу recovery
```cmd
fastboot boot путь\к\recovery.img
```

#### Активируйте режим mass storage
> После того как Xiaomi Pad 5 загрузится в модифицированный recovery выполните команду
```cmd
adb shell msc
```

#### Запустите диспетчер дисков Windows
> Как только Xiaomi Pad 5 будет обнаружен как диск выполните команду
```cmd
diskpart
```

#### Выберите том esp
> Используйте `list volume`, чтобы найти его, он называется "ESPNABU"
```diskpart
select volume <number>
```

#### Назначьте букву Y
```diskpart
assign letter y
```

#### Выйдите из diskpart
```diskpart
exit
```

#### Модифицируйте файлы загрузчика
> Чтобы включить тестовую подпись, выполните команду
```cmd
bcdedit /store Y:\EFI\Microsoft\BOOT\BCD /set "{default}" testsigning on
```

#### Удаление SiPolicy
> Предполагая, что вы отключаете SecureBoot на уже установленной системе, вам нужно удалить этот файл, иначе система не загрузится
```cmd
del Y:\EFI\Microsoft\Boot\SiPolicy.p7b
```

#### Удалите букву диска для ESPNABU.
> Если это не сработает, проигнорируйте это и перейдите к следующей команде. Этот фантомный диск исчезнет при следующей перезагрузке компьютера.
```cmd
mountvol y: /d
```

#### Перезагрузитесь в fastboot
```cmd
adb reboot bootloader
```

#### Прошивка UEFI
> Убедитесь, что вы используете соответствующий образ UEFI без Secure Boot с этой страницы.
>
> Для v2608.03 замените `<путь\к\MiPad5.UEFI-v2608.03_nSB.img>` на фактический путь к образу. Если вы используете более старую версию драйверов, используйте соответствующее ей имя noSB UEFI.
```cmd
fastboot flash boot путь\к\MiPad5.UEFI-v2608.03_nSB.img
```

> [!WARNING]
> Не забудьте также заменить старый UEFI в папке UEFI во внутренней памяти Android, чтобы избежать случайной прошивки при следующей перезагрузке в Windows из Android

#### Перезагрузитесь в Windows
```cmd
fastboot reboot
```

## Готово!
