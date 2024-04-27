<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Apps úteis e algumas instruções pra o Windows no Xiaomi pad 5

## Esconder o disco D: (Partição modem)
> [!NOTE]
> Isso é recomendado pois algum programa pode tentar modificar a partição, o que não pode acontecer

- Abra uma janela do cmd (prompt de comando) e use ```diskpart```
- Use ```list volume``` para ver todos os volumes disponíveis
- Selecione o disco com a letra D usando ```select volume $```, substituindo o "$" pelo número do volume
- Remova a letra D com ```remove letter d```
- Saia do diskpart usando ```exit```

#### Concluído!


## Desativando o modo USB host
> [!Warning]
> Quando o modo USB host está ligado, os dispositovos conectados no USB do tablet vão ser alimentados pelo próprio tablet.
> Sendo assim dispositivos que não têm alimentação/que precisam de alimentação/não tem bateria própria NÃO vão funcionar quando o modo USB host estiver desativado

Execute o [Controle de USB Host](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/USBHost) para ativar/desativar o modo USB host, no programa confirme se você quer ativar/desativar o modo USB host 

#### Concluído!


## Desativando o secureboot
> Caso você queira atualizar os drivers sem um outro PC

[Guia para desativar o secureboot](/guide/Portuguese/disable-secureboot-pt.md)

#### Concluído!


## Instalando o Microsoft Office / Microsoft 365
- Faça o Download do [Arquivo ISO](https://drive.google.com/file/d/1-i-0RraTSgwxqQSWal3uYWCen1TjK6d3/view?usp=drivesdk) to the tablet
- Use o botão direito do mouse no arquivo iso para montar e abrir no explorer
- Execute o programa ```Office Tool Plus.exe``` para iniciar o wizard de instalação
- Na janela que surgir, pressione `Yes`
- Espere a instalação terminar

#### Concluído!


## Ativar o Windows / Office
Siga as instruções do Massgravel [aqui](https://github.com/massgravel/Microsoft-Activation-Scripts)

#### Concluído!


## Como usar o Flash traseiro no Windows 
 - Faça o download do arquivo [Flashlight.7z](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/flashlight_fix.7z) e descompacte o arquivo em qualquer pasta
> Execute o flashlight.exe para ativar o Flash
> Pressione qualquer tecla pra desativar

#### Concluído!




















