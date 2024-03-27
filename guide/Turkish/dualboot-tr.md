<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Xiaomi Pad 5'te Windows Çalıştırma

## Android and Windows'u sorunsuzca dualboot edebilme

### Gerekli Dosyalar
- ```Beyin```
- ```Rootlu bir tablet```
- ```Tablette yüklü Windows```
- [```UEFI imajı```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v3.img)
- [```WOA Helper uygulaması```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/woahelper.apk)
- [```StA Installer```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/StA_Installer_nabu.exe)

## Dualboot uygulamasını kurma
> Bu rehber rootlu olduğunuzu varsayar, eğer değilseniz lütfen öncelikle [root rehberini](2-rootguide-tr.md) takip edin

### Kurulum - Android
> [!NOTE]
> Dosyaları Windows klasörüne taşıyamıyorsanız, bu, Windows'u yeniden başlatmak yerine kapattığınız anlamına gelir. Bu sorunu gidermek için Windows'a geri dönün ve yeniden başlat'ı kullanın, ardından yeniden başlatılırken fastboot'a boot edip fastbootu Android'e dönmek için kullanın.

- [WOA Helper uygulamasını](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/woahelper.apk) indirin ve kurun, ardından açın ve root erişimi verin.
- [UEFI imajını](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v2.img) indirin ve dahili depolama alanınızdaki `UEFI` adlı klasörün içerisine yerleştirin.
- WOA Helper uygulamasına dönün ve `Back up Android boot` butonuna basın. Teker teker hem 'Windows` hem de 'Android' seçeneklerini seçin.
- `Mount Windows` butonuna basın, ardından [StA_Installer_nabu.exe](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/StA_Installer_nabu.exe) indirin ve dahili depolama alanınızdaki yeni oluşturulan `Windows` klasörüne taşıyın
- WOA Helper uygulamasına dönün ve `Quickboot to Windows` tuşuna basın .

### Kurulum - Windows
-  `C:\StA_Installer_nabu.exe` konumuna gidin ve exe'yi çalıştırın. Çalışmazsa, uygulamanın çalışmasını engelleme ihtimalinden dolayı, herhangi bir antivirüs yazılımının aktif olmadığından emin olun.

##### Android'e boot etme
- Masaüstünüzde oluşturulmuş olan yeni kısayolu çalıştırın (erişim kolaylığı için başlat menünüze / görev çubuğunuza da sabitleyebilirsiniz)

##### Windows'a boot etme
- WOA Helper uygulamasındaki `Quickboot to Windows` butonuna basın ya da hızlı ayarlar panelinizde yeni oluşturulmuş olan toggle'ı kullanın
  
## Bitti!
