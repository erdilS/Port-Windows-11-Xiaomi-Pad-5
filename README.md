# Running Windows on the Xiaomi Pad 5

<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

## ⚠️ **Warning**

We're not responsible for bricked devices, missing recovery partitions, dead microSD cards, dead cats or dogs, nuclear wars or you getting fired because you forgot to boot back in to android for the alarm.

This project is in an early stage, all the files here have been contributed by other users, here you will find a guide with the working files we managed to get. This is a delicate process, do it under your own risk and follow all the steps carefully.

**IF YOU AREN'T COMFORTABLE MODDING YOUR TABLET OR ITS PARTITION TABLE OR YOU ARE PARANOID OF BRICKING YOUR DEVICE CLICK AWAY NOW!!! YOU HAVE BEEN WARNED, YOU ARE ON YOUR OWN IF YOU BRICK YOUR DEVICE!!! AGAIN! YOU HAVE BEEN WARNED!!!**

## Project status

Beta. Most of the hardware works, but some components do not work yet.

#### Features

- [X] Audio
- [X] Battery status
- [X] Bluetooth
- [X] Brightness
- [ ] Camera
- [ ] Charging ``In progress, working partially ``
- [X] Display
- [ ] Suspend / Sleep Mode
- [X] GPU
- [X] Touchscreen
- [X] UFS
- [X] USB ``PD hub needed``
- [X] Wi-Fi
- [ ] Xiaomi Pen and Keyboard support

#### Sensors

- [X] Accelerometer
- [X] Gyroscope
- [X] Light sensor
- [X] Magnetometer
- [X] Proximity

## Guides and requirements

<details> 
<summary><strong>Required Tools/Files</strong></summary>

Human:

- Understand English, Spanish, Turkish, Italian, French or Ukrainian

- Understand how to use TWRP
- Understand how to use CMD
- Functioning brain

PC:

- [Windows on ARM image](https://uupdump.net/) (Windows 11 is recommended)
- [platform-tools](https://developer.android.com/studio/releases/platform-tools).
- [DriverUpdater](https://github.com/WOA-Project/DriverUpdater/releases/) to install the [drivers](https://github.com/map220v/MiPad5-Drivers)

Tablet:

- [UEFI image and TWRP](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/1.0)

 </details>

### Windows installation instructions

<details>

<summary><strong>English</strong></summary>

1 - [Create partitions](guide/English/1-partition-en.md)

2 - [Install Windows](guide/English/2-install-en.md)

 </details>

<details>

<summary><strong>Türkçe</strong></summary>

1 - [Bölümleri oluşturma](guide/Turkish/1-partition-tr.md)

2 - [Windows kurulumu](guide/Turkish/2-install-tr.md)

 </details>

<details>

<summary><strong>Ukrainian</strong></summary>

1 - [Створення розділів](guide/Ukrainian/1-partition-uk.md)

2 - [Встановлення Windows](guide/Ukrainian/2-install-uk.md)

 </details>

<details>

<summary><strong>Español</strong></summary>

1 - [Crear particiones](guide/Español/1-particiones-es.md)

2 - [Instalar Windows](guide/Español/2-instalacion-es.md)

 </details>

<details>

<summary><strong>Français</strong></summary>

1 - [Création des partitions](guide/Francais/1-partition-fr.md)

2 - [Installation de Windows](guide/Francais/2-install-fr.md)

 </details>

<details>

<summary><strong>Italian</strong></summary>

1 - [Creare le partizioni](guide/Italian/1-partizioni-it.md)

2 - [Installare Windows](guide/Italian/2-installazione-it.md)

  </details>

### Other guides:

<details>

<summary><strong>English</strong></summary>

- [If you just want to update the drivers follow these commands](guide/English/update-en.md)
- [Dual booting](guide/English/otherthings-en.md)
- [Uninstalling Windows](guide/English/uninstall-en.md)

 </details>

<details>

<summary><strong>Türkçe</strong></summary>

- [Sadece sürücüleri güncellemek istiyorsanız bu rehberi takip edin](guide/Turkish/update-tr.md)
- [Dual boot işlemleri](guide/Turkish/otherthings-tr.md)
- [Windows&#39;u kaldırmak](guide/Turkish/uninstall-tr.md)

 </details>

<details>

<summary><strong>Ukrainian</strong></summary>

- [Якщо ви хочете оновити драйвера, дотримуйтесь цих команд](guide/Ukrainian/update-uk.md)
- [Подвійне завантаження](guide/Ukrainian/otherthings-uk.md)
- [Видалення Windows](guide/Ukrainian/uninstall-uk.md)

 </details>

<details>

<summary><strong>Español</strong></summary>

- [Si solo quieres actualizar los drivers sigue estos comandos](guide/Español/Actualizar-es.md)
- [Dual boot](guide/Español/Otras-cosas-es.md)
- [Desinstalar Windows](guide/Español/Desinstalar-es.md)

 </details>

<details>

<summary><strong>Français</strong></summary>

- [Mise à jour des drivers uniquement, suivez ce guide](guide/Francais/update-fr.md)
- [Configuration du Dual booting, suivez ce guide](guide/Francais/otherthings-fr.md)
- [Désinstaller Windows, suivez ce guide](guide/Francais/uninstall-fr.md)

 </details>

<details>

<summary><strong>Italian</strong></summary>

- [Se vuoi aggiornare i drivers leggi questa guida](guide/Italian/aggiornare_driver-it.md)

- [Guida per il dualboot](guide/Italian/dualboot-altro-it.md)

- [Disinstallare Windows](guide/Italian/disinstallazione-it.md)
    
 </details>


## Contributors

<details>

<summary><b><strong>Credits</strong></b></summary>

- [Icesito68](https://github.com/Icesito68) ```Made Windows partitioning commands, made original vayu repo and made spanish translation```

- [Map220v](https://github.com/map220v) ```Maintains UEFI and Drivers```
  
- [Renegade Project](https://github.com/edk2-porting) ```Making the core of this project```

- [gus33000](https://github.com/gus33000) ```Providing help, also made base install guide, all of the original drivers and the msc script```

- [Renegade Project Discord members](https://discord.gg/XXBWfag) ```Provided Help```
 
- [MollySophia](https://github.com/MollySophia) ```Helped to fix battery status```

- [bibarub](https://github.com/bibarub) ```Made original bat file for switching Windows to Android```

- [entaromia](https://github.com/entaromia) ```Made application for switching Android to Windows```

- [ciyanogen](https://github.com/ciyanogen) ```Made turkish translation```

- [ArturoGC06](https://github.com/ArturoGC06) ```Made spanish translation```

- [Maxsenza151](https://github.com/Maxsenza151) ```Made italian translation```

- [HeavyMistick](https://github.com/HeavyMistick) ```Made french translation```

- [halal-beef](https://github.com/halal-beef) ```Maintains guide```

 </details>
