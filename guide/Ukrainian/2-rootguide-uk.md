<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Running Windows on the Xiaomi Pad 5

## Отримати root 
> [!NOTE]
> **Якщо у вас уже є root, просто пропустіть цей крок і перейдіть до наступної сторінки**

### передумови
- ```мозок```
  
- [```Резервне копіювання завантаження Android```](/guide/English/1-partition-en.md#Make-a-backup-of-your-existing-boot-image) (резервну копію якої ви створили на першій сторінці посібника)


## Патч завантаження 

- Скопіюйте ```normal_boot.img``` файл із ```platform tools``` папку на планшет 


- Завантажте та встановіть [Magisk app](https://github.com/topjohnwu/Magisk/releases/latest) на планшет
  
-  Відкрийте програму Magisk і натисніть ```Install``` кнопку. Виберіть ```Select and Patch a File``` варіант і знайдіть ```normal_boot.img``` файл, який ви скопіювали на планшет. Натисніть на ```Let's Go``` і дочекайтеся завершення процесу виправлення.
  
- Скопіюйте ```magisk_patched....img``` файл із ```Downloads``` папку на планшеті до ```platform tools``` папку на комп’ютері.

- Перезавантажте в fastboot
  
- Відкрийте командний рядок у platform tools папку

 ## Flash patched boot 
 > Замінити `<magisk_patched.img>` з фактичним ```magisk_patched.img``` ім'я/шлях.
```cmd
fastboot flash boot <magisk_patched.img>
```

### [Наступний крок: встановлення Windows](/guide/Ukrainian/3-install-uk.md)

