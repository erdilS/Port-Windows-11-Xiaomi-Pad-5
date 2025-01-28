<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Xiaomi Pad 5 에서 윈도우 구동

## 문제 해결

## 안드로이드에서 윈도우 폴더로 파일을 이동할 수 없음

윈도우 폴더로 파일을 이동할 수 없다면, 윈도우를 재부팅할 때 다시 시작이 아닌 시스템 종료를 이용하였기 때문일 수 있습니다. 이 문제를 해결하기 위하여, 윈도우로 다시 부팅하고 다시 시작 버튼을 이용하세요. 그런 다음, 다시 시작될 때 fastboot로 부팅하고 안드로이드로 다시 돌아올 수 있도록 작업하세요 

##### 끝!
## fastboot 또는 리커버리에서 장치가 인식되지 않음
> 이 경우는 주로 (적절한) USB 드라이버가 설치되지 않았음을 의미합니다
- [QUD.zip](https://github.com/n00b69/woa-betalm/releases/download/Qfil/QUD.zip)을 다윤로드하고 압축 해제하세요.
- 장치 관리자를 열고 알 수 없는 장치나 **Android**, **ADB Interface**, 또는 **QUSB_BULK** 등 오류가 표시되는 장치를 찾습니다.
- 이 장치를 마우스로 우클릭하고, "드라이버 업데이트" > "내 컴퓨터에서 드라이버 찾아보기"를 선택하고, 이전에 압축 해제했던 **QUD 폴더** 를 선택합니다.

##### 끝!

## 윈도우에서 충전 작동 안 됨
> [!WARNING]
> 호스트 모드가 활성화된 경우 유전원 USB 허브를 사용하지 마세요. 그렇지 않으면 잠재적으로 장치를 손상시킬 가능성이 있습니다. 유전원 USB 허브를 사용하고자 하는 경우, [USB host mode 비활성화 가이드](/guide/Korean/Additional-materials-ko.md#usb-호스트-모드-비활성화)를 참조하시기 바랍니다.

윈도우에서의 충전은 오직 특정한 케이블에서만 작동됩니다. 작동된다고 알려진 케이블은 순정 Poco X3 Pro 케이블, (USB-A 포트의 주황/빨강 핀으로도 식별될 수 있습니다) 그리고 Nimaso 100W USB-C to USB-C 고속 충전 케이블 입니다.

##### 끝!

## fastboot에 진입된 NABU가 내 PC/노트북에서 감지되지 않음. 어떻게 해결?
- [**`QUD.zip`**](https://github.com/n00b69/woa-betalm/releases/download/Qfil/QUD.zip)을 다운로드하고 압축해제 합니다.
- 장치 관리자를 열고 알 수 없는 장치 또는 Android 및 QUSB_BULK로 표시되며 오류가 발생한 장치를 확인합니다.
- 해당 장치를 마우스로 우클릭하고, **```드라이버 업데이트```** → **`내 컴퓨터에서 드라이버 찾아보기`** 순서대로 선택합니다. 그런 다음 아까 압축해제한 QUD 폴더를 선택합니다.

##### 끝!


## 안드로이드로 부팅할 수 있으나 부트로더로 부팅할 수 없음

### 준비물:
- [Termux](https://play.google.com/store/apps/details?id=com.termux)

- [안드로이드 플랫폼 도구](https://developer.android.com/studio/releases/platform-tools)

- [SHRP 리커버리](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/SHRP.img)

#### If you have access to Android:
- Install **Termux** and grant it root access.
- Install **tsu** and **parted** using these two commands, press `Y` if it asks you to confirm:
```cmd
pkg install tsu
```
```cmd
pkg install parted
```
- Run the below command to open parted:
```cmd
parted /dev/block/sda
```
- Run ```print``` to list all partitions.
- Look for partitions that are more than 16 characters long, for example "Basic Data Partition" and note their volume number.
- Rename this partition with ```name $ test```, replacing **$** with the partition number, and replacing **test** with the name you want the partition to have.
- Run ```quit```.

##### Done!


#### If you have access to Windows:
- Rename **C:\boot.img** to **C:\bootb.img**.
- Download the **SHRP recovery** image, rename it to **boot.img**, and place it in `C:\`.
- Run the **Switch to Android** or **Android** shortcut to flash and boot into SHRP recovery.
- Once booted into the recovery, connect your device to your PC and run:
```cmd
adb shell parted /dev/block/sda
```
- Run ```print``` to list all partitions.
- Look for partitions that are more than 16 characters long, for example "Basic Data Partition" and note their volume number.
- Rename this partition with ```name $ test```, replacing **$** with the partition number, and replacing **test** with the name you want the partition to have.
- Run ```quit```.
- Run ```adb reboot bootloader```, and when you see the **FASTBOOT** logo on your screen, flash your Android boot image with ```fastboot flash boot_a path\to\boot.img```.
- You may have to do the same for **boot_b** if your device does not boot, or if it boots back to the recovery.

> [!important]
> Make sure to put the UEFI image back into the UEFI folder, or if you used the Windows method, the boot.img in C:\

##### Done!

## 부팅 시 fsa4480.sys 블루스크린
- 드라이버 폴더를 엽니다

- NABU.xml에서 ```<DriverPackageFile Path="$(mspackageroot)\components\QC8150\Device\DEVICE.SOC_QC8150.NABU\Drivers\USB" Name="fsa4480.inf" ID="fsa4480"/>``` 줄을 제거합니다

- 드라이버를 재설치합니다

- UEFI로 부팅합니다
> [!NOTE]
> 이렇게 해도 블루스크린이 나타나면, `재설치` 가이드를 참고하여 이 드라이버 패키지를 사용하세요 

##### 끝!

## 안드로이드로 전환 후 무한부팅
- fastboot로 부팅하세요

- ```fastboot set_active other```

- ```fastboot flash boot <boot.img>```

- ```fastboot reboot```

##### 끝!

















