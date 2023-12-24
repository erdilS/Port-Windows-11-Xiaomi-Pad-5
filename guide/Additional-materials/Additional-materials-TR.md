<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Xiaomi pad 5'te Windows için faydalı uygulamalar ve talimatlar

## Microsoft Office

- Bunu indir [dosya](https://drive.google.com/file/d/1st8xVpxtJbe2GVTEZrC_RNumKllR97Hp/view?usp=sharing) tablete
  
- Kuruluma herhangi bir müdahaleyi önlemek için Windows Defender'ı kapatın
  
- Iso dosyasına sağ tıklayın ve Explorer'da açmak için Bağla'yı seçin

- OTOMATİK çalıştır'a çift tıklayın.kurulum sihirbazını başlatmak için exe
  
- Yüklemek istediğiniz dili ve bileşenleri seçin ve ardından Yüklemeyi başlat'ı tıklatın
  
- Yükleme ve etkinleştirmenin tamamlanmasını bekleyin

- Windows Defender'ı tekrar açın

- Office'i kullanmanın tadını çıkarın!

 ## Activate Windows

> Powershell'i açın ve şunu yazın: 

  ```cmd
irm https://massgrave.dev/get | iex 
```
> Bir pencere göründüğünde, 1'i seçin

 ## El feneri nasıl kullanılır

 - İndirmek [Flashlight.7z](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/flashlight_fix.7z) ve herhangi bir klasöre sıkıştırın

> El fenerini çalıştır.el fenerini etkinleştirmek için exe

> devre dışı bırakmak için herhangi bir tuşa basın

## Enabling charging and USB host mode

> [!WARNING]
>  Make sure any registry edits are done on the Mi Pad 5 itself

> [!NOTE]
> C to C charging with a PD supported device has been confirmed working and the 33W charger provided by Xiaomi is also confirmed to be working

- Download  [Script from Misha803](https://t.me/droidscripts/22) to easy enable it
 
- Or use traditional method - In the registry editor, change the value of the parameter ```RoleSwitchMode``` from ```3``` to ```1```: ```Computer\HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Enum\ACPI\QCOM0597\0\Device Parameters```. 


