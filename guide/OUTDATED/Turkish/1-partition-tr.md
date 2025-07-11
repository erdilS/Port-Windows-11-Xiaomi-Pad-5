<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 çalıştıran bir Xiaomi Pad 5">

# Xiaomi Pad 5'te Windows Çalıştırma

## Kurulum

### Gerekli Dosyalar
- ```Kilidi açılmış bootloader``` - (Bootloader'ınız kilitliyse ve kilidi nasıl açacağınızı bilmiyorsanız [bu](unlock-bootloader.md) rehberi kullanın)

- `Beyin`

- [```Recovery imajı```](https://github.com/ArKT-7/twrp_device_xiaomi_nabu/releases/tag/mod-win)

- [```Android platform araçları```](https://developer.android.com/studio/releases/platform-tools)

### Notes:
>[!NOTE]
> Herhangi bir Android romunu (MIUI/Hyper OS ya da herhangi bir custom rom olabilir) dualboot için kullanabilirsiniz

> [!Warning]
> Bütün verileriniz silinecektir. İhtiyaacınız olan veriler varsa şimdi yedekleyin.
> 
> Eğer bir hata yaptığınızı düşünüyorsanız, TABLETİNİZİ YENİDEN BAŞLATMAYIN, [Telegram grubumuzda](https://t.me/nabuwoa) yardım isteyin.
>
>**LÜTFEN YOUTUBE VEYA BAŞKA BİR PLATFORMDAKİ GÜNCEL OLMAYAN VİDEO REHBERLERİNİ KULLANMAYIN! BU VİDEOLAR ESKİDİR VE BUNLARI KULLANARAK CİHAZINIZI BRICK EDEBİLİRSİNİZ! EĞER BİR VİDEO REHBERİNE İHTİYACINIZ VARSA, [ArtoSeVeN](https://www.youtube.com/channel/UCYjwfxlYlJ7Nnzv01oszQvA) TARAFINDAN HAZIRLANAN BU [YENİ VİDEO REHBERİNİ](https://youtu.be/BbgTbTGbXYg) KULLANIN**


### Cihazınızı bölümlere ayırın ve bootu yedekleyin
> [!NOTE]
> Nasıl başlayacağınızı bilmiyor musunuz? İndirdiğiniz [```Android platform araçları```](https://developer.android.com/studio/releases/platform-tools) arşiv dosyasını bir yere çıkartın: örneğin ``"C:\platform-tools"``. Ardından yönetici olarak ``cmd (komut istemcisi)`` veya `powershell` açın ve komutun `"bulunduğu\yol\platform-tools"` kısmını, platform-tools klasörünün bulunduğu gerçek yolla değiştirerek şu komutu girin:

```cmd
cd "bulunduğu\yol\platform-tools"
```
> Bu pencereyi rehberin tamamında kullanın; pencereyi rehberdeki adımları tamamlayana kadar kapatmayın.

#### **fastboot**'a reboot edin 
- Cihazınızı **fastboot**'a boot etmek için reboot sırasında **`ses kısma`** tuşuna basılı tutun

- Cihazınızı kabloyla bilgisayara bağlayın

#### Modlanmış recoverye boot edin
> platform-tools klasöründe açın, sonrasında (tabletiniz fastboot modundayken) aşağıdaki komutu çalıştırın
```cmd
fastboot boot bulunduğu\yol\recovery.img
```

#### Cihazınızı bölümlere ayırın
> Komutun **$** kısmına Windows'a ayırmak istediğiniz depolama boyutunu girin (sayısal olarak boyutu girin, sonuna GB eklemeyin)
> 
> Komutu tekrar çalıştırmanız istenirse bunu yapın
```sh
adb shell partition $
```

### Mevcut boot imajınızın bir yedeğini alın
```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/normal_boot.img" && adb pull /tmp/normal_boot.img
```

#### Android'in hâlâ çalışıp çalışmadığını kontrol edin 
> Bunun için yeniden başlatın. Boot yapmazsa, reovery'de wipe all data (tüm veriler silme işlevi) yapın ve tekrar -yeniden başlatmayı- deneyin.

```cmd
adb reboot
```


### [Sonraki aşama: Rootlama (root erişimi alma)](/guide/Turkish/2-rootguide-tr.md)
