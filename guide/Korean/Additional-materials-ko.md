<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# 윈도우가 설치된 Xiaomi pad 5를 위한 유용한 앱과 설명

### 지원되는 앱/게임 목록
이것은 결코 포괄적인 목록이 아니며 단순히 커뮤니티에서 테스트한 앱/게임을 나열한 것입니다
[이 링크를 참고하세요](https://docs.google.com/spreadsheets/d/1XYuoySgYQE0HL573sA-0RGMX7I4lt5rWJuQ8Z8yRJNY/edit?usp=drivesdk)

[이 링크에서](https://armrepo.ver.lt/) 전용 ARM 소프트웨어 목록을 확인할 수 있습니다

#### 끝!

## D 드라이브 숨기기 (modem 파티션)
> [!NOTE]
> 몇몇 애플리케이션들이 이 드라이브에 쓰기 작업을 할 수 있는데, 이 드라이브가 수정되면 안 되기 때문에 이 부분은 권장됩니다

- [`ModemHide.vbs`](https://github.com/Misha803/My-Scripts/releases/tag/ModemHide)를 NABU에 다운로드 합니다
- 파일을 실행합니다
- 사용자 계정 컨트롤 창에서 권한을 허용합니다 
- 창이 나타나면 `Yes`를 선택합니다


#### 끝! 


## USB 호스트 모드 비활성화
> [!Warning]
> 전원이 공급되지 않는 USB 장치는 작동하지 않습니다

> [!Important]
> 이 과정은 컴퓨터가 아니라 Mi Pad 5의 Windows에서 진행해야 합니다.

[USB Host Mode Control](https://github.com/Misha803/My-Scripts/releases/tag/USB-Host-Mode-Control)을 실행하여 USB 호스트 모드를 활성화/비활성화하세요. USB 호스트 모드를 비활성화/활성화할지 확인하세요 

#### 끝!

## Windows 업데이트나 ISO 이미지를 사용하여 Windows를 업데이트할 수 있나요?
- ✅ **그렇습니다!** Windows 업데이트에서 모든 업데이트를 설치할 수 있으며 ISO 이미지를 사용하여 진행할 수도 있습니다.

## Windows를 설치한 후 Android를 업데이트할 수 있나요?
- ✅ **그렇습니다!** 어떤 방식으로든 Android를 업데이트할 수 있습니다. 업데이트 후 [안드로이드 재루팅 가이드](Re-rooting-ko.md)를 참고하세요

## secureboot 비활성화
> [!Warning]
> 필요한 경우에만 진행하세요!

> [**`secureboot 비활성화 가이드`**](/guide/Korean/disable-secureboot-ko.md)

#### 끝!


## Microsoft Office / Microsoft 365 설치
- 태블릿에 [ISO 파일](https://drive.google.com/file/d/10FTyC0XBccj0BkxdIa_W_haixQz-d3to/view?usp=drivesdk)을 다운로드 하세요
- 파일에 마우스 우클릭을 하고 탑재를 선택하여 파일 탐색기에서 파일을 여세요
- ```Office Tool Plus.exe```를 더블 클릭하여 설치 마법사를 시작하세요
- 사용자 계정 컨트롤 창에서 권한을 허용합니다 
- 창이 나타나면, `Yes`를 선택하세요
- 설치가 완료될 때까지 기다리세요

#### 끝!


## Windows / Office 활성화
[이곳](https://github.com/massgravel/Microsoft-Activation-Scripts)에서 Massgravel님의 설명을 참조하세요

#### 끝!


## ~플래시 사용법~
 - [Flashlight.7z](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/flashlight_fix.7z)를 다운로드하고 압축을 해제하세요
> flashlight.exe를 실행하여 플래시를 켜세요
> 아무 키나 눌러 플래시를 끄세요

#### 끝!

## Windows 11 초기화
> [!Warning]
> 이 과정을 완료하면, 파일, 설정, 앱을 포함한 Windows의 모든 데이터가 삭제됩니다.
- 설정 앱을 엽니다.
- 시스템을 선택합니다.
- 복구 탭을 선택합니다.
- **복구 옵션** 부분 밑에서, **이 PC 초기화** 부분의 ```PC 초기화``` 버튼을 선택합니다.
- ```모든 항목 제거``` 옵션을 선택합니다.
- ```로컬 다시 설치``` 옵션을 선택합니다.
- `다음` 버튼을 선택합니다.
- `다시 설정` 버튼을 선택합니다.
> 재부팅 후에, Windows가 초기화됩니다.

#### 끝!


## 밝기 최적화 비활성화

- **`Win + I`** 키를 입력하거나 시작 버튼을 마우스로 우클릭하고 "설정"을 선택하여 Windows 11 설정을 엽니다.

- 왼쪽 사이드바에서 **`시스템`** 을 선택합니다.

- 시스템 설정에서 **`디스플레이`** 를 선택합니다.

- **`밝기`** 부분에서, 두 개의 옵션이 있습니다:

**```1. 조명이 변경될 때 밝기 자동 변경:```**

> 체크 박스를 선택 해제하여 이 옵션을 끄세요.
  
 **```2. 표시된 콘텐츠와 밝기를 최적화하여 배터리 향상을 지원합니다:```**

> 메뉴에서 **`끄기`** 를 선택하여 이 옵션을 끄세요.

>[!NOTE]
> 이렇게 하면, 콘텐츠와 밝기 최적화가 기기에서 비활성화됩니다.

 #### 끝!













