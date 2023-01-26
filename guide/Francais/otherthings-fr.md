## Les prérequis pour le Dual Boot

- Un cerveau
- Ne marche que sur le slot A!
- Avoir un appareil rooté et un backup du fichier de boot de votre appareil rooté
- [Téléchargez ces fichiers](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/dualboot)

### Côté Windows (sur votre tablette):

- Installez [Cygwin](https://www.cygwin.com/setup-x86_64.exe) avec l'outil coreutils (il est présent par défaut)
- Renommez votre fichier de boot (boot file) : boot.img
- Placez votre boot Android dans à la racine du disque C:\ (C:\boot.img)
- Exécutez le fichier "bat" avec les droits administrateurs ou créez un raccourci windows ayant les droits administrateurs

### Côté Android :

- Installez l'application switchtowin.apk to device.
- Renommez votre fichier UEFI : boot.img.
- Placez le fichier UEFI dans le dossier /sdcard/windows (/sdcard/windows/boot.img).
- Lancez l'application et lui donnez les privileges de root.
- Cliquez sur le bouton "Switch to Windows" lorsque vous voulez démarrez Windows.
