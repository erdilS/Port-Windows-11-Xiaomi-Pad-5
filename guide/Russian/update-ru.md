<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Windows на Xiaomi Pad 5

## Обновление драйверов

### Требования

- [образ UEFI](https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/images/xiaomi-nabu_secureboot-v2.img)
  
- [Recovery](../../../../releases/tag/1.0)
  
- [Драйверы](https://github.com/map220v/MiPad5-Drivers/releases/latest)

#### Запустите рекавери с компьютера при помощи команды

```cmd
fastboot boot <recovery.img>
```

#### Запустите msc
> Если скрипт попросит запустить его ещё раз, то так и сделайте

```cmd
adb shell msc
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

> Вы можете скачать драйвера [тут](https://github.com/map220v/MiPad5-Drivers/releases/latest)

```cmd
 Откройте папку с драйверами и заустите OfflineUpdater.cmd
```



### Запустите Windows с помощью загрузочного образа UEFI 

```
fastboot flash boot <uefi.img>
```

## Готово!
