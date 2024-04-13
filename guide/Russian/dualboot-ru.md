<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Running Windows on the Xiaomi Pad 5

## Настройка двойной загрузки между Windows и Android

### Требования
- ```Мозг```
- ```Рут```
- ```Установленная Windows```
- [```Образ UEFI```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v3.img)
- [```WOA Helper```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/woahelper.apk)
- [```StA Installer```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/StA_Installer_nabu.exe)

## Установка приложения двойной загрузки
> В этом руководстве предполагается, что у вас есть рут, Если нет, пожалуйста, сначала выполните [root guide](2-rootguide-ru.md)

### Установка - Android
> [!NOTE]
> Если вы не можете перемещать файлы в папку Windows, это значит что вы выполнили завершение работы вместо перезагрузки. Что бы исправить это, загрузитесь обратно в Windows и выполните перезагрузку, затем, когда он перезапустится, загрузитесь Fastboot и используйте его для возврата к Android.

- Скачайте и установите приложение WOA Helper, затем откройте его и предоставьте root права.
- Скачайте **образ UEFI** и скопируйте его в папку `UEFI` в вашем внутреннем хранилище, если папки нет, создайте её.
- Нажмите кнопку `СМОНТИРОВАТЬ WINDOWS`, затем скачайте и переместите **StA_Installer_nabu.exe** в появившуюся папку `Windows` в вашем внутреннем хранилище.
- Вернитесь в приложение WOA Helper и нажмите`БЫСТРАЯ ЗАГРУЗКА В WINDOWS`.
  
> [!NOTE]
> The first Windows boot can take up to 10 minutes, don't worry and just wait

> [!Important]
> On the first Windows boot, it will not see any Wi-Fi networks. Restart your tablet by holding down the power button until it restarts. After the reboot, it will be fixed. If you get a pop-up saying "Could not connect", press retry until it works (usually 5 times)

### Установка - Windows
- Перейдите в `C:\StA_Installer_nabu.exe` и запустите его. Если это не сработает, убедитесь, что все антивирусные программы выключены, так как они, вероятно, не позволят приложению запуститься.

#### Загрузка в Android
- Запустите созавшийся ярлык на вашем рабочем столе (Вы также можете закрепить его в меню пуск / панели задач для быстрого доступа)

#### Загрузка в Windows
- Нажмите `БЫСТРАЯ ЗАГРУЗКА В WINDOWS`внутри приложения, или воспользуйтесь недавно созданным переключателем на панели быстрых настроек
  
## Готово!
