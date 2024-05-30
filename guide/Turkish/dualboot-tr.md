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
- **WoA Helper** uygulamasını indirin ve kurun, sonrasında uygulamayı açın ve root erişimi verin.
- **UEFI imajını** indirin ve dahili depolama alanınızdaki `UEFI` adlı klasörün içerisine yerleştirin.
- **WoA Helper** uygulamasını açın ve **WOA TOOLBOX**'taki **STA CREATOR**'u kullanın

> [!Important]
> `/sdcard/Windows` klasörü boşsa, romunuz mount işlevini desteklemiyordur. Bu durumda uygulama içerisinde bir boot.img dosyası oluşturmak ve bunu, Windows'a ilk boot edişinizde manuel olarak kopyalamak zorundasınız (mesela, dosyayı bir yere upload edip sonrasında Windows'a geçtiğinizde dosyayı indirebilirsiniz). Aynı şeyler dahili depolamanızda oluşturulan StA dosyaları için de geçerlidir
>
> Eğer klasör salt okunur ise aynı şeyleri yapmanız gerekir

- **QUICKBOOT TO WINDOWS** butonuna basın

### Windows Tarafındaki Kurulum
-  `C:\sta` konumuna gidin, -eğer yoksa- masaüstüne sta.exe'nin bir kısayolunu oluşturun.

#### Android'e boot etme
- Masaüstünüzde yeni oluşturulmuş olan kısayolu çalıştırın (erişim kolaylığı için başlat menünüze ya da görev çubuğunuza sabitleyebilirsiniz)

#### Windows'a boot etme
- WOA Helper uygulamasındaki `WINDOWS'A QUICKBOOT ET` butonuna basın ya da hızlı ayarlar panelinizde yeni oluşturulmuş olan toggle'ı kullanın
  
## Bitti!
