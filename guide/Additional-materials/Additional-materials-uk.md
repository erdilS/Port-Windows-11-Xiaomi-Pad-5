<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Корисні програми та інструкції для Windows на Xiaomi pad 5

## Встановіть Microsoft Office

- Завантажте цей [файл](https://drive.google.com/file/d/1st8xVpxtJbe2GVTEZrC_RNumKllR97Hp/view?usp=sharing) до планшета
  
- Вимкніть Windows Defender, щоб уникнути будь-яких перешкод під час встановлення
  
- Клацніть правою кнопкою миші на файлі iso і виберіть "змонтувати", щоб відкрити його в Провіднику файлів

- Двічі клацніть на AUTORUN.exe, щоб запустити майстер встановлення
  
- Виберіть мову та компоненти, які потрібно встановити, а потім натисніть кнопку почати встановлення
  
- Дочекайтеся завершення установки і активації

- Знову ввімкніть Windows Defender

- Насолоджуйтесь використанням Office!

 ## Активувати Windows

> Відкрийте PowerShell і введіть: 

  ```cmd
irm https://massgrave.dev/get | iex 
```
> Коли з'явиться вікно, виберіть 1

 ## Як користуватися ліхтариком

 - Скачавши [Flashlight.7z](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/flashlight_fix.7z) і розпакуйте в будь-яку папку

> Запустіть flashlight.exe, щоб увімкнути ліхтарик

> Натисніть будь-яку клавішу, щоб вимкнути це

## Увімкнення режиму зарядки та USB-хостингу

> [!WARNING]
>  Переконайтеся, що всі зміни в реєстрі виконані на самому Mi Pad 5

> [!NOTE]
> Підтверджено працездатність зарядки C-to-C за допомогою пристрою з підтримкою PD, а також підтверджено працездатність зарядного пристрою потужністю 33 Вт, наданого Xiaomi

- Завантажити [Скрипт від Misha803](https://t.me/droidscripts/22) щоб легко включити його
 
- Або скористайтеся традиційним методом-в редакторі реєстру змініть значення параметра ```RoleSwitchMode``` від ```3``` до ```1```: ```Computer\HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Enum\ACPI\QCOM0597\0\Device Parameters```. 

