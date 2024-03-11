<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Windows no Xiaomi Pad 5

## Dualbooting entre o Android e o Windows

### Pré requesitos
- ```Cérebro```
- ```que o tablet tenha root```
- ```Windows instalado no tablet```
- [```Imagem do UEFI```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v3.img)
- [```WOA Helper app```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/woahelper.apk)
- [```StA Installer```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/StA_Installer_nabu.exe)

## Configurando o app de dualboot
> Esse guia pressupõe que você tem root, caso contrário, siga o [guia de root](2-rootguide-pt.md) primeiro

### Preparação - Android
> [!NOTE]
> Se você não consegue mover arquivos para a pasta Windows, significa que você desligou o Windows ao invés de reiniciar. Pra concertar isso, inicie de volta para o Windows, e enquando ele reinicia, coloque o tablet no modo fastboot e inicie o Android de volta

- Faça o download e instale o [WOA Helper app](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/woahelper.apk), then open it and grant it root access.
- Faça o download da [Imagem UEFI](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v3.img) e coloque na pasta chamada `UEFI` no armazenamento interno, caso essa pasta não exista, você pode criá-la.
- Return to the WOA Helper app and press the `Back up Android boot` button. Select both the `Windows` and `Android` options.
- Press the `Mount Windows` button, then download and move [StA_Installer_nabu.exe](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/StA_Installer_nabu.exe) to the newly created `Windows` folder in your internal storage.
- Return to the WOA Helper app and press `Quickboot to Windows`.

### Preparação - Windows
- Navigate to `C:\StA_Installer_nabu.exe` and run it. If it doesn't work, make sure that any antivirus software is off, as it will probably not let the app run

##### Booting to Android
  - Run the new shortcut on your desktop (you can also pin it to your start menu / taskbar for ease of access)

##### Booting to Windows
  - Press `Quickboot to Windows` inside the app, or use the newly created toggle in your quick settings panel
  
## Finished!

