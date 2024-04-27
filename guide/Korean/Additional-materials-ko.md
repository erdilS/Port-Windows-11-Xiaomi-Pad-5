<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# 윈도우가 설치된 Xiaomi pad 5를 위한 유용한 앱과 설명

## D 드라이브 숨기기 (modem 파티션)
> [!NOTE]
> 몇몇 애플리케이션들이 이 드라이브에 쓰기 작업을 할 수 있는데, 이 드라이브가 수정되면 안 되기 때문에 이 부분은 권장됩니다

- 명령 프롬프트를 열고 ```diskpart``` 명령어를 실행합니다
- ```list volume``` 명령어를 실행하여 모든 이용 가능한 볼륨들을 찾습니다
- ```select volume $``` 명령어를 이용하여 D 디스크를 선택합니다. 이때 "$" 를 볼륨 숫자로 교체하십시오
- ```remove letter d``` 명령어로 문자를 제거합니다
- ```exit``` 명령어로 diskpart를 종료합니다

#### 끝!


## USB 호스트 모드 비활성화
> [!Warning]
> 전원이 공급되지 않는 USB 장치는 작동하지 않습니다

[USB Host Control](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/USBHost) 파일을 실행하여 USB 호스트 모드를 활성화/비활성화합니다. 이때 비활성화/활성화 메시지를 확인하고 

#### 끝!


## secureboot 비활성화
> PC 없이 드라이버를 업데이트하고자 하는 경우 아래의 가이드를 참조하십시오

[secureboot 비활성화 가이드](/guide/Korean/disable-secureboot-ko.md)

#### 끝!


## ```Microsoft Office```/```Microsoft 365``` 설치
- 태블릿에 [ISO 파일](https://drive.google.com/file/d/1-i-0RraTSgwxqQSWal3uYWCen1TjK6d3/view?usp=drivesdk)을 다운로드 하십시오
- 파일에 마우스 우클릭을 하고 탑재를 선택하여 파일 탐색기에서 파일을 여십시오
- ```Office Tool Plus.exe```를 더블 클릭하여 설치 마법사를 시작하십시오
- 창이 나타나면, `Yes`를 선택하십시오
- 설치가 완료될 때까지 기다리십시오

#### 끝!


## Windows / Office 활성화
[이곳](https://github.com/massgravel/Microsoft-Activation-Scripts)에서 Massgravel의 설명을 참조하십시오

#### 끝!


## 플래시 사용법
 - [Flashlight.7z](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/flashlight_fix.7z)를 다운로드하고 압축을 해제하십시오
> flashlight.exe를 실행하여 플래시를 켜십시오
> 아무 키나 눌러 플래시를 끄십시오

#### 끝!


















