<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Xiaomi Pad 5'te Windows Çalıştırma

## Android ve Windows'u sorunsuzca dualboot edebilme

### Gerekli Dosyalar
- ```Beyin```
- ```Rootlu bir tablet```
- ```Tablette yüklü Windows```
- [```UEFI imajı```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v3.img)
- [```WoA Helper uygulaması```](https://github.com/Marius586/WoA-Helper-update/releases/tag/WOA)
- [```StA Installer```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/StA_Installer_nabu.exe)

## Dualboot uygulamasının kurulumu
> Bu rehber rootlu olduğunuzu varsayar, eğer değilseniz lütfen öncelikle [root rehberini](2-rootguide-tr.md) takip edin

### Android Tarafındaki Kurulum
- WoA Helper uygulamasını indirin ve kurun, sonrasında uygulamayı açın ve root erişimi verin.
- **UEFI imajını** indirin ve dahili depolama alanınızdaki `UEFI` adlı klasörün içerisine yerleştirin.
- `MOUNT WINDOWS` butonuna basın, ardından **StA_Installer_nabu.exe** indirin ve dahili depolama alanınızdaki yeni oluşturulmuş olan `Windows` klasörüne taşıyın
- WoA Helper uygulamasına dönün ve `WINDOWS'A QUICKBOOT ET` tuşuna basın .

> [!NOTE]
> Windows'un ilk bootu 10 dakika kadar sürebilir. Endişelenmeyin, sadece bekleyin.

### Windows Tarafındaki Kurulum
-  `C:\StA_Installer_nabu.exe` konumuna gidin ve dosyayı çalıştırın. Eğer çalışmazsa, herhangi bir antivirüs yazılımının aktif olmadığından emin olun (antivirüs uygulaması, uygulamanın çalıştırılmasını engelleyebilir).

#### Android'e boot etme
- Masaüstünüzde yeni oluşturulmuş olan kısayolu çalıştırın (erişim kolaylığı için başlat menünüze ya da görev çubuğunuza sabitleyebilirsiniz)

#### Windows'a boot etme
- WOA Helper uygulamasındaki `WINDOWS'A QUICKBOOT ET` butonuna basın ya da hızlı ayarlar panelinizde yeni oluşturulmuş olan toggle'ı kullanın
  
## Bitti!
