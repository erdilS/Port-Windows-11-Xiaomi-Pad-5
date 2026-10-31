<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Xiaomi Pad 5'te Windows Çalıştırma

## Cihazı EDL Modda Geri Yükleme

### EDL moduna girme
> Xiaomi Pad 5'i **EDL moduna** almanın iki yolu vardır. Size uygun olanı kullanın.

> [!NOTE]
>
> ▶️ Menüyü açmak için tıklayın.

<details>
  <summary><strong>Yöntem 1: Bootloader kilidi açık</strong></summary>

> Bootloader kilidiniz açıksa, **fastboot modunda** şu komutu çalıştırın
```cmd
fastboot oem edl
```

</details>

<details>
  <summary><strong>Yöntem 2: Bootloader kilitli veya cihaz açılmıyor</strong></summary>

- **EDL kablonuz** varsa cihazınıza takın ve **EDL moduna** girmek için kablonun üzerindeki düğmeye basın.
> İşe yarayan EDL kablolarının adında genellikle V2 bulunur, örneğin **Hydra V2 EDL Cable**.
- Alternatif olarak **test noktalarını kısa devre yapın** (bunun için tableti ekran tarafından sökmeniz gerekir, talimatları YouTube'da bulabilirsiniz).

</details>

### Cihazı kontrol edin
- Bilgisayarınızda **Aygıt Yöneticisi**'ni açın ve **Qualcomm HS-USB QDLoader 9008** gibi yeni bir aygıt arayın.
- Aygıtın adı **QUSB_BULK_CID** ise ve/veya **Aygıt Yöneticisi**'nde sarı bir uyarı ⚠️ görünüyorsa sürücüleri kurmanız/güncellemeniz gerekir.
- Bunun için **[QUD.zip](https://github.com/n00b69/woa-betalm/releases/download/Qfil/QUD.zip)** dosyasını indirip arşivden çıkarın, Aygıt Yöneticisi'nde hatalı aygıtı seçin, **Sürücüyü güncelleştir**'e tıklayın ve çıkardığınız **QUD** klasörünü seçin.

## MiFlash ile flashlama

### Gerekli Dosyalar
- [`Yamalı MiFlash Tool`](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/Files/MiFlashPatched.zip)

- [`Yamalı firehose (.elf) dosyası`](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/Files/prog_ufs_firehose_sm7150_ddr.elf)

- [`Nabu için fastboot ROM`](https://xiaomifirmwareupdater.com/hyperos/nabu/)

### Dosyaları hazırlayın
- Xiaomi Pad 5 için indirdiğiniz **fastboot ROM**'u arşivden çıkarın.
- İndirdiğiniz **MiFlashPatched.zip** dosyasını arşivden çıkarın.
- İndirdiğiniz **firehose (.elf)** dosyasını, çıkardığınız **fastboot ROM** içindeki **images** klasörüne kopyalayın ve mevcut dosyanın üzerine yazın.

#### MiFlash Tool'u açın
- Çıkardığınız **MiFlashPatched.zip** içindeki **MiFlash** klasörüne gidin.
- **XiaoMiFlash.exe** dosyasını yönetici olarak çalıştırın.

### ROM'u flashlayın
- **MiFlash**'ta **Select** düğmesine tıklayın ve **fastboot ROM**'u çıkardığınız klasörü seçin (**firehose.elf** dosyasını değiştirdiğiniz klasör).
- **MiFlash**'ta **Clean All** seçeneğinin işaretli olduğundan emin olun.
- Cihazın bağlı olduğunu doğrulamak için **MiFlash**'ta **Refresh**'e tıklayın.
- Cihazınız algılandıktan ve **Clean All** seçiliyken flashlamayı başlatmak için **Flash**'a tıklayın.

> [!Important]
> 2 dakika içinde kaybolmayan bir hata görürseniz cihazı yeniden **EDL moduna** alın, ardından tekrar denemek için yine **Refresh** ve **Flash**'a tıklayın.

#### Cihazı yeniden başlatın
- Flashlama bittiğinde cihazı yeniden başlatmak için **Reboot** düğmesine tıklayın.

---

#### Bitti!
Xiaomi Pad 5'iniz artık orijinal çalışır durumuna geri yüklenmiş olmalı!
