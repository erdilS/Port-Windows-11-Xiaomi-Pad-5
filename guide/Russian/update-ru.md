<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Установка Windows на Xiaomi Pad 5

## Обновление драйверов

### Требования

- [Образ UEFI](../../../../releases/tag/1.0)
- [Скрипт монтирования разделов](../../../../releases/tag/1.0)
- [TWRP](../../../../releases/tag/1.0)
- [DriverUpdater](https://github.com/WOA-Project/DriverUpdater/releases/latest)
- [Драйверы](https://github.com/map220v/MiPad5-Drivers)

#### Запустите рекавери с компьютера при помощи команды

```cmd
fastboot boot <recovery.img>
```

#### Скопируйте скрипт msc в /sbin

```cmd
adb push msc.sh /sbin/
```

#### Выполните скрипт msc

```cmd
adb shell msc.sh
```

### Привязка букв к разделам

#### Запустите Менеджер дисков Windows

> Как только планшет определился как диск

```cmd
diskpart
```


### Привязка буквы  `X` к разделу Windows

#### Выберите Windows раздел планшета
> Используйте команду `list volume` чтобы найти разделы "WINNABU"

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

> Замените `<nabudriversfolder>` расположением папки с драйверами

#### Откройте командную строку от имени администратора 


```cmd
DriverUpdater.exe -d <nabudriversfolder>\definitions\Desktop\ARM64\Internal\nabu.txt -r <nabudriversfolder> -p X:
```


### Boot with Windows bootable UEFI image
### Запустите Windows с помощью загрузочного образа UEFI 

```
fastboot flash boot <uefi.img>
```

## Готово!
