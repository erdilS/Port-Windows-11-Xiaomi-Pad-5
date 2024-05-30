<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Xiaomi Pad 5'te Windows Çalıştırma
> [!WARNING]
> **LÜTFEN YOUTUBE VEYA BAŞKA BİR PLATFORMDAKİ GÜNCEL OLMAYAN VİDEO REHBERLERİNİ KULLANMAYIN! BU VİDEOLAR ESKİDİR VE BUNLARI KULLANARAK CİHAZINIZI BRICK EDEBİLİRSİNİZ! EĞER BİR VİDEO REHBERİNE İHTİYACINIZ VARSA, [ArtoSeVeN](https://www.youtube.com/channel/UCYjwfxlYlJ7Nnzv01oszQvA) TARAFINDAN HAZIRLANAN BU [YENİ VİDEO REHBERİNİ](https://youtu.be/BbgTbTGbXYg) KULLANIN**

## Kurulum

### Gerekli Dosyalar
- ```Beyin```

- [```DriveLetterAssigner script```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/DriveLetterAssigner.V1.0.exe)

- [```ARM Windows esd```](https://worproject.com/esd) (Şu seçenekleri seçin: Version: ```11``` | Build: ```22631.2861``` | Architecture: ```ARM64``` | Edition: ```CLIENT``` | Language:  ```istediğiniz dil```)
  
- [```Sürücüler (driverlar)```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/Drivers)

### Windows'u kurmaya başlamak için recovery'e boot edin
```cmd
fastboot boot <recovery.img>
```

#### msc çalıştırın
> Sizden komutu bir kez daha çalıştırmanıza dair uyarı gelirse, bunu yapın
```cmd
adb shell msc
```

### WINNABU ve ESPNABU bölümlerine harf atayın 

> **Sadece [```DriveLetterAssigner scriptini```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/DriveLetterAssigner.V1.0.exe) çalıştırın ve klavyede "Y" tuşuna basın**

> X ve Y harflerini tabletin Windows ve ESP bölümlerine otomatik olarak atayacaktır

### Windows'u kurun
> [!Important]
> **Yönetici (admin) cmd**'si kullandığınızdan emin olun

> `<bulunduğu\yol\install.esd>` yerine install.esd dosyasının bulunduğu gerçek yolu yazın (install.wim olarak da adlandırılmış olabilir)

```cmd
dism /apply-image /ImageFile:<bulunduğu\yol\install.esd> /index:6 /ApplyDir:X:\
```

> Eğer `Error 87` hatası alırsanız, `dism /get-imageinfo /ImageFile:<bulunduğu\yol\install.esd>` komutu ile imajınızın indexini (dizinini) kontrol edin, ardından `index:6` yerine imajınızdaki Windows 11 Pro'nun gerçek index numarasını yazın

### Sürücüleri kurun
> Sürücü arşivini çıkarın, ardından `OfflineUpdater.cmd` dosyasını açın

> Bir harf girmenizi isterse, **WINNABU** sürücü harfini girin (X olmalıdır), ardından enter tuşuna basın

#### EFI için Windows bootloader dosyalarını oluşturun
> Boot dosyaları kopyalanırken bir hata oluşursa, yalnızca [```DriveLetterAssigner scriptini```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/DriveLetterAssigner.V1.0.exe) yeniden çalıştırın, bu ESPNABU'ya U harfini atayacaktır, ardından Y'yi U ile değiştirerek aşağıdaki komutu tekrar çalıştırın
```cmd
bcdboot X:\Windows /s Y: /f UEFI
```

#### ESPNABU'nun harfini kaldırın
> Eğer bu işe yaramazsa, bu adımı görmezden gelin ve bir sonraki adıma geçin. Bu hayalet sürücü bilgisayarınızı bir sonraki yeniden başlatışınızda kaybolacaktır.
```cmd
mountvol y: /d
```

### Android'e reboot edin
```cmd
adb reboot
```

> Cihazınızı kurduktan sonra son adıma gidin

## [Son Aşama: Dualboot (çift sistem) kurulumu](dualboot-tr.md)




















