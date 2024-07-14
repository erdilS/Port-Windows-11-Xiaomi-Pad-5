<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Xiaomi Pad 5 에서 윈도우 구동

## 루팅 
> [!NOTE]
> **이미 루팅했다면 이 단계를 건너뛰고 다음 페이지로 이동하세요**

### 준비물
- ```뇌```
  
- [```안드로이드 boot 이미지 백업```](/guide/Korean/1-partition-ko.md#기존-boot-이미지-백업) (가이드의 첫 페이지에서 백업한 파일)

### boot 이미지 패치 
- ```normal_boot.img``` 파일을  ```플랫폼 도구``` 폴더에서 태블릿으로 복사하세요

- 태블릿에서 [Magisk 앱](https://github.com/topjohnwu/Magisk/releases/latest)을 다운로드하고 설치하세요
  
-  Magisk 앱을 열고 ```Install``` 버튼을 클릭하세요. ```Select and Patch a File``` 옵션을 선택하고 태블릿에 복사한 ```normal_boot.img``` 파일을 선택하세요. ```Let's Go``` 버튼을 클릭하고 패치 과정이 완료될 때까지 기다리세요.
  
- 태블릿의 ```Downloads``` 폴더에서 ```magisk_patched....img``` 파일을 컴퓨터의 ```플랫폼 도구``` 폴더로 복사하세요. 

### fastboot로 재부팅
- 재부팅될 때 **`볼륨 아래`** 버튼을 누른 상태를 유지하여 NABU를 **fastboot**로 재부팅하세요

- 케이블을 사용하여 PC/노트북에 기기를 연결합니다

- 이전에 열었던 명령 프롬프트 창으로 돌아갑니다

### 패치된 boot 이미지 플래시 
> `<magisk_patched.img>`를 ```magisk_patched.img``` 의 실제 이름/경로로 교체하세요.
```cmd
fastboot flash boot <magisk_patched.img>
```

### [다음 단계: 윈도우 설치](/guide/Korean/3-install-ko.md)












