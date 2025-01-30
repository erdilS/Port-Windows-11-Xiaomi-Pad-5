<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Windows no Xiaomi Pad 5

## Instalação

### Pré requesitos
- ```Cérebro```
 
- [```DriveLetterAssigner Tool```](https://github.com/Misha803/My-Scripts/releases/tag/DriveLetterAssigner)
  
- [```ARM Windows ESD```](https://arkt-7.github.io/woawin/)
    
- [```Drivers```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/Drivers)

- [```UEFI image```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/UEFI)

### Inicie novamente o recovery para começar a instalação do Windows
> Replace `path\to\recovery.img` with the actual path of the recovery image
```cmd
fastboot boot path\to\recovery.img
```

#### Execute o msc 
> Se o comando disser pra fazer de novo, faça
```cmd
adb shell msc
```

### Atribuindo letras para WINNABU e ESPNABU
> Execute o script **DriveLetterAssigner** e pressione `Y` no seu teclado para atribuir as letras **X** e **Y** nas partições **WINNABU** e **ESPNABU**

### Instalar Windows
> [!Important]
> Tenha certeza de que está rodando o CMD/Powershell como **Administrador**

> Replace `path\to\install.esd` with the actual path of install.esd (it may also be named install.wim or 22631.2861.XXXXXXX.esd)

```cmd
dism /apply-image /ImageFile:path\to\install.esd /index:6 /ApplyDir:X:\
```

> Se o erro `Error 87` surgir, verifique o index da sua imagem (install.esd ou install.wim) com o comando `dism /get-imageinfo /ImageFile:<caminho\para_o\install.esd>`, e bustitua o `index:6` com o index correto do Windows 11 Pro da sua imagem

### Copying your boot.img into Windows
- Drag and drop the **rooted_boot.img** from the **platform-tools** folder into the **WINNABU** disk in Windows Explorer, then rename it to **boot.img**.

### Instalar os drivers
> Descompacte o arquivo dos Drivers, então execute o arquivo `OfflineUpdater.cmd` (if an error shows up, run `OfflineUpdaterFix.cmd` instead)

> Se exigido que você digite uma letra, digite a letra da partição **WINNABU** (no caso a letra **X**), aperte enter

#### Crie os arquivos do bootloader do windows para o EFI
> Se um erro ocorrer ao copiar os arquivos do bootloader, execute o **DriveLetterAssigner** novamente, e execute o comando abaixo novamente, substituindo a letra **Y** pelo **U**
```cmd
bcdboot X:\Windows /s Y: /f UEFI
```

#### Remova a letra do disco ESPNABU
> Se isso não funcionar, ignore e faça o próximo comando. O disco fantasma vai desaparecer na próxima reinicializção do seu PC.
```cmd
mountvol y: /d
```

### Reboot into fastboot
```cmd
adb reboot bootloader
```

#### Boot into the UEFI
> Replace `path\to\nabu-uefi.img` with the actual path of the UEFI image
```cmd
fastboot boot path\to\nabu-uefi.img
```

### Reboot into Android
> Your device should reboot by itself after +- 10 minutes of waiting, after which you will be booted into Android, for the last step.

## [Último passo: Configurar o Dualboot](/guide/Portuguese/4-dualboot-pt.md)
















