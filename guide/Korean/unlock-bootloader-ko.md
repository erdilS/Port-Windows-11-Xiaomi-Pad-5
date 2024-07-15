<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Xiaomi Pad 5 에서 윈도우 구동

## 부트로더 언락: HyperOS/MIUI를 위한 자세한 단계별 가이드

### 준비물:
- [```Mi Community 앱(HyperOS/MIUI 14 이상만 해당)```](https://apkpure.net/xiaomi-community/com.mi.global.bbs/download).

- [`Mi Unlock Tool`](https://miuirom.xiaomi.com/rom/u1106245679/6.5.224.28/miflash_unlock-en-6.5.224.28.zip).
>

>[!NOTE]
>
> Mi unlock Tool이 안내하는 대기 시간은 사람마다 다를 수 있으므로 참고하세요.

>[!WARNING]
>
> 대기 시간 동안, 기기를 초기화하거나 Xiaomi 계정을 로그아웃하지 마세요.
>
> 데이터 백업: 부트로더 언락은 기기의 모든 데이터를 지울 것입니다. 진행하기 전에 중요한 데이터를 백업하세요.

### 1. 개발자 옵션 활성화:

   **MIUI를 사용 중인 경우:**
   - 설정 → 휴대전화 정보 → MIUI 버전 순서대로 이동합니다.
   - 개발자 옵션이 활성화될 때까지 MIUI 버전을 계속 누릅니다(아래에 팝업이 표시됩니다).

   **HyperOS를 사용 중인 경우:**
   - 설정 → 내 기기 → 자세한 정보 및 사양 → OS 버전 순서대로 이동합니다.
   - 개발자 옵션이 활성화될 때까지 OS 버전을 계속 누릅니다(아래에 팝업이 표시됩니다).


### 2. OEM 잠금 해제 및 USB 디버깅 활성화:
   - 설정 → 일반 → 개발자 옵션 순서대로 이동합니다.
   - OEM 잠금 해제 및 USB 디버깅을 활성화합니다.

### 3. Mi 계정 추가:/언락 신청

<details>
<summary><b><strong>표준 과정 (Miui-13 또는 이전 버전):</strong></b></summary>

 **```3. Mi 계정 추가:```**
   - 설정 > 일반 > 개발자 옵션 > Mi 언락 상태 순서대로 이동합니다.
   - "계정 및 기기 추가"를 클릭합니다. 성공적으로 추가하면, "추가 완료" 메시지가 출력됩니다.

  </summary>
</details>

<details>
<summary><b><strong>신규 과정 (HyperOS/miui-14 이상만 해당):</strong></b></summary>

>

> 기기가 글로벌 모델인 경우, 언제든지 부트로더 언락을 신청할 수 있습니다.

   **시간 트릭:**
   - Xiaomi는 매일 2,000개의 기기만을 언락할 수 있도록 합니다.
   - 이 일일 한도의 시간은 모스크바 시간으로 오후 7시에 초기화됩니다.

 **```3. 언락 신청:```**
   - 모스크바 시간으로 오후 7시가 될 때까지 기다린 후 준비하세요. 신속하게 진행하지 않으면 해당 과정이 진행되지 않을 수 있습니다.
   - Xiaomi Community 앱을 열고 Global로 설정한 후 기기와 동일한 계정으로 로그인하세요.
   - "Me" 탭으로 가서 "Unlock bootloader"를 클릭한 다음, "Apply"를 클릭합니다.
   - 액세스가 허용되면 설정 > 일반 > 개발자 옵션 > Mi 언락 상태 순서대로 이동합니다.
   - "계정 및 기기 추가"를 클릭합니다. 성공적으로 추가하면, "추가 완료" 메시지가 출력됩니다.

  </summary>
</details>

### 4. 부트로더 언락:
   - Mi Flash Unlock Tool을 열고 아까와 같은 Mi 계정으로 로그인합니다.
   - 기기를 Fastboot 모드로 진입하고 PC에 기기를 연결합니다.
   - PC에서 Mi Unlock Tool을 사용하여 부트로더를 언락합니다.
   - 99% 이후 대기 시간 오류 (약 72시간/3일) 가 표시되면 모든 창을 닫고 대기 시간 만큼 기다린 다음에, 4단계의 과정을 다시 진행하세요.

  
#### 도움을 주신 분들:
이 가이드를 테스트해주신 분들: [@ArKT_7](https://t.me/ArKT_7), [@I914900HX](https://t.me/I914900HX), [@Samponnporlsak](https://t.me/Samponnporlsak)

HyperOS/miui-14에 적용되는 시간 트릭을 공유해 주신 [@hxruofficial](https://t.me/hxruofficial)님께 특별히 감사드립니다. hxruofficial님은 Qualcomm 플래싱, EDL 및 FDL을 전문으로 합니다. [HXRU Tool](https://hxrutool.com/)에서 hxruofficial님이 제작한 도구와 서비스를 확인해보세요.
