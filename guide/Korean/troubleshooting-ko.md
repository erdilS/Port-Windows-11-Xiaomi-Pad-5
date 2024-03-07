<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Xiaomi Pad 5 에서 윈도우 구동

## 문제 해결

## 윈도우에서 충전 작동 안 됨
> [!WARNING]
> host mode가 활성화된 경우 유전원 USB 허브를 사용하지 마십시오. 그렇지 않으면 잠재적으로 장치를 손상시킬 가능성이 있습니다. 유전원 USB 허브를 사용하고자 하는 경우, [USB host mode 비활성화 가이드](/guide/Korean/Additional-materials-ko.md#usb-호스트-모드-비활성화)를 참조하시기 바랍니다.

윈도우에서의 충전은 오직 특정한 케이블에서만 작동됩니다. 작동된다고 알려진 케이블은 순정 Poco X3 Pro 케이블, (USB-A 포트의 주황/빨강 핀으로도 식별될 수 있습니다) 그리고 Nimaso 100W USB-C to USB-C 고속 충전 케이블 입니다.


## 안드로이드로 부팅할 수 있으나 부트로더로 부팅할 수 없음

### 준비물:

- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)

> [!WARNING]
 Xiaomi Pad 5에는 장치에 플래시하여 완전히 작동하는 커스텀 리커버리가 없기 때문에 아마도 이러한 단계는 도움이 되지 않을 것입니다. 또한 대부분의 최신 A/B 장치와 마찬가지로 TWRP 설치 zip 등이 없으며 fastboot가 손상되어 기존 리커버리 이미지로 부팅할 수 없습니다. AOSP 롬을 이미 설치한 경우 AOSP 리커버리가 이미 설치되어 있을 수 있으며 직접 부팅할 수 있으므로 다음 단계를 진행할 수 있습니다. 루팅되지 않은 MIUI의 경우, 이 단계는 도움이 되지 않습니다.
>
> 따라서 공백과 특수 문자가 포함된 디스크 레이블을 사용하지 마십시오. 가능하다면 백만 번은 테스트된 ESPNABU 및 WINNABU 레이블을 사용하십시오. 디스크 레이블을 잘못 입력하여 fastboot를 손상시켰는데 루팅되지 않은 MIUI를 사용 중인 경우 승인된 계정으로 EDL을 통해 롬을 플래시해야 하며 이에 대한 비용을 지불해야 할 수 있습니다.


이는 부트로더가 처리할 수 없는 볼륨 이름이 있는 파티션으로 인해 발생합니다. 이를 해결하려면 아래의 명령어를 입력하십시오.

- 리커버리로 부팅하십시오

- PC에 태블릿을 연결하십시오

- PC에서 명령 프롬프트를 여십시오

- ```adb shell```를 실행하십시오

- ```parted```를 실행하십시오

- ```print```를 실행하여 모든 파티션을 불러오십시오

- 이름에 공백이 있는 파티션을 찾으십시오 (예: "Basic Data Partition") 그리고 그 볼륨의 숫자를 기억하십시오

- 이제 ```rm <vol number>```를 실행하십시오 (예: ```rm 99```)


## 부팅 시 fsa4480.sys 블루스크린

- 드라이버 폴더를 여십시오

- ```components\QC8150\Device\DEVICE.SOC_QC8150.NABU\Drivers\USB``` 폴더를 제거하십시오

- 드라이버를 재설치하십시오

- UEFI로 부팅하십시오

- 부팅되면, 제거된 드라이버를 다시 추가하여 드라이버를 다시 재설치하십시오


## 안드로이드로 전환 후 무한부팅

- fastboot를 실행하십시오

- ```fastboot set_active other```

- ```fastboot flash boot <boot.img>```

- ```fastboot reboot```
