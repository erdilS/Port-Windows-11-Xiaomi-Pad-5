<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Xiaomi Pad 5 에서 윈도우 구동

## 듀얼부팅 가이드

### 준비물
- [```Magisk```](https://github.com/topjohnwu/Magisk/releases/latest)
  
- [```UEFI 이미지```](https://github.com/remtrik-stuff/MiPad5-Windows-Releases/releases/download/2601.19/MiPad5.UEFI-v2601-19.img)
  
- [```WoA Helper 앱```](https://github.com/n00b69/woa-helper/releases/tag/APK)

## 듀얼부팅 가이드
> 이 가이드는 태블릿이 루팅되어있다고 가정하므로 루팅하지 않았다면 [해당 가이드](2-rootguide-ko.md)를 먼저 보시기 바랍니다.

### 부트 이미지 백업
> [!NOTE]
> Only do this step if you just changed your Android ROM and are setting up dualboot again. If you just installed Windows and are setting up dualboot for the first time, you can skip this step.

> 듀얼 부팅을 설정하기 전에 현재 부트 이미지를 백업해야 합니다.

- **WOA Helper**를 실행합니다.
- **Back up boot image** 메뉴로 이동합니다.
- 대상(target)으로 **Windows**를 선택합니다.

> 이렇게 하면 Android 부트 이미지의 백업이 생성되어 장치가 Android와 Windows 사이에서 듀얼 부팅을 올바르게 전환할 수 있습니다.

### 설정 - 안드로이드
- **WOA Helper** 앱을 다운로드 및 설치하시고, 앱을 열고 루트 권한을 허용하세요.
- **UEFI 이미지** 를 다운로드하고 내부 저장소의 `UEFI` 폴더로 파일을 이동하세요.
- **WINDOWS로 즉시 부팅** 버튼을 선택하세요.

### 설정 - 윈도우
> [!Tip]
> Windows를 처음 부팅하고 Microsoft 계정 로그인을 건너뛰려는 경우, 네트워크 페이지 에서 **인터넷에 연결되어 있지 않음** 버튼을 선택하고, 다음 페이지가 표시되면, **제한된 설치로 계속** 버튼을 선택하세요.

#### 안드로이드로 부팅합니다
- 바탕화면에 새로 생성된 바로 가기를 실행하세요 (빠른 실행을 위해 시작 메뉴 / 작업표시줄에 고정할 수도 있습니다)

#### 윈도우로 부팅합니다
- 앱 내에서 `WINDOWS로 즉시 부팅`을 선택하거나, 퀵패널에 새로 생성된 토글 버튼을 선택하세요
  
## 끝!


















