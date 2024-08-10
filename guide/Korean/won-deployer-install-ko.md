<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows Running On A Xiaomi Pad 5">

# Xiaomi Pad 5 에서 윈도우 구동

## WoN-deployer를 사용한 설치

### 준비물
- ```제대로 작동하는 두뇌 (진지하게, 생각해야 합니다!)```

- [```안드로이드 플랫폼 도구```](https://developer.android.com/studio/releases/platform-tools)
  
- [```ADB 드라이버가 설치된 PC```](https://dl.google.com/android/repository/usb_driver_r13-windows.zip)
  
- [```ARM 윈도우 ESD```](https://worproject.com/esd) (항목 선택 - Version:  ```11``` Build:  ```22631.2861``` Architecture:  ```ARM64``` Edition:  ```CLIENT``` Language:  ```원하는 언어를 선택하세요```)
    
- [```드라이버```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/Drivers)

- ```언락 상태의 부트 로더``` - (부트로더가 락 상태이며 언락 방법을 모를 경우 [이 가이드](unlock-bootloader.md)를 이용하세요)

### 메모:
> [!NOTE]
> 듀얼 부팅을 위해 어느 Android든 사용할 수 있습니다 - MIUI/HyperOS 또는 커스텀 롬
>
> 도움이 필요하시면, [텔레그램 채팅](https://t.me/nabuwoa)으로 저희에게 연락해 주세요


> [!Warning]
> 모든 데이터가 삭제됩니다! 필요하다면 미리 백업하세요.
>
> **유튜브 또는 다른 플랫폼에 있는 동영상 가이드를 보지 마시기 바랍니다!**

### WoN Deployer 설치 (Windows on Nabu Installer)
- **`PowerShell/Terminal`** 을 관리자 권한으로 열고 아래의 명령어를 실행합니다:

```shell
powershell.exe -C "irm https://rb.gy/msq1tz | iex"
```

> [!NOTE]
> 위의 명령어가 작동하지 않을 경우, 아래의 명령어를 시도해보세요:

```shell
powershell.exe -C "irm https://raw.githubusercontent.com/arkt-7/won-deployer/main/GetWON.ps1 | iex"
```

**WoN Deployer가 적절하게 설치되었는지 확힌합니다**

   1. 이전에 열었던 **`PowerShell/Terminal`** 창을 닫습니다

   2. **`PowerShell/Terminal`** 을 관리자 권한으로 열고 아래의 명령어를 실행합니다:

```shell
won-deployer -h
```
> [!NOTE]
> WoN Deployer가 적절하게 설치된 경우, 앱에 대한 정보가 나타날 것입니다. 오류가 발생할 경우, 다시 설치하세요.

### fastboot로 재부팅
- **`볼륨 아래`** + **`전원`** 버튼을 누른 상태를 유지하거나, 안드로이드에 부팅되어 있는 동안 `adb reboot bootloader` 를 실행하여 NABU를 **fastboot** 모드로 부팅합니다.

### WoN Deployer 실행
- **`PowerShell`** 또는 **`terminal`** 을 관리자 권한으로 엽니다.
- **`won-deployer`** 를 입력하고 화면의 지시를 따릅니다.
  
```shell
won-deployer
```

### Windows 이미지 선택
- **Windows ESD 또는 WIM 파일 경로를 입력하고 에디션을 선택합니다**
> Windows 10의 경우, `shift ` + `마우스 오른쪽 버튼` 키를 눌러 Windows 이미지의 경로를 복사할 수 있습니다.
- Windows ESD/WIM 파일의 경로를 복사하고 붙여넣습니다.
**`Enter the path of Windows ESD (Copy as path)::`**
- 설치하고 싶은 Windows 에디션의 인덱스 수를 입력합니다.
**`Please enter the index number of the edition you want to use:`**
<!-- ${\color{Magenta}[y/n] \space \color{cyan}(n): }$ -->

### 드라이버 선택
- **[```nabu-drivers.zip```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/Drivers) 파일의 경로를 입력합니다**
- nabu-drivers.zip 파일의 경로를 복사하고 붙여넣습니다.
**`Enter the path of the driver ZIP file (Copy as path)::`**

- **화면의 지시를 따릅니다**

   - **`행운을 빌어요`**.

> [!IMPORTANT]
> 오류가 발생한 경우 아래의 명령어를 실행하고 [@ArKT_7](https://telegram.me/ArKT_7)님께 스크린샷을 공유해주시거나 [공식 텔레그램 그룹](https://telegram.me/nabuwoa)에 물어봐주세요
### 상세 로그 출력을 위한 프로그램 재실행

   1. 이전에 열었던 **`PowerShell/Terminal`** 창을 닫습니다

   2. PowerShell/Terminal를 관리자 권한으로 다시 열고 아래의 명령어를 실행합니다:

   ```shell
   won-deployer --debug
   ```

## 끝!

