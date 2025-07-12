<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Windows no Xiaomi Pad 5

## Desativando o secureboot
> [!Important]
> Apenas use esse guia se você quer desativar o secureboot.

### Pré requesitos
- ```Cérebro```

- [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools)

- [```Imagem do Recovery```](https://github.com/ArKT-7/twrp_device_xiaomi_nabu/releases/tag/mod-win)

- [```Imagem UEFI (Secureboot off)```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/XXXnabu-NoSecureboot-v4.img)

## Vantagens e desvantagens de ter secureboot
> Por padrão, ele já vem ativado, nada precisa ser feito se você quer assim

##### Vantagens e desvantagens de ter secureboot ativado
- √ Sem marca d'água na tela
- √ Progrmas que NÃO funcionam no Modo de teste, vão funcionar normalmente
- √ Você pode atulizar o Windows de uma versão para outra no próprio Windows Update
- × Você NÃO pode atualizar os Drivers sem usar um outro PC

##### Vantagens e desvantagens de ter secureboot desativado
- √ Você pode atulizar os Drivers sem precisar de um outro PC
- × Marca d'água do modo de teste na tela
- × Alguns programas/jogos podem não funcionar
- × Você NÃO pode atulizar o Windows pelo próprio Windows Update

## Desativando o secureboot

#### Faça um backup da imagem de inicialização do Android
> Você vai precisar iniciar o Android, se já fez um backup, pode pular esse passo

Use a função `Backup Android boot` no app WOA Helper, ou inicie o recovery e execute
```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/rooted_boot.img" && adb pull /tmp/rooted_boot.img
```

#### Inicie o recovery
> Substitua o <caminho\para_o\recovery> com o caminho correto para o arquivo da imagem do recovery 
```cmd
fastboot boot <caminho\para_o\recovery.img>
```

#### Execute o msc
> Quando o seu Xiaomi Pad 5 iniciar no modo recovery use
```cmd
adb shell msc
```

#### Inicie o gerenciador de discos do Windows
> Quando o seu Xiaomi Pad 5 for detectado como um disco use
```cmd
diskpart
```

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

#### Modifique os arquivos de inicialização
> Para ativar o modo de teste
```cmd
bcdedit /store Y:\EFI\Microsoft\BOOT\BCD /set "{default}" testsigning on
```

#### Removendo o SiPolicy
> Assumindo que você está desativando o secureboot em uma instalação existente, você precisa apagar esse arquivo para o Windows iniciar
```cmd
del Y:\EFI\Microsoft\Boot\SiPolicy.p7b
```

#### Remova a letra do disco ESPNABU
>  Se isso não funcionar, ignore e faça o próximo comando. O disco fantasma vai desaparecer na próxima reinicializção do seu PC.
```cmd
mountvol y: /d
```

#### Reinicie para o fastboot
```cmd
adb reboot bootloader
```

#### Fazendo o flash da UEFI
> Tenha certeza de que está usando a UEFI com o secureboot desativado, substitua <caminho\para_o\uefi-NoSecureboot-v3.img> com o caminho correto para a imagem UEFI
```cmd
fastboot flash boot <caminho\para_o\uefi-NoSecureboot-v3.img>
```

> [!Important]
> Não esqueça de substituir a imagem UEFI na pasta UEFI no Android, para não fazer o flash da imagem UEFI antiga por acidente

#### Inicie o Windows novamente
```cmd
fastboot reboot
```

## Concluído!
