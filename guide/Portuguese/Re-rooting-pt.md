<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Windows no the Xiaomi Pad 5

## Refazendo o Root no Android
Este Guia é para quando uma atulizacão da MIUI/Hyper OS remove o root.

### Pré requisitos
- [```Imagem do Recovery```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)
  
- [```Android Platform Tools```](https://developer.android.com/studio/releases/platform-tools)

### Inicie o recovery usando seu PC com o comando
```cmd
fastboot boot <recovery.img>
```

### Faça um backup da sua boot.img atual
```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/normal_boot.img" && adb pull /tmp/normal_boot.img
```

### Reinicie para o Android
```cmd
adb reboot
```

### Patch boot 
- Copie o arquivo ```normal_boot.img``` da pasta ```platform tools``` para o armazenamento do tablet 
- Abra o Magisk e selecione a opção ```Instalar```. Selecione a opção ```Selecione e corrija um arquivo``` e procure o arquivo ```normal_boot.img``` que voçê copiou para o tablet. Aperte a opção ```VAMOS LÁ``` e espere o processo de patch finalizar.
- Copie o arquivo ```magisk_patched....img``` que está na pasta ```Downloads``` no tablet para a pasta ```platform tools``` no seu PC. 
- Reinicie no modo fastboot
- Abra o cmd (command prompt) na pasta platform tools

### Faça o flash do magisk_patched.img 
 > Substitua o `<magisk_patched.img>` com o nome (ou caminho) que está no ```magisk_patched.img``` que você copiou do tablet.
```cmd
fastboot flash boot <magisk_patched.img>
```

### Atualize a boot.img no C:\ do Windows
- Reinicie para o Android
- Abra o ```WOA Helper```
- Monte o ```Windows```
- Em qualquer gerenciador de arquivos, vá na pasta ```Windows``` 
- Apague a ```boot.img```

> [!NOTE]
> **A nova boot.img vai ser gerada no C:\ na próxima inicialização**

## Concluído!















