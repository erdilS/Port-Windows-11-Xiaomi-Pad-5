#### Démarrez votre appareil en mode recovery avec votre PC

```cmd
fastboot boot <recovery.img>
```

## Placez le script "msc" dans /sbin/

```cmd
adb push msc.sh /sbin/
```

### Exécutez le script "msc"

```cmd
adb shell sh /sbin/msc.sh
```

## Assignez les lettres aux disques

#### Lancez le gestionnaire de disque Windows

> Quand la tablette est détectée, utilisez la commande

```cmd
diskpart
```

### Assignez la lettre `X` au volume Windows

#### Sélectionnez les volumes Windows du téléphone

> Utilisez la commande `list volume` pour le trouver, il s'agit généralement du dernier volume.

```diskpart
select volume <number>
```

#### Assignez la lettre x

```diskpart
assign letter=x
```

### Quittez diskpart:

```diskpart
exit
```

# Installez les drivers

> Remplacez `<nabudriversfolder>` par le chemin du dossier contenant les drivers

> Ovrez une fenêtre cmd avec les droits administrateurs

```cmd
driverupdater.exe -d <nabudriversfolder>\definitions\Desktop\ARM64\Internal\nabu.txt -r <nabudriversfolder> -p X:
```

##### Démarrez l'appareil en utilisant l'image bootable UEFI de Windows

```
fastboot flash boot <uefi.img>
```

# Fini!
