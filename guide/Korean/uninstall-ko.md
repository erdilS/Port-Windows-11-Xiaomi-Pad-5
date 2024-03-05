<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Xiaomi Pad 5 에서 윈도우 구동

## 제거

### 왜 이 과정이 필요합니까?

윈도우 제거를 원할 경우 수동으로 파티션을 제거하지 않고 이 과정이 사용되며 이를 통해 실수 또한 방지합니다.

부트로더 리락을 원할 경우 파티션 테이블을 순정 상태로 돌려놓아야 합니다.

### 준비물

- [```안드로이드 플랫폼 도구```](https://developer.android.com/studio/releases/platform-tools)
  
- [```리커버리 이미지```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

#### 커스텀 리커버리로 부팅합니다
```cmd
fastboot boot <recovery.img>
```

#### 파티션 레이아웃을 복원합니다
> [!Warning]
> 안드로이드 파일이 모두 초기화됩니다. 필요하다면 미리 백업하십시오.
```cmd
adb shell restore
```

### 안드로이드로 재부팅
```cmd
adb reboot 
```
## 끝!
