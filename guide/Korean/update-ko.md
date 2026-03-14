<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Xiaomi Pad 5 에서 윈도우 구동

## 드라이버 업데이트

> [!NOTE]
> 이 안내서는 **드라이버를 2601.19 버전으로 업데이트하기 위한 것이 아닙니다**.  
> 이 버전에 대해 사용할 경우 오류나 시스템 불안정이 발생할 수 있습니다.

### 준비물
- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)

- [맞춤화된 리커버리 이미지](https://github.com/ArKT-7/twrp_device_xiaomi_nabu/releases/tag/mod-win)

- [UEFI 이미지 & 드라이버](https://github.com/remtrik-stuff/MiPad5-Windows-Releases/releases)


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
> This process will take between 3 and 6 hours Do not worry, this is normal.

- 드라이버 압축 파일을 압축 해제하고, `OfflineUpdater.cmd` 파일을 엽니다 (오류가 발생할 경우, `OfflineUpdaterFix.cmd` 를 실행하세요)

> 프로그램이 문자를 입력하라고 하는 경우, **WINNABU** (기본적으로 **X** 입니다) 의 드라이브 문자를 입력하고, enter 키를 입력하세요

#### Reboot your device
> [!Warning]
> Make sure to also change the UEFI image in Android, otherwise you may face a "blue/black screen of death" (BSoD) when booting Windows later.
```cmd
adb reboot
```

## Finished!











