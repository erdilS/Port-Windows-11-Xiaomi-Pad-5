# Installation de Windows

### Démarrez le recovery pour installer Windows

```cmd
fastboot boot <recovery.img>
```

### Placez le script "msc" dans /sbin/

```cmd
adb push msc.sh /sbin/
```

### Executez le script "msc"

```cmd
adb shell sh /sbin/msc.sh
```

## Assignez les lettres aux disques

#### Lancez le gestionnaire de disque Windows

> Quand la tablette est détectée, utilisez la commande suivante

```cmd
diskpart
```

### Assignez la lettre `X` au volume Windows

#### Sélectionnez les volumes Windows du téléphone

> Utilisez la commande `list volume` pour les trouver, il s'agit des volumes nommés "WINNABU" et "ESPNABU"

```diskpart
select volume <number>
```

#### Assignez la lettre X

```diskpart
assign letter=x
```

### Assignez la lettre `Y` au volume ESP

#### Selectionnez le volume ESP du téléphone

> Utilisez la commande `list volume` pour le trouver, il s'agit généralement du dernier volume.

```diskpart
select volume <number>
```

#### Assignez la lettre Y

```diskpart
assign letter=y
```

### Quittez diskpart

```diskpart
exit
```

## Installation

> Remplacez `<path/to/install.wim>` par le chemin actuel du fichier "install.wim".

> `install.wim` se trouve dans le dossier "sources" contenu dans l'archive ISO.
>
> Vous pouvez le récupérer en montant l'archive ISO sur le PC ou en extrayant l'archive.

```cmd
dism /apply-image /ImageFile:<path/to/install.wim> /index:1 /ApplyDir:X:\
```

# Installez les drivers

> Remplacez `<nabudriversfolder>` par le chemin du dossier contenant les drivers

```cmd
driverupdater.exe -d <nabudriversfolder>\definitions\Desktop\ARM64\Internal\nabu.txt -r <nabudriversfolder> -p X:
```

# Créez le fichier de démarrage de Windows pour l'EFI

```cmd
bcdboot X:\Windows /s Y: /f UEFI
```

# Autorisez les drivers non signés

> Si vous ne faites pas cela, vous aurez un blue screen au démarrage (BSOD)

```cmd
bcdedit /store Y:\EFI\Microsoft\BOOT\BCD /set {default} testsigning on
```

# Démarrez l'appareil sous Windows

### Réalisez un backup de votre "boot image" d'origine

```cmd
adb shell "dd if=/dev/block/bootdevice/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/boot.img"
```

##### Récupérez le backup sur votre PC

```cmd
adb pull /tmp/boot.img
```

### Redémarrez en bootloader

```cmd
adb reboot bootloader
```

### Flashez l'image UEFI à l'aide de TWRP

```cmd
fastboot flash boot boot-nabu.img
```

# Redémarrez l'appareil sur Android

> Récupérez le backup des fichiers de démarage (boot image) et flashez les avec fastboot

```cmd
fastboot flash boot boot.img
```

# Fini!
