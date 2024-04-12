<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Xiaomi Pad 5 에서 윈도우 구동

## 문제 해결

## I can't move files to the Windows folder from Android 

If you are unable to move files to the Windows folder, it means you shut down Windows instead of restarting it. To fix this issue, boot back to Windows and use restart, then as it restarts boot to fastboot and use it to return to Android

##### 끝!

## 윈도우에서 충전 작동 안 됨
> [!WARNING]
> host mode가 활성화된 경우 유전원 USB 허브를 사용하지 마십시오. 그렇지 않으면 잠재적으로 장치를 손상시킬 가능성이 있습니다. 유전원 USB 허브를 사용하고자 하는 경우, [USB host mode 비활성화 가이드](/guide/Korean/Additional-materials-ko.md#usb-호스트-모드-비활성화)를 참조하시기 바랍니다.

윈도우에서의 충전은 오직 특정한 케이블에서만 작동됩니다. 작동된다고 알려진 케이블은 순정 Poco X3 Pro 케이블, (USB-A 포트의 주황/빨강 핀으로도 식별될 수 있습니다) 그리고 Nimaso 100W USB-C to USB-C 고속 충전 케이블 입니다.

##### 끝!

## 안드로이드로 부팅할 수 있으나 부트로더로 부팅할 수 없음

### 준비물:

- [안드로이드 플랫폼 도구](https://developer.android.com/studio/releases/platform-tools)

- [SHRP 리커버리](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/SHRP.img)

> [!Important]
> This will only work if you are rooted. If you aren't, the only way to recover is to flash your device with EDL using [MrAuthTool](https://mrauthtool.com/)

- Remove the **UEFI** image from the UEFI folder in your internal storage, then place the **SHRP recovery** image here
- Press `QUICKBOOT TO WINDOWS` in the WOA Helper app
- Once booted into the recovery, connect your device to your PC and run:
```cmd
adb shell parted /dev/block/sda
```
- Run ```print``` to list all partitions
- Look for partitions that have spaces in the names e.g "Basic Data Partition" and note their volume number
- Remove this partition with ```rm $```, replacing **$** with the volume number
- Run ```quit```
- Run ```adb reboot bootloader```, and when you see the **FASTBOOT** logo on your screen, flash your Android boot image with ```fastboot flash boot_a path\to\boot.img```
- You may have to do the same for **boot_b** if your device does not boot, or if it boots back to the recovery

> [!Note]
> Make sure you replace the recovery image in the UEFI folder with the UEFI file again

##### 끝!

## 부팅 시 fsa4480.sys 블루스크린이 뜸

- 드라이버 폴더를 여십시오

- ```components\QC8150\Device\DEVICE.SOC_QC8150.NABU\Drivers\USB``` 폴더를 제거하십시오

- 드라이버를 재설치하십시오

- UEFI로 부팅하십시오

- 부팅되면, 제거된 드라이버를 다시 추가하여 드라이버를 다시 재설치하십시오

##### 끝!

## 안드로이드로 전환 후 무한부팅됨

- fastboot를 실행하십시오

- ```fastboot set_active other```

- ```fastboot flash boot <boot.img>```

- ```fastboot reboot```

##### 끝!
