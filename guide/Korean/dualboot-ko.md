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
- WOA Helper 앱을 열고 **WOA 도구**에서 **STA 생성**을 선택하세요.
> [!Important]
> `/sdcard/Windows`가 비어있는 경우, 기기의 롬이 마운트를 지원하지 않으며 앱에서 boot.img 백업을 생성해야 합니다. 그런 다음 Windows로 부팅할 때 백업된 boot.img를 수동으로 Windows에 복사해야 합니다. (예시: 클라우드에 업로드한 다음 Windows로 부팅한 후 다운로드합니다.) StA 파일도 같은 방식으로 진행합니다. (해당 파일 또한 내부 저장소에 생성되어 있습니다.)
>
> 폴더가 읽기 전용인 경우 같은 방식으로 진행하세요.
- **WINDOWS로 즉시 부팅** 버튼을 선택하세요.

### 설정 - 윈도우
> [!Tip]
> Windows를 처음 부팅하고 Microsoft 계정 로그인을 건너뛰려는 경우, 네트워크 페이지 에서 **인터넷에 연결되어 있지 않음** 버튼을 선택하고, 다음 페이지가 표시되면, **제한된 설치로 계속** 버튼을 선택하세요.
- sta 바로가기가 없는 경우, `C:\sta`로 이동하여 **sta.exe**의 바로가기를 바탕화면에 만드세요.

#### 안드로이드로 부팅합니다
- 바탕화면에 새로 생성된 바로 가기를 실행하세요 (빠른 실행을 위해 시작 메뉴 / 작업표시줄에 고정할 수도 있습니다)

#### 윈도우로 부팅합니다
- 앱 내에서 `WINDOWS로 즉시 부팅`을 선택하거나, 퀵패널에 새로 생성된 토글 버튼을 선택하세요
  
## 끝!

> [!TIP]
> [**```유용한 앱 및 설명```**](Additional-materials-ko.md) 페이지를 확인해보세요. Windows 정품 인증 방법에 대한 가이드와 기타 유용한 정보를 확인할 수 있습니다.










