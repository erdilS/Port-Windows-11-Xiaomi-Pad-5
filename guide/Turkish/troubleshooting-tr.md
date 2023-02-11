<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 çalıştıran bir Xiaomi Pad 5">

# Xiaomi Pad 5 üzerinde Windows çalıştırma

## Ender Karşılaşılan Bazı Sorunları Giderme


## Cihaz Android üzerinde açılabiliyor fakat bootloader modunda açılamıyor

### Gereksinimler:

- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)

> **Uyarı** Muhtemelen bu adımlar işinize yaramayacaktır zira Xiaomi Pad 5 için henüz düzgün çalışan bir kurtarma modu yok, dolayısıyla cihaza yüklenebilir bir kurtarma modu da yok. Eğer halihazırda AOSP tabanlı bir custom rom yüklüyse bu adımların işinizi görme olasılığı yüksek, fakat root edilmemiş MIUI yüklü ise bu adımlar hiçbir işinize yaramaz.

> Bu sebepten ötürü bölümlerinize boşluk ve özel karakter içeren isim vermekten kaçının, hatta mümkünse defalarca test edilmiş ESPNABU ve WINNABU hariç isim kullanmayın, aksi takdirde yetkili hesap kullanılarak yazılım yüklenmesi gerekebilir, bu işlem ise ücretlidir.

Bu sorun bootloader'ın kaldıramadığı bölüm isimlerinden ötürü oluşmakta, bu sorunu gidermek için şu adımları (uygulayabilirseniz) uygulayın:

- Recovery modunda cihazı (bir şekilde) açın.

- Tableti bilgisayarınıza bağlayın.

- Bilgisayarınızda ir komut istemcisi (cmd) açın.

- ```adb shell``` komutunu çalıştırın.

- ```parted``` komutunu çalıştırın.

- ```print``` komutunu çalıştırarak bölümleri listeleyin.

- İçinde boşluk içeren bölümlere (örneğin "kedi arşivi" gibi) bakının ve numaralarını not alın.

- Ardından ```rm <bölüm numarası>``` komutunu çalıştırın. (örneğin ```rm 99``` şeklinde)


## Önyükleme esnasında fsa4480.sys kaynaklı mavi ekran

- Sürücü klasörünü açın.

- ```components\QC8150\Device\DEVICE.SOC_QC8150.NABU\Drivers\USB``` klasörünü silin.

- Bu sürücüleri geri yükleyin.

- Windows'u en az 1 kere başarılı bir şekilde açın.

- Windows başarılı bir şekilde açıldıktan sonra sildiğiniz sürücüleri geri ekleyin ve yeniden yükleyin.

