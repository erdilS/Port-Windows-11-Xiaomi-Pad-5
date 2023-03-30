<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Windows на Xiaomi Pad 5

## Двойная загрузка Android и Windows

### Требования

- Android с root-правами и ядро Android с root-правами

- [Загрузите файлы](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/dualboot) 

### Со стороны Windows

- Установите [Cygwin](https://www.cygwin.com/setup-x86_64.exe) и coreutils (установится по умолчанию)

- Переименуйте файл ядра Android в boot.img

- Переместите его в C:\ (C:\boot.img)

- Запустите bat-файл с правами администратора или создайте ярлык с правами администратора

### Со стороны Android

- Установите на планшете файл switchtowin.apk

- Переименуйте UEFI файл в boot.img

- Переместите его в /sdcard/windows (/sdcard/windows/boot.img)

- Запустите приложение и предоставьте ему root-доступ

- Нажмите "Switch to Windows" если вы хотите сменить систему на Windows

