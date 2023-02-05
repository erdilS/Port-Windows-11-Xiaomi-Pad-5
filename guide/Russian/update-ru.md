#### Запустите режим восстановления с компьютера с помощью команды

```cmd
fastboot boot <recovery.img>
```

## Скопируйте скрипт

```cmd
adb push msc.sh /sbin/
```

### Выполните скрипт

```cmd
adb shell sh /sbin/msc.sh
```

## Привяжите букву к разделу

#### Запустите Менеджер дисков Windows

> Как только планшет определился как диск

```cmd
diskpart
```


### Привязка буквы `X` к разделу Windows

#### Выберите Windows раздел планшета
> Используйте команду `list volume` чтобы найти его, обычно это предпоследний раздел
```diskpart
select volume <number>
```

#### Привяжите букву X
```diskpart
assign letter=x
```

### Закройте diskpart
```diskpart
exit
```


# Установка драйверов

> Замените `<nabudriversfolder>` расположением папки с драйверами

> Откройте командную строку от имени администратора

```cmd
driverupdater.exe -d <nabudriversfolder>\definitions\Desktop\ARM64\Internal\nabu.txt -r <nabudriversfolder> -p X:
```


##### Запустите Windows с помощью загрузочного образа UEFI  #####

```
fastboot flash boot <uefi.img>
```


# Готово!
