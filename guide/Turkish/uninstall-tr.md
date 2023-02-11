<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 çalıştıran bir Xiaomi Pad 5">

# Xiaomi Pad 5 üzerinde Windows Çalıştırma

## Windows'un kaldırılması

Windows'u kaldırmak istiyorsanız bölümleri elle teker teker silmek yerine birkaç komut ile kaldıracağız. Bu bizleri uzunca bir rehber hazırlamaktan ve sizlerin komutları yazarken herhangi bir hata yapmanızdan kurtaracak.

Bootloader'ı geri kilitlemek istiyorsanız bölüm tablonuzun orijinal hale gelmesi gerekmektedir.

### Prerequisites

- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)
- [gpt_both0.bin](../../../../releases/tag/1.0)


> Komuttaki <gpt_both0.bin> kısmını gpt_both0.bin dosyasının konumuyla değiştirin. Dosyayı [releases sayfasından](../../../../releases/) indirebilirsiniz.


# Varsayılan bölüm tablosunu geri yükleyin

```cmd
fastboot flash partition:0 <gpt_both0.bin>
```

# Bootloop yaşamamak ve bölüm boyutunu geri yüklemek için Userdata bölümünü biçimlendirin
```cmd
fastboot -w
```
