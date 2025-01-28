<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Xiaomi Pad 5 에서 윈도우 구동

## 설치

### 준비물
- ```잠금 해제된 부트 로더``` - (부트로더가 락 상태이며 언락 방법을 모를 경우 [이 가이드](unlock-bootloader-ko.md)를 이용하세요)

-  `뇌`

- ```Windows 10(또는 상위 버전)이 탑재된 PC/노트북```

- [```안드로이드 플랫폼 도구```](https://developer.android.com/studio/releases/platform-tools)
  
- [```맞춤화된 리커버리 이미지```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

### 메모:
>[!NOTE]
> 듀얼 부팅을 위해 어떤 안드로이드든 사용할 수 있습니다 - MIUI/Hyper OS 또는 커스텀 롬

> [!Warning]
> 모든 데이터가 초기화됩니다! 필요하면 지금 백업하세요.
> 
> 실수한 것 같다면 태블릿을 재부팅하지 마시고, [텔레그램 채팅](https://t.me/nabuwoa)으로 도움을 요청하세요

### 명령 프롬프트를 관리자 권한으로 열기
> [!NOTE]
> 어디서부터 시작해야 할지 잘 모르십니까? 다운로드된 [```안드로이드 플랫폼 도구```](https://developer.android.com/studio/releases/platform-tools) 폴더를 원하는 경로에 압축해제 하세요. 경로의 예시는 다음과 같습니다. ```"C:\platform-tools"``` 그런 다음 ```명령 프롬프트``` 또는 `powershell`을 관리자 권한으로 여세요. 경로  `"path\to\platform-tools"`를 플랫폼 도구 폴더의 실제 경로로 변경하세요
```cmd
cd "path\to\platform-tools"
```
> 전체 가이드를 이용하는 동안 이 창을 계속 유지하세요. 창을 닫지 마세요.

> [!Note]
> 장치가 fastboot 또는 리커버리 모드에서 인식되지 않을 경우, [이 가이드](troubleshooting-ko.md#fastboot-또는-리커버리에서-장치가-인식되지-않음)를 이용하여 USB 드라이버를 설치해야 합니다

#### **fastboot**로 재부팅합니다
- USB 케이블이 연결된 상태로 재부팅될 때 **`볼륨 아래`** 버튼을 누른 상태를 유지하여 NABU를 **fastboot 모드**로 부팅하세요
- 또는, 안드로이드에 부팅되어 있는 동안 아래의 명령어를 사용해도 됩니다
```cmd
adb reboot bootloader
```

#### 맞춤화된 리커버리로 부팅합니다
> fastboot 모드에서, `path\to\recovery.img`를 리커버리 이미지의 실제 경로로 변경하세요
```cmd
fastboot boot path\to\recovery.img
```

### 기존 boot 이미지 백업
```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/normal_boot.img" && adb pull /tmp/normal_boot.img
```

### 장치 파티션 수정
> 장치의 파티션을 수정하기 위한 두 가지 방법이 있습니다. 아래에서 원하는 방법을 선택하세요.
 
> [!NOTE]
>
> ▶️ 클릭하여 메뉴를 확장하세요.

### 방법 1: 자동 파티셔닝 (권장됨)

<details>
  <summary><strong>클릭하면 방법 1을 볼 수 있어요</strong></summary> 

### 파티셔닝 스크립트 실행
> **$** 를 Windows에 할당할 저장용량으로 변경하세요 (명령어의 끝 부분에 GB를 추가하지 마시고, 숫자만을 입력하세요)
>
> 한번 더 실행하라는 문구가 출력되면, 명령어를 한번 더 입력하세요
```cmd
adb shell partition $
```

### [다음 단계: 루팅](/guide/Korean/2-rootguide-ko.md)

</details>

----

### 방법 2: 수동 파티셔닝 (잘 알고 있는 경우에만 이용하세요)

<details>
  <summary><strong>클릭하면 방법 2를 볼 수 있어요</strong></summary> 

#### data를 마운트 해제합니다
> 오류 문구가 출력되어도 무시하고 계속 진행하세요
```cmd
adb shell umount /dev/block/by-name/userdata
``` 

#### 파티션 테이블 크기를 수정합니다
```cmd
adb shell sgdisk --resize-table 64 /dev/block/sda
```

### 파티셔닝 준비
```cmd
adb shell parted /dev/block/sda
``` 

#### 현재 파티션 테이블을 출력합니다
> Parted가 파티션 목록을 출력하면 **userdata** 항목이 목록의 마지막 파티션일 것입니다
```cmd
print
``` 

#### userdata를 제거합니다
> **$** 를 **userdata** 파티션의 숫자로 변경하세요 (**31** 일 것입니다)
```cmd
rm $
``` 

#### userdata를 다시 생성합니다
> **10.9GB** 를 이전에 삭제했던 **userdata** 의 시작 값으로 변경하세요
>
> **70GB** 를 **userdata** 에 할당할 끝 값으로 변경하세요. 아래의 예시 명령어에서 안드로이드의 사용 가능한 공간은 70GB-10.9GB = **59GB** 입니다
```cmd
mkpart userdata ext4 10.9GB 70GB
``` 

#### ESP 파티션을 생성합니다
> **70GB** 를 **userdata** 의 끝 값으로 변경하세요
>
> **70.3GB** 를 이전에 사용했던 값에 **0.3GB** 를 추가한 값으로 변경하세요
```cmd
mkpart esp fat32 70GB 70.3GB
``` 

#### Windows 파티션을 생성합니다
> **70.3GB** 를 **esp** 의 끝 값으로 변경하세요
```cmd
mkpart win ntfs 70.3GB -0MB
``` 

#### ESP를 부팅 가능하게 설정합니다
> `print` 를 입력하여 모든 파티션을 볼 수 있습니다. "$"를 ESP 파티션 숫자로 변경하세요 (**32** 일 것입니다)
```cmd
set $ esp on
``` 

#### parted을 종료합니다
```cmd
quit
``` 

### Windows 및 ESP 파티션 포맷
> `print` 명령어가 출력된 곳으로 스크롤하여 **win** 파티션의 숫자가 **33** 인지 확인하세요
```cmd
adb shell mkfs.ntfs -f /dev/block/sda33 -L WINNABU
``` 

> `print` 명령어가 출력된 곳으로 스크롤하여 **esp** 파티션의 숫자가 **32** 인지 확인하세요
```cmd
adb shell mkfs.fat -F32 -s1 /dev/block/sda32 -n ESPNABU
```

### GPT 수정
> 이 과정을 진행하지 않으면 Windows가 장치를 벽돌로 만들 수도 있습니다
```cmd
adb shell fixgpt
```

#### 장치를 재부팅합니다
> 안드로이드가 잘 부팅되는지 확인해보세요
>
> 부팅되지 않는다면, 순정 리커버리로 재부팅하여 공장 초기화를 진행해보세요
```cmd
adb reboot
```

### [다음 단계: 루팅](/guide/Korean/2-rootguide-ko.md)

----

</details>





























