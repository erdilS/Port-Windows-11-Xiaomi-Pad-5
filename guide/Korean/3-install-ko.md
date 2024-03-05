<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Xiaomi Pad 5 에서 윈도우 구동
> [!WARNING]
> **다른 동영상 가이드는 주로 최신 상태가 아니며 NABU를 벽돌로 만들 가능성이 있기 때문에 보지 마시기 바랍니다!!! 정말 동영상 가이드가 필요하다면, [ArtoSeVeN](https://www.youtube.com/channel/UCYjwfxlYlJ7Nnzv01oszQvA) 의 [동영상 가이드](https://youtu.be/BbgTbTGbXYg) 를 보십시오**

## 설치
> [!NOTE]
> 지금부터 CMD 또는 powershell 을 관리자 권한으로 열고, `cd C:\path\to\platform-tools` 명령어를 사용하여 플랫폼 도구 폴더에 액세스 하는 것을 권장합니다. 이때 이 경로를 폴더의 실제 경로로 교체하십시오.
> Use the same window in the entire guide, do not close it.

### 준비물
- ```뇌```

- [```UEFI 이미지```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v3.img)
  
- [```ARM 윈도우 esd```](https://worproject.com/esd) (항목 선택 - Version:  ```11``` Build:  ```22631.2861``` Architecture:  ```ARM64``` Edition:  ```CLIENT``` Language:  ```원하는 언어를 선택하십시오```)
    
- [```드라이버```](https://github.com/map220v/MiPad5-Drivers/releases/latest)

### 윈도우 설치 시작을 위해 다시 리커버리로 부팅

```cmd
fastboot boot <recovery.img>
```

#### msc를 실행합니다

> 한번 더 실행하라는 문구가 출력되면, 명령어를 한번 더 입력하십시오

```cmd
adb shell msc
```
### 디스크에 문자 할당
  

#### 윈도우 디스크 관리자를 시작합니다

> 샤오미 패드 5 가 디스크로 인식되면 아래의 명령어를 입력하십시오

```cmd
diskpart
```


#### `X` 를 윈도우 볼륨에 할당합니다

#### 태블릿의 윈도우 볼륨을 선택합니다
> `list volume` 를 사용하여 볼륨을 찾으십시오. 볼륨의 이름은 "WINNABU" 입니다.

```diskpart
select volume <number>
```

#### 문자 X를 할당합니다
```diskpart
assign letter x
```

### ESP 볼륨에 `Y` 할당

#### 태블릿의 esp 볼륨을 선택합니다
> `list volume` 를 사용하여 볼륨을 찾으십시오. 볼륨의 이름은 "ESPNABU" 입니다.

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

> [이곳](https://github.com/map220v/MiPad5-Drivers/releases/latest)에서 드라이버를 다운로드할 수 있습니다

> `"Automatic WINNABU detection failed! Enter Drive Letter manually"`이 출력된다면 **`X`**를 입력하십시오

```cmd
 드라이버 폴더를 열고 OfflineUpdater.cmd를 실행하십시오
```

### EFI에 대한 윈도우 부트로더 파일 생성
> 부팅 파일 복사 도중 오류가 발생한다면, ESPNABU가 문자 Y로 할당되어 있는지 보기 위해 `diskpart` 를 확인하십시오. 할당되어있지 않다면, K와 같은 다른 문자를 추가하고 아래 명령어의 Y들을 해당 문자로 각각 변경하십시오
```cmd
bcdboot X:\Windows /s Y: /f UEFI
```

## ESPNABU에 대한 드라이브 문자 제거
> 이 명령어가 작동하지 않더라도, 무시하고 다음에 입력할 명령어로 건너뛰십시오. 이 드라이브는 PC를 재부팅하면 자동으로 제거됩니다.
```cmd
mountvol y: /d
```


## 윈도우로 부팅

### 루팅 boot 이미지 백업

```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/rooted_boot.img" && adb pull /tmp/rooted_boot.img
```

### 부트로더로 재부팅

```cmd
adb reboot bootloader
```

### UEFI 이미지 다운로드 및 플래시
> [UEFI 이미지](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v3.img)를 다운로드하십시오

```cmd
fastboot flash boot <path to image>
```

## 윈도우로 재부팅
```cmd
fastboot reboot
```

> [!NOTE]
> 윈도우로 처음 부팅되면, Wi-Fi 네트워크 목록이 나타나지 않습니다. 다시 시작될 때까지 전원 버튼을 눌러 태블릿을 다시 시작하십시오. 재부팅 후, 문제가 해결됩니다. "연결할 수 없음" 팝업이 출력되면, 될 때까지 다시 시도를 선택하십시오 (일반적으로 5번 정도 선택하면 됩니다)

### 안드로이드로 재부팅
윈도우가 설정을 마친 후, 윈도우 에서 다시 시작 버튼을 선택하십시고 (종료 버튼이 아닙니다), 다시 시작되면, fastboot로 재부팅하기 위해 `볼륨 아래` + `전원`을 누르고 있으십시오
> 안드로이드로 돌아오기 위하여 백업 boot 이미지를 사용하여 fastboot에서 플래시 하십시오

```cmd
fastboot flash boot rooted_boot.img
```

```cmd
fastboot reboot
```

### [마지막 단계: 듀얼부팅 설정](dualboot-ko.md)
