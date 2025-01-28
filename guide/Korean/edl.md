<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Xiaomi Pad 5 에서 윈도우 구동

## EDL 모드의 장치 복구
> 이 가이드에는 장치를 복구하는 두 가지 방법이 포함되어 있습니다. 방법 1이 안되면, 방법 2를 이용해보세요

### EDL 모드로 진입
> Xiaomi Pad 5를 **EDL 모드** 로 부팅하기 위한 두 가지 방법이 있습니다. 현재 상황에 맞는 것을 사용하세요.

> [!NOTE]
>
> ▶️ 클릭하여 메뉴를 확장하세요.

<details>
  <summary><strong>방법 1: 부트로더가 언락 상태일 때</strong></summary>

> 부트로더가 언락되어 있으면, **fastboot mode** 에서 아래의 명령어를 입력하세요
```cmd
fastboot oem edl
```

</details>

<details>
  <summary><strong>방법 2: 부트로더가 락 상태이거나 장치가 부팅 불가능할 때</strong></summary>

- **EDL 케이블** 이 있다면 장치에 이 케이블을 연결하고 케이블의 버튼을 눌러 **EDL mode** 로 부팅합니다.
> 온라인에서 찾을 수 있는 EDL 케이블은 이름에 V2가 포함되어 있어야 작동합니다. (예시: **Hydra V2 EDL Cable**)
- 또는, **테스트 포인트를 쇼트킵니다**. (장치의 뒷판을 열어야 합니다)

</details>

### 모든 것이 괜찮은지 확인
- PC에서 **장치 관리자** 를 열고 **Qualcomm HS-USB QDLoader 9008** 와 같은 새로운 장치를 찾습니다.
- **장치 관리자** 에서 장치 이름이 **QUSB_BULK_CID** 이거나 노란색 경고 ⚠️ 표시가 있는 경우, 드라이버를 설치/업데이트해야 합니다.
- 드라이버를 설치하기 위하여, **[QUD.zip](https://github.com/n00b69/woa-betalm/releases/download/Qfil/QUD.zip)** 파일을 다운로드 및 압축 해제하고, 장치 관리자에서 오류가 발생한 장치를 선택히고, **드라이버 업데이트** 선택하고, 압축 해제했던 **QUD 폴더** 를 선택하세요.

> [!NOTE]
>
> ▶️ 클릭하여 메뉴를 확장하세요.

<details>
  <summary><strong>방법 1: 무료 방법</strong></summary>

## 방법 1: 무료 방법

### 준비물
- [`패치된 MiFlash 도구`](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/MiFlashPatched.zip)

- [`패치된 firehose (.elf) 파일`](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/prog_ufs_firehose_sm7150_ddr.elf)

- `추출된` [`Nabu의 fastboot 롬`](http://xmfirmwareupdater.com/miui/nabu/) 

### 필요한 파일 준비
- Unzip the **fastboot ROM** for your Xiaomi Pad 5.
- Unzip the **MiflashPatched.zip** file you downloaded earlier.
- Copy the **firehose (.elf)** file from the **MiflashPatched.zip** folder into the **images** folder inside your extracted **fastboot ROM**, overwriting the existing file.

#### Open MiFlash Tool 
- Navigate to the **MiFlash** folder inside the extracted **MiflashPatched.zip**.
- Launch **XiaoMiFlash.exe** as an administrator.

### Flashing the ROM
- Click the **Select** button in **MiFlash** and choose the folder where you extracted your **fastboot ROM** (the one where you replaced the **firehose.elf** file).
- In the **MiFlash** tool, ensure the **"Clean All"** option is checked.
- Click **Refresh** in **MiFlash** to verify the connection to your device.
- After confirming your device is detected and the **"Clean All"** option is selected, click **Flash** to start the flashing process.

> [!Important]
> If you see any error that doesn't go away after 2 minutes, reboot the device into **EDL mode** again, then click **Refresh** and **Flash** again to retry.

#### 장치를 재부팅합니다
- 플래시가 완료되면, **Reboot** 버튼을 클릭하여 장치를 재부팅합니다.

</details>

<details>
  <summary><strong>방법 2: 유료 EDL 방법</strong></summary>

## 방법 2: HXRU Tool을 통한 유료 복구

### 준비물 
- `$3 USDT` 및 크레딧을 위한 암호화폐 지갑 (일부 러시아 은행 계좌 가능)

- HXRU 지원 소통을 위한 `텔레그램 계정`

- [`MiFlash HXRU 도구`](https://hxrutool.net/tool/Xiaomi_Auth_Tool_v9.0.0.5_mtk.zip)
 
- [`Nabu의 순정 fastboot 롬`](http://xmfirmwareupdater.com/miui/nabu/)  
### HXRU Tool 설정  
- **[HXRU dashboard](https://dashboard.hxrutool.com/Register)** 에서 계정을 생성합니다.
- **MiFlash HXRU** 도구를 다운로드 및 압축 해제합니다.

#### 크레딧을 구매합니다 
- 텔레그램에서 **@hxruofficial** 님께 연락하여 **5 크레딧** (대략 **$3**)을 구매합니다. 장치를 복구하려면 이 크레딧이 필요합니다.

### 장치 복구
- Open **XiaoMiFlash.exe** and grant it administrator access.
- Download the stock fastboot rom for your device (which should have a .tgz extension) and open it. Inside there should be a .tar file. Extract the contents of this .tar file into any folder).
- Click the **select** button in **XiaoMiFlash** and select this folder.
- Press **flash**.
- If you get a `write time out` error, hold the **power** + **volume down** button for +- 30 seconds to reboot EDL. After this press the **flash** button again.
- After a few seconds a login popup should show up. Enter your HRXU account details here and press **Request Auth Flashing**.

#### 장치를 재부팅합니다
- **flash done** 이 표시되면, **전원** 을 14초 정도 누른 상태를 유지하여 장치를 재부팅합니다.

</details>

### Reflashing your rom with MiFlash
> [!Warning]
> These tools only flash the rom to one slot. If your device ever switches slots, it'll boot back into EDL again.
- Reboot to fastboot mode.
- Flash the fastboot rom a second time using **MiFlash** or with the **flash_all.bat** file in the rom.
- Reboot after it finishes flashing.

#### 성공!
이제 Xiaomi Pad 5가 원래대로 성공적으로 복구되었을 것입니다!
































