<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Windows на Xiaomi Pad 5

## Обновление драйверов

### Требования
- [```Recovery```](../../../../releases/tag/1.0)

- [```образ UEFI```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v3.img)
  
- [```Драйверы```](https://github.com/map220v/MiPad5-Drivers/releases/latest)

### Запустите рекавери с компьютера при помощи команды
```cmd
fastboot boot <recovery.img>
```

#### Запустите msc
> Если скрипт попросит запустить его ещё раз, то так и сделайте
```cmd
adb shell msc
```

#### Запустите Менеджер дисков Windows
> Как только планшет определился как диск
```cmd
diskpart
```

#### Выберите Windows раздел планшета
> Используйте команду `list volume` чтобы найти разделы **WINNABU**

```diskpart
select volume <number>
```

#### Привяжите букву X
```diskpart
assign letter=x
```

#### Закройте diskpart
```diskpart
exit
```

### Установка драйверов
> Если он напишет `"Automatic WINNABU detection failed! Enter Drive Letter manually"`, введите **`X`**
```cmd
 Откройте папку с драйверами и заустите OfflineUpdater.cmd
```

### Reboot to fastboot to flash UEFI
> You can also use the WOA Helper app, in which case you can reboot with ```adb reboot```
>
> Make sure you use the latest UEFI, because Windows might not boot if you update drivers without updating the UEFI
```cmd
adb reboot bootloader
```

#### Boot with Windows bootable UEFI image
> Replace <uefi.img> with the actual path of the UEFI image
```
fastboot flash boot <uefi.img>
```

## Готово!
