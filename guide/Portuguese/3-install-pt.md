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

- [```Imagem do UEFI```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v3.img)
  
- [```Windows ARM esd```](https://worproject.com/esd) (Selecione - Version:  ```11``` Build:  ```22631.2861``` Architecture:  ```ARM64``` Edition:  ```CLIENT``` Language:  ```selecione seu idioma```)
    
- [```Drivers```](https://github.com/map220v/MiPad5-Drivers/releases/latest)

### Inicie novamente o recovery para começar a instalação do Windows

```cmd
fastboot boot <recovery.img>
```

#### Execute o msc 

> Se o comando disser pra fazer de novo, faça

```cmd
adb shell msc
```
### Atribua letras aos discos
  

#### Inicie o gerenciador de discos do Windows

> Quando o seu Xiaomi Pad 5 for detectado como um disco use

```cmd
diskpart
```


#### Atribua a letra `X` para o volume Windows

#### Selecione o volume Windows do tablet
> Use `list volume` para encontrá-lo, é o que tem o nome de "WINNABU"

```diskpart
select volume <número>
```

#### Atribua a letra X
```diskpart
assign letter x
```

### Atribua a letra `Y` para o volume ESP

#### Selecione o volume esp do tablet
> Use `list volume` para encontrá-lo, é o que tem o nome de "ESPNABU"

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

  
  

### Instalar

> Substitua o `<caminho\para_o\install.esd>` com o caminho correto do arquivo install.esd (também pode estar nomeado como install.wim)

```cmd
dism /apply-image /ImageFile:<caminho\para_o\install.esd> /index:6 /ApplyDir:X:\
```

> Se o erro `Error 87` surgir, verifique o index da sua imagem (install.esd ou install.wim) com o comando `dism /get-imageinfo /ImageFile:<caminho\para_o\install.esd>`, e bustitua o `index:6` com o index correto do Windows 11 Pro da sua imagem


### Instalar os Drivers

> Você pode fazer o download dos drivers [aqui](https://github.com/map220v/MiPad5-Drivers/releases/latest)

> Se aparecer `"Automatic WINNABU detection failed! Enter Drive Letter manually"` digite **`X`**

```cmd
 abra a pasta dos Drivers e inicie o OfflineUpdater.cmd
```

### Crie os arquivos do bootloader do windows para o EFI
> Se um erro acontecer ao copiar os arquivos de boot, verifique com o `diskpart` se o ESPNABU ainda está com a letra Y. Se não estiver com a letra Y, use outra letra (como o K por exemplo) e substitua a letra Y do comando abaixo com a nova letra que você colocou
```cmd
bcdboot X:\Windows /s Y: /f UEFI
```

## Remova a letra do disco ESPNABU
> Se isso não funcionar, ignore e faça o próximo comando. O disco fantasma vai desaparecer na próxima reinicializção do seu PC.
```cmd
mountvol y: /d
```


## Iniciando o Windows

### Faça um backup da boot.img com root do Android

```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/rooted_boot.img" && adb pull /tmp/rooted_boot.img
```

### Reinicie para o bootloader

```cmd
adb reboot bootloader
```

### Faça o download e o flash da imagem UEFI
> Download da [Imagem UEFI](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v3.img)

```cmd
fastboot flash boot <caminho da imagem UEFI>
```

## Inicie o Windows
```cmd
fastboot reboot
```

> [!NOTE]
> Na primeira inicialização do Windows, ele não vai detectar redes Wi-Fi. Segure o botão de desligar do tablet até o mesmo reiniciar. Após ele iniciar novamente, o Wi-Fi vai funcionar. Se o pop-up "Não foi possível conectar" surgir, pressione tentar novamente até funcionar (pode precisar de até 5 tentativas)

### Iniciando o Android novamente
Após configurar o Windows, use a opção de reiniciar do Windows (NÃO USE DESLIGAR), enquanto ele reinicia, segure `volume menos` + `botão power` para iniciar o fastboot
> Use a imagem de boot do Android que você fez o backup para iniciar ele novamente

```cmd
fastboot flash boot rooted_boot.img
```

```cmd
fastboot reboot
```

### [Último passo: Configurar o Dualboot](/guide/Portuguese/dualboot-pt.md)
