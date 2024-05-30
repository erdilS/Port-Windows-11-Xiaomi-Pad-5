<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 çalıştıran bir Xiaomi Pad 5">

# Xiaomi Pad 5'te Windows çalıştırma

## Sorun Giderme

## Android'ten Windows klasörüne dosya taşıyamıyorum

 Windows klasörüne dosya taşıyamıyorsanız, bu, cihazı yeniden başlatmak yerine kapattığınız anlamına gelir. Bu sorunu düzeltmek için Windows'a dönün ve yeniden başlatın, yeniden başlatmadan sonra fastboota boot edin ve Android'e dönün

## Windows'ta şarj işlemi çalışmıyor
> [!WARNING]
> Host modu etkinken ek güçle beslenen bir USB çoklayıcı kullanmayın; bu, cihazınızı bozabilir. Ek güçle beslenen bir USB çoklayıcı kullanıyorsanız, lütfen [USB host modu devre dışı bırakma rehberini](/guide/Additional-materials/Additional-materials-en.md#disabling-usb-host-mode) kullanın

Windows'ta şarj etme yalnızca belirli kablolarla olabilmektedir. Çalıştığı bilinen kablolar, orijinal Poco X3 Pro kablosu (USB-A bağlantı noktasındaki ek turuncu/kırmızı piniyle tanınır) ve Nimaso 100W USB-C'den USB-C'ye hızlı şarj kablosudur.

## Cihaz Android'e boot ediyor fakat bootloader'a boot edemiyor

### Gerekli Dosyalar:
- [Android platform araçları](https://developer.android.com/studio/releases/platform-tools)

- [SHRP Recovery](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/SHRP.img)

> [!Important]
> Bu işlem, sadece rootluysanız çalışacaktır. Rootlu değilseniz, cihazı kurtarmanın tek yolu EDL yoluyla flashlamadır [MrAuthTool](https://mrauthtool.com/)

- Dahili depolamanızdaki UEFI klasöründen **UEFI** dosyasını silin,  **SHRP recovery** imajını yerleştirin
- WoA Helper uygulamasında `QUICKBOOT TO WINDOWS` butonuna basın
- Recovery'e boot edildiğinde, cihazı PC'ye bağlayın ve şu komutu çalıştırın:
```cmd
adb shell parted /dev/block/sda
```
- Bütün bölümleri listelemek için ```print```'i çalıştırın
- 16 karakterden uzun bölümlere -örneğin "Temel Veri Bölümü (Basic Data Partition)" bakın ve bölüm numarasını not edin
- Rename this partition with ```name $ test```, replacing **$** with the partition number, and replacing **test** with the name you want the partition to have
- ```quit```'i çalıştırın
- ```adb reboot bootloader``` çalıştırın ve ekranınızda **FASTBOOT** logosunu gördüğünüzde, bu komutla ```fastboot flash boot_a path\to\boot.img``` Android boot imajınızı flashlayın
- Eğer cihazınız boot etmiyorsa ya da recovery'e geri boot ediyorsa, aynı işlemleri **boot_b** için de yapmalısınız

> [!NOTE]
> UEFI klasöründeki recovery imajını UEFI dosyasıyla tekrardan değiştirmeyi unuymayın


## Boot esnasında fsa4480.sys kaynaklı mavi ekran oluyor

- Sürücü klasörünü açın

- Nabu.xml dosyasından ```<DriverPackageFile Path="$(mspackageroot)\components\QC8150\Device\DEVICE.SOC_QC8150.NABU\Drivers\USB" Name="fsa4480.inf" ID="fsa4480"/>``` satırını silin

- Sürücüyü yeniden yükleyin

- UEFI'ye boot edin

> [!NOTE]
> Halen mavi ekran alıyorsanız, `yeniden kurulum` rehberini takip edin ve bu driver paketini kullanın

## Android'e geçiş yaptıktan sonra bootloop (sürekli yeniden başlama döngüsü) oluyor

- fastboot'a boot edin

- ```fastboot set_active other```

- ```fastboot flash boot <boot.img>```

- ```fastboot reboot```
