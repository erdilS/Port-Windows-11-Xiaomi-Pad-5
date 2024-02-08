<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 çalıştıran bir Xiaomi Pad 5">


# Xiaomi Pad 5 üzerinde Windows Çalıştırma

### Aşama 1: Windows'un yükleneceği bölümleri oluşturma

### Gerekli Dosyalar

- [```Recovery İmajı```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [```platform tools```](https://developer.android.com/studio/releases/platform-tools)

## Notlar:
> [!WARNING]
> Diskpart üzerinden bölüm silmeye kalkışırsanız Windows'un göndereceği UFS komutu cihaz tarafından yanlış yorumlanarak cihazın UFS belleğinin tümüyle silinmesine yola açabilir.
>
>  Bölümlerde değişiklik yapmak için yalnızca recovery mod üzerinden parted ile işlem yapın.
> 
> Cihazda bulunan tüm verileriniz silinecektir. Yedeğini almayı gerektiren dosyalarınız varsa yedeklemeyi ihmal etmeyin.
> 
> Rehberdeki komutların tümü test edilmiştir.
> 
 Aynı komutları ikişer kez (ya da daha fazla) çalıştırmayın.
> 
> Eğer hata yaptığınızı düşünüyorsanız TABLETİNİZİ YENİDEN BAŞLATMAYIN ve [Telegram grubumuzdan](https://t.me/nabuwoa) yardım isteyin.
>
> 
> Komutların hepsini birden çalıştırmak yerine sırayla teker teker çalıştırın!
>
> KOMUTLARI GİRERKEN HERHANGİ BİR HATA YAPMAYIN!!! EĞER YANLIŞ BİR ŞEY YAPARSANIZ CİHAZINIZI BOZABİLİRSİNİZ.

#### Bir bilgisayar aracılığıyla recovery modunda cihazı başlatın
```cmd
fastboot boot <recovery.img>
```
##### Bölümleme komut dosyasını çalıştırın

> Sizden bir kez daha çalıştırmanızı isterse, bunu yapın

> Bu **isteğe bağlıdır** ancak bu komut dosyasını kullanarak **özel boyutlar ayarlayabilirsiniz**
> Özel boyutları ayarlamak için ```adb shell partition [GB CİNSİNDEN HEDEF WİNDOWS BOYUTU]```

> Sonunda GB eklemediğinizden emin olun, sadece sayı

```cmd
adb shell partition
```
### Make a backup of your existing boot image

```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/normal_boot.img" && adb pull /tmp/normal_boot.img
```


#### Check if Android still starts
> just see if Android still works
If isn't boot or looping on animation, use MIUI recovery or other recoveries for wiping data.

```cmd
adb reboot
```




## [Sonraki aşama: get root](/guide/Turkish/2-rootguide-tr.md)
