Оновлення драйверів у Windows
#### Запустіть TWRP за допомогою завантажувача

```cmd
fastboot boot <twrp.img>
````



### Виконання скрипта msc

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


# Встановлення драйверів

> Замініть `<nabudriversfolder>` на вашу назву папки з драйверами.

> Відкрийте командний рядок від імені адміністратора

```cmd
driverupdater.exe -d <nabudriversfolder>\definitions\Desktop\ARM64\Internal\nabu.txt -r <nabudriversfolder> -p X:
```

##### Завантаження за допомогою завантажувального образу UEFI Windows #####

```
fastboot flash boot <uefi.img>
```


# Готово!
