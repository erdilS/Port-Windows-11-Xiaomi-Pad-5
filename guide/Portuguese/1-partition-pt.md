<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Windows no Xiaomi Pad 5

## Instalação



### Pré requesitos
-  ```Cérebro```
  
- [```Imagem do Recovery```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools)

### Notas:
> [!NOTE]
> Não sabe como começar? Só descompactar o [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools), por exemplo ```"C:\platform-tools"``` e abra o ```cmd (command prompt)``` ou o `powershell` como administrador e digite:
```cmd
cd "caminho\para_o\platform-tools"
```
> Substitua o  `"caminho\para_o\platform-tools"` com a diretório certo para a pasta do platform tools


> [!Warning]\
> Se você apagar alguma partição usando o diskpart depois ou agora, o Windows vai enviar um comando ufs que é mal interpretado CAUSANDO COM QUE A UFS SEJA COMPLETAMENTE FORMATADA (O TABLET SERA BRICKADO)
> 
> Faça um backup de seus arquivos importantes que estiverem no Android antes de começar.
> 
> Todos os comandos foram previamente testados.
> 
> NÃO REINICIE O TABLET se você acha que fez algo errado, peça por ajuda no [Telegram chat](https://t.me/nabuwoa)
>
> **POR FAVOR NÃO USE VÍDEOS TUTORIAIS DO YOUTUBE OU QUALQUER OUTRA PLATAFORMA! ESTES PODEM ESTAR DESATUALIZADOS E VOCÊ PODE BRICKAR SEU TABLET SEGUINDO OS MESMOS! PRECISA DE UM TUTORIAL EM VÍDEO, USE ESSE (VÍDEO EM INGLÊS) [NEW VIDEO GUIDE](https://youtu.be/BbgTbTGbXYg) DO [ArtoSeVeN](https://www.youtube.com/channel/UCYjwfxlYlJ7Nnzv01oszQvA)**


### Particionando seu dispositivo e fazendo backup da boot.img

#### Inicie o recovery usando seu PC com o comando
```cmd
fastboot boot <recovery.img>
```
#### Particionando seu dispositivo

> Se o comando disser pra fazer de novo, faça

> Isso é **opcional**, mas você também pode definir **uma capacidade customizada para a partição do windows (por padrão, o armazenamento é divido igualmente)**

> Para escolher uma capacidade customizada use  ```adb shell partition [VALOR DA CAPACIDADE DA PARTIÇÃO DO WINDOWS EM GB]```

> Não precisa colocar GB no final, só o número

```cmd
adb shell partition
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
