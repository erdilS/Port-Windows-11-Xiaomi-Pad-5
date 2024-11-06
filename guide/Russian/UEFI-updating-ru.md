<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Запуск Windows на Xiaomi Pad 5

## Обновление UEFI 
> [!Warning]
> Если вы переходите от более старой версии UEFI, выпущенной до 15 января, к UEFI-V3, вам также потребуется обновить драйверы. Это можно сделать с помощью [гайда по обновлению драйверов](update-ru.md)

### Зачем нужно это руководство?

Мы не можем ответить на этот вопрос, но некоторые люди интересуются

### Требования 
- [```WOA Helper```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/woahelper.apk)
  
- [```Последняя версия UEFI```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v3.img)

## Замените старый UEFI на новый
> Если вы ещё не настроили двойную загрузку, то выполните [настройку двойной загрузки](/guide/English/dualboot-en.md), что бы настроить WOA Helper правильно
- Загрузитесь в Android
- Откройте папку `UEFI` во внутренней памяти Android 
- Удалите старый UEFI
- Положите новый UEFI в эту папку

## Готово, перезагружайтесь в Windows и наслаждайтесь  

> [!NOTE]
> Если вы столкнулись с BSOD или ваша Windows не загружается должным образом, убедитесь, что вы используете последние версии драйверов. При необходимости обновите их
