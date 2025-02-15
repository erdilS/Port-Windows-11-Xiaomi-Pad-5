<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Xiaomi Pad 5'te Windows Çalıştırma

## Android'i Yeniden Rootlama
Bu bölüm, MIUI/HyperOS güncellendiğinde ve root kaldırıldığında yeniden rootlama işlemi boyunca size rehberlik edecektir.

### Ön Gereklilikler
- [```Recovery İmajı```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)
  
- [```Android Platform Araçları```](https://developer.android.com/studio/releases/platform-tools)

### PC'de alttaki komutu kullanarak recovery modunu çalıştırın
```cmd
fastboot boot <recovery.img>
```

### Mevcut boot imajınızın yedeğini alın
```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/normal_boot.img" && adb pull /tmp/normal_boot.img
```

### Android'e geri boot edin
```cmd
adb reboot
```

### Boot'u yamalayın
- ```platform tools``` klasöründeki ```normal_boot.img``` dosyasını tabletinize kopyalayın
- Magisk uygulamasını açın ve ```Install``` butonuna tıklayın. ```Select and Patch a File``` seçeneğine tıklayın ve tablete kopyaladığınız ```normal_boot.img``` dosyasını seçin. ```Let's Go``` butouna basın, yamalama işleminin bitmesini bekleyin
- Tabletinizin ```İndirilenler (Downloads)``` klasöründeki ```magisk_patched....img``` dosyasını bilgisayarınızdaki ```platform tools``` klasörüne kopyalayın
- Fastboot'a reboot edin
- Platform tools klasörü üzerinden cmd açın

### Yamalı boot'u flashlayın
 > Komutun `<magisk_patched.img>` kısmını ```magisk_patched.img``` dosyasının bulunduğu asıl yolla değiştirin.
```cmd
fastboot flash boot <magisk_patched.img>
```

### Windows' C:\ klasöründeki boot.img dosyasını güncelleyin
- Android'e geri boot edin
- ```WOA Helper```'ı açın
- ```Windows```'u mount edin
- Herhangi bir dosya yöneticisi uygulaması üzerinden dahili depolamanızdaki ```Windows``` klasörüne girin
- ```boot.img``` dosyasını silin

> [!NOT]
> **Güncellenmiş boot.img dosyası bir sonraki rebootta C:\ klasöründe otomatik olarak oluşturulmuş olacaktır**

## Bitti!















