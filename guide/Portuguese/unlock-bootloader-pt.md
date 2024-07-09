<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Windows no Xiaomi Pad 5

## Desbloqueando o Bootloader: Um guia detalhado passo-a-passo para HyperOS/MIUI

### Pré requesitos:
- [```Aplicativo Mi Community (apenas para HyperOS/MIUI 14)```](https://apkpure.net/xiaomi-community/com.mi.global.bbs/download).

- [`A Mi Unlock Tool`](https://miuirom.xiaomi.com/rom/u1106245679/6.5.224.28/miflash_unlock-en-6.5.224.28.zip).
>

>[!NOTE]
>
> O período de espera na Mi Unlock Tool pode variar, apenas aguarde.

>[!WARNING]
>
> Durante o período de espera, não formatar o tablet ou desconectar a sua conta Xiaomi.
>
> Fazer Backup: Desbloquear o Bootloader vai formatar seu tablet, por isso faça o Backup de arquivos importantes antes de desbloquear.

### 1. Ativar a Opções do Desenvolvedor:

   **Na MIUI:**
   - Vá para Configurações → Sobre o telefone → Versão do MIUI.
   - Aperte na Versão do MIUI várias vezes até que a opções do desenvolder seja ativada (um popup vai avisar).

   **Na HyperOS:**
   - Vá para Configurações → Sobre o telefone → Informações e especificações detalhadas → Versão do OS.
   - Aperte na Versão do OS várias vezes até que a opções do desenvolder seja ativada (um popup vai avisar).


### 2. Enable OEM Unlocking and USB Debugging:
   - Vá para Configurações → Configurações adicionais → Opções do Desenvolvedor.
   - Ative o Desbloqueio de OEM e a Depuração USB.

### 3. Adicionar conta e solicitar o desbloqueio

<details>
<summary><b><strong>Processo comum (Para aqueles na Miui-13 ou inferior):</strong></b></summary>

 **```3. Adicionar conta:```**
   - Vá para Configurações > Configurações adicionais > Opções do Desenvolvedor > Status do Mi Unlock.
   - Aperte em "Adicionar conta e dispositivo". Se feito com sucesso, o aviso "Adicionado com sucesso" vai surgir.

  </summary>
</details>

<details>
<summary><b><strong>Novo Processo (Apenas para HyperOS/miui-14):</strong></b></summary>

>

> Se seu dispositivo é da versão global, vocẽ pode se inscrever para o desbloqueio de bootloader em um horário específico.

   **Truque do Horário:**
   - A Xiaomi permite a inscrição diária de 2,000 dispositivos.
   - O horário que essa contagem diária reseta é as 7 PM Horário de Moscow.

 **```3. Solicitando o Desbloqueio:```**
   - Sincronize com o fuso horário de Moscow e quando for as 7 PM, esteja pronto e seja rápido.
   - Abra o aplcativo Xiaomi Community, selecione Global, e entre com a mesma conta do seu dispositivo.
   - Vá para a sessão "Me", clique na opção "Unlock bootloader," e por fim em "Solicite o desbloqueio".
   - Quando você receber o acesso, vá para Configurações > Configurações adicionais > Opções do Desenvolvedor > Status do Mi Unlock.
   - Aperte em "Adicionar conta e dispositivo". Se feito com sucesso, o aviso "Adicionado com sucesso" vai surgir.

  </summary>
</details>

### 4. Desbloqueando o Bootloader:
   - Abra a Mi Flash Unlock Tool e entre com a mesma conta Mi do dispositivo.
   - Inicie o dispositivo no modo Fastboot e conecte no PC.
   - Use a Mi Unlock Tool no seu PC para desbloquear o bootloader.
   - se o erro periódo de espera (waiting period error) surgir depois dos 99%, provavelmente 72 hours/3 dias, saia do programa e espere esse periódo acabar, então repita o passo 4.

  
#### Créditos e Reconhecimentos:
Este guia foi testado por: [@ArKT_7](https://t.me/ArKT_7), [@I914900HX](https://t.me/I914900HX), [@Samponnporlsak](https://t.me/Samponnporlsak)

Agradecimentos especiais para [@hxruofficial](https://t.me/hxruofficial) por compartilhar o truque do horário na HyperOS/miui-14. Ele é especializado em Qualcomm flashing, EDL, e FDL. Veja as ferramentas e serviços dele em [HXRU Tool](https://hxrutool.com/).
