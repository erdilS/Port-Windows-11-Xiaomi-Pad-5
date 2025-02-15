<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Windows no Xiaomi Pad 5

## Dualbooting entre o Android e o Windows

### Pré requesitos
- ```Cérebro```

- ```que o tablet tenha root```

- ```Windows instalado no tablet```
- 
- [```UEFI image```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v3.img)

- [```WoA Helper app```](https://github.com/n00b69/woa-helper/releases/tag/APK)

## Configurando o app de dualboot
> Esse guia pressupõe que você tem root, caso contrário, siga o [guia de root](2-rootguide-pt.md) primeiro

### Preparação - Android
- Download and install the **WOA Helper** app, then open it and grant it root access.
- Download the **UEFI image** and place it inside the folder named `UEFI` in your internal storage.
- Open the WOA Helper app and use the **STA CREATOR** in **WOA TOOLBOX**.
> [!Important]
> If `/sdcard/Windows` is empty, your rom does not support mounting and you will have to make a boot.img backup inside the app, then copy it manually to Windows once you boot to it (for example by uploading it somewhere and then downloading it while booted into Windows). The same applies to the StA files, which are also generated in your internal storage.
>
> Do the same thing if the folder is read-only.
- Press the **REINÍCIO RÁPIDO PARA O WINDOWS** button.

### Preparação - Windows
> [!Tip]
> If this is your first time booting Windows and you wish to skip the Microsoft Account login, press the **I don't have internet** button in the WiFi page, then when prompted, press the **Continue with limited setup** button.
- Navigate to `C:\sta` and create a shortcut of **sta.exe** to your desktop, if one isn't already present

#### Inicializando o Android
- Abra o novo atalho na sua área de trabalho (para facilitar o acesso, você pode fixar o programa no menu iniciar / na barra de tarefas).

#### Inicializando o Windows
- Pressione **REINÍCIO RÁPIDO PARA O WINDOWS** no app, ou adicione o toggle no seu painel de configurações rápidas.
  
## Concluído!

