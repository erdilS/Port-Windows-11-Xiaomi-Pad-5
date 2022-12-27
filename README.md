# Xiaomi Pad 5'te Windows 11 Çalıştırma

<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

## ⚠️ **UYARI**

Hardbrick olan cihazlardan, recovery bölümleri eksik olan cihazlardan, ölü microSD kartlarından, ölü kedi ve köpeklerden, veya Android'e bootlamayı unuttunuz ve alarmınız çalmadı diye oluşacak nükleer savaşlardan sorumlu değiliz.

Bu proje daha erken aşamalarda, burdaki tüm dosyalar başka sizin gibi kullanıcılardan alınmıştır, burda çalışan dosyaları bulabilirsiniz. Bu yapmak riskli ve zor, bunu yaparken risk sizindir ve lütfen tüm aşamaları dikkatlice takip edin.

**EĞER TABLETİNİZİ MODLAMAKTAN VEYA DİSK TABANI İLE OYNAMAKTAN VEYA HARDBRİCK YEMEKTEN KORKUYORSANIZ HEMEN BURDAN AYRILIN!!! UYARILDINIZ, EĞER CİHAZINIZI BRİCK EDERSENİZ SİZİN SORUMLULUĞUNUZ ALTINDADIR!!! TEKRAR EDİYORUZ! UYARILDINIZ!!!**

## Proje durumu

Beta. Donanımın çoğu çalışıyor, fakat bazıları hala sorunlu/çalışmıyor.

#### Özellikler

- [ ] Ses ```Sadece USB veya Bluetooth```
- [x] Batarya durumu
- [x] Bluetooth
- [x] Parlaklık
- [ ] Kamera
- [ ] Şarz ```Yapım aşamasında, yarım yamalak çalışıyor ```
- [x] Ekran
- [ ] FM
- [x] GPU [GPU düzeltmeyi okumak için buraya tıklayın](guide/English/otherthings-en.md)
- [x] Dokunmatik ekran
- [x] UFS
- [x] USB ```PD hub gerekli```
- [x] Wi-Fi

#### Sensörler
- [x] Accelerometer
- [x] Gyroscope
- [x] Parlaklık sensörü
- [x] Mangnemator
- [x] Yakınlık sensörü


## Rehber & gerekenler

<details> 
<summary><strong>Gereken Programlar/Dosyalar</strong></summary>

Siz/İnsan:

- İngilizce bilmeli

- TWRP kullanımını anlamalı/bilmeli

- CMD/komut yürütmeyi bilmeli

- Çalışan bir beyni olmalı

PC:

- [Windows on ARM imajı](https://uupdump.net/) (Windows 11 önerilir)

- [platform-tools](https://developer.android.com/studio/releases/platform-tools).

- [DriverUpdater](https://github.com/WOA-Project/DriverUpdater/releases/) en son [driverları](https://github.com/map220v/MiPad5-Drivers) kurmak için linke tıklayın

Tablet:

- [UEFI imajı ve TWRP](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/1.0)

</details> 


### Windows kurulum detayları

<details> 

<summary><strong>English</strong></summary>

1 - [Create partitions](guide/English/1-partition-en.md)

2 - [Install Windows](guide/English/2-install-en.md)

<summary><strong>Türkçe</strong></summary>

1 - [Diskleri oluşturun](guide/English/1-partition-en.md)

2 - [Windows kurun](guide/English/2-install-en.md)
  
</details> 

### Diğer rehberler:

<details> 

<summary><strong>English</strong></summary>

- [If you just want to update the drivers follow these commands](guide/English/update-en.md)

- [Dual booting and updating GPU driver](guide/English/otherthings-en.md)

- [Uninstalling Windows](guide/English/uninstall-en.md)
  
<summary><strong>Türkçe</strong></summary>

- [Eğer sadece driverları güncellemek istiyorsanız bu komutları takip edin](guide/English/update-en.md)

- [Dual boot ve GPU driverları](guide/English/otherthings-en.md)

- [Windows'u silme](guide/English/uninstall-en.md)
 
</details> 

## Destek olanlar

<details> 

<summary><b><strong>Teşekkürler</strong></b></summary>

- [Icesito68](https://github.com/Icesito68) ```Made Windows partitioning commands and made original vayu repo```

- [Map220v](https://github.com/map220v) ```Maintains UEFI and Drivers```
  
- [Renegade Project](https://github.com/edk2-porting) ```Making the core of this project```

- [gus33000](https://github.com/gus33000) ```Providing help, also made base install guide, all of the original drivers and the msc script```

- [Renegade Project Discord members](https://discord.gg/XXBWfag) ```Provided Help```
 
- [MollySophia](https://github.com/MollySophia) ```Helped to fix battery status```

- [bibarub](https://github.com/bibarub) ```Made original bat file for switching Windows to Android```

- [entaromia](https://github.com/entaromia) ```Made application for switching Android to Windows```

</details>  

