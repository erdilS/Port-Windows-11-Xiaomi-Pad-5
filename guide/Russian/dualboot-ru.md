<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Running Windows on the Xiaomi Pad 5

## Настройка двойной загрузки между Windows и Android

### Требования
- ```Мозг```
- ```root```
- ```Установленая Windows```
- [```Образ UEFI```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v3.img)
- [```Приложение WOA Helper```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/woahelper.apk)
- [```StA Installer```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/StA_Installer_nabu.exe)

## Установка риложения двойной загрузки
> В этом руководстве предполагается, что у вас есть root, Если нет, пожалуйста выполните [root guide](2-rootguide-ru.md) сначала.

### Установка - Android
> [!NOTE]
> Если вы не можете перемещать файлы в папку Windows, это значит что вы выполнили завершение работы вместо перезагрузки. Что бы исправить это, загрузитесь обратно в Windows и выполните перезагрузку, затем, когда он перезапустится, загрузитесь в fastboot и используйте его для возврата к Android.
- Скачайте и устновите приложение [WOA Helper](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/woahelper.apk), затем откройте его и предоставьте root права.
- Скачайте [образ UEFI](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v3.img) и скопируйте его в папку `UEFI` в вашем внутреннем хранилище, если папки нет, создайте её.
- Вернитесь к приложению WOA Helper и нажмите кнопку `Back up Android boot`. Выберите оба варианта `Windows` и `Android`.
- Нажмите кнопку `Mount Windows`, затем скачайте и переместите [StA_Installer_nabu.exe](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/StA_Installer_nabu.exe) в появившуюся папку `Windows` в вашем внутреннем хранилище.
- Вернитесь в приложение WOA Helper и нажмите`Quickboot to Windows`.

### Установка - Windows
- Перейдите в `C:\StA_Installer_nabu.exe` и запустите его. Если это не сработает, убедитесь, что все антивирусные программы выключены, так как они, вероятно, не позволят приложению запуститься.

##### Загрузка в Android
  - Запустите созавшийся ярлык на вашем рабочем столе (Вы также можете закрепить его в меню пуск / панели задач для быстрого доступа)

##### Загрузка в Windows
  - Нажмите `Быстрая загрузка в Windows`внутри приложения, или воспользуйтесь недавно созданным переключателем на панели быстрых настроек
  
## Готово!
