<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Xiaomi Pad 5 에서 윈도우 구동

## 루팅 
> [!NOTE]
> **이미 루팅했다면 이 단계를 건너뛰고 다음 페이지로 이동하세요**

### 준비물
- ```뇌```

- [```Magisk.apk```](https://github.com/topjohnwu/Magisk/releases/latest)

### magisk 설치 
- [`magisk.apk`](https://github.com/topjohnwu/Magisk/releases/latest) PC/노트북에서 다운로드합니다 
> `path\to\magisk.apk`를 magisk.apk의 실제 경로로 변경하세요
```cmd
adb push path\to\magisk.apk /tmp/magisk.zip && adb shell twrp install /tmp/magisk.zip
```

#### Android로 재부팅합니다
> 부팅되지 않는다면, 순정 리커버리로 재부팅하여 공장 초기화를 진행해보세요
```cmd
adb reboot
```

### 설정 마무리
- 장치의 초기 설정을 마치고 [Magisk](https://github.com/topjohnwu/Magisk/releases/latest)를 다운로드하고 설치합니다. (설치되어 있지 않은 경우)
- **Magisk** 앱을 열고 화면에 표시되는 지시를 따르면 장치가 몇 초후 재부팅됩니다.

### 루팅된 boot.img 백업
> 맞춤화된 리커버리 이미지로 재부팅한 후 아래의 명령어를 실행하세요
```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/rooted_boot.img" && adb pull /tmp/rooted_boot.img
```

### [다음 단계: 윈도우 설치](/guide/Korean/3-install-ko.md)






























