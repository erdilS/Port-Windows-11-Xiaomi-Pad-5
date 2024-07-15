<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Xiaomi Pad 5 에서 윈도우 구동

## 안드로이드 및 윈도우 듀얼부팅

### 준비물
- ```뇌```
- ```루팅된 태블릿```
- ```윈도우가 설치된 태블릿```
- [```UEFI 이미지```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v3.img)
- [```WoA Helper 앱```](https://github.com/Marius586/WoA-Helper-update/releases/tag/WOA)

## 듀얼부팅 앱 설정
> 이 가이드는 태블릿이 루팅되어있다고 가정하므로 루팅하지 않았다면 [루팅 가이드](2-rootguide-ko.md)를 먼저 보시기 바랍니다.

### 설정 - 안드로이드
- **WOA Helper** 앱을 다운로드 및 설치하시고, 앱을 열고 루트 권한을 허용하세요.
- **UEFI 이미지** 를 다운로드하고 내부 저장소의 `UEFI` 폴더로 파일을 이동하세요.
- Open the WOA Helper app and use the **STA CREATOR** in **WOA TOOLBOX**.
> [!Important]
> If `/sdcard/Windows` is empty, your rom does not support mounting and you will have to make a boot.img backup inside the app, then copy it manually to Windows once you boot to it (for example by uploading it somewhere and then downloading it while booted into Windows). The same applies to the StA files, which are also generated in your internal storage.
>
> Do the same thing if the folder is read-only.
- Press the **QUICKBOOT TO WINDOWS** button.

### 설정 - 윈도우
> [!Tip]
> If this is your first time booting Windows and you wish to skip the Microsoft Account login, press the **I don't have internet** button in the WiFi page, then when prompted, press the **Continue with limited setup** button.
- Navigate to `C:\sta` and create a shortcut of **sta.exe** to your desktop, if one isn't already present

#### 안드로이드로 부팅합니다
- 바탕화면에 새로 생성된 바로 가기를 실행하세요 (빠른 실행을 위해 시작 메뉴 / 작업표시줄에 고정할 수도 있습니다)

#### 윈도우로 부팅합니다
- 앱 내에서 `WINDOWS로 즉시 부팅`을 선택하거나, 퀵패널에 새로 생성된 토글 버튼을 선택하세요
  
## 끝!

> [!TIP]
> Don't forget to check out [**```Useful apps and instructions```**](Additional-materials-en.md) page. You'll find a guide on how to activate your Windows, as well as other helpful information.










