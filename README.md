# Running Windows on the Xiaomi Pad 5

<img align="right" src="https://github.com/wormstest/src_vayu_windows/blob/main/Vayu-Windows11 (3).png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

## ⚠️ **Warning**

We're not responsible for bricked devices, missing recovery partitions, dead microSD cards, dead cats or dogs, nuclear wars or you getting fired because you forgot to boot back in to android for the alarm.

This project is in an early stage, all the files here have been contributed by other users, here you will find a guide with the working files we managed to get. This is a delicate process, do it under your own risk and follow all the steps carefully.

**IF YOU AREN'T COMFORTABLE MODDING YOUR PHONE OR ITS PARTITION TABLE OR YOU ARE PARANOID OF BRICKING YOUR DEVICE CLICK AWAY NOW!!! YOU HAVE BEEN WARNED, YOU ARE ON YOUR OWN IF YOU BRICK YOUR DEVICE!!! AGAIN! YOU HAVE BEEN WARNED!!!**

## Project status

Beta. Most of the hardware works, but some components do not work yet.

#### Features

- [ ] Audio ```Only by USB or Bluetooth```
- [x] Battery status
- [x] Bluetooth
- [x] Brightness
- [ ] Camera
- [ ] Charging ```In progress, working partially ```
- [x] Display
- [ ] FM
- [x] GPU
- [x] Touchscreen
- [x] UFS
- [x] USB ```PD hub needed```
- [x] Wi-Fi

#### Sensors
- [x] Accelerometer
- [x] Gyroscope
- [x] Light sensor
- [x] Magnetometer
- [x] Proximity


## Guides and requirements

<details> 
<summary><strong>Required Tools/Files</strong></summary>

Human:

- Understand English, Spanish or Russian 

- Understand how to use TWRP

- Understand how to use CMD

- Functioning brain

PC:

- [Windows on ARM image](https://uupdump.net/) (Windows 11 is recommended)

- [platform-tools](https://developer.android.com/studio/releases/platform-tools).

- [DriverUpdater](https://github.com/WOA-Project/DriverUpdater/releases/) to install the [drivers](https://github.com/map220v/MiPad5-Drivers)

Tablet:

- [UEFI image and TWRP](https://github.com/Icesito68/Port-Windows-11-Xiaomi-Pad-5/releases/latest)

</details> 


### Windows installation instructions

<details> 

<summary><strong>English</strong></summary>

1 - [Create partitions](guide/English/1-partition-en.md)

2 - [Install Windows](guide/English/2-install-en.md)
  
</details> 
  
<details> 

<summary><strong>Español</strong></summary>

1 - [Crear particiones](guide/Español/1-particiones-es.md)

2 - [Instalar Windows](guide/Español/2-instalacion-es.md)
  
</details> 

<details> 
  
<summary><strong>Русский</strong></summary>

1 - [Создание разделов](/guide/Russian/1-partition-ru.md)

2 - [Установка Windows](/guide/Russian/2-install-ru.md)
  
</details> 

### Other guides:

<details> 

<summary><strong>English</strong></summary>

- [If you just want to update the drivers follow these commands](guide/English/update-en.md)
  
</details> 

<details> 

<summary><strong>Español</strong></summary>

- [Si solo quieres actualizar los drivers sigue estos comandos](guide/Español/Actualizar-es.md)
  
</details> 

<details> 

<summary><strong>Русский</strong></summary>

- [Если вы хотите обновить драйвера, следуйте этим командам](guide/Russian/update-ru.md)

</details> 

## Contributors

<details> 

<summary><b><strong>Credits</strong></b></summary>

- [Icesito68](https://github.com/Icesito68) ```Made Windows partitioning commands and made this repo```

- [Map220v](https://github.com/map220v) ```Provided help and vayu UEFI uses nabu UFS patches and ACPI and also ported mi pad 5 drivers```

- [Degdag](https://github.com/degdag) ```Improves UEFI and ported drivers```

- [halal-beef](https://github.com/halal-beef) ```Built EDK2 and modified it enough to boot Windows, also ported drivers```
  
- [Renegade Project](https://github.com/edk2-porting) ```Making the core of this project```

- [gus33000](https://github.com/gus33000) ```Providing help, also made base install guide, all of the original drivers and the msc script```

- [Renegade Project Discord members](https://discord.gg/XXBWfag) ```Provided Help```
 
- [ArturoGC06](https://github.com/ArturoGC06) ```Helped in the beginning of the project to the translations and gave Windows data```

- [SebastianZSXS](https://github.com/SebastianZSXS) ```Helped to patch Windows PE```

- [MollySophia](https://github.com/MollySophia) ```Helped to fix battery status```

- [haouarihk](https://github.com/haouarihk) ```Great suggestions on the command notes, also made the new guide```

- [bibarub](https://github.com/bibarub) ```Guide improvenents```

- [wormstest](https://github.com/wormstest) ```Russian translation``` 

- [proganime1200](https://github.com/proganime1200) ```Tremendously helped to make this possible, heavily contirbuted to the old guide by finding bk01-04 partitions and had managed to nearly get winpe booting in the early stages```

</details>  

