<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Запуск Windows на Xiaomi Pad 5

## Обновление UEFI 
> [!Warning]
> Если вы обновляетесь со старой версии UEFI (15 января или ранее) до UEFI-V3, вам также необходимо обновить драйверы, что можно сделать с помощью [гайд по обновлению драйверов](update-ru.md)

### Почему это руководство нужно?

Я не знаю, но некоторые люди спрашивают об этом 

### Требования 
- [```WOA Helper app```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/woahelper.apk)
  
- [```Latest UEFI```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v3.img)

## Замените старый UEFI на новый
> Если вы ещё не настроили двойную загрузку, то выполните [настройку двойной загрузки](/guide/English/dualboot-en.md), что бы настроить WOA Helper правильно
- Загрузитесь в Android
- Откройте папку `UEFI` во внутренней памяти Android 
- Удалите старый UEFI
- Положите новый UEFI в эту папку

## Готово, переключайтесь на Windows и наслаждайтесь  

> [!NOTE]
> Если вы получили BSOD или Windows не загружается нормально, убедитесь что вы используете последнюю версию драйверов и обновите их 
