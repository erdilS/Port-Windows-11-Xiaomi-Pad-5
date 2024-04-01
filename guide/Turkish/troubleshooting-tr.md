<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 çalıştıran bir Xiaomi Pad 5">

# Xiaomi Pad 5'te Windows çalıştırma

## Sorun Giderme

## Android'ten Windows klasörüne dosya taşıyamıyorum

 Windows klasörüne dosya taşıyamıyorsanız, bu cihazı yeniden başlatmak yerine kapattığınızı gösterir. Bu sorunu düzeltmek için Windows'a dönün ve yeniden başlatın, yeniden başlatmadan sonra fastboota boot edin ve Android'e dönün

## Windows'ta şarj işlemi çalışmıyor
> [!WARNING]
> Host modu etkinken ek güçle beslenen bir USB çoklayıcı kullanmayın, bu cihazınızı bozabilir. Ek güçle beslenen bir USB çoklayıcı kullanıyorsanız, lütfen [USB host modu devre dışı bırakma rehberini](/guide/Additional-materials/Additional-materials-en.md#disabling-usb-host-mode) kullanın

Windows'ta şarj etme yalnızca belirli kablolarla olabilmektedir. Çalıştığı bilinen kablolar, orijinal Poco X3 Pro kablosu (USB-A bağlantı noktasındaki ek turuncu/kırmızı piniyle tanınır) ve Nimaso 100W USB-C'den USB-C'ye hızlı şarj kablosudur.

## Cihaz Android'e boot ediyor fakat bootloader'a boot edemiyor

### Gerekli Dosyalar:

- [Android platform araçları](https://developer.android.com/studio/releases/platform-tools)

> [!WARNING]
> Muhtemelen bu adımlar işinize yaramayacaktır zira Xiaomi Pad 5'e flaslamak için düzgün çalışan bir custom recovery henüz yok. Ayrıca yeni A/B cihazlarının çoğunda olduğu gibi TWRP Installer zip vb. yoktur ve bozuk fastboot nedeniyle mevcut recovery imajını boot edemezsiniz. Zaten AOSP rom yüklediyseniz, muhtemelen önceden yüklenmiş bir AOSP recoverysi de vardır ve buna doğrudan boot edebilirsiniz, bundan dolayı bu adımları takip edebilirsiniz. Rootsuz MIUI yüklüyse, bu adımlar size yardımcı olmayacaktır.
>
> Bu yüzden bölümlerinize boşluk ve özel karakter içeren isim vermekten kaçının, hatta mümkünse defalarca test edilmiş ESPNABU ve WINNABU hariç isim kullanmayın, aksi takdirde EDL üzerinden yetkili hesap kullanılarak yazılım yüklenmesi gerekebilir, bu işlem ise ücretlidir.

Bu sorun bootloader'ın kavrayamadığı volume isimlerinden ötürü oluşmakta, bu sorunu gidermek için şu adımları uygulayın:

- Recovery'e boot edin

- Tableti bilgisayara bağlayın

- Bilgisayarda platform araçları cmd'sini açın

- ```adb shell``` komutunu çalıştırın

- ```parted``` komutunu çalıştırın

- ```print``` komutunu çalıştırarak bölümleri listeleyin

- Adlarında boşluk olan bölümleri arayın, örneğin "Temel Veri Bölümü (Basic Data Partition)" ve birim numaralarını not edin

- Ardından ```rm <volume numarası>``` komutunu çalıştırın. (örneğin ```rm 99```)


## Boot esnasında fsa4480.sys kaynaklı mavi ekran oluyor

- Sürücü klasörünü açın

- Remove the NABU.xml dosyasından ```<DriverPackageFile Path="$(mspackageroot)\components\QC8150\Device\DEVICE.SOC_QC8150.NABU\Drivers\USB" Name="fsa4480.inf" ID="fsa4480"/>``` satırını silin

- Sürücüyü yeniden yükleyin

- UEFI'ye boot edin

> [!NOTE]
> Halen mavi ekran alıyorsanız, `yeniden kurulum` rehberini takip edin ve bu driver paketini kullanın

## Android'e geçiş yaptıktan sonra bootloop (/sürekli yeniden başlama) oluyor

- fastboot'a boot edin

- ```fastboot set_active other```

- ```fastboot flash boot <boot.img>```

- ```fastboot reboot```
