<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Xiaomi Pad 5'te Windows Çalıştırma

## Cihazı EDL Modda Geri Yükleme
> Bu işlem, cihazınız EDL moduna kendi kendine boot ettiğinde ya da başka yollarla geri yükleyemediğinizde son çare olarak yapılı

### Prerequisites
- $5 USDT olan bir kripto cüzdan

- [Bir Telegram hesabı](https://telegram.org)

- [MrAuthTool 2.0](https://mrauthtool.com/)

- [Stok fastboot rom](https://xiaomifirmwareupdater.com/miui/nabu/)

### MrAuthTool'u ayarlayın
- Bir MrAuthTool hesabı oluşturun [buradan](https://mrauthtool.com/Sing_Up.php)
- MrAuthTool ana sayfasından **MR 2.0**'ı indirin, **Mr_Auth_Tool_2.0.exe** dosyasını arşivden çıkarın ve açın
- Oluşturduğunuz hesaba bağlanın

### Kredi satın alın
> Kredi satın almak için Telegram'daki MrAuthTool ana sayfasında listelenen yetkili satıcılardan biriyle iletişime geçin.
>
> Birden fazla kişiyle iletişime geçmekten imtina etmeyin, çünkü bazılarının yanıt vermesi uzun sürebilir.
> 
> Bu aracı kullanarak cihazınızı flashlamak için **5** krediye ihtiyacınız olacaktır.

### EDL modda boot edin
> [!Note]
> Eğer zaten EDL modundaysanız, bu adımı atlayın ve "cihazınızı flashlayın" adımına geçin
- Bootloader kilidiniz açıksa ve fastboot moduna erişiminiz varsa, EDL moduna boot etmek için ```fastboot oem edl``` komutunu çalıştırın

> Bootloader'ınız kilitliyse veya Android boot etmiyorsa ve fastboot moduna hiçbir şekilde erişemiyorsanız, EDL test noktalarını kısa devre yapmak için cihazınızın arkasını çıkarmanız veya bir EDL kablosu kullanmanız gerekecektir
>
> (Her EDL kablosu çalışacak diye bir şey yoktur, yani çalışmayan bir kabloya para harcama riskiniz olabilir, fakat bu yine de cihazınızı açmak zorunda olmaktan daha iyidir)
- Adında **V2** olan bir kablo arayın, örneğin **Hydra V2 EDL Cable** veya **V2 EDL Pro Cable**. Kablonun USB-C cihazları için olduğundan emin olun
- Kabloyu cihazınıza takın, ardından kablo üzerindeki [bunun gibi](https://t.me/nabuwoa/204867) görünen düğmeyi basılı tutun
- Cihaz şimdi EDL moda boot etmeli

### Cihazınızı flashlayın
- Cihazınız için stok fastboot romunu indirin ve MrAuthTool'da seçin
- **flash**'a basın
- Wait until it finishes flashing, then reboot.
> [!Note]
> Araç takılı kalır ve flashlama yapmazsa, bilgisayarınızda USB bağlantı kesilme sesini duyana kadar **güç** düğmesine (yaklaşık 30 saniye) basılı tutup cihazınızı yeniden başlatın (işe yaramazsa **güç** + **ses kısma ya da açma** düğmelerinin bir kombinasyonunu kullanmanız gerekebilir)

### MiFlash ile yeniden rom flashlayın
> [!Important]
> Bu araç yalnızca bir slota rom flashlar, eğer cihazınız slot değiştirirse, yeniden EDL moda düşebilirisinz.
- Fastboot moda reboot et
- Ya **MiFlash** kullanarak ya da romdaki **flash_all.bat** dosyası ile ikinci kez rom flashlayın
- Flashlama bittiğinde yeniden başlatın

## Bitti!
























