
<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Запуск Windows на Xiaomi Pad 5

## Получить root
> **Если у вас уже есть root права просто пропустите эту страницу и перейдите к следующей**

### Требования
- ```Мозг```
- [```Бэкап образа boot от Android```](/guide/English/1-partition-en.md#Make-a-backup-of-your-existing-boot-image) (вы делали его первой странице)


## Пропатчите загрузачный образ

- скопируйте файл ```normal_boot.img``` из папки ```platform-tools``` на планшет 


- Скачайте и установите [Приложение Magisk](https://github.com/topjohnwu/Magisk/releases/latest) на планшет
  
-  Откройте приложение Magisk и нажмите кнопку```Установка```. Выберите опцию```Пропатчить boot-образ ``` и найдите файл ```normal_boot.img``` который вы скопировали на планшет. Нажмите на кнопку ```Установить``` и дождитесь завершения процесса.
  
- Скопируйте файл ```magisk_patched....img``` из папки ```Downloads``` на планшете, в папку  ```platform tools``` на компьютере. 

- Перезагрузитесь в fastboot
  
- Откройте командную строку в папке platform tools 
 ## Прошейте патченый boot-образ
 > Замените `<magisk_patched.img>` актуальным путём/названием файла ```magisk_patched.img``` 
```cmd
fastboot flash boot <magisk_patched.img>
```

### [Следующий шаг: Установка Windows](/guide/Russian/3-install-ru.md)
