<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">
# Running Windows on the Xiaomi Pad 5

## Оновлення драйверів у Windows


### Передумова

- [```образ recovery```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)
  
- [```Образ UEFI```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v3.img)
  
- [```Драйвері```](https://github.com/map220v/MiPad5-Drivers/releases/latest)




#### Запустіть Recovery за допомогою завантажувача

```cmd
fastboot boot <recovery.img>
````



### Виконання скрипта msc
> Якщо скрипт попросить запустити його ще раз, то так і зробіть

```cmd
adb shell msc
````

## Призначення літери диску

#### Запуск diskpart

> Коли Pad 5 визначився як диск

```cmd
diskpart
```

### Призначення літери `x` розділу Windows

#### Виберіть розділ Windows на телефоні
> Використовуйте list volume, щоб знайти його, зазвичай це передостанній розділ.
```diskpart
select volume <номер>
````

#### Призначення літери x
```diskpart
assign letter=x
````

### Вихід з diskpart:
```diskpart
exit
````


### Встановлення драйверів

> Ви можете завантажити драйвери [тут](https://github.com/map220v/MiPad5-Drivers/releases/latest)

> Якщо написано `"Automatic WINNABU detection failed! Enter Drive Letter manually"` Введіть **`X`**
```cmd
 Відкрийте папку драйверів і запустіть OfflineUpdater.cmd
```

##### Завантаження за допомогою завантажувального образу UEFI Windows #####

```
fastboot flash boot <uefi.img>
```


# Готово!
