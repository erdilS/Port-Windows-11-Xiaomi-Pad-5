<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Windows no Xiaomi Pad 5
> [!WARNING]
> **POR FAVOR NÃO USE VÍDEOS TUTORIAIS DO YOUTUBE OU QUALQUER OUTRA PLATAFORMA! ESTES PODEM ESTAR DESATUALIZADOS E VOCÊ PODE BRICKAR SEU TABLET SEGUINDO OS MESMOS! PRECISA DE UM TUTORIAL EM VÍDEO, USE ESSE (VÍDEO EM INGLÊS) [VIDEO GUIDE](https://youtu.be/BbgTbTGbXYg) POR [ArtoSeVeN](https://www.youtube.com/channel/UCYjwfxlYlJ7Nnzv01oszQvA)**

## Instalação
### Pré requesitos
- ```Cérebro```
 
- [```DriveLetterAssigner```](https://github.com/Misha803/My-Scripts/releases/tag/DriveLetterAssigner_NABU)
  
- [```Windows ARM esd```](https://worproject.com/esd) (Selecione - Version:  ```11``` Build:  ```22631.2861``` Architecture:  ```ARM64``` Edition:  ```CLIENT``` Language:  ```selecione seu idioma```)
    
- [```Drivers```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/Drivers)

### Inicie novamente o recovery para começar a instalação do Windows
```cmd
fastboot boot <recovery.img>
```

#### Execute o msc 
> Se o comando disser pra fazer de novo, faça
```cmd
adb shell msc
```

### Atribuindo letras para WINNABU e ESPNABU
> Execute o script **DriveLetterAssigner_NABU** e pressione `Y` no seu teclado para atribuir as letras **X** e **Y** nas partições **WINNABU** e **ESPNABU**

### Instalar Windows
> [!Important]
> Tenha certeza de que está rodando o CMD/Powershell como **Administrador**

> Substitua o `<caminho\para_o\install.esd>` com o caminho correto do arquivo install.esd (também pode estar nomeado como install.wim)
```cmd
dism /apply-image /ImageFile:<caminho\para_o\install.esd> /index:6 /ApplyDir:X:\
```

> Se o erro `Error 87` surgir, verifique o index da sua imagem (install.esd ou install.wim) com o comando `dism /get-imageinfo /ImageFile:<caminho\para_o\install.esd>`, e bustitua o `index:6` com o index correto do Windows 11 Pro da sua imagem

### Instalar os drivers
> Descompacte o arquivo dos Drivers, então execute o arquivo `OfflineUpdater.cmd`

> Se exigido que você digite uma letra, digite a letra da partição **WINNABU** (no caso a letra **X**), aperte enter

#### Crie os arquivos do bootloader do windows para o EFI
> Se um erro acontecer ao copiar os arquivos de boot, verifique com o `diskpart` se o ESPNABU ainda está com a letra Y. Se não estiver com a letra Y, use outra letra (como o K por exemplo) e substitua a letra Y do comando abaixo com a nova letra que você colocou
```cmd
bcdboot X:\Windows /s Y: /f UEFI
```

#### Remova a letra do disco ESPNABU
> Se isso não funcionar, ignore e faça o próximo comando. O disco fantasma vai desaparecer na próxima reinicializção do seu PC.
```cmd
mountvol y: /d
```

### Reboot to Android
```cmd
adb reboot
```

> Set up your device, then go to the last step

## [Último passo: Configurar o Dualboot](/guide/Portuguese/dualboot-pt.md)
















