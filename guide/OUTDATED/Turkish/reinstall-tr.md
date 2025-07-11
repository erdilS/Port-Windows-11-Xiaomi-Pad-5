<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Xiaomi Pad 5'te Windows Çalıştırma

## Yeniden kurulum
Windows sürümünüzü beğenmediyseniz veya Windows kurulumunuzu bozduysanız ya da başka bir şey yaptıysanız, muhtemelen Windows'u yeniden yüklersiniz. Neyse ki bu işlem çok kolaydır.

> [!IMPORTANT]
> Açıkçası, bu işlem tüm Windows dosyalarınızı silecektir. Bunlardan herhangi birini yedeklemek isterseniz, [WOA Helper](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/woahelper.apk) uygulamasını kullanarak Windows'u mount edip saklamak istediğiniz dosyaları manuel olarak kopyalayabilirsiniz


### Gerekli Dosyalar

- `Mevcut Windows ve boot bölümleri` (*Bunlarla henüz tanışmadıysanız, [geri dönün ve bu rehber hiç var olmamış gibi davranın](/guide/Turkish/1-partition-tr.md)*)

- [``Recovery imajı``](https://github.com/ArKT-7/twrp_device_xiaomi_nabu/releases/tag/mod-win)

- [``Android platform araçları``](https://developer.android.com/studio/releases/platform-tools)


### Windows ve boot bölümlerini biçimlendirmek için recovery'e boot edin

```cmd
fastboot boot <recovery.img>
```

### Bölümleri formatlayın
> Eğer komutu bir kez daha çalıştırmanıza dair uyarı gelirse, bunu yapın
```cmd
adb shell format
```

## [Sıradaki adım: Windows'u tekrardan kurma](/guide/Turkish/3-install-tr.md#Execute-msc)
