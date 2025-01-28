<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Xiaomi Pad 5 에서 윈도우 구동

## 윈도우 24H2를 안전하게 사용하기 위한 GPT 수정

### 준비물:
- [```잘 설치된 윈도우```](selection-ko.md)

- [```리커버리 이미지```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [```안드로이드 플랫폼 도구```](https://developer.android.com/studio/releases/platform-tools)

> [!Important]
> 윈도우 24H2를 안전하게 사용하려면, EDL 문제를 예방하기 위해 이 과정이 필요합니다.

> [!NOTE]
> 이 과정을 진행해도 기존에 설치된 안드로이드 및 윈도우에 영향을 주지 않습니다.

### fastboot 모드로 재부팅
- USB 케이블이 연결된 상태로 재부팅될 때 **`볼륨 아래`** 버튼을 누른 상태를 유지하여 NABU를 **fastboot 모드**로 부팅하세요
- 또는, USB 디버깅이 활성화되어 있다면, 안드로이드에 부팅되어 있는 동안 아래의 명령어를 사용해도 됩니다.
```cmd
adb reboot bootloader
```

### 맞춤화된 리커버리로 부팅
> `path\to\recovery.img` 를 다운로드된 **recovery.img** 의 실제 경로로 변경하세요
```cmd
fastboot boot path\to\recovery.img
```

### GPT 수정
> 리커버리 이미지로 부팅되면 아래의 명령어를 입력하세요
>
> 한번 더 실행하라는 문구가 출력되면, 명령어를 한번 더 입력하세요
```cmd
adb shell fixgpt
```

### 장치 재부팅
```cmd
adb reboot
```

## ✅ 끝났습니다! 이제 윈도우 24H2를 안전하게 사용할 수 있습니다.























