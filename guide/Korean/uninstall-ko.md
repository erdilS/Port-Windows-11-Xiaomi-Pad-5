<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Xiaomi Pad 5 에서 윈도우 구동

## 제거

### 왜 이 과정이 필요합니까?

윈도우 제거를 원할 경우 수동으로 파티션을 제거하지 않고 이 과정이 사용되며 이를 통해 실수 또한 방지합니다.

부트로더 리락을 원할 경우 파티션 테이블을 순정 상태로 복원해야 합니다.

### 준비물

- [```안드로이드 플랫폼 도구```](https://developer.android.com/studio/releases/platform-tools)
  
- [```리커버리 이미지```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

#### Android로 전환합니다
> 제거 과정을 진행하기 전에 Android로 전환하세요

#### **fastboot**로 재부팅합니다
- 재부팅될 때 **`볼륨 아래`** 버튼을 누른 상태를 유지하여 NABU를 **fastboot**로 재부팅하세요

- 케이블을 사용하여 PC/노트북에 기기를 연결합니다

#### 맞춤화된 리커버리로 부팅합니다
> platform-tools 폴더에서 CMD 창을 열고, 아래의 명령어를 실행합니다 (fastboot 모드에 진입하면 실행하세요)
```cmd
fastboot boot path\to\recovery.img
```

#### 파티션 레이아웃을 복원합니다
> [!Warning]
> 안드로이드 파일이 모두 초기화됩니다. 필요하다면 미리 백업하세요.
```cmd
adb shell restore
```

### 안드로이드로 재부팅
```cmd
adb reboot 
```

> [!NOTE]
> MIUI 리커버리로 부팅된 경우 다음 작업을 수행하세요:
> 1. Wipe Data를 선택합니다
> 2. 모든 데이터를 삭제합니다
> 3. 데이터가 성공적으로 삭제되면, Back To Main Menu를 선택합니다
> 4. Reboot를 선택합니다
> 5. 시스템으로 재부팅합니다

## 끝!
