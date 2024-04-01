<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 çalıştıran bir Xiaomi Pad 5">

# Xiaomi Pad 5'te Windows Çalıştırma

## Kurulum

### Gerekli Dosyalar

- ```Kilidi açılmış bootloader```

- `Beyin`

- [```Recovery imajı```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [```Android platform araçları```](https://developer.android.com/studio/releases/platform-tools)

### Notes:
> [!Warning]
> Bütün verileriniz silinecektir. İhtiyaacınız olan veriler varsa şimdi yedekleyin.
> 
> Eğer bir hata yaptığınızı düşünüyorsanız TABLETİNİZİ YENİDEN BAŞLATMAYIN, [Telegram grubumuzda](https://t.me/nabuwoa) yardım isteyin.
>
>**LÜTFEN YOUTUBE VEYA BAŞKA BİR PLATFORMDAKİ GÜNCEL OLMAYAN VİDEO REHBERLERİNİ KULLANMAYIN! BU VİDEOLAR ESKİDİR VE BUNLARI KULLANARAK CİHAZINIZI BRICK EDEBİLİRSİNİZ! EĞER BİR VİDEO REHBERİNE İHTİYACINIZ VARSA, [ArtoSeVeN](https://www.youtube.com/channel/UCYjwfxlYlJ7Nnzv01oszQvA) TARAFINDAN HAZIRLANAN BU [YENİ VİDEO REHBERİNİ](https://youtu.be/BbgTbTGbXYg) KULLANIN**


### Cihazınızı bölümlere ayırma ve bootu yedekleme
> [!NOTE]
> Nasıl başlayacağınızı bilmiyor musunuz? İndirdiğiniz [```Android platform araçları```](https://developer.android.com/studio/releases/platform-tools) arşiv dosyasını bir yere çıkartın: örneğin ``"C:\platform-tools"``. Ardından yönetici olarak ``cmd (komut istemcisi)`` veya `powershell` açın ve komutun `"bulunduğu\yol\platform-tools"` kısmını, platform-tools klasörünün bulunduğu gerçek yolla değiştirerek şu komutu girin:
```cmd
cd "bulunduğu\yol\platform-tools"
```
> Bu pencereyi rehberin tamamında kullanın; pencereyi rehberdeki adımları tamamlayana kadar kapatmayın.

#### Bir bilgisayar aracılığıyla recovery modunda cihazı başlatın
```cmd
fastboot boot <recovery.img>
```

#### Cihazınızı bölümlere ayırma

> Sizden komutu bir kez daha çalıştırmanıza dair bir uyarı gelirse, bunu yapın

> **Bu isteğe bağlı:** isterseniz *özel boyut ayarlaması* yapabilirsiniz. Bunun için şu komutu kullanın: ```adb shell partition [GB CİNSİNDEN İSTEDİĞİNİZ WINDOWS BOYUTU]``` (komutun sonuna -GB harfleri eklenmemiş olarak- istediğiniz boyutu sayı olarak yazacaksınız. mesela windows'a 200gb yer ayrımak isterseniz ```adb shell partition 200``` komutunu girecekesiniz. Eğer özel boyut ayarlaması yapmazsanız varsayılan olarak hafıza boyutu yarıya yarıya bölünür. Varsayılan hali alttaki komuttur)

```cmd
adb shell partition
```

### Mevcut boot imajınızın bir yedeğini alın

```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/normal_boot.img" && adb pull /tmp/normal_boot.img
```


#### Android'in hâlâ çalışıp çalışmadığını kontrol edin 
> Bunun için yeniden başlatın. Boot yapmazsa, reovery'de wipe all data (/tüm veriler silme) yapın ve tekrar -yeniden başlatmayı- deneyin.

```cmd
adb reboot
```


### [Sonraki aşama: Rootlama (root erişimi alma)](/guide/Turkish/2-rootguide-tr.md)
