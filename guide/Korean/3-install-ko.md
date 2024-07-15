<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Xiaomi Pad 5 에서 윈도우 구동
> [!WARNING]
> **다른 동영상 가이드는 주로 최신 상태가 아니며 NABU를 벽돌로 만들 가능성이 있기 때문에 보지 마시기 바랍니다!!! 정말 동영상 가이드가 필요하다면, [ArtoSeVeN](https://www.youtube.com/channel/UCYjwfxlYlJ7Nnzv01oszQvA)의 [동영상 가이드](https://youtu.be/BbgTbTGbXYg)를 보세요**

## 설치

### 준비물
- ```뇌```

  [```드라이브 문자 할당 프로그램```](https://github.com/Misha803/My-Scripts/releases/tag/DriveLetterAssigner_NABU)
  
- [```ARM 윈도우 esd```](https://worproject.com/esd) (항목 선택 - Version:  ```11``` Build:  ```22631.2861``` Architecture:  ```ARM64``` Edition:  ```CLIENT``` Language:  ```원하는 언어를 선택하세요```)
    
- [```드라이버```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/Drivers)

### 윈도우 설치 시작을 위해 다시 리커버리로 부팅
> 경로 **path\to**를 리커버리 이미지의 실제 경로로 변경하세요
```cmd
fastboot boot <recovery.img>
```

#### msc를 실행합니다
> 한번 더 실행하라는 문구가 출력되면, 명령어를 한번 더 입력하세요
```cmd
adb shell msc
```

### WINNABU와 ESPNABU에 문자 할당
> **DriveLetterAssigner_NABU** 파일을 열고 키보드의 `Y` 키를 입력하여 문자 **X**와 **Y**를 **WINNABU**와 **ESPNABU**로 자동으로 할당합니다

### 설치
> [!Important]
> CMD/Powershell이 **관리자 권한**으로 실행되고 있는지 확인하세요

> `<path\to\install.esd>`를 실제 install.esd의 경로로 변경하세요 (파일 이름이 install.wim 일 수도 있습니다)

```cmd
dism /apply-image /ImageFile:<path\to\install.esd> /index:6 /ApplyDir:X:\
```

> `오류 87`이 출력되는 경우, `dism /get-imageinfo /ImageFile:<path\to\install.esd>` 명령어로 이미지의 인덱스를 확인하시고, `index:6` 을 이미지에 있는 Windows 11 Pro의 실제 인덱스 수로 변경하세요

### 드라이버 설치
> 드라이버 파일을 압축 해제하고, `OfflineUpdater.cmd` 파일을 실행하세요

> 프로그램이 문자를 입력하라고 하는 경우, **WINNABU** (기본적으로 **X** 입니다) 의 드라이브 문자를 입력하고, enter 키를 입력하세요

#### EFI에 대한 윈도우 부트로더 파일 생성
> 부팅 파일 복사 도중 오류가 발생하는 경우, ESPNABU가 문자 Y로 할당되어 있는지 보기 위해 `diskpart`를 확인하세요. 할당되어있지 않다면, K와 같은 다른 문자를 추가하고 아래 명령어의 Y들을 해당 문자로 각각 변경하세요
```cmd
bcdboot X:\Windows /s Y: /f UEFI
```

#### ESPNABU에 대한 드라이브 문자 제거
> 이 명령어가 작동하지 않더라도, 무시하고 다음에 입력할 명령어로 건너뛰세요. 이 드라이브는 PC를 재부팅하면 자동으로 제거됩니다.
```cmd
mountvol y: /d
```

### 안드로이드로 재부팅
```cmd
adb reboot
```

> 장치의 초기 설정을 마친 다음에, 마지막 단계로 이동하세요

## [마지막 단계: 듀얼부팅 설정](dualboot-ko.md)









