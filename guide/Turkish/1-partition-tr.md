<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 çalıştıran bir Xiaomi Pad 5">


# Xiaomi Pad 5 üzerinde Windows Çalıştırma

### Aşama 1: Windows'un yükleneceği bölümleri oluşturma

### Gerekli Dosyalar

- [Recovery İmajı](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)

## Notlar:
> **Uyarı** Diskpart üzerinden bölüm silmeye kalkışırsanız Windows'un göndereceği UFS komutu cihaz tarafından yanlış yorumlanarak cihazın UFS belleğinin tümüyle silinmesine yola açabilir. Bölümlerde değişiklik yapmak için yalnızca recovery mod üzerinden parted ile işlem yapın.
- Cihazda bulunan tüm verileriniz silinecektir. Yedeğini almayı gerektiren dosyalarınız varsa yedeklemeyi ihmal etmeyin.
- Rehberdeki komutların tümü test edilmiştir.
- `udevadm` uyarılarını görmezden gelin
- Aynı komutları ikişer kez (ya da daha fazla) çalıştırmayın.
- Recovery modunda ekran çalışmamaktadır. Tüm işlemleri shell vasıtasıyla yapacağız.
- Eğer hata yaptığınızı düşünüyorsanız TABLETİNİZİ YENİDEN BAŞLATMAYIN ve [Telegram grubumuzdan](https://t.me/nabuwoa) yardım isteyin.

#### ⚠️ Komutların hepsini birden çalıştırmak yerine sırayla teker teker çalıştırın!

##### ⚠️ KOMUTLARI GİRERKEN HERHANGİ BİR HATA YAPMAYIN!!! EĞER YANLIŞ BİR ŞEY YAPARSANIZ CİHAZINIZI BOZABİLİRSİNİZ.

#### Bir bilgisayar aracılığıyla recovery modunda cihazı başlatın
```cmd
fastboot boot <recovery.img>
```
> Eğer cihazınızda halihazırda TWRP yüklüyse bu aşamada tek yapmanız gereken şey cihaz kapalıyken güç tuşuna ve ses açma tuşuna aynı anda basılı tutmak.

#### Varsayılan olarak bağlanmış bölümlerin bağlantısını kesin
```cmd
adb shell twrp unmount /data
```

## ADB Shell'i başlatın
```cmd
adb shell
```

### Bölüm tablosunu genişletin
> Bu işlemle beraber Windows bölümleri cihaza sığacaktır.
```sh
sgdisk --resize-table 64 /dev/block/sda
```

### parted dosyasının izinlerini düzeltin
```sh
chmod 755 /tmp/parted
```

### parted'ı başlatın
```sh
/tmp/parted /dev/block/sda
```


### `userdata` bölümünü silin
> Dilerseniz
>  `print all`
> komutuyla 31 numaralı bölümün userdata olduğunu kontrol edebilirsiniz. Yanlış bölümü silmek cihazı geri dönülemez bir şekilde brick etmeye yol açabilir.
```sh
rm 31
```

### Gerekli bölümleri oluşturun
> Eğer "ignore or cancel" tarzında uyarılar alırsanız sadece "i" yazıp Enter tuşuna basın.

<details>
<summary><b><strong>128GB modeller için</strong></b></summary>

- ESP bölümünü oluşturun (Windows önyükleme yöneticisini ve EFI dosyalarını barındırır)
```sh
mkpart esp fat32 10.9GB 11.4GB
```

- Windows'un yükleneceği ana bölümü oluşturun
```sh
mkpart win ntfs 11.4GB 70.2GB
```

- Android'in data bölümünü oluşturun
```sh
mkpart userdata ext4 70.2GB 126GB
```
  </summary>
</details>

<details>
<summary><b><strong>256GB modeller için</strong></b></summary>

- ESP bölümünü oluşturun (Windows önyükleme yöneticisini ve EFI dosyalarını barındırır)
```sh
mkpart esp fat32 10.9GB 11.4GB
```

- Windows'un yükleneceği ana bölümü oluşturun
```sh
mkpart win ntfs 11.4GB 120.8GB
```

- Android'in data bölümünü oluşturun
```sh
mkpart userdata ext4 120.8GB 254GB
```
  </summary>
</details>

### ESP bölümünü EFI imajının algılayabilmesi için önyüklenebilir yapın
```sh
set 31 esp on
```

### parted'dan çıkın
```sh
quit
```

### TWRP'ye ilk aşamadaki gibi tekrardan girin

### Tekrardan ADB Shell'i başlatın
```cmd
adb shell
```

### Bölümleri biçimlendirin
-  ESP bölümünü FAT32 olarak biçimlendirin
```sh
mkfs.fat -F32 -s1 /dev/block/bootdevice/by-name/esp -n ESPNABU
```

-  Windows bölümünü NTFS olarak biçimlendirin
```sh
mkfs.ntfs -f /dev/block/bootdevice/by-name/win -L WINNABU
```

-  Userdata bölümünü EXT4 olarak biçimlendirin
```sh
mke2fs -t ext4 /dev/block/bootdevice/by-name/userdata
```

### Android'in açılıp açılmadığını kontrol edin.
Tabletinizi yeniden başlatın, ve Android'in çalışıp çalışmadığını kontrol edin.
Eğer Android açılmıyorsa ya da bootanimationda takılı kaldıysa MIUI recovery ile veya başka recoveryler ile data bölümünü biçimlendirin.

## [Sonraki aşama: Windows kurulumu](/guide/Turkish/2-install-tr.md)
