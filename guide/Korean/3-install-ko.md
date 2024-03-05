<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Xiaomi Pad 5 에서 윈도우 구동
> [!WARNING]
> **다른 동영상 가이드는 주로 최신 상태가 아니며 NABU를 벽돌로 만들 가능성이 있기 때문에 보지 마시기 바랍니다!!! 정말 동영상 가이드가 필요하다면, [ArtoSeVeN](https://www.youtube.com/channel/UCYjwfxlYlJ7Nnzv01oszQvA) 의 [동영상 가이드](https://youtu.be/BbgTbTGbXYg) 를 보십시오**

## 설치
> [!NOTE]
> 지금부터 CMD 또는 powershell 을 관리자 권한으로 열고, `cd C:\path\to\platform-tools` 명령어를 사용하여 플랫폼 도구 폴더에 액세스 하는 것을 권장합니다. 이때 이 경로를 폴더의 실제 경로로 교체하십시오.
> Use the same window in the entire guide, do not close it.

### 준비물
- ```뇌```

- [```UEFI 이미지```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v3.img)
  
- [```ARM 윈도우 esd```](https://worproject.com/esd) (항목 선택 - Version:  ```11``` Build:  ```22631.2861``` Architecture:  ```ARM64``` Edition:  ```CLIENT``` Language:  ```원하는 언어를 선택하십시오```)
    
- [```드라이버```](https://github.com/map220v/MiPad5-Drivers/releases/latest)

### 윈도우 설치 시작을 위해 다시 리커버리로 부팅

```cmd
fastboot boot <recovery.img>
```

#### msc를 실행합니다

> 한번 더 실행하라는 문구가 출력되면, 명령어를 한번 더 입력하십시오

```cmd
adb shell msc
```
### 디스크에 문자 할당
  

#### 윈도우 디스크 관리자를 시작합니다

> 샤오미 패드 5 가 디스크로 인식되면 아래의 명령어를 입력하십시오

```cmd
diskpart
```


#### `X` 를 윈도우 볼륨에 할당합니다

#### 태블릿의 윈도우 볼륨을 선택합니다
> `list volume` 를 사용하여 볼륨을 찾으십시오. 볼륨의 이름은 "WINNABU" 입니다.

```diskpart
select volume <number>
```

#### 문자 X를 할당합니다
```diskpart
assign letter x
```

### ESP 볼륨에 `Y` 할당

#### 태블릿의 esp 볼륨을 선택합니다
> `list volume` 를 사용하여 볼륨을 찾으십시오. 볼륨의 이름은 "ESPNABU" 입니다.

```diskpart
select volume <number>
```

#### 문자 Y를 할당합니다

```diskpart
assign letter y
```

#### diskpart를 종료합니다
```diskpart
exit
```

  
  

### 설치

> Replace `<path\to\install.esd>` with the actual path of install.esd (it may also be named install.wim)

```cmd
dism /apply-image /ImageFile:<path\to\install.esd> /index:6 /ApplyDir:X:\
```

> If you get `Error 87`, check the index of your image with `dism /get-imageinfo /ImageFile:<path\to\install.esd>`, then replace `index:6` with the actual index number of Windows 11 Pro in your image


### Install Drivers

> You can download the Drivers [here](https://github.com/map220v/MiPad5-Drivers/releases/latest)

> If it says `"Automatic WINNABU detection failed! Enter Drive Letter manually"` type **`X`**

```cmd
 Open the folder with Drivers and run OfflineUpdater.cmd
```

### Create Windows bootloader files for the EFI
> If an error occurs when copying boot files, check `diskpart` to see if ESPNABU still has letter Y. If it does not, add any other letter (such as K) and replace the Y in the below command with said letter respectively
```cmd
bcdboot X:\Windows /s Y: /f UEFI
```

## Remove the drive letter for ESPNABU
> If this does not work, ignore it and skip to the next command. This phantom drive will disappear the next time you reboot your PC.
```cmd
mountvol y: /d
```


## Boot into Windows

### Make a backup of your rooted boot image

```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/rooted_boot.img" && adb pull /tmp/rooted_boot.img
```

### Reboot to bootloader 

```cmd
adb reboot bootloader
```

### Download and flash the UEFI image
> Download the [UEFI image](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v3.img)

```cmd
fastboot flash boot <path to image>
```

## Reboot to Windows
```cmd
fastboot reboot
```

> [!NOTE]
> On the first Windows boot, it will not see any Wi-Fi networks. Restart your tablet by holding down the power button until it restarts. After the reboot, it will be fixed. If you get a pop-up saying "Could not connect", press retry until it works (usually 5 times)

### Boot back into Android
After Windows has been set up, press the restart button in Windows (NOT SHUTDOWN), then as it restarts, hold `volume down` + `power`to reboot back to fastboot
> Use your backup boot image and flash it in fastboot to return to Android

```cmd
fastboot flash boot rooted_boot.img
```

```cmd
fastboot reboot
```

### [Last step: Set up Dualboot](dualboot-en.md)
