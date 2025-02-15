<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 çalıştıran bir Xiaomi Pad 5">

# Xiaomi Pad 5 üzerinde Windows Çalıştırma

## Kaldırma

### Bu neden gerekli?

Windows'u kaldırmak istiyorsanız bölümleri elle teker teker silmek yerine birkaç komut ile kaldırmak insan hatasını engelleyecektir. Ayrıca bu bizleri uzunca bir rehber hazırlamaktan kurtaracaktır.

Bootloader'ı geri kilitlemek istiyorsanız bölüm tablonuzun orijinal haline gelmesi gerekmektedir.

#### Gerekli Dosyalar

- [```Android platform araçları```](https://developer.android.com/studio/releases/platform-tools)
  
- [```Recovery imajı```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

#### Modlu (modifiye edilmiş) recovery'e boot edin
```cmd
fastboot boot <recovery.img>
```

#### Bölüm düzeninizi restore edin
> [!Warning]
> Bu işlem Android dosyalarınızı silecektir. Gerekirse önce yedekleyin.
```cmd
adb shell restore
```

#### Android'e reboot edin
```cmd
fastboot reboot 
```

## Bitti!
