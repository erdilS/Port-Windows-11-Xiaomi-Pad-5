<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 çalıştıran bir Xiaomi Pad 5">

# Xiaomi Pad 5'te Windows Çalıştırma

## Kurulum

### Gerekli Dosyalar

- Beyin

- [```Recovery imajı```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [```Android platform araçları```](https://developer.android.com/studio/releases/platform-tools)

### Notes:
> [!NOTE]
> Nasıl başlayacağınızı bilmiyor musunuz? İndirdiğiniz [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools) dosyasını açın, örneğin ``"C:\platform-tools"``, ardından yönetici olarak ``cmd (komut istemcisi)`` veya `powershell` açın ve yazın:

```cmd
cd "path\to\platform-tools"
```

> `"path\to\platform-tools"` kısmına platform-tools klasörünün bulunduğu gerçek yolu yazın

> [!Warning]\
> Şimdi veya ileriki bir zamanda diskpart üzerinden bölüm silmeye kalkışırsanız Windows'un göndereceği UFS komutu cihaz tarafından yanlış yorumlanarak cihazın UFS belleğinin tümüyle silinmesine yol açabilir.
> 
> Cihazda bulunan tüm verileriniz silinecektir. Yedeğini almayı gerektiren dosyalarınız varsa yedeklemeyi ihmal etmeyin.
> 
> Rehberdeki komutların tümü test edilmiştir.
> 
> Eğer bir hata yaptığınızı düşünüyorsanız TABLETİNİZİ YENİDEN BAŞLATMAYIN, [Telegram grubumuzdan](https://t.me/nabuwoa) yardım isteyin.
>
>**LÜTFEN YOUTUBE VEYA BAŞKA BİR PLATFORMDAKİ GÜNCEL OLMAYAN VİDEO REHBERLERİNİ KULLANMAYIN! BU VİDEOLAR ESKİDİR VE BUNLARI KULLANARAK CİHAZINIZI BRICK EDEBİLİRSİNİZ! EĞER BİR VİDEO REHBERİNE İHTİYACINIZ VARSA, [ArtoSeVeN](https://www.youtube.com/channel/UCYjwfxlYlJ7Nnzv01oszQvA) TARAFINDAN HAZIRLANAN BU [YENİ VİDEO REHBERİNİ](https://youtu.be/BbgTbTGbXYg) KULLANIN**

### Cihazınızı bölümlere ayırma ve bootu yedekleme

#### Bir bilgisayar aracılığıyla recovery modunda cihazı başlatın
```cmd
fastboot boot <recovery.img>
```

##### Cihazınızı bölümlere ayırma

> Sizden komutu bir kez daha çalıştırmanıza dair bir uyarı gelirse, bunu yapın

> Bu **isteğe bağlıdır** ancak bu komut dosyasını kullanarak **özel boyutlar ayarlayabilirsiniz**

> Özel boyutları ayarlamak için ```adb shell partition [GB CİNSİNDEN HEDEFLENEN WINDOWS BOYUTU]```

>  Komutun sonuna GB harflerini eklemediğinizden emin olun, sadece sayı

```cmd
adb shell partition
```

### Mevcut boot imajınızın bir yedeğini alın

```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/normal_boot.img" && adb pull /tmp/normal_boot.img
```


#### Android'in hâlâ çalışıp çalışmadığını kontrol edin 
> Android'in hâlâ çalışıp çalışmadığını kontrol etmek için yeniden başlatın. Boot yapmazsa, reovery'de wipe all data (/tüm veriler silme) yapın ve tekrar deneyin.

```cmd
adb reboot
```
### [Sonraki aşama: Rootlama (root erişimi alma)](/guide/Turkish/2-rootguide-tr.md)
