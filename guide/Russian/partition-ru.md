<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Установка Windows на Xiaomi Pad 5

## Установка

### Разметка устройства

### Требования

- [Образ рекавери](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [ADB и Fastboot](https://developer.android.com/studio/releases/platform-tools)

### Примечание:
> **Внимание** если вы удалите любой раздел с помощью diskpart сейчас или позже, Windows рано или поздно отправит команду памяти, которая будет неправильно распознана в следствие чего вся память будет стерта.
- Все пользовательские файлы будут стерты! Создайте резервную копию, если это необходимо.
- Эти команды были протестированы.
- Игнорируйте ошибки `udevadm`.
- Не выполняйте одну команду дважды.
- В рекавери экран не работает.
- НЕ ПЕРЕЗАГРУЖАЙТЕ ПЛАНШЕТ! Если вы считаете, что совершили ошибку, обратитесь за помощью в [чат Telegram](https://t.me/nabuwoa).


#### ⚠️ Не запускайте все команды сразу, выполняйте их по очереди!

##### ⚠️ НЕ СОВЕРШАЙТЕ ОШИБОК!!! В ПРОТИВНОМ СЛУЧАЕ ВЫ МОЖЕТЕ ПОВРЕДИТЬ ВАШ ПЛАНШЕТ!!!


#### Запустите рекавери с компьютера при помощи команды
```cmd
fastboot boot <recovery.img>
```
> Если у вас уже установлен TWRP, просто зажмите кнопку питания и увеличения громкости во время загрузки

#### Запустите ADB shell
```cmd
adb shell
```

#### Измените размер таблицы разделов
> Чтобы разделы Windows вместились в таблицу разделов
```sh
sgdisk --resize-table 64 /dev/block/sda
```

#### Запустите parted
```sh
parted /dev/block/sda
```

#### Удалите раздел `userdata`
> Вы можете убедиться, что раздел 31 - это раздел с пользовательскими данными, выполнив команду `print all`
```sh
rm 31
```

#### Создание разделов
> Если вы получаете уведомления, спрашивающие "Ignore or cancel?", просто введите `i` и нажмите Enter


<details>
<summary><b><strong>Для 128ГБ моделей</strong></b></summary>

- Создайте раздел ESP (хранит загрузчик Windows и файлы EFI)
```sh
mkpart esp fat32 10.9GB 11.4GB
```

- Создайте главный раздел, в который будет установлена Windows
```sh
mkpart win ntfs 11.4GB 70.2GB
```

- Создайте раздел для данных в Android
```sh
mkpart userdata ext4 70.2GB 126GB
```
  </summary>
</details>

<details>
<summary><b><strong>Для 256ГБ моделей</strong></b></summary>

- Создайте раздел ESP (хранит загрузчик Windows и файлы EFI)
```sh
mkpart esp fat32 10.9GB 11.4GB
```

- Создайте главный раздел, в который будет установлена Windows
```sh
mkpart win ntfs 11.4GB 120.8GB
```

- Создайте раздел для данных в Android
```sh
mkpart userdata ext4 120.8GB 254GB
```

  </summary>
</details>


#### Сделайте раздел ESP загрузочным чтобы образ EFI мог обнаружить его
```sh
set 31 esp on
```

#### Выйдите из parted
```sh
quit
```
#### Перезапустите планшет в загрузчик
```sh
reboot bootloader
```

#### Запустите рекавери
```cmd
fastboot boot <recovery.img>
```

#### Снова запустите ADB shell
```cmd
adb shell
```

#### Отформатируйте разделы
-  Отформатируйте раздел ESP в файловую систему FAT32
```sh
mkfs.fat -F32 -s1 /dev/block/bootdevice/by-name/esp -n ESPNABU
```

-  Отформатируйте раздел Windows в файловую систему NTFS
```sh
mkfs.ntfs -f /dev/block/bootdevice/by-name/win -L WINNABU
```

-  Отформатируйте раздел `userdata`
```sh
mke2fs -t ext4 /dev/block/bootdevice/by-name/userdata
```


#### Проверьте, запускается ли Android
Просто перезапустите планшет и убедитесь, что Android запускается Если система не запускается или вы получили цикличную перезагрузку, используйте режим восстановления MIUI или другой режим восстановления чтобы отформатировать раздел `data`.

### [Следующий шаг: установка Windows](/guide/Russian/2-install-ru.md)
