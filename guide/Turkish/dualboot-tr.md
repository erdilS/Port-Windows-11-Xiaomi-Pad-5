<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Running Windows on the Xiaomi Pad 5

## Dualbooting Android and Windows seamlessly

### Prerequisites
- ```Beyin```
- ```Köklü bir tablet```
- ```Tablete yüklü pencereler```
- [```UEFI görüntüsü```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v2.img)
- [```WOA Helper uygulama```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/woahelper.apk)
- [```StA Installer```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/StA_Installer_nabu.exe)

## Dualboot uygulamasını kurma
> Bu kılavuz, köklü olduğunuzu varsayar, eğer değilseniz, lütfen [root rehber](2-rootguide-tr.md) ilk.

### Kurulum - Android
> [!NOTE]
> Dosyaları Windows klasörüne taşıyamıyorsanız, bu, Windows'u yeniden başlatmak yerine kapattığınız anlamına gelir. Bu sorunu gidermek için Windows'a geri dönün ve yeniden başlat'ı kullanın, ardından önyüklemeyi fastboot'a yeniden başlatıp Android'e dönmek için kullanın.
- Indirin ve yükleyin [WOA Helper uygulama](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/woahelper.apk), ardından açın ve kök erişimi verin.
- [UEFI görüntüsünü](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v2.img) indirin ve dahili depolama alanınızdaki `UEFI` adlı klasörün içine yerleştirin, bu klasör yoksa oluşturun.
- WOA Helper uygulamasına dönün ve `Back up Android boot` düğmesine basın. Hem 'Windows` hem de 'Android' seçeneklerini seçin.
- `Mount Windows` düğmesine basın, ardından indirin ve taşıyın [StA_Installer_nabu.exe](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/StA_Installer_nabu.exe) dahili depolama alanınızdaki yeni oluşturulan `Windows` klasörüne.
- WOA Yardımcı uygulamasına dönün ve tuşuna basın `Quickboot to Windows`.

### Kurulum - Windows
-  Şuraya git `C:\StA_Installer_nabu.exe` ve çalıştır. Çalışmazsa, muhtemelen uygulamanın çalışmasına izin vermeyeceğinden, herhangi bir virüsten koruma yazılımının kapalı olduğundan emin olun.

##### Android'e önyükleme
  - Masaüstünüzde yeni kısayolu çalıştırın (erişim kolaylığı için başlat menünüze / görev çubuğunuza da sabitleyebilirsiniz)

##### Booting to Windows
  - Basın `Quickboot to Windows` uygulamanın içinde veya hızlı ayarlar panelinizde yeni oluşturulan geçişi kullanın
  
## Bitti!
