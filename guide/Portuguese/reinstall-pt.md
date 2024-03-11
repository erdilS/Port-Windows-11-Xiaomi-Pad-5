<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Windows no the Xiaomi Pad 5

## Re-instalação
Se você não gostou da sua versão do Windows, estragou sua instalação do Windows, ou algo do tipo, você provavelmente vai querer re-instalar o Windows. Por sorte isso é algo muito simples de fazer.

> [!IMPORTANT]
> Lembre-se, isso vai apagar todos os seus arquivos apenas do Windows. Se você precisa fazer um backup de algum arquivo na partição do Windows, você pode montar a partição usando o app [WOA Helper](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/woahelper.apk) app and manually copying any files you wish to keep


### Pré requesitos

- ```Partições do Windows e inicialização``` (*Se não for o caso, [esqueça esse guia e use esse aqui](/guide/Portuguese/1-partition-pt.md)*)

- [```Iamgem do Recovery```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools)


### Inicie o recovery para formatar o Windows e a partição de inicialização

```cmd
fastboot boot <recovery.img>
```

### Formatando as partições
> Se o comando disser pra fazer de novo, faça
```cmd
adb shell format
```
## [Próximo passo: Re-instalar o Windows](/guide/Portuguese/3-install-pt.md#execute-o-msc)
