<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Windows no Xiaomi Pad 5
> [!WARNING]
> **POR FAVOR NÃO USE VÍDEOS TUTORIAIS DO YOUTUBE OU QUALQUER OUTRA PLATAFORMA! ESTES PODEM ESTAR DESATUALIZADOS E VOCÊ PODE BRICKAR SEU TABLET SEGUINDO OS MESMOS! PRECISA DE UM TUTORIAL EM VÍDEO, USE ESSE (VÍDEO EM INGLÊS) [VIDEO GUIDE](https://youtu.be/BbgTbTGbXYg) POR [ArtoSeVeN](https://www.youtube.com/channel/UCYjwfxlYlJ7Nnzv01oszQvA)**

## Instalação
> [!NOTE]
> É recomendado que use o CMD ou powershell como administrador, e então acessar a pasta platform-tools usando o comando `cd C:\caminho\para_o\platform-tools`, substituindo o \caminho\para_o com o caminho correto para a pasta platform-tools.
> Use a mesma janela para todos os comandos, não feche a janela em nenhum momento.

### Pré requesitos
- ```Cérebro```
  
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

### Inicie o gerenciador de discos do Windows
> Quando o seu Xiaomi Pad 5 for detectado como um disco use
```cmd
diskpart
```

#### Selecione o volume Windows do tablet
> Use `list volume` para encontrá-lo, é o que tem o nome de **WINNABU**
```diskpart
select volume <número>
```

#### Atribua a letra X
```diskpart
assign letter x
```

#### Selecione o volume ESP do tablet
> Use `list volume` para encontrá-lo, é o que tem o nome de **ESPNABU**
```diskpart
select volume <número>
```

#### Atribua a letra Y
```diskpart
assign letter y
```

#### Saia do diskpart 
```diskpart
exit
```

### Instalar Windows
> Substitua o `<caminho\para_o\install.esd>` com o caminho correto do arquivo install.esd (também pode estar nomeado como install.wim)
```cmd
dism /apply-image /ImageFile:<caminho\para_o\install.esd> /index:6 /ApplyDir:X:\
```

> Se o erro `Error 87` surgir, verifique o index da sua imagem (install.esd ou install.wim) com o comando `dism /get-imageinfo /ImageFile:<caminho\para_o\install.esd>`, e bustitua o `index:6` com o index correto do Windows 11 Pro da sua imagem

### Instalar os drivers
> Se aparecer `"Automatic WINNABU detection failed! Enter Drive Letter manually"` digite **`X`**
```cmd
 abra a pasta dos Drivers e inicie o OfflineUpdater.cmd
```
> If any errors appear under **Installing App Packages**, ignore them and continue

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
















