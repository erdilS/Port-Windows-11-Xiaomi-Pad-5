
<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Xiaomi Pad 5'te Windows çalıştırma

## Almak root 
> [!NOTE]
> **Zaten kökünüz varsa, bu adımı atlayın ve bir sonraki sayfaya gidin**

### Önkoşullar
- ```Beyin```
  
- [```Android önyükleme yedeklemesi```](/guide/English/1-partition-en.md#Make-a-backup-of-your-existing-boot-image) (which you backup on the first guide page)


## Yama önyüklemesi

- Kopyala ```normal_boot.img``` dosyadan ```platform tools``` tablete klasör


- Indirin ve yükleyin [Magisk uygulama](https://github.com/topjohnwu/Magisk/releases/latest) tablete
  
- Magisk uygulamasını açın ve ```Yüklemek``` düğme. Seçmek ```Bir Dosya Seçin ve Düzeltin``` seçenek ve bulmak ```normal_boot.img``` tablete kopyaladığınız dosya. Tıklayın ```hadi gidelim``` düğmesine basın ve yama işleminin tamamlanmasını bekleyin.
  
- Kopyala ```magisk_patched....img``` dosyadan ```Downloads``` tablet üzerindeki klasör ```platform tools``` bilgisayarınızdaki klasör.

- Fastboot için yeniden başlat
  
- Platform araçları klasöründe komut istemi'ni açın

 ## Flaş yamalı önyükleme
 > Yerini almak `<magisk_patched.img>` gerçek ile ```magisk_patched.img``` isim / yol.
```cmd
fastboot flash boot <magisk_patched.img>
```

### [Sonraki adım: Windows'u Yükleme](/guide/Turkish/3-install-tr.md)
