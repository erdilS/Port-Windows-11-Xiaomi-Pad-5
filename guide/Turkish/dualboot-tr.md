<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 çalıştıran bir Xiaomi Pad 5">


# Xiaomi Pad 5 üzerinde Windows çalıştırma

## Windows ve Android'in tek bir slotta dual-boot olarak yüklenmesi

### Gereksinimler

- Beyin

- Rootlu Android ve rootlu Android boot.img yedeği

- [DualBoot dosyaları](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/dualboot) 

### Dualboot işleminin Windows tarafı

- Yüklemek [STA](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/StA_Installer_nabu.exe)

- Boot yedeğinizin adını boot.img yapın

- Android boot yedeğinizi C:\ dizinine kopyalayın (C:\boot.img)

- Android'e geçmek için masaüstünüzde kısayolu açın

### Dualboot işleminin Android tarafı

- [switchtowin.apk](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/switchtowindows.apk) dosyasını cihaza kurun.

-  Create folder Windows in Android storage

- UEFI dosyasının adını boot.img olarak adlandırın.

-  UEFI dosyanızı oluşturulan klasöre yerleştirin (/Android depolama/Windows/boot.img)

- Uygulamayı başlatın ve root izni verin.

- "Switch to Windows" butonuna bastığınızda cihaz yeniden başlatılacak ve Windows'a giriş yapacaktır.

