# Xiaomi Pad 5 Üzerinde Windows Çalıştırma

## Android ve Windows'u Sorunsuz Dualboot Yapma

### Gereksinimler
- ```Beyin```
- ```Rootlu tablet```
- ```Tablete kurulu Windows```
- [```UEFI görüntüsü```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v3.img)
- [```WoA Helper uygulaması```](https://github.com/n00b69/woa-helper/releases/tag/APK)

## Dualboot Uygulamasını Ayarlama
> Bu kılavuz rootlu olduğunuzu varsayar, rootlu değilseniz, lütfen önce [root kılavuzunu](2-rootguide-tr.md) takip edin

### Kurulum - Android
- **WOA Helper** uygulamasını indirin ve kurun, ardından açın ve root erişimi verin.
- **UEFI görüntüsünü** indirin ve dahili depolamanızda `UEFI` adlı klasörün içine yerleştirin.
- WOA Helper uygulamasını açın ve **WOA TOOLBOX**'ta **STA CREATOR**'ı kullanın.
> [!Önemli]
> Eğer `/sdcard/Windows` boşsa, ROM'unuz mount desteklemiyor demektir ve uygulama içinde boot.img yedeği oluşturmanız, ardından Windows'a önyükleme yaptıktan sonra manuel olarak kopyalamanız gerekecek (örneğin bir yere yükleyip ardından Windows'a önyükleme yaptığınızda indirerek). Aynı şey iç depolamanızda oluşturulan StA dosyaları için de geçerlidir.
>
> Klasör salt okunursa da aynı işlemi yapın.
- **QUICKBOOT TO WINDOWS** butonuna basın.

### Kurulum - Windows
> [!İpucu]
> Eğer bu ilk defa Windows'u önyüklediğiniz zamansa ve Microsoft Hesabı girişini atlamak istiyorsanız, WiFi sayfasında **İnternetim yok** butonuna basın, ardından istendiğinde **Sınırlı kurulumla devam et** butonuna basın.
- `C:\sta` dizinine gidin ve **sta.exe**'nin bir kısayolunu masaüstünüze oluşturun, eğer zaten mevcut değilse

#### Android'e Önyükleme
- Masaüstünüzdeki yeni kısayolu çalıştırın (kolay erişim için başlat menüsüne veya görev çubuğuna da sabitleyebilirsiniz)

#### Windows'a Önyükleme
- Uygulama içindeki **QUICKBOOT TO WINDOWS** butonuna basın veya hızlı ayarlar panelinizde yeni oluşturulan düğmeyi kullanın
  
## Tamamlandı!

> [!İPUCU]
> Windows'unuzu nasıl etkinleştireceğinize dair kılavuzun yanı sıra diğer yararlı bilgileri bulabileceğiniz [**```Yararlı uygulamalar ve talimatlar```**](Additional-materials-en.md) sayfasına göz atmayı unutmayın.
