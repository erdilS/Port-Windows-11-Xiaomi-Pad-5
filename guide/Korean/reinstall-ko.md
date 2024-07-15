<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Xiaomi Pad 5 에서 윈도우 구동

## 재설치
윈도우 버전이 마음에 들지 않거나 윈도우 설치에 실패한 경우, 또는 기타 등등의 이유로 인해, 윈도우 재설치를 원할 수 있습니다. 다행히도 이 과정은 매우 쉽습니다.

> [!IMPORTANT]
> 재설치는 모든 윈도우 파일을 매우 확실하게 지웁니다. 백업을 원한다면, [WOA Helper](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/woahelper.apk) 앱을 사용하여 Windows를 마운트하고 수동으로 파일을 복사할 수 있습니다


### 준비물

- ```이미 존재하는 Windows 및 boot 파티션``` (*해당 파티션들이 없는 경우, [이 가이드를 참고하세요](/guide/Korean/1-partition-ko.md)*)

- [```리커버리 이미지```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [```안드로이드 플랫폼 도구```](https://developer.android.com/studio/releases/platform-tools)

### fastboot로 재부팅
- 재부팅될 때 **`볼륨 아래`** 버튼을 누른 상태를 유지하여 NABU를 **fastboot**로 재부팅하세요

- 케이블을 사용하여 PC/노트북에 기기를 연결합니다

### 윈도우 및 boot 파티션 포맷을 위한 리커버리 부팅

```cmd
fastboot boot <recovery.img>
```

### 파티션 포맷
> 한번 더 실행하라는 문구가 출력되면, 명령어를 한번 더 입력하세요
```cmd
adb shell format
```
## [다음 단계: 윈도우 재설치](/guide/Korean/3-install-ko.md#msc를-실행합니다)
