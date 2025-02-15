# Xiaomi Pad 5 Üzerinde Windows Çalıştırma

## HyperOS/MIUI için Bootloader Kilidini Açma: Ayrıntılı Adım Adım Kılavuz

### Gereksinimler:
- [```Mi Community App(sadece HyperOS/MIUI 14 için)```](https://apkpure.net/xiaomi-community/com.mi.global.bbs/download).

- [`Mi Unlock Tool`](https://miuirom.xiaomi.com/rom/u1106245679/6.5.224.28/miflash_unlock-en-6.5.224.28.zip).

>[!NOTE]
>
> Mi Unlock Tool'daki bekleme süresi farklı olabilir, bu yüzden bekleyin.

>[!WARNING]
>
> Bekleme süresi boyunca, cihazınızı sıfırlamayın veya Xiaomi hesabınızdan çıkış yapmayın.
>
> Veri Yedekleme: Bootloader kilidini açmak, cihazınızdaki tüm verileri silecektir. Devam etmeden önce önemli verilerinizi yedekleyin.

### 1. Geliştirici Seçeneklerini Etkinleştirme:

   **MIUI için:**
   - Ayarlar → Telefon hakkında → MIUI sürümüne gidin.
   - Geliştirici seçenekleri etkinleştirilene kadar MIUI sürümüne birkaç kez dokunun (aşağıda bir pop-up göreceksiniz).

   **HyperOS için:**
   - Ayarlar → Cihazım → Detaylı bilgi ve özellikler → OS sürümüne gidin.
   - Geliştirici seçenekleri etkinleştirilene kadar OS sürümüne birkaç kez dokunun (aşağıda bir pop-up göreceksiniz).

### 2. OEM Kilidini Açma ve USB Hata Ayıklamayı Etkinleştirme:
   - Ayarlar → Ek ayarlar → Geliştirici seçeneklerine gidin.
   - OEM kilidini açmayı ve USB hata ayıklamayı etkinleştirin.

### 3. Mi Hesabı Bağlama/Uygulama ile kilit açma

<details>
<summary><b><strong>Standart İşlem (Miui-13 veya daha düşük sürümde olanlar için):</strong></b></summary>

 **```3. Mi Hesabı Bağlama:```**
   - Ayarlar > Ek ayarlar > Geliştirici seçenekleri > Mi Kilit Açma durumu'na gidin.
   - "Mi Hesabınızı Ekleyin"e tıklayın. Başarılı ekleme sonrası "Başarıyla Eklendi" mesajını göreceksiniz.

  </summary>
</details>

<details>
<summary><b><strong>Yeni İşlem (sadece HyperOS/miui-14 için):</strong></b></summary>

>

> Cihazınız global versiyon ise, belirli bir zamanda bootloader kilidi açma başvurusu yapabilirsiniz.

   **Zaman Hilesi:**
   - Xiaomi, günlük olarak 2.000 cihazın kilidini açmaya izin verir.
   - Bu günlük sınırın sıfırlanma zamanı Moskova saatiyle 19:00'dır.

 **```3. Kilit açma başvurusu yapma:```**
   - Zamanınızı Moskova saatiyle 19:00 ile eşleştirin ve hazır olun, hızlı olmazsanız bu işe yaramaz.
   - Xiaomi Community uygulamasını açın, Global olarak ayarlayın ve cihazınızdaki aynı hesapla giriş yapın.
   - "Ben" sekmesine gidin, "Bootloader kilidini aç" seçeneğine tıklayın, ardından "Başvur" seçeneğine tıklayın.
   - Erişim izni verildikten sonra Ayarlar > Ek ayarlar > Geliştirici seçenekleri > Mi Kilit Açma durumu'na gidin.
   - "Mi Hesabınızı Ekleyin"e tıklayın. Başarılı ekleme sonrası "Başarıyla Eklendi" mesajını göreceksiniz.

  </summary>
</details>

### 4. Bootloader Kilidini Açma:
   - Mi Flash Unlock Tool'u açın ve aynı Mi hesabıyla giriş yapın.
   - Cihazınızı Fastboot Moduna alın ve PC'nize bağlayın.
   - PC'nizdeki Mi Unlock Tool'u kullanarak bootloader kilidini açın.
   - 99%'da bekleme süresi hatası gösterirse, büyük olasılıkla 72 saat/3 gün, her şeyi kapatın ve süre dolana kadar bekleyin, ardından 4. adımı tekrarlayın.

#### Teşekkürler ve Takdirler:
Bu kılavuz, [@ArKT_7](https://t.me/ArKT_7), [@I914900HX](https://t.me/I914900HX), [@Samponnporlsak](https://t.me/Samponnporlsak) tarafından test edilmiştir.

Özellikle HyperOS/miui-14'te uygulama zaman hilesini paylaşan [@hxruofficial](https://t.me/hxruofficial)'e teşekkür ederiz. Kendisi Qualcomm flashlama, EDL ve FDL konularında uzmandır. Araçlarını ve hizmetlerini [HXRU Tool](https://hxrutool.com/) adresinden inceleyebilirsiniz.
