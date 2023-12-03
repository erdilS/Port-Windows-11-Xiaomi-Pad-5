<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 çalıştıran bir Xiaomi Pad 5">


# Xiaomi Pad 5 üzerinde Windows Çalıştırma

### Aşama 1: Windows'un yükleneceği bölümleri oluşturma

### Gerekli Dosyalar

- [Recovery İmajı](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)

## Notlar:
> [!WARNING]
> Diskpart üzerinden bölüm silmeye kalkışırsanız Windows'un göndereceği UFS komutu cihaz tarafından yanlış yorumlanarak cihazın UFS belleğinin tümüyle silinmesine yola açabilir. Bölümlerde değişiklik yapmak için yalnızca recovery mod üzerinden parted ile işlem yapın.
> 
> Cihazda bulunan tüm verileriniz silinecektir. Yedeğini almayı gerektiren dosyalarınız varsa yedeklemeyi ihmal etmeyin.
> 
> Rehberdeki komutların tümü test edilmiştir.
> 
> `udevadm` uyarılarını görmezden gelin
> 
 Aynı komutları ikişer kez (ya da daha fazla) çalıştırmayın.
> 
> Recovery modunda ekran çalışmamaktadır. Tüm işlemleri shell vasıtasıyla yapacağız.
> 
> Eğer hata yaptığınızı düşünüyorsanız TABLETİNİZİ YENİDEN BAŞLATMAYIN ve [Telegram grubumuzdan](https://t.me/nabuwoa) yardım isteyin.
>
> 
> Komutların hepsini birden çalıştırmak yerine sırayla teker teker çalıştırın!
>
> 
> KOMUTLARI GİRERKEN HERHANGİ BİR HATA YAPMAYIN!!! EĞER YANLIŞ BİR ŞEY YAPARSANIZ CİHAZINIZI BOZABİLİRSİNİZ.

#### Bir bilgisayar aracılığıyla recovery modunda cihazı başlatın
```cmd
fastboot boot <recovery.img>
```
##### Bölümleme komut dosyasını çalıştırın

> Sizden bir kez daha çalıştırmanızı isterse, bunu yapın

> Bu **isteğe bağlıdır** ancak bu komut dosyasını kullanarak **özel boyutlar ayarlayabilirsiniz**
> Özel boyutları ayarlamak için ```adb kabuk bölümü [GB CİNSİNDEN HEDEF WİNDOWS BOYUTU]```

> Sonunda GB eklemediğinizden emin olun, sadece sayı

```cmd
adb shell partition
```

### Android'in açılıp açılmadığını kontrol edin.
Tabletinizi yeniden başlatın, ve Android'in çalışıp çalışmadığını kontrol edin.
Eğer Android açılmıyorsa ya da bootanimationda takılı kaldıysa MIUI recovery ile veya başka recoveryler ile data bölümünü biçimlendirin.

## [Sonraki aşama: Windows kurulumu](/guide/Turkish/2-install-tr.md)
