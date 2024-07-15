<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Xiaomi Pad 5 에서 윈도우 구동

## 설치

### 준비물
- ```언락 상태의 부트 로더``` - (부트로더가 락 상태이며 언락 방법을 모를 경우 [이 가이드](unlock-bootloader.md)를 이용하세요)

-  `뇌`
  
- [```리커버리 이미지```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [```안드로이드 플랫폼 도구```](https://developer.android.com/studio/releases/platform-tools)

### 메모:
>[!NOTE]
> 듀얼 부팅을 위해 어느 Android든 사용할 수 있습니다 (MIUI/Hyper OS 또는 커스텀 롬)

> [!Warning]
> 모든 데이터가 초기화됩니다! 필요하다면 지금 백업하세요.
> 
> 실수한 것 같다면 태블릿을 재부팅하지 마시고, [텔레그램 채팅](https://t.me/nabuwoa)으로 도움을 요청하세요
>
> **유튜브 또는 다른 플랫폼에 있는 최신 상태가 아닌 동영상 가이드를 보지 마시기 바랍니다! 이러한 동영상들은 최신 상태가 아니므로 따라 하다가 장치를 벽돌로 만들 수 있습니다! 정말 동영상 가이드가 필요하다면, [ArtoSeVeN](https://www.youtube.com/channel/UCYjwfxlYlJ7Nnzv01oszQvA)의 [동영상 가이드](https://youtu.be/BbgTbTGbXYg)를 보세요**

### 리파티션 및 boot 이미지 백업
> [!NOTE]
> 어디서부터 시작해야 할지 잘 모르십니까? 다운로드된 [```안드로이드 플랫폼 도구```](https://developer.android.com/studio/releases/platform-tools) 폴더를 원하는 경로에 압축해제 하세요. 경로의 예시는 다음과 같습니다. ```"C:\platform-tools"``` 그런 다음 ```명령 프롬프트``` 또는 `powershell`을 관리자 권한으로 여세요. 경로  `"path\to\platform-tools"`를 플랫폼 도구 폴더의 실제 경로로 변경하세요
```cmd
cd "path\to\platform-tools"
```
> 전체 가이드를 이용하는 동안 이 창을 계속 유지하세요. 창을 닫지 마세요.

#### **fastboot**로 재부팅합니다
- 재부팅될 때 **`볼륨 아래`** 버튼을 누른 상태를 유지하여 NABU를 **fastboot**로 재부팅하세요

- 케이블을 사용하여 PC/노트북에 기기를 연결합니다

#### 맞춤화된 리커버리로 부팅합니다
> 경로 **path\to\recovery.img**를 리커버리 이미지의 실제 경로로 변경하세요
```cmd
fastboot boot path\to\recovery.img
```

### 리파티션 진행
> **$** 를 Windows에 할당할 저장용량으로 변경하세요 (명령어의 끝 부분에 GB를 추가하지 마시고, 숫자만을 입력하세요)
>
> 한번 더 실행하라는 문구가 출력되면, 명령어를 한번 더 입력하세요
```sh
adb shell partition $
```

### 기존 boot 이미지 백업
```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/normal_boot.img" && adb pull /tmp/normal_boot.img
```

#### 안드로이드가 작동되는지 다시 확인합니다
> 안드로이드가 작동하는지 확인하기 위해 재부팅하세요. 부팅되지 않는다면, 리커버리에서 초기화를 진행하고 다시 시도하세요.

```cmd
adb reboot
```


### [다음 단계: 루팅](/guide/Korean/2-rootguide-ko.md)
