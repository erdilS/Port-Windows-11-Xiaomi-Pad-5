<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Xiaomi Pad 5 에서 윈도우 구동

## 안드로이드 재루팅
이 부분은 MIUI/Hyper OS가 업데이트되어 루트가 제거되는 경우를 위한 재루팅 과정을 설명합니다.

### 준비
- [```리커버리 이미지```](https://github.com/ArKT-7/twrp_device_xiaomi_nabu/releases/tag/mod-win)
  
- [```안드로이드 플랫폼 도구```](https://developer.android.com/studio/releases/platform-tools)

- [```Magisk.apk```](https://github.com/topjohnwu/Magisk/releases/latest)

### **fastboot** 로 재부팅
- 재부팅될 때 **`볼륨 아래`** 버튼을 누른 상태를 유지하여 NABU를 **fastboot**로 재부팅하세요

- 케이블을 사용하여 PC/노트북에 기기를 연결합니다

### 맞춤화된 리커버리로 부팅
> fastboot 모드에서, 경로 `path\to\recovery.img`를 리커버리 이미지의 실제 경로로 변경하세요
```cmd
fastboot boot path\to\recovery.img
```

### magisk 설치 
- [`magisk.apk`](https://github.com/topjohnwu/Magisk/releases/latest) PC/노트북에서 다운로드합니다 
> `path\to\magisk.apk`를 magisk.apk의 실제 경로로 변경하세요
```cmd
adb push path\to\magisk.apk /tmp/magisk.zip && adb shell twrp install /tmp/magisk.zip
```

#### 안드로이드로 재부팅합니다
> 부팅되지 않는다면, 순정 리커버리로 재부팅하여 공장 초기화를 진행해보세요
```cmd
adb reboot
```

### 설정 마무리
- 장치의 초기 설정을 마치고 [Magisk](https://github.com/topjohnwu/Magisk/releases/latest)를 다운로드하고 설치합니다. (설치되어 있지 않은 경우)
- **Magisk** 앱을 열고 화면에 표시되는 지시를 따르면 장치가 몇 초후 재부팅됩니다.


### Windows의 C:\에 boot.img 업데이트
- 안드로이드로 재부팅합니다
- ```WOA Helper```를 엽니다
- ```BACKUP BOOT IMAGE``` > ```Windows``` 순서대로 클릭합니다
- 끝

## 끝!















