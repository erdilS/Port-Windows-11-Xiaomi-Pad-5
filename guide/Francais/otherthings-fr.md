## Les prés-requis pour le Dual Boot

- Un cerveau
- Ne marche que sur le slot A!
- Avoir un appareil rooté et un backup du fichier de boot de votre appareil rooté
- [Télécharger ces fichiers](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/dualboot)

### Côté Windows (sur votre tablette):

- Installer [Cygwin](https://www.cygwin.com/setup-x86_64.exe) avec l'outil coreutils (il est présent par défaut)
- Renommer votre fichier de boot (boot file) : boot.img
- Placez votre boot Android dans à la racine du disque C:\ (C:\boot.img)
- Exécuter le fichier "bat" avec les droits administrateurs ou créez un raccourci windows ayant les droits administrateurs

### Côté Android :

- Installer l'application switchtowin.apk to device.
- Renommer votre fichier UEFI : boot.img.
- Placer le fichier UEFI dans le dossier /sdcard/windows (/sdcard/windows/boot.img).
- Lancer l'application et lui donner les privileges de root.
- Cliquez sur le bouton "Switch to Windows" lorsque vous voulez démarrer Windows.
