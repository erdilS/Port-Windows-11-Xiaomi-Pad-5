<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Xiaomi Pad 5 에서 윈도우 구동

## 안드로이드 및 윈도우 듀얼부팅

### 준비물
- ```뇌```
- ```루팅된 태블릿```
- ```윈도우가 설치된 태블릿```
- [```UEFI 이미지```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v3.img)
- [```WoA Helper 앱```](https://github.com/Marius586/WoA-Helper-update/releases/tag/WOA)
- [```StA Installer```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/StA_Installer_nabu.exe)

## 듀얼부팅 앱 설정
> 이 가이드는 태블릿이 루팅되어있다고 가정하므로 루팅하지 않았다면 [루팅 가이드](2-rootguide-ko.md)를 먼저 보시기 바랍니다.

### 설정 - 안드로이드
> [!NOTE]
> 윈도우 폴더로 파일을 이동할 수 없다면, 윈도우에서 다시 시작이 아닌 종료를 선택해서 그런 것입니다. 이 문제를 해결하기 위해, 다시 윈도우로 부팅해서 다시 시작을 선택하시고, 다시 시작되면 fastboot로 부팅하여 안드로이드로 돌아십시오.

- WoA Helper 앱을 다운로드 및 설치하시고, 앱을 열고 루트 권한을 허용하십시오.
- **UEFI 이미지** 를 다운로드하고 내부 저장소의 `UEFI` 폴더로 파일을 이동하십시오. 해당 폴더가 존재하지 않는다면, 새로 만드십시오.
- `MOUNT WINDOWS` 버튼을 선택하시고, **StA_Installer_nabu.exe** 을 다운로드 하여 내부 저장소의 새로 생성된 `Windows` 폴더로 이동하십시오.
- WOA Helper 앱으로 돌아와 `QUICKBOOT TO WINDOWS` 를 선택하십시오.

### 설정 - 윈도우
- `C:\StA_Installer_nabu.exe` 로 이동하고 실행하십시오. 실행되지 않는다면, 바이러스 백신 소프트웨어가 앱을 실행하지 못하게 할 수도 있으므로 백신이 꺼져있는지 확인하십시오.

#### 안드로이드로 부팅합니다
- 바탕화면에 새로 생성된 바로 가기를 실행하십시오 (빠른 실행을 위해 시작 메뉴 / 작업표시줄에 고정할 수도 있습니다)

#### 윈도우로 부팅합니다
- 앱 내에서 `QUICKBOOT TO WINDOWS` 를 선택하거나, 퀵패널에 새로 생성된 토글 버튼을 선택하십시오
  
## 끝!






