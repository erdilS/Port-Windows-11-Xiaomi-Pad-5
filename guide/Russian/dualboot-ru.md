<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Windows на Xiaomi Pad 5

## Двойная загрузка Android и Windows

### Требования

- Android с root-правами и пропатченное Magisk'ом ядро Android

### Со стороны Windows

- Установите [STA](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/StA_Installer_nabu.exe)

- Переименуйте файл ядра Android в boot.img

- Переместите его в C:\ (C:\boot.img)

- Запустите ярлык на рабочем столе чтобы перезагрузиться в Андроид 

### Со стороны Android

- Установите на планшете  приложение [switchtowindows](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/switchtowindows.apk)

- Создайте папку Windows в паияти Андроида
  
- Переименуйте UEFI файл в boot.img

- Переместите его в созданную папку (/Память Андроид/Windows/boot.img)

- Запустите приложение и предоставьте ему root-доступ

- Нажмите "Switch to Windows" если вы хотите сменить систему на Windows

