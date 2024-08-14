<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Xiaomi Pad 5'te Windows Çalıştırma
> [!WARNING]
> **LÜTFEN YOUTUBE VEYA BAŞKA BİR PLATFORMDAKİ GÜNCEL OLMAYAN VİDEO REHBERLERİNİ KULLANMAYIN! BU VİDEOLAR ESKİDİR VE BUNLARI KULLANARAK CİHAZINIZI BRICK EDEBİLİRSİNİZ! EĞER BİR VİDEO REHBERİNE İHTİYACINIZ VARSA, [ArtoSeVeN](https://www.youtube.com/channel/UCYjwfxlYlJ7Nnzv01oszQvA) TARAFINDAN HAZIRLANAN BU [YENİ VİDEO REHBERİNİ](https://youtu.be/BbgTbTGbXYg) KULLANIN**

## Kurulum

### Gerekli Dosyalar
- ```Beyin```

- [```DriveLetterAssigner```](https://github.com/Misha803/My-Scripts/releases/tag/DriveLetterAssigner)

- [```ARM Windows esd```](https://worproject.com/esd) (Şu seçenekleri seçin: Version: ```11``` | Build: ```22631.2861``` | Architecture: ```ARM64``` | Edition: ```CLIENT``` | Language:  ```istediğiniz dil```)
  
- [```Sürücüler (driverlar)```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/Drivers)

### Windows'u kurmaya başlamak için recovery'e boot edin
> Komutun **bulunduğu\yol** ksımını, recovery imajının bulunduğu asıl yolla değiştirin
```cmd
fastboot boot bulunduğu\yol\recovery.img
```

#### msc çalıştırın
> Sizden komutu bir kez daha çalıştırmanıza dair uyarı gelirse, bunu yapın
```cmd
adb shell msc
```

### WINNABU ve ESPNABU bölümlerine harf atayın 

> **X** ve **Y** harflerini tabletin **WINNABU** ve **ESPNABU** bölümlerine otomatik olarak atayabilmesi için **[```DriveLetterAssigner scriptini```](https://github.com/Misha803/My-Scripts/releases/tag/DriveLetterAssigner) çalıştırın ve klavyede "Y" tuşuna basın**

### Windows'u kurun
> [!Important]
> **Yönetici (admin) cmd**'si kullandığınızdan emin olun

> `<bulunduğu\yol\install.esd>` yerine install.esd dosyasının bulunduğu gerçek yolu yazın (install.wim ya da 22631.2861.XXXXXXX.esd olarak da adlandırılmış olabilir)

```cmd
dism /apply-image /ImageFile:<bulunduğu\yol\install.esd> /index:6 /ApplyDir:X:\
```

> Eğer `Error 87` hatası alırsanız, `dism /get-imageinfo /ImageFile:<bulunduğu\yol\install.esd>` komutu ile imajınızın indexini (dizinini) kontrol edin, ardından `index:6` yerine imajınızdaki Windows 11 Pro'nun gerçek index numarasını yazın

### boot.img dosyasını Windows'a kopyalayın
- **root.img** dosyasını **platform-tools** klasöründen **WINNABU** diskine sürükleyip bırakın, sonra da adını **boot.img** olarak değiştirin.

### Sürücüleri kurun
> Sürücü arşivini çıkarın, ardından `OfflineUpdater.cmd` dosyasını açın (eğer hata verirse, `OfflineUpdaterFix.cmd` dosyasını çalıştırın)

> Bir harf girmenizi isterse, **WINNABU** sürücü harfini girin (bu harf X olmalıdır), ardından enter tuşuna basın

#### EFI için Windows bootloader dosyalarını oluşturun
> Boot dosyaları kopyalanırken bir hata oluşursa, yalnızca [```DriveLetterAssigner'ı```](https://github.com/Misha803/My-Scripts/releases/tag/DriveLetterAssigner) yeniden çalıştırın (bu ESPNABU'ya U harfini atayacaktır), ardından komuttaki **Y** harfini **U** ile değiştirerek aşağıdaki komutu tekrar çalıştırın
```cmd
bcdboot X:\Windows /s Y: /f UEFI
```

#### ESPNABU'nun harfini kaldırın
> Eğer bu işe yaramazsa, bu adımı görmezden gelin ve bir sonraki adıma geçin. Bu hayalet sürücü bilgisayarınızı bir sonraki yeniden başlatışınızda kaybolacaktır.
```cmd
mountvol y: /d
```

### fastboot'a reboot edin
```cmd
adb reboot bootloader
```

#### UEFI'ye boot edin
> Komutun `bulunduğu\yol\ kısmını, UEFI imajının bulunduğu asıl yolla değiştirin
```cmd
fastboot boot bulunduğu\yol\nabu-uefi.img
```

### Android'e reboot edin
Cihazınız yaklaşık 10 dakikada Widows'a boot etmelidir, ardından Android'e boot ederek son adıma geçin


## [Son Aşama: Dualboot (çift sistem) kurulumu](dualboot-tr.md)

















