<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Running Windows on the Xiaomi Pad 5

## Отримання root 
> [!NOTE]
> **Якщо у вас уже є root, просто пропустіть цей крок і перейдіть до наступної сторінки**

### Передумови
- Мозок
  
- [```Резервне копіювання завантаження Android```](/guide/English/1-partition-en.md#Make-a-backup-of-your-existing-boot-image) (резервну копію якої ви створили на першій сторінці посібника)

## Патч завантаження 

- Скопіюйте ```normal_boot.img``` файл із ```platform tools``` папку на планшет 

- Завантажте та встановіть [Magisk app](https://github.com/topjohnwu/Magisk/releases/latest) на планшет
  
- Відкрийте програму Magisk і натисніть ```Install``` кнопку. Виберіть ```Select and Patch a File``` варіант і знайдіть ```normal_boot.img``` файл, який ви скопіювали на планшет. Натисніть на ```Let's Go``` і дочекайтеся завершення процесу виправлення.
  
- Скопіюйте ```magisk_patched..img``` файл із теки ```Downloads``` на планшеті до теки ```platform-tools``` на комп’ютері.

- Перезавантажте планшет в fastboot
  
- Відкрийте командний рядок у теці platform-tools

 ## Прошивка виправленного boot
 > Замінити `<magisk_patched.img>` на фактичний шлях і ім'я ```magisk_patched.img```.
```cmd
fastboot flash boot <magisk_patched.img>
```

### [Наступний крок: Встановлення Windows](/guide/Ukrainian/3-install-uk.md)

