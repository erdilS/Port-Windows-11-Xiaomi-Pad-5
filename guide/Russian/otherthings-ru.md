## Требования для двойной загрузки

- Мозг

- Работает только со слотом A!

- Android с root-правами и ядро Android с root-правами

- [Загрузите файлы](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/dualboot) 

### Со стороны Windows

- Установите [Cygwin](https://www.cygwin.com/setup-x86_64.exe) и coreutils (устанавливается по умолчанию)

- Переименуйте файл ядра Android в boot.img

- Переместите его в C:\ (C:\boot.img)

- Запустите bat-файл с правами администратора или создайте ярлык с правами администратора

### Со стороны Android

- Установите на планшете файл switchtowin.apk

- Переименуйте UEFI файл в boot.img

- Переместите его в /sdcard/windows (/sdcard/windows/boot.img)

- Запустите приложение и разрешите ему root-доступ

- Нажмите "Switch to Windows" если вы хотите сменить систему на Windows

