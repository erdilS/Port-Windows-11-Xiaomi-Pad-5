<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Xiaomi Pad 5 에서 윈도우 구동

## 문제 해결

## 안드로이드에서 윈도우 폴더로 파일을 이동할 수 없음

윈도우 폴더로 파일을 이동할 수 없다면, 윈도우를 재부팅할 때 다시 시작이 아닌 시스템 종료를 이용하였기 때문일 수 있습니다. 이 문제를 해결하기 위하여, 윈도우로 다시 부팅하고 다시 시작 버튼을 이용하십시오. 그런 다음, 다시 시작될 때 fastboot로 부팅하고 안드로이드로 다시 돌아올 수 있도록 작업하십시오 

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
> 이 작업은 오직 기기를 루팅했을 때만 가능합니다. 루팅하지 않았을 때의 복구 방법은 [MrAuthTool](https://mrauthtool.com/)을 이용하여 EDL로 기기에 플래시하는 방법뿐입니다.

- 내부 저장소의 UEFI 폴더에서 **UEFI** 이미지를 제거하십시오. 그런 다음, **SHRP recovery** 이미지를 이곳으로 이동하십시오
- WOA Helper 앱에서 `QUICKBOOT TO WINDOWS`를 선택하십시오
- 리커버리로 부팅되면, PC에 기기를 연결하고 아래의 명령어를 입력하십시오
```cmd
adb shell parted /dev/block/sda
```
- 모든 파티션을 보기 위하여 ```print```를 입력하십시오
- "Basic Data Partition"와 같이 이름에 공백 문자가 있는 파티션을 찾고 해당 파티션의 볼륨 숫자를 기억하십시오
- ```rm $```를 입력하여 해당 파티션을 제거하십시오. 이때 **$** 를 볼륨 숫자로 교체하십시오
- ```quit```를 입력하십시오
- ```adb reboot bootloader```를 입력하고, 화면에서 **FASTBOOT** 로고가 보일 때, ```fastboot flash boot_a boot.img\의\경로```를 입력하여 안드로이드 boot 이미지를 플래시하십시오
- 기기가 부팅되지 않거나, 리커버리로 다시 부팅되면 **boot_b** 에도 같은 작업을 해야할 수 있습니다

> [!Note]
> UEFI 폴더의 리커버리 이미지를 UEFI 파일로 교체했는지 다시 한 번 확인하십시오

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
