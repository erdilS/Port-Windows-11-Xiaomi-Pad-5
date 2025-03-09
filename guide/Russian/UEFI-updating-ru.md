<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Запуск Windows на Xiaomi Pad 5

## Обновление UEFI 
> [!Warning]
> Если вы переходите от более старой версии UEFI, выпущенной до 2 февраля 2025 года, к UEFI-V4, вам потребуется обновить драйверы. Это можно сделать с помощью [гайда по обновлению драйверов](update-ru.md).
> 
> Учтите, что следующий релиз драйверов будет работать, только если вы переустановите Windows с новыми драйверами и UEFI, поэтому есть смысл переустановить Windows сейчас

### Требования 
- [```WOA Helper```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/woahelper.apk)
  
- [```Последняя версия UEFI```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/nabu-uefi-v4.img)

## Замените старый UEFI на новый
> Если вы ещё не настроили двойную загрузку, то выполните [настройку двойной загрузки](/guide/Russian/4-dualboot-ru.md), что бы настроить WOA Helper правильно
- Загрузитесь в Android
- Откройте папку `UEFI` во внутренней памяти Android 
- Удалите старый UEFI
- Поместите новый UEFI в эту папку

## Готово, перезагружайтесь в Windows и наслаждайтесь  

> [!NOTE]
> Если вы столкнулись с BSOD или ваша Windows не загружается должным образом, убедитесь, что вы используете последние версии драйверов. При необходимости обновите их
