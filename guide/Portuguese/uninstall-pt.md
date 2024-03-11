<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Windows no the Xiaomi Pad 5

## Desinstalação

### Porque isso é necessário?

Se você quer desinstalar o Windows, esse guia é necessário já que você NÃO pode simplesmente apagar as partições do Windows manualmente.

Se você pretende bloquear o bootloader, é necessário recuperar a tabela de partição padrão.

### Pré requesitos

- [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools)
  
- [```Imagem do Recovery```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

#### Incie o recovery
```cmd
fastboot boot <recovery.img>
```

#### Recupere a tabela de partições
> [!Warning]
> Isso vai limpar todos os arquivos do Android, faça um backup se necessário.
```cmd
adb shell restore
```

### Inicie o Android 
```cmd
adb reboot 
```
## Pronto!
