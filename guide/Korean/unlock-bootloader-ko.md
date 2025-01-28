<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Xiaomi Pad 5 에서 윈도우 구동

## 부트로더 언락: HyperOS/MIUI를 위한 자세한 단계별 가이드

### 준비물
- [`📲 Mi Community 앱(HyperOS/MIUI 14만 해당)`](https://apkpure.net/xiaomi-community/com.mi.global.bbs/download).

- [`🔧 Mi Unlock Tool`](https://miuirom.xiaomi.com/rom/u1106245679/6.5.224.28/miflash_unlock-en-6.5.224.28.zip).

- [`🛠️ HyperSploit (우회 프로그램)`](https://github.com/TheAirBlow/HyperSploit/releases/download/1.0.0/HyperSploit-Windows.exe).

> [!WARNING]
>
> 데이터 백업: 부트로더 언락은 기기의 모든 데이터를 제거합니다. 과정을 진행하기 전에 중요한 데이터를 백업했는지 확인하세요.

### 개발자 옵션 활성화
- **HyperOS인 경우:**
  - **설정 → 내 기기 → 자세한 정보 및 사양 → OS 버전** 순서대로 이동합니다.
  - 개발자 옵션이 활성화될 때까지 OS 버전을 계속 누릅니다. (아래에 팝업이 표시됩니다)

- **MIUI인 경우:**
  - **설정 → 휴대전화 정보 → MIUI 버전** 순서대로 이동합니다.
  - 개발자 옵션이 활성화될 때까지 MIUI 버전을 계속 누릅니다. (아래에 팝업이 표시됩니다)

### OEM 잠금 해제 및 USB 디버깅 활성화
- **설정 → 일반 → 개발자 옵션** 순서대로 이동합니다.
- **OEM 잠금 해제** 및 **USB 디버깅** 을 활성화합니다.

### 새로운 방법 (HyperOS/MIUI 14)
<details>
  <summary><strong>클릭하여 확장하세요</strong></summary>

  <details>
   <summary><strong>방법 1: HyperSploit 우회 사용 (권장됨) </strong></summary>

**이 방법은 Mi Community 앱에서 신청하는 동안 대기 시간 한도를 우회할 것입니다.**

### 언락을 위한 적용 (HyperSploit)
- **HyperSploit-Windows.exe** 를 관리자 권한으로 실행합니다.
- 기기에 창이 나타나면, **확인** 을 선택하여 USB 디버깅을 허용합니다.
- **HyperSploit** 창의 화면에 표시되는 지시를 따릅니다. **attempt to bind account** 가 표시되면 다음 과정을 진행합니다:
- **설정 → 일반 → 개발자 옵션 → Mi 언락 상태** 순서대로 이동합니다.
- **계정 및 기기 추가** 를 클릭하고, 추가가 끝나면, HyperSploit이 **Successfully binded** 를 표시할 것입니다

  </details>
  
  <details>
    <summary><strong>방법 2: 시간 트릭 사용 </strong></summary>
    
**기기가 글로벌 모델인 경우, 특정 시간에 부트로더 언락을 신청할 수 있습니다.**
- Xiaomi는 **하루에 2,000대 언락** 을 허용합니다.
- 이 일일 한도의 재설정 시간은 **모스크바 시간대 오후 7시** 입니다.

### 언락을 위한 신청
- **모스크바 시간대 오후 7시** 가 될 때까지 기다린 후 준비하세요. 신속하게 진행하지 않으면 해당 과정이 진행되지 않을 수 있습니다.
- **Xiaomi Community 앱** 을 열고 Global로 설정한 후 기기와 동일한 계정으로 로그인하세요.
- **"Me"** 탭으로 가서 **"Unlock bootloader"** 를 클릭한 다음, **"Apply"** 를 클릭합니다.
- 액세스가 허용되면 **설정 > 일반 > 개발자 옵션 > Mi 언락 상태** 순서대로 이동합니다.
- **계정 및 기기 추가** 를 클릭합니다. 성공적으로 추가하면, **추가 완료** 메시지가 출력됩니다.

  </details>
  
</details>

### 일반적인 방법 (MIUI 13 또는 하위)
<details>
  <summary><strong>클릭하여 확장하세요</strong></summary>

### Mi 계정 추가
- 설정 > 일반 > 개발자 옵션 > Mi 언락 상태 순서대로 이동합니다.
- "계정 및 기기 추가"를 클릭합니다. 성공적으로 추가하면, "추가 완료" 메시지가 출력됩니다.

</details>

### 부트로더 언락
- **Mi Flash Unlock Tool** 을 열고 아까와 같은 Mi 계정으로 로그인합니다.
- 기기를 **fastboot 모드** 로 진입하고 PC에 기기를 연결합니다.
- PC에서 Mi Unlock Tool을 사용하여 부트로더를 언락합니다.
- 대기 시간 오류 `약 72시간/3일`가 표시되면 모든 창을 닫고 대기 시간 만큼 기다린 다음에, 이 과정을 다시 진행하세요.

> [!NOTE]
> Mi unlock Tool이 표시하는 대기 시간은 사람마다 다를 수 있습니다.
>
> 대기 시간 동안, 기기를 초기화하거나 Xiaomi 계정을 로그아웃하지 마세요.


### 도움을 주신 분
- **이 가이드는 다음 분께서 테스트 및 검증해주셨습니다.** [@ArKT_7](https://t.me/ArKT_7)  **GitHub:** [@ArKT-7](https://github.com/ArKT-7)






















