<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Windows no the Xiaomi Pad 5

## Resolvendo problemas

## Não consigo carregar o tablet no Windows
> [!WARNING]
> Não use um adaptador ou hub USB com entrada pra carregador, seu tablet pode ser danificado. Se você usa um adaptador ou hub USB com entrada para carregador, por favor use o [guia para desativar o modo USB host](/guide/Portuguese/Additional-materials-pt.md#desativando-o-modo-usb-host)

O carregamento no Windows funciona apenas com alguns cabos específicos. Alguns cabos que funcionam são; o cabo original que vem com o Poco X3 Pro (Pode ser identificado pelo pino laranja/vermelho na porta USB-A), e o cabo "Nimaso 100W USB-C to USB-C fast charging cable".


## O Tablet Inicia o Android, mas não o modo bootloader

### Pré requesitos:

- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)

> [!WARNING]
 Provavelmente isso não vai ajudar muito, já que o Xiaomi Pad 5 não tem um custom recovery que funcione perfeitamente. E também como a maioria dos dispositivos com o esquema A/B não temos um instalador do TWRP em zip etc. E você não vai conseguir iniciar uma imagem de recovery, devido o bootloader quebrado. Se você já tem uma rom AOSP, provavelmente a mesma vai ter um recovery AOSP instalado que você pode acessar, assim você pode seguir os seguintes passos. Se você usa a MIUI sem root, esses guia não vai te ajudar.
>
> Então por favor não use nomes com espaços e caracteres especiais nos seus discos e partições internas, e se possível use apenas os nomes ESPNABU e WINNABU, que já foram testados milhares de vezes. Se você perdeu o fastboot por usar nomes diferenciados ou usa a MIUI sem root, você só vai conseguir recuperar ao estado de fábrica usando o modo EDL, que apenas funciona com uma conta autorizada, que é um serviço pago.


Isso é causado pelo fato do fastboot não suportar certos formatos de nomes usados nas partições, para consertar:

- Inicie o recovery

- Conecte o tablet ao PC

- Abra o cmd no PC

- Use ```adb shell```

- Use ```parted```

- Use ```print``` para listar todas as partições

- Procure por partições que tem espaço no nome, por exemplo "Basic Data Partition" e confira o número do volume/partição

- Agora use ```rm <vol number>``` por exemplo ```rm 99```


## fsa4480.sys BSOD (tela azul) ao iniciar o Windows

- Abra a pasta do instalador dos Drivers

- Remova a pasta ```components\QC8150\Device\DEVICE.SOC_QC8150.NABU\Drivers\USB```

- Instale os Drivers novamente

- Inicie a imagem da UEFI

- Deixe o Windows iniciar, e instale novamente os Drivers que você modificou


## Bootloop ao iniciar ao mudar para o Android

- Use o fastboot

- ```fastboot set_active other```

- ```fastboot flash boot <boot.img>```

- ```fastboot reboot```
