<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Xiaomi Pad 5 에서 윈도우 구동

## 드라이버 업데이트

### 준비물
- [```리커버리 이미지```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [```UEFI 이미지```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v3.img)

- [```드라이버```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/Drivers)

### 아래의 명령어를 PC로 입력하여 리커버리 부팅
```cmd
fastboot boot <recovery.img>
```

#### mass storage mode 활성화
> 한번 더 실행하라는 문구가 출력되면, 명령어를 한번 더 입력하십시오
```cmd
adb shell msc
```

### 윈도우 디스크 관리자를 시작합니다
> 샤오미 패드 5가 디스크로 인식되면 아래의 명령어를 입력하십시오
```cmd
diskpart
```

#### 태블릿의 윈도우 볼륨을 선택합니다
> `list volume` 명령어를 사용하여 볼륨을 찾으십시오. 볼륨의 이름은 **WINNABU** 입니다.
```diskpart
select volume <number>
```

#### 문자 X를 할당합니다
```diskpart
assign letter x
```

#### diskpart를 종료합니다
```diskpart
exit
```

### 드라이버 설치
> `"Automatic WINNABU detection failed! Enter Drive Letter manually"`이 출력된다면 **`X`** 를 입력하십시오
```cmd
 드라이버 폴더를 열고 OfflineUpdater.cmd를 실행하십시오
```

### fastboot로 재부팅하여 UEFI 플래시
> 또는 WOA Helper 앱을 사용할 수도 있습니다. 이 경우, ```adb reboot``` 명령어를 통하여 재부팅할 수 있습니다.
>
> 최신 버전의 UEFI를 사용하고 있는지 확인하십시오. UEFI를 업데이트하지 않고 드라이버를 업데이트하면 Windows가 부팅되지 않을 수도 있습니다
```cmd
adb reboot bootloader
```

#### 윈도우로 부팅가능한 UEFI 이미지로 부팅합니다
> <uefi.img>를 실제 UEFI 이미지의 경로로 변경하십시오
```cmd
fastboot flash boot <uefi.img>
```

## 끝!
