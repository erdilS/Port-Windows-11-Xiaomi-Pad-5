<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Windows no Xiaomi Pad 5

## Instalação

### Pré requesitos
- [```Bootloader desbloqueado```](/guide/Portuguese/unlock-bootloader-pt.md)

-  ```Cérebro```

- ```Windows 10(or higher) PC/Laptop```

- [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools)

- [```Imagem do Recovery```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

### Notas:
> [!Warning]\
> You can use any Android for dualboot - MIUI/Hyper OS or any custom ROM

> [!Warning]
> All your data will be erased! Back up now if needed.
> 
> DO NOT REBOOT YOUR TABLET if you think you made a mistake, ask for help in the [Telegram chat](https://t.me/nabuwoa)

### Particionando seu dispositivo e fazendo backup da boot.img
> [!NOTE]
> Não sabe como começar? Só descompactar o [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools), e abra o ```cmd (command prompt)``` ou o `powershell` como administrador e digite o seguinte comando, substituindo o "caminho\para_o\platform-tools" com o lacal correto da pasta:
```cmd
cd "caminho\para_o\platform-tools"
```
> Use essa mesma janela em todos os passos.

> [!Note]
> If your device is not detected in fastboot or recovery mode, you'll have to install USB drivers [using this guide](troubleshooting-en.md#device-is-not-recognized-in-fastboot-or-recovery)

#### Reboot into fastboot mkde
- Boot your NABU into **fastboot mode** by holding down the **`volume down`** button while rebooting with a USB cable connected
- Alternatively, run the below command while booted in Android
```cmd
adb reboot bootloader
```

### Inicie o recovery usando seu PC com o comando
> Substitua o `caminho\para_o\recovery.img` com o caminho correto do recovery.img
```cmd
fastboot boot caminho\para_o\recovery.img
```

### Faça um backup da sua boot.img atual
```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/normal_boot.img" && adb pull /tmp/normal_boot.img
```

### Partitioning your device
> There are two methods to partition your device. Please select the method you would like to use below.
 
> [!NOTE]
>
> ▶️ Click to expand the menu.

### Method 1: Automatic partitioning (recommended)

<details>
  <summary><strong>Click here for method 1</strong></summary> 

### Particionando seu dispositivo
> Substitua o **$** com a quantidade de armazenamento que você quer que o Windows tenha (não escreva GB, apenas digite o número)
> 
> Se o comando disser pra fazer de novo, faça
```sh
adb shell partition $
```

### [Próximo passo: Instalar o Root](/guide/Portuguese/2-rootguide-pt.md)

</details>

----

### Method 2: Manual partitioning (use it only if you know what you're doing)

<details>
  <summary><strong>Click here for method 2</strong></summary> 

#### Unmount data
> Ignore any possible errors and continue
```cmd
adb shell umount /dev/block/by-name/userdata
``` 

#### Resizing the partition table
```cmd
adb shell sgdisk --resize-table 64 /dev/block/sda
```

### Preparing for partitioning
```cmd
adb shell parted /dev/block/sda
``` 

#### Printing the current partition table
> Parted will print the list of partitions, **userdata** should be the last partition in the list
```cmd
print
``` 

#### Removing userdata
> Replace **$** with the number of the **userdata** partition, which should be **31**
```cmd
rm $
``` 

#### Recreating userdata
> Replace **10.9GB** with the former start value of **userdata** which we just deleted
>
> Replace **70GB** with the end value you want **userdata** to have. In this example your available usable space in Android will be 70GB-10.9GB = **59GB**
```cmd
mkpart userdata ext4 10.9GB 70GB
``` 

#### Creating ESP partition
> Replace **70GB** with the end value of **userdata**
>
> Replace **70.3GB** with the value you used before, adding **0.3GB** to it
```cmd
mkpart esp fat32 70GB 70.3GB
``` 

#### Creating Windows partition
> Replace **70.3GB** with the end value of **esp**
```cmd
mkpart win ntfs 70.3GB -0MB
``` 

#### Making ESP bootable
> Use `print` to see all partitions. Replace "$" with your ESP partition number, which should be **32**
```cmd
set $ esp on
``` 

#### Exit parted
```cmd
quit
``` 

### Formatting Windows and ESP partitions
> Ensure that **win** actually has partition number **33** by scrolling up to the output of the `print` command
```cmd
adb shell mkfs.ntfs -f /dev/block/sda33 -L WINNABU
``` 

> Ensure that **esp** actually has partition number **32** by scrolling up to the output of the `print` command
```cmd
adb shell mkfs.fat -F32 -s1 /dev/block/sda32 -n ESPNABU
```

### Fixing the GPT
> Or Windows may brick your device
```cmd
adb shell fixgpt
```

#### Verifique se o Android ainda inicia
> To check if Android still starts
>
> If it doesn't, reboot into stock recovery and perform a factory reset there
```cmd
adb reboot
```

### [Próximo passo: Instalar o Root](/guide/Portuguese/2-rootguide-pt.md)

----

</details>



















