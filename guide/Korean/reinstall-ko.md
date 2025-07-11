<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Xiaomi Pad 5 에서 윈도우 구동

## 재설치
윈도우 버전이 마음에 들지 않거나 윈도우 설치에 실패한 경우, 또는 기타 등등의 이유로 인해, 윈도우 재설치를 원할 수 있습니다. 다행히도 이 과정은 매우 쉽습니다.

> [!IMPORTANT]
> 재설치는 모든 윈도우 파일을 매우 확실하게 지웁니다. 백업을 원한다면, [WOA Helper](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/woahelper.apk) 앱을 사용하여 Windows를 마운트하고 수동으로 파일을 복사할 수 있습니다

### 준비물
- ```이미 존재하는 Windows 및 boot 파티션``` (*해당 파티션들이 없는 경우, [돌아가서 이 가이드를 참고하세요](/guide/Korean/1-partition-ko.md)*)

- [```리커버리 이미지```](https://github.com/ArKT-7/twrp_device_xiaomi_nabu/releases/tag/mod-win)

- [```안드로이드 플랫폼 도구```](https://developer.android.com/studio/releases/platform-tools)

#### **fastboot**로 재부팅합니다
- USB 케이블이 연결된 상태로 재부팅될 때 **`볼륨 아래`** 버튼을 누른 상태를 유지하여 NABU를 **fastboot 모드**로 부팅하세요
- 또는, 안드로이드에 부팅되어 있는 동안 아래의 명령어를 사용해도 됩니다
```cmd
adb reboot bootloader
```

### 맞춤화된 리커버리로 부팅
> `path\to\recovery.img`를 리커버리 이미지의 실제 경로로 변경하세요
```cmd
fastboot boot path\to\recovery.img
```

### 파티션 포맷
> 한번 더 실행하라는 문구가 출력되면, 명령어를 한 번 더 입력하세요
```cmd
adb shell format
```

## [다음 단계: 윈도우 재설치](/guide/Korean/3-install-ko.md#msc를-실행합니다)
