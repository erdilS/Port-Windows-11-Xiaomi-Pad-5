<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Запуск Windows на Xiaomi Pad 5

> [!NOTE]
> Ця інструкція **не рекомендується для оновлення драйверів до версії 2601.19**.  
> Використання її для оновлення до цієї версії може призвести до проблем або нестабільної роботи системи як каже мейнтейнера.

## Оновлення драйверів у Windows

### Необхідні файли
- [```Recovery```](https://github.com/ArKT-7/twrp_device_xiaomi_nabu/releases/tag/mod-win)
  
- [UEFI образ & Драйвері](https://github.com/remtrik-stuff/MiPad5-Windows-Releases/releases)


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
> [!Note]
> Цей процес займе від 3 до 6 годин, не хвилюйтеся, це нормально.

- Розпакуйте архів з драйверами, потім відкрийте файл `OfflineUpdater.cmd` (якщо виникне помилка, натомість запустіть `OfflineUpdaterFix.cmd`)

> Якщо з'явиться запит на введення літери, введіть літеру диска **WINNABU** (це має бути **X**), а потім натисніть Enter

#### Перезавантажте пристрій
> [!Warning]
> Не забудьте також змінити образ UEFI в Android, інакше під час завантаження Windows ви можете зіткнутися з "blue/black screen of death" (BSoD).
```cmd
adb reboot
```

## Готово!

