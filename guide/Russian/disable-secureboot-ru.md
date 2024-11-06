<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Windows на Xiaomi Pad 5

## Отключение SecureBoot 
> [!Important]
> Следуйте этому руководству, только если вы хотите отключить SecureBoot.

### Требования
- ```Мозг```

- [```SDK platform tools```](https://developer.android.com/studio/releases/platform-tools)

- [```Образ рекавери```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [```Образ UEFI(SecureBoot в нём выключен зарание)```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-NoSecureboot-v3.img)

## Плюсы и минусы SecureBoot
> По умолчанию, SecureBoot включен в этом гайде

##### Плюсы и минусы SecureBoot
- √ Отсутствие водяного знака на рабочем столе
- √ Приложения, которые не работают в тестовом режиме, будут работать
- √ Вы можете установить крупные обновления (например, с 22h2 на 23h2) непосредственно в центре обновления Windows
- × Вы не сможете установить неподписанные драйверы

##### Плюсы и минусы отключения SecureBoot
- √ Вы можете устанавливать неподписанные драйверы
- × Водяной знак тестового режима на рабочем столе
- × Некоторые приложения/игры с анти-читерским ПО могут не работать
- × Вы не сможете установить крупные обновления (например, с 22h2 до 23h2) через центр обновления Windows

## Отключение SecureBoot

#### Создайте резервную копию рутированного boot-образа.
> Она вам понадобится для возврата к Android, но вы можете пропустить этот шаг, если уже создали резервную копию.

Используйте функцию `Backup Android boot` в приложении WOA Helper или загрузитесь в модифицированное рекавери и выполните команду
```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/rooted_boot.img" && adb pull /tmp/rooted_boot.img
```

#### Загрузитесь в рекавери
> Замените <путь\к\recovery> на фактический путь к образу рекавери
```cmd
fastboot boot <путь\к\recovery.img>
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
> Убедитесь, что вы используете UEFI без SecureBoot с этой страницы, замените <path\to\uefi-NoSecureboot-v3.img> на фактический путь к образу UEFI
```cmd
fastboot flash boot <path\to\uefi-NoSecureboot-v3.img>
```

> [!Важно]
> Не забудьте также заменить старый UEFI в папке UEFI во внутренней памяти Android, чтобы избежать случайной прошивки при следующей попытке перейти на Windows с Android

#### Перезагрузитесь в Windows
```cmd
fastboot reboot
```

## Готово!
