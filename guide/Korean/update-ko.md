<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Xiaomi Pad 5 에서 윈도우 구동

## 드라이버 업데이트

### 준비물
- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)

- [맞춤화된 리커버리 이미지](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [UEFI 이미지](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/UEFI)

- [드라이버](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/Drivers)

### 맞춤화된 리커버리로 부팅합
> `path\to\recovery.img`를 리커버리 이미지의 실제 경로로 변경하세요
```cmd
fastboot boot path\to\recovery.img
```

#### msc 스크립트 실행
> 한번 더 실행하라는 문구가 출력되면, 명령어를 한번 더 입력하세요
```cmd
adb shell msc
```

### Diskpart
```cmd
diskpart
```

#### 태블릿의 윈도우 볼륨을 선택합니다
> `list volume` 을 이용하여 볼륨을 찾고, "$"을 **WINNABU** 의 실제 숫자로 변경하세요
```diskpart
select volume $
```

#### 문자 X 를 할당합니다
```diskpart
assign letter x
```

#### diskpart를 종료합니다
```diskpart
exit
```

### 드라이버 설치
> [!Note]
> 이 과정은 20분 정도 걸립니다. 걱정하지 마세요. 일반적인 시간입니다.

- 드라이버 압축 파일을 압축 해제하고, `OfflineUpdater.cmd` 파일을 엽니다 (오류가 발생할 경우, `OfflineUpdaterFix.cmd` 를 실행하세요)

> 프로그램이 문자를 입력하라고 하는 경우, **WINNABU** (기본적으로 **X** 입니다) 의 드라이브 문자를 입력하고, enter 키를 입력하세요

#### 기기를 재부팅합니다
> 안드로이드에서도 UEFI 이미지를 변경했는지 확인하세요. 그렇지 않으면 이후 윈도우로 부팅할 때 "블루 스크린" (BSoD) 이 표시될 수 있습니다.
```cmd
adb reboot
```

## 끝!












