<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Windows no Xiaomi Pad 5

## Instalação



### Pré requesitos

- [```Bootloader desbloqueado```](/guide/Portuguese/unlock-bootloader-pt.md)

-  ```Cérebro```
  
- [```Imagem do Recovery```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools)

### Notas:
> [!Warning]\
> Faça um backup de seus arquivos importantes que estiverem no Android antes de começar.
> 
> NÃO REINICIE O TABLET se você acha que fez algo errado, peça por ajuda no [Telegram chat](https://t.me/nabuwoa)
>
> **POR FAVOR NÃO USE VÍDEOS TUTORIAIS DO YOUTUBE OU QUALQUER OUTRA PLATAFORMA! ESTES PODEM ESTAR DESATUALIZADOS E VOCÊ PODE BRICKAR SEU TABLET SEGUINDO OS MESMOS! PRECISA DE UM TUTORIAL EM VÍDEO, USE ESSE (VÍDEO EM INGLÊS) [NEW VIDEO GUIDE](https://youtu.be/BbgTbTGbXYg) DO [ArtoSeVeN](https://www.youtube.com/channel/UCYjwfxlYlJ7Nnzv01oszQvA)**

### Particionando seu dispositivo e fazendo backup da boot.img
> [!NOTE]
> Não sabe como começar? Só descompactar o [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools), e abra o ```cmd (command prompt)``` ou o `powershell` como administrador e digite o seguinte comando, substituindo o "caminho\para_o\platform-tools" com o lacal correto da pasta:
```cmd
cd "caminho\para_o\platform-tools"
```
> Use essa mesma janela em todos os passos.

#### Inicie o recovery usando seu PC com o comando
> Substitua o **caminho\para_o** com o caminho correto do recovery.img
```cmd
fastboot boot caminho\para_o\recovery.img
```
#### Particionando seu dispositivo
> Substitua o **$** com a quantidade de armazenamento que você quer que o Windows tenha (não escreva GB, apenas digite o número)
> 
> Se o comando disser pra fazer de novo, faça
```sh
adb shell partition $
```

### Faça um backup da sua boot.img atual
```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/normal_boot.img" && adb pull /tmp/normal_boot.img
```


#### Verifique se o Android ainda inicia
> Reinicie para verificar se o Android inicia. Se não iniciar, faça um wipe data no recovery e tente novamente.

```cmd
adb reboot
```


### [Próximo passo: Instalar o Root](/guide/Portuguese/2-rootguide-pt.md)
