<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Windows no Xiaomi Pad 5

## Re-instalação
Se você não gostou da sua versão do Windows, estragou sua instalação do Windows, ou algo do tipo, você provavelmente vai querer re-instalar o Windows. Por sorte isso é algo muito simples de fazer.

> [!IMPORTANT]
> Lembre-se, isso vai apagar todos os seus arquivos apenas do Windows. Se você precisa fazer um backup de algum arquivo na partição do Windows, você pode montar a partição usando o app [WOA Helper](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/woahelper.apk) e copiar os arquivos que você quer salvar


### Pré requesitos
- ```Partições do Windows e inicialização``` (*Se não for o caso, [esqueça esse guia e use esse aqui](/guide/Portuguese/1-partition-pt.md)*)

- [```Iamgem do Recovery```](https://github.com/ArKT-7/twrp_device_xiaomi_nabu/releases/tag/mod-win)

- [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools)


#### Reboot into fastboot mode
- Boot your NABU into **fastboot mode** by holding down the **`volume down`** button while rebooting with a USB cable connected
- Or, if you have USB debugging enabled, run the below command while booted into Android.
```cmd
adb reboot bootloader
```

### Boot modified recovery
> Replace `path\to\recovery.img` with the actual path of the modded recovery image
```cmd
fastboot boot path\to\recovery.img
```

### Formatando as partições
> Se o comando disser pra fazer de novo, faça
```cmd
adb shell format
```

## [Próximo passo: Re-instalar o Windows](/guide/Portuguese/3-install-pt.md#execute-o-msc)













