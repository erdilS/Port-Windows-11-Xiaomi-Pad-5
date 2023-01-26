Cette étape est nécessaire, elle permet de créer les partitions nécessaires à l'installation de Windows.

## Notes:

> **Attention** si vous supprimez, maintenant ou plus tard, une partition avec l'outil "diskpart", Windows enverra une commande ufs qui sera mal interprétée et qui supprimera l'intégralitée de votre ufs.

- Vos données personnelles vont être effacées ! Sauvegardez les maintenant si vous souhaitez les conserver.
- Les commandes suivantes ont déjà été testées.
- Ignorez les messages de prévention de type `udevadm`.
- Ne pas répéter une  même commande 2 fois de suite.
- En mode recovery, votre écran ne sera pas fonctionnel.
- NE PAS REDEMARRER VOTRE APPAREIL, si vous pensez avoir fait une erreur, demandez de l'aide sur le [groupe Télégram](https://t.me/nabuwoa) .

#### Démarrez votre appareil en mode recovery avec votre PC

```cmd
fastboot boot <recovery.img>
```

> Si vous avez déjà TWRP installé sur votre appareil, appuyer simultanément sur les boutons "power" et "volume +" au démarrage.

#### Démontez l'ensemble des partitions

```cmd
adb shell twrp unmount /data
```

## Placez le script "parted" dans /tmp/

> Afin de répartir les partitions

```cmd
adb push parted /tmp/
```

## Lancez ADB shell

```cmd
adb shell
```

### Redimensionnez la table des partitions

> Pour adaptez les partitions Windows

```sh
sgdisk --resize-table 64 /dev/block/sda
```

### Modifiez les permissions du script "parted"

```sh
chmod 755 /tmp/parted
```

### Démarrez du script "parted"

```sh
/tmp/parted /dev/block/sda
```

### Supprimez la partition contenant les données personnelles (`userdata`)

> Vous pouvez vérifier que la partition 31 est bien celle contenant les données personnelles en exécutant la commande `print all` avant d'exécuter la commande suivante

```sh
rm 31
```

### Création des partitions

> Si vous avez n'importe quels messages d'erreurs vous demandant de choisir entre "ignorer" ou "annuler", tappez uniquement "i" puis "entrer"

#### Pour les appareils ayant une capacitée de stockage de 128Go :

- Créez une partition ESP (elle stockera les fichiers permettant le démarrage de Windows et les fichiers EFI)

```sh
mkpart esp fat32 10.9GB 11.4GB
```

- Créez la partition principale dans laquelle Windows sera installé

```sh
mkpart win ntfs 11.4GB 70.2GB
```

- Créez la partition contenant les données Android

```sh
mkpart userdata ext4 70.2GB 126GB
```

#### Pour les appareils ayant une capacitée de stockage de 256Go :

- Créez une partition ESP (elle stockera les fichiers permettant le démarrage de Windows et les fichiers EFI)

```sh
mkpart esp fat32 10.9GB 11.4GB
```

- Créez la partition principale dans laquelle Windows sera installé

```sh
mkpart win ntfs 11.4GB 120.8GB
```

- réez la partition contenant les données Android

```sh
mkpart userdata ext4 120.8GB 254GB
```

### Rendre la partition ESP bootable pour permettre à l'image EFI de la détecter

```sh
set 31 esp on
```

### Quittez le script "parted"

```sh
quit
```

### Redémarrez l'appareil en mode "bootloader"

```sh
reboot bootloader
```

### Lancez le mode recovery

```cmd
fastboot boot <recovery.img>
```

### Démarrez une nouvelle fois ADB shell sur votre PC

```cmd
adb shell
```

### Formatez les partitions

- Formatez la partition ESP en FAT32

```sh
mkfs.fat -F32 -s1 /dev/block/bootdevice/by-name/esp -n ESPNABU
```

- Formatez la partition Windows en NTFS

```sh
mkfs.ntfs -f /dev/block/bootdevice/by-name/win -L WINNABU
```

- Formatez la partition "données personnelles"

```sh
mke2fs -t ext4 /dev/block/bootdevice/by-name/userdata
```

### Testez si Android démarre

Redémarrez votre appareil, et regardez si Android fonctionne toujours. Si il ne démarre pas ou tourne un boucle, utilisez un recovery (MIUI ou autres) afin de nettoyer les données.

## [Prochaine étape : Installation de Windows](guide\Francais\2-install-fr.md)
