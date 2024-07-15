<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# 윈도우가 설치된 Xiaomi pad 5를 위한 유용한 앱과 설명

### 지원되는 앱/게임 목록
This is by no means a comprehensive list, it simply lists apps/games that have been tested by the community
[The link can be found here](https://docs.google.com/spreadsheets/d/1XYuoySgYQE0HL573sA-0RGMX7I4lt5rWJuQ8Z8yRJNY/edit?usp=drivesdk)

You can also find a list of dedicated ARM software [at this link](https://armrepo.ver.lt/)

#### 끝!

## D 드라이브 숨기기 (modem 파티션)
> [!NOTE]
> 몇몇 애플리케이션들이 이 드라이브에 쓰기 작업을 할 수 있는데, 이 드라이브가 수정되면 안 되기 때문에 이 부분은 권장됩니다

- Download [`ModemHide.vbs`](https://github.com/Misha803/My-Scripts/releases/tag/ModemHide) to your NABU
- Run it
- Approve any UAC dialogs 
- Click `Yes` in the dialog box


#### 끝! 


## USB 호스트 모드 비활성화
> [!Warning]
> 전원이 공급되지 않는 USB 장치는 작동하지 않습니다

> [!Important]
> The following steps must be done on the Mi Pad 5 in Windows, not on your computer. 

Run [USB Host Mode Control](https://github.com/Misha803/My-Scripts/releases/tag/USB-Host-Mode-Control) to enable/disable USB host mode and  confirm that you want to disable/enable USB host mode 

#### 끝!

## Сan I update my Windows using Windows Update or an ISO image?
- ✅ **Yes!** You can install any updates that appear in Windows Update and you can also use an ISO image for this

## Can I update my Android after installing Windows?
- ✅ **Yes!** You can update Android in any way, just use the [Re-rooting Android guide](Re-rooting-en.md) after the update

## secureboot 비활성화
> [!Warning]
> 필요한 경우에만 진행하세요!

> [**`secureboot 비활성화 가이드`**](/guide/Korean/disable-secureboot-ko.md)

#### 끝!


## ```Microsoft Office```/```Microsoft 365``` 설치
- 태블릿에 [ISO 파일](https://drive.google.com/file/d/10FTyC0XBccj0BkxdIa_W_haixQz-d3to/view?usp=drivesdk)을 다운로드 하세요
- 파일에 마우스 우클릭을 하고 탑재를 선택하여 파일 탐색기에서 파일을 여세요
- ```Office Tool Plus.exe```를 더블 클릭하여 설치 마법사를 시작하세요
- 사용자 계정 컨트롤 창에서 권한을 허용합니다 
- 창이 나타나면, `Yes`를 선택하세요
- 설치가 완료될 때까지 기다리세요

#### 끝!


## Windows / Office 활성화
[이곳](https://github.com/massgravel/Microsoft-Activation-Scripts)에서 Massgravel의 설명을 참조하세요

#### 끝!


## ~플래시 사용법~
 - [Flashlight.7z](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/flashlight_fix.7z)를 다운로드하고 압축을 해제하세요
> flashlight.exe를 실행하여 플래시를 켜세요
> 아무 키나 눌러 플래시를 끄세요

#### 끝!

## Windows 11 초기화
> [!Warning]
> After you complete these steps, all your data in Windows will be erased including files, settings, and apps.
- Open Settings app.
- Click on System.
- Click the Recovery tab.
- Under the **Recovery options** section, click the ```Reset PC``` button in the **Reset this PC** setting.
- Click the ```Remove Everything``` option.
- Select the ```Local reinstall``` option.
- Click the `Next` button.
- Click the `Reset` button.
> After rebooting, you will get a clean Windows.

#### 끝!


## 자동 밝기 최적화 비활성화

- Open Windows 11 Settings by pressing **`Win + I`** or by right-clicking the Start button and selecting "Settings".

- Navigate to the **`System`** section from the left sidebar.

- Select **`Display`** within the System settings.

- In the **`Brightness`** section, you'll see two options:

**```1. Change brightness automatically when lighting changes:```**

> Turn this option off by toggling the switch to the **`Off`** position.
  
 **```2. Change brightness based on content:```**

> Turn this option off by selecting **`Off`** from the dropdown menu.

>[!NOTE]
> After making these changes, adaptive brightness and content-adaptive brightness will be disabled on your device.

 #### 끝!













