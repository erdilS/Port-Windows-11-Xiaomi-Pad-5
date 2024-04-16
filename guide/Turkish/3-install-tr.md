<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Xiaomi Pad 5'te Windows Çalıştırma
> [!WARNING]
> **LÜTFEN YOUTUBE VEYA BAŞKA BİR PLATFORMDAKİ GÜNCEL OLMAYAN VİDEO REHBERLERİNİ KULLANMAYIN! BU VİDEOLAR ESKİDİR VE BUNLARI KULLANARAK CİHAZINIZI BRICK EDEBİLİRSİNİZ! EĞER BİR VİDEO REHBERİNE İHTİYACINIZ VARSA, [ArtoSeVeN](https://www.youtube.com/channel/UCYjwfxlYlJ7Nnzv01oszQvA) TARAFINDAN HAZIRLANAN BU [YENİ VİDEO REHBERİNİ](https://youtu.be/BbgTbTGbXYg) KULLANIN**

## Windows Kurulumu
> [!NOTE]
> Şimdi CMD veya powershell'i yönetici olarak açmanız ve ardından -yolunu klasörün gerçek yolu ile değiştirdiğiniz- `cd C:\gerçek\yol\platform-tools` komutunu kullanarak platform-tools klasörüne erişmeniz önerilir .
> Tüm kılavuz boyunca aynı pencereyi kullanın, pencereyi kapatmayın.

### Gerekli Dosyalar
- ```Beyin```

- [```ARM Windows esd```](https://worproject.com/esd) (Şu seçenekleri seçin: Version: ```11``` | Build: ```22631.2861``` | Architecture: ```ARM64``` | Edition: ```CLIENT``` | Language:  ```istediğiniz dil```)
  
- [```Sürücüler (driverlar)```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/Drivers)


### Windows'u kurmaya başlamak için recovery'e boot edin
```cmd
fastboot boot <recovery.img>
```

#### msc çalıştırın
> Sizden komutu bir kez daha çalıştırmanızı dair uyarı gelirse, bunu yapın
```cmd
adb shell msc
```

### Diskpart'ı (Windows disk yönetimini) başlatın
> [!WARNING]
> DISKPART'TA İKEN SİLME, OLUŞTURMA YA DA BAŞKA BİR DEĞİŞİKLİK YAPMAYIN!!! BU BÜTÜN UFS'NİZİ SİLECEKTİR YA DA FASTBOOT'A BOOT ETMENİZİ ENGELLEYECEKTİR!!! BU CİHAZINIZIN ÇÖZÜMÜ OLMAKSIZIN KALICI OLARAK BRICK OLDUĞU ANLAMINA GELİR! (cihazı Xiaomi servisine götürme ya da EDL ile flashlama elbette bir çözümdür ancak mevzubahis iki çözüm de ücretsiz değildir)

```cmd
diskpart
```

#### Tabletinizdeki Windows volümünü seçin
> Bunu bulmak için `list volume` komutunu kullanabilirsiniz, "WINNABU" isimli volümdür.
```diskpart
select volume <volume numarası>
```

#### X harfini atayın
```diskpart
assign letter x
```

#### Tabletteki ESP bölümünü seçin
> Bunu bulmak için `list volume` komutunu kullanabilirsiniz, "ESPNABU" isimli volümdür.
```diskpart
select volume <volume numarası>
```

#### Y harfini atayın
```diskpart
assign letter y
```

#### Diskpart arayüzünden çıkın.
```diskpart
exit
```

### Windows kurulumu
> `<bulunduğu\yol\install.esd>` yerine install.esd dosyasının bulunduğu gerçek yolu yazın (install.wim olarak da adlandırılmış olabilir)
```cmd
dism /apply-image /ImageFile:<bulunduğu\yol\install.esd> /index:6 /ApplyDir:X:\
```

> Eğer `Error 87` hatası alırsanız, `dism /get-imageinfo /ImageFile:<bulunduğu\yol\install.esd>` komutu ile imajınızın indexini (dizinini) kontrol edin, ardından `index:6` yerine imajınızdaki Windows 11 Pro'nun gerçek index numarasını yazın

### Sürücü kurulumu
> Eğer `"Automatic WINNABU detection failed! Enter Drive Letter manually"` diyorsa **`X`** yazın
```cmd
 Sürücülerin bulunduğu klasörü açın ve OfflineUpdater.cmd dosyasını çalıştırın
```
> If any errors appear under **Installing App Packages**, ignore them and continue

#### EFI için Windows bootloader dosyalarını oluşturun
> Boot dosyalarını kopyalarken bir hata oluşursa, ESPNABU'nun hala Y harfine sahip olup olmadığını kontrol edin. Eğer Y harfine sahip değilse, başka bir harf (mesela K) ekleyin ve aşağıdaki komuttaki Y'yi sırasıyla söz konusu harfle değiştirin
```cmd
bcdboot X:\Windows /s Y: /f UEFI
```

#### ESPNABU'nun harfini kaldırın
> Eğer bu işe yaramazsa, bunu görmezden gelin ve bir sonraki komuta geçin. Bu hayalet sürücü bilgisayarınızı bir sonraki yeniden başlatışınızda kaybolacaktır.
```cmd
mountvol y: /d
```

### Android'e reboot edin
```cmd
adb reboot
```

> Cihazınızı kurduktan sonra son adıma gidin

## [Son Aşama: Dualboot (çift sistem) kurulumu](dualboot-tr.md)




















