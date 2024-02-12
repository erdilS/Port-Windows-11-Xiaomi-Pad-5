<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Running Windows on the Xiaomi Pad 5

## Безпроблемне подвійне завантаження Android і Windows 

### Передумови 
- Мозок 
- Коренева табличка 
- На планшет встановлена Windows 
- [UEFI image](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/uefi.img)
- [WOA Helper app](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/woahelper.apk)
- [StA Installer](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/StA_Installer_nabu.exe)

## Налаштування програми подвійного завантаження  
> У цьому посібнику передбачається, що ви рутовані, якщо ні, дотримуйтесь інструкцій  [кореневий напрямний](2-rootguide-uk.md) перший.

### Налаштування - Android
> [!NOTE]
> Якщо ви не можете перемістити файли до папки Windows, це означає, що ви вимкнули Windows, а не перезавантажили її. Щоб вирішити цю проблему, завантажте Windows і скористайтеся перезапуском, а потім, коли він перезавантажиться, завантажте швидке завантаження та скористайтеся ним, щоб повернутися до Android. 
- Завантажте та встановіть [WOA Helper app](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/woahelper.apk), потім відкрийте його та надайте йому доступ root.
- Завантажити [UEFI image](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/uefi.img) and помістіть його в папку під назвою `UEFI` у вашій внутрішній пам'яті; якщо ця папка не існує, створіть її.
- Поверніться до програми WOA Helper і натисніть кнопку `Backup Android boot`. Виберіть параметри `Windows` і `Android`.
- Натисніть `Mount Windows` кнопку, потім завантажте та перемістіть [StA_Installer_nabu.exe](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/StA_Installer_nabu.exe) у щойно створену папку `Windows` у вашій внутрішній пам’яті. 
- Поверніться до програми WOA Helper і натисніть `Quickboot to Windows`.

### Setup - Windows
- Перейдіть до `C:\StA_Installer_nabu.exe` та запустіть його. Якщо це не працює, переконайтеся, що будь-яке антивірусне програмне забезпечення вимкнено, оскільки воно, ймовірно, не дозволить запустити програму. 

##### Завантаження Android 
  - Запустіть новий ярлик на робочому столі (ви також можете закріпити його в меню «Пуск»/панелі завдань для зручності доступу) 

##### Завантаження Windows
  - Прес `Quickboot to Windows` у програмі або скористайтеся новоствореним перемикачем на панелі швидких налаштувань 
  
## Готово!
