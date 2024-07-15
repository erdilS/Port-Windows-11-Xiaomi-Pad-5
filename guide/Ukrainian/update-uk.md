<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Запуск Windows на Xiaomi Pad 5

## Оновлення драйверів у Windows

### Необхідні файли
- [```Recovery```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)
  
- [```UEFI образ```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v3.img)
  
- [```Драйвері```](https://github.com/map220v/MiPad5-Drivers/releases/latest)

### Запустіть Recovery за допомогою завантажувача
```cmd
fastboot boot <recovery.img>
````

#### Виконання скрипта msc
> Якщо скрипт попросить запустити його ще раз, то так і зробіть
```cmd
adb shell msc
````

### Запуск diskpart
> Коли Pad 5 визначився як диск
```cmd
diskpart
```

#### Виберіть розділ Windows на телефоні
> Використовуйте list volume, щоб знайти його, зазвичай це передостанній розділ.
```diskpart
select volume <номер>
````

#### Призначення літери x
```diskpart
assign letter=x
````

#### Вихід з diskpart:
```diskpart
exit
```

### Встановлення драйверів
> Якщо написано `"Automatic WINNABU detection failed! Enter Drive Letter manually"` введіть **`X`**
>
> Відкрийте папку драйверів і запустіть ```OfflineUpdater.cmd```


### Перезавантаження до fastboot для прошивки UEFI
> Ви також можете використовувати програму WOA Helper, у цьому випадку ви можете перезавантажити за допомогою ```adb reboot```
>
> Переконайтеся, що ви використовуєте останню версію UEFI, тому що Windows може не завантажитися, якщо оновити драйвери без оновлення UEFI
```cmd
adb reboot bootloader
```

#### Завантаження з завантажувальним образом UEFI Windows
> Замініть <uefi.img> на фактичний шлях до образу UEFI
```cmd
fastboot flash boot <uefi.img>
```

## Готово!

