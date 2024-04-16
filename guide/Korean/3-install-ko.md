<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Xiaomi Pad 5 에서 윈도우 구동
> [!WARNING]
> **다른 동영상 가이드는 주로 최신 상태가 아니며 NABU를 벽돌로 만들 가능성이 있기 때문에 보지 마시기 바랍니다!!! 정말 동영상 가이드가 필요하다면, [ArtoSeVeN](https://www.youtube.com/channel/UCYjwfxlYlJ7Nnzv01oszQvA)의 [동영상 가이드](https://youtu.be/BbgTbTGbXYg)를 보십시오**

## 설치
> [!NOTE]
> 지금부터 명령 프롬프트 또는 Windows Powershell 을 관리자 권한으로 열고, `cd C:\path\to\platform-tools` 명령어를 사용하여 플랫폼 도구 폴더에 액세스 하는 것을 권장합니다. 이때 이 경로를 폴더의 실제 경로로 교체하십시오.
> 가이드에서의 모든 명령어는 같은 창에서 입력하시고, 창을 닫지 마십시오.

### 준비물
- ```뇌```
  
- [```ARM 윈도우 esd```](https://worproject.com/esd) (항목 선택 - Version:  ```11``` Build:  ```22631.2861``` Architecture:  ```ARM64``` Edition:  ```CLIENT``` Language:  ```원하는 언어를 선택하십시오```)
    
- [```드라이버```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/Drivers)

### 윈도우 설치 시작을 위해 다시 리커버리로 부팅
```cmd
fastboot boot <recovery.img>
```

#### msc를 실행합니다
> 한번 더 실행하라는 문구가 출력되면, 명령어를 한번 더 입력하십시오
```cmd
adb shell msc
```

#### 윈도우 디스크 관리자를 시작합니다
> 샤오미 패드 5가 디스크로 인식되면 아래의 명령어를 입력하십시오
```cmd
diskpart
```

#### 태블릿의 윈도우 볼륨을 선택합니다
> `list volume` 명령어를 사용하여 볼륨을 찾으십시오. 볼륨의 이름은 "WINNABU" 입니다.
```diskpart
select volume <number>
```

#### 문자 X를 할당합니다
```diskpart
assign letter x
```

#### 태블릿의 ESP 볼륨을 선택합니다
> `list volume` 명령어를 사용하여 볼륨을 찾으십시오. 볼륨의 이름은 "ESPNABU" 입니다.
```diskpart
select volume <number>
```

#### 문자 Y를 할당합니다
```diskpart
assign letter y
```

#### diskpart를 종료합니다
```diskpart
exit
```

### 설치
> `<path\to\install.esd>`를 실제 install.esd의 경로로 변경하십시오 (파일 이름이 install.wim 일 수도 있습니다)

```cmd
dism /apply-image /ImageFile:<path\to\install.esd> /index:6 /ApplyDir:X:\
```

> `오류 87`이 출력된다면, `dism /get-imageinfo /ImageFile:<path\to\install.esd>` 명령어로 이미지의 인덱스를 확인하시고, `index:6` 을 이미지에 있는 Windows 11 Pro의 실제 인덱스 수로 변경하십시오

### 드라이버 설치
> `"Automatic WINNABU detection failed! Enter Drive Letter manually"`이 출력된다면 **`X`** 를 입력하십시오
```cmd
 드라이버 폴더를 열고 OfflineUpdater.cmd를 실행하십시오
```
> If any errors appear under **Installing App Packages**, ignore them and continue

#### EFI에 대한 윈도우 부트로더 파일 생성
> 부팅 파일 복사 도중 오류가 발생한다면, ESPNABU가 문자 Y로 할당되어 있는지 보기 위해 `diskpart`를 확인하십시오. 할당되어있지 않다면, K와 같은 다른 문자를 추가하고 아래 명령어의 Y들을 해당 문자로 각각 변경하십시오
```cmd
bcdboot X:\Windows /s Y: /f UEFI
```

#### ESPNABU에 대한 드라이브 문자 제거
> 이 명령어가 작동하지 않더라도, 무시하고 다음에 입력할 명령어로 건너뛰십시오. 이 드라이브는 PC를 재부팅하면 자동으로 제거됩니다.
```cmd
mountvol y: /d
```

### 안드로이드로 재부팅
```cmd
adb reboot
```

> 장치의 초기 설정을 마친 다음에, 마지막 단계로 이동하십시오

## [마지막 단계: 듀얼부팅 설정](dualboot-ko.md)














