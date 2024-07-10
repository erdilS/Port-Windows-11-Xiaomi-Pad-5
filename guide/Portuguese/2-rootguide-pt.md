<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Windows no Xiaomi Pad 5

## Conseguindo root 
> [!NOTE]
> **Se você já tem root, pode pular para o próxmo passo**

### Pré requesitos
- ```Cérebro```
  
- [```A boot.img do Android```](/guide/Portuguese/1-partition-pt.md#fa%C3%A7a-um-backup-da-sua-bootimg-atual) (que você fez o backup seguindo a página anterior)


### Patch da boot.img com o magisk
- Copie o arquivo ```normal_boot.img``` da pasta ```platform tools``` para o armazenamento do tablet 

- Faça o download e instale o [Magisk app](https://github.com/topjohnwu/Magisk/releases/latest) no tablet
  
-  Abra o Magisk e selecione a opção ```Instalar```. Selecione a opção ```Selecione e corrija um arquivo``` e procure o arquivo ```normal_boot.img``` que voçê copiou para o tablet. Aperte a opção ```VAMOS LÁ``` e espere o processo de patch finalizar.
  
- Copie o arquivo ```magisk_patched....img``` que está na pasta ```Downloads``` no tablet para a pasta ```platform tools``` no seu PC. 

- Reinicie no modo fastboot
  
- Abra o cmd (command prompt) na pasta platform tools 

 ### Faça o flash do magisk_patched.img
 > Substitua o `<magisk_patched.img>` com o nome (ou caminho) que está no ```magisk_patched.img``` que você copiou do tablet.
```cmd
fastboot flash boot <magisk_patched.img>
```

### [Próximo Passo: Instalando o Windows](/guide/Portuguese/3-install-pt.md)
