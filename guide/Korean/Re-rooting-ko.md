<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Xiaomi Pad 5 에서 윈도우 구동

## 안드로이드 재루팅
이 부분은 MIUI가 업데이트되어 루트가 제거된 경우를 위한 재루팅 과정을 가이드합니다.

### 준비
- [```리커버리 이미지```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)
  
- [```안드로이드 플랫폼 도구```](https://developer.android.com/studio/releases/platform-tools)

### fastboot로 재부팅
- 재부팅될 때 **`볼륨 아래`** 버튼을 누른 상태를 유지하여 NABU를 **fastboot**로 재부팅하세요

- 케이블을 사용하여 PC/노트북에 기기를 연결합니다

### PC에서 명령어로 리커버리 시작
```cmd
fastboot boot <recovery.img>
```

### 기존 boot 이미지 백업
```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/normal_boot.img" && adb pull /tmp/normal_boot.img
```

### 안드로이드로 재부팅
```cmd
adb reboot
```

### boot 패치
- ```normal_boot.img``` 파일을 ```플랫폼 도구``` 폴더에서 태블릿으로 복사합니다
- Magisk 앱을 열고 ```Install``` 버튼을 클릭합니다. ```Select and Patch a File``` 옵션을 선택하고 태블릿에 복사한 ```normal_boot.img``` 파일을 찾습니다. ```Let's Go``` 버튼을 클릭하고 패치 과정이 끝날 때까지 기다립니다.
- ```magisk_patched....img``` 파일을 태블릿의 ```Downloads``` 폴더에서 컴퓨터의 ```플랫폼 도구``` 폴더로 복사합니다. 
- fastboot로 재부팅합니다
- 플랫폼 도구 폴더에서 명령 프롬프트를 엽니다 

### 패치된 boot 플래시
 > `<magisk_patched.img>`를 실제 ```magisk_patched.img```의 이름/경로로 교체하세요.
```cmd
fastboot flash boot <magisk_patched.img>
```

### Windows의 C:\에 boot.img 업데이트
- 안드로이드로 재부팅합니다
- ```WOA Helper```를 엽니다
- ```Windows```를 마운트합니다
- 파일 탐색기를 열고 내부 저장소의 ```Windows``` 폴더로 이동합니다
- ```boot.img```를 삭제합니다

> [!NOTE]
> **업데이트된 boot.img는 재부팅 후 C:\에 자동으로 생성됩니다**

## 끝!















