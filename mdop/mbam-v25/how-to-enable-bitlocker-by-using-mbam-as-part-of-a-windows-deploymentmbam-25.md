---
title: 如何使用 MBAM 做為 Windows 部署的一部分來啟用 BitLocker
description: 如何使用 MBAM 做為 Windows 部署的一部分來啟用 BitLocker
author: dansimp
ms.assetid: 7609ad7a-bb06-47be-b186-0a2db787c8a5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 04/23/2017
ms.openlocfilehash: 4b2cbf333c705088d0a068521fb65e99551bb1f1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811630"
---
# 如何使用 MBAM 做為 Windows 部署的一部分來啟用 BitLocker


本主題說明如何使用 MBAM 作為 Windows 影像和部署程式的一部分，在最終使用者的電腦上啟用 BitLocker。 如果您在重新開機時看到黑屏（安裝階段結束之後），指出無法解除鎖定磁片磁碟機，請參閱在[windows 10 版本1511中使用預配 BitLocker 時，舊版的 Windows 版本不會在「安裝程式視窗和建構管理員」步驟之後啟動](https://support.microsoft.com/en-us/help/4494799/earlier-windows-versions-don-t-start-after-you-use-pre-provision-bitlo)。

**必要條件：**

-   現有的 Windows 映像部署程式– Microsoft 部署工具套件（MDT）、Microsoft System Center Configuration Manager 或其他影像工具或程式–必須在適當的地方

-   您必須先在 BIOS 中啟用 TPM，然後才能看到作業系統

-   MBAM 伺服器基礎結構必須就緒且易於存取

-   必須建立 BitLocker 所需的系統磁碟分割

-   在 MBAM 中，電腦必須先加入網域，才能完全啟用 BitLocker

**若要在 Windows 部署中使用 MBAM 2.5 SP1 啟用 BitLocker**

1. 在 MBAM 2.5 SP1 中，在 Windows 部署期間啟用 BitLocker 的建議方法是使用 `Invoke-MbamClientDeployment.ps1` PowerShell 腳本。

   -   在 `Invoke-MbamClientDeployment.ps1` 影像處理常式期間，腳本會 Enacts BitLocker。 當 BitLocker 原則需要時，MBAM 代理程式會在網域使用者第一次登入影像之後，立即提示網域使用者建立 PIN 或密碼。

   -   輕鬆搭配 MDT、System Center Configuration Manager 或獨立影像處理常式使用

   -   與 PowerShell 2.0 或更新版本相容

   -   使用 TPM 金鑰保護裝置加密 OS 容量

   -   完全支援 BitLocker 預配

   -   選擇性地加密 FDDs

   -   針對 Windows 7 的託管 TPM OwnerAuth，MBAM 必須擁有 TPM 才能進行保管。
   針對 Windows 8.1、Windows 10 RTM 和 Windows 10 版本1511，支援以 TPM OwnerAuth 進行保管。
   如果您使用的是 Windows 10 版本1607或更新版本，則只有 Windows 可以取得 TPM 擁有權。 在 addiiton 中，Windows 將不會在預配 TPM 時保留 TPM 擁有者密碼。 如需詳細資訊，請參閱[TPM 擁有者密碼](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password)。

   -   已保管的復原金鑰與復原金鑰套件

   -   立即報告加密狀態

   -   新的 WMI 提供者

   -   詳細記錄

   -   強健的錯誤處理

   您可以 `Invoke-MbamClientDeployment.ps1` 從[Microsoft.com 下載中心](https://www.microsoft.com/download/details.aspx?id=54439)下載腳本。 這是您的部署系統將呼叫以設定 BitLocker 磁碟機加密的主要腳本，以及使用 MBAM 伺服器來記錄復原金鑰。

   **MBAM 的 WMI 部署方法：** 已在 MBAM 2.5 SP1 中新增下列 WMI 方法，以支援使用 PowerShell 腳本啟用 BitLocker `Invoke-MbamClientDeployment.ps1` 。

   <a href="" id="mbam-machine-wmi-class"></a>**MBAM \ _MACHINE WMI 類別** 
   **PrepareTpmAndEscrowOwnerAuth：** 讀取 TPM OwnerAuth，並使用 MBAM 復原服務將它傳送到 MBAM 復原資料庫。 如果 TPM 不是擁有且自動預配未開啟，它會產生 TPM OwnerAuth 並取得擁有權。 如果失敗，則會傳回錯誤代碼以進行疑難排解。

   **記事**如果您使用的是 Windows 10 版本1607或更新版本，則只有 Windows 可以取得 TPM 擁有權。 在 addiiton 中，Windows 將不會在預配 TPM 時保留 TPM 擁有者密碼。 如需詳細資訊，請參閱[TPM 擁有者密碼](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password)。

| 參數 | 描述 |
| -------- | ----------- |
| RecoveryServiceEndPoint | 指定 MBAM 復原服務端點的字串。 |

以下是常見的錯誤訊息清單：

| 常見傳回值 | 錯誤訊息 |
| -------------------- | ------------- |
|  **S_OK**<br />0（0x0） | 方法已成功完成。 |
| **MBAM_E_TPM_NOT_PRESENT**<br />2147746304（0x80040200） | 電腦中不存在 TPM，或 BIOS 設定中已停用 TPM。 |
| **MBAM_E_TPM_INCORRECT_STATE**<br />2147746305（0x80040201） | TPM 不處於正確的狀態（啟用、啟動且允許擁有者安裝）。 |
| **MBAM_E_TPM_AUTO_PROVISIONING_PENDING**<br />2147746306（0x80040202） | MBAM 無法取得 TPM 的擁有權，因為自動配為擱置中。 自動預配完成後再試一次。 |
| **MBAM_E_TPM_OWNERAUTH_READFAIL**<br />2147746307（0x80040203） | MBAM 無法讀取 TPM 擁有者授權值。 此值可能已在成功進行委託之後被移除。 在 Windows 7 上，如果 TPM 是由其他人所擁有，則 MBAM 無法讀取這個值。 |
| **MBAM_E_REBOOT_REQUIRED**<br />2147746308（0x80040204） | 必須重新開機電腦，才能將 TPM 設定為正確的狀態。 您可能需要手動重新開機電腦。 |
| **MBAM_E_SHUTDOWN_REQUIRED**<br />2147746309（0x80040205） | 電腦必須關閉並再次開啟，才能將 TPM 設定為正確的狀態。 您可能需要手動重新開機電腦。 |
| **WS_E_ENDPOINT_ACCESS_DENIED**<br />2151481349（0x803D0005） | 遠端端點拒絕存取。 |
| **WS_E_ENDPOINT_NOT_FOUND**<br />2151481357（0x803D000D） | 遠端端點不存在或無法找到。 |
| * * WS_E_ENDPOINT_FAILURE<br />2151481357（0x803D000F） | 遠端端點無法處理要求。 |
| **WS_E_ENDPOINT_UNREACHABLE**<br />2151481360（0x803D0010） | 無法到達遠端端點。 |
| **WS_E_ENDPOINT_FAULT_RECEIVED**<br />2151481363（0x803D0013） | 從遠端端點收到包含錯誤的郵件。 請確定您連線到正確的服務端點。 |
| **WS_E_INVALID_ENDPOINT_URL** 2151481376 （0x803D0020） | 端點位址 URL 無效。 URL 必須以 "HTTP" 或 "HTTPs" 開頭。 |

   **ReportStatus：** 使用 MBAM 狀態報表服務，讀取卷的合規性狀態，並將它傳送到 MBAM 合規性狀態資料庫。 狀態包括密碼強度、保護器類型、保護程式狀態與加密狀態。 如果失敗，則會傳回錯誤代碼以進行疑難排解。

   | 參數 | 描述 |
   | --------- | ----------- |
   | ReportingServiceEndPoint | 指定 MBAM 狀態報表服務端點的字串。 |

   以下是常見的錯誤訊息清單：

   | 常見傳回值 | 錯誤訊息 |
   | -------------------- | ------------- |
   | **S_OK**<br /> 0（0x0） | 方法成功 |
   | **WS_E_ENDPOINT_ACCESS_DENIED**<br />2151481349（0x803D0005） | 遠端端點拒絕存取。|
   | **WS_E_ENDPOINT_NOT_FOUND**<br />2151481357（0x803D000D） | 遠端端點不存在或無法找到。 |
   | **WS_E_ENDPOINT_FAILURE**<br /> 2151481357（0x803D000F） | 遠端端點無法處理要求。 |
   | **WS_E_ENDPOINT_UNREACHABLE**<br />2151481360（0x803D0010） | 無法到達遠端端點。 |
   | **WS_E_ENDPOINT_FAULT_RECEIVED**<br />2151481363（0x803D0013） | 從遠端端點收到包含錯誤的郵件。 請確定您連線到正確的服務端點。 |
   | **WS_E_INVALID_ENDPOINT_URL**<br />2151481376（0x803D0020） | 端點位址 URL 無效。 URL 必須以 "HTTP" 或 "HTTPs" 開頭。 |

   <a href="" id="mbam-volume-wmi-class"></a>**MBAM \ _VOLUME WMI Class** **EscrowRecoveryKey：** 讀取大量的復原數位密碼和金鑰套件，並使用 MBAM 復原服務將其傳送至 MBAM 復原資料庫。 如果失敗，則會傳回錯誤代碼以進行疑難排解。

   | 參數 | 描述 |
   | --------- | ----------- |
   | RecoveryServiceEndPoint | 指定 MBAM 復原服務端點的字串。 |

   以下是常見的錯誤訊息清單：

   | 常見傳回值 | 錯誤訊息 |
   | -------------------- | ------------- |
   | **S_OK**<br />0（0x0） | 方法成功 |
   | **FVE_E_LOCKED_VOLUME**<br />2150694912（0x80310000） | 該卷已鎖定。 |
   | **FVE_E_PROTECTOR_NOT_FOUND**<br />2150694963（0x80310033） | 找不到該卷的數位密碼保護器。 |
   | **WS_E_ENDPOINT_ACCESS_DENIED**<br />2151481349（0x803D0005） | 遠端端點拒絕存取。 |
   | **WS_E_ENDPOINT_NOT_FOUND**<br />2151481357（0x803D000D） | 遠端端點不存在或無法找到。 |
   | **WS_E_ENDPOINT_FAILURE**<br />2151481357（0x803D000F） | 遠端端點無法處理要求。 |
   | **WS_E_ENDPOINT_UNREACHABLE**<br />2151481360（0x803D0010） | 無法到達遠端端點。 |
   | **WS_E_ENDPOINT_FAULT_RECEIVED**<br />2151481363（0x803D0013） | 從遠端端點收到包含錯誤的郵件。 請確定您連線到正確的服務端點。 |
   | **WS_E_INVALID_ENDPOINT_URL**<br />2151481376（0x803D0020） | 端點位址 URL 無效。 URL 必須以 "HTTP" 或 "HTTPs" 開頭。 |
     

2. **使用 Microsoft 部署工具套件（MDT）和 PowerShell 部署 MBAM**

   1.  在 MDT 中，建立新的部署共用或開啟現有的部署共用。

       **注意**  
       `Invoke-MbamClientDeployment.ps1`PowerShell 腳本可以與任何影像進程或工具搭配使用。 本節說明如何使用 MDT 整合它，但步驟與將它與任何其他進程或工具整合的方式類似。

       **警告**  
       如果您使用的是 BitLocker 預配（WinPE），且想要維持 TPM 擁有者授權值，您必須 `SaveWinPETpmOwnerAuth.wsf` 立即在 WinPE 中新增腳本，然後才能在完整作業系統中重新開機安裝。 **如果您不使用此腳本，您將會在重新開機時遺失 TPM 擁有者授權值。**

   2.  複製 `Invoke-MbamClientDeployment.ps1` 至** &lt; DeploymentShare &gt; \\Scripts**。 如果您使用的是預配，請將檔案複製 `SaveWinPETpmOwnerAuth.wsf` 到** &lt; DeploymentShare &gt; \\Scripts**。

   3.  將 MBAM 2.5 SP1 用戶端應用程式新增到部署共用中的 [應用程式] 節點。

       1.  在 [**應用程式**] 節點底下，按一下 [**新增應用程式**]。

       2.  選取 [**使用來源檔案的應用程式**]。 按 **\[下一步\]**。

       3.  在 [**應用程式名稱**] 中，輸入 "MBAM 2.5 SP1 用戶端]。 按 **\[下一步\]**。

       4.  流覽至包含的目錄 `MBAMClientSetup-<Version>.msi` 。 按 **\[下一步\]**。

       5.  輸入 "MBAM 2.5 SP1 用戶端] 作為您要建立的目錄。 按 **\[下一步\]**。

       6.  `msiexec /i MBAMClientSetup-<Version>.msi /quiet`在命令列中輸入。 按 **\[下一步\]**。

       7.  接受其餘的預設值來完成 [新增應用程式] 嚮導。

   4.  在 MDT 中，以滑鼠右鍵按一下部署共用的名稱，然後按一下 [**屬性**]。 按一下 [**規則**] 索引標籤。新增下列各列：

       `SkipBitLocker=YES``BDEInstall=TPM``BDEInstallSuppress=NO``BDEWaitForEncryption=YES`

       按一下 [確定] 以關閉視窗。

   5.  在 [任務順序] 節點底下，編輯 Windows 部署所用的現有任務序列。 如果您想要的話，您可以用滑鼠右鍵按一下 [**任務序列**] 節點，選取 [**新增任務序列**]，然後完成嚮導，以建立新的任務序列。

       在所選任務序列的 [**任務順序**] 索引標籤上，執行下列步驟：

       1.  如果您想在 WinPE 中啟用 BitLocker，且只加密已使用的空間，請在 [**預先安裝**] 資料夾底下啟用 [**啟用 bitlocker （離線）** ] 選項。

       2.  若要在使用預配時保留 TPM OwnerAuth，允許 MBAM 稍後進行保管，請執行下列動作：

           1.  尋找 [**安裝作業系統**] 步驟

           2.  在其後加入新的**執行命令列**步驟

           3.  為步驟**保留 TPM OwnerAuth**命名

           4.  將命令列設定為 [ `cscript.exe "%SCRIPTROOT%/SaveWinPETpmOwnerAuth.wsf"`
            **注意事項]：** 對於 windows 10 版本1607或更新版本，只有 WINDOWS 可以取得 TPM 擁有權。 在 addiiton 中，Windows 將不會在預配 TPM 時保留 TPM 擁有者密碼。 如需詳細資訊，請參閱[TPM 擁有者密碼](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password)。

       3.  在 [**狀態還原**] 資料夾中，刪除 [**啟用 BitLocker** ] 任務。

       4.  在 [**自訂**工作] 下的 [**狀態還原**] 資料夾中，建立新的**安裝應用程式**工作，並將其命名為**安裝 MBAM Agent**。 按一下 [**安裝單一應用程式**] 選項按鈕，然後流覽至先前建立的 MBAM 2.5 SP1 用戶端應用程式。

       5.  在 [**自訂**工作] 下的 [**狀態還原**] 資料夾中，建立新的**執行 POWERSHELL 腳本**工作（在 MBAM 2.5 SP1 用戶端應用程式步驟之後），並使用下列設定（根據您的環境更新參數）：

           -   Name （名稱）：針對 MBAM 設定 BitLocker

           -   PowerShell 腳本： `Invoke-MbamClientDeployment.ps1`

           -   參數

               <table>
               <colgroup>
               <col width="33%" />
               <col width="33%" />
               <col width="33%" />
               </colgroup>
               <tbody>
               <tr class="odd">
               <td align="left"><p>-RecoveryServiceEndpoint</p></td>
               <td align="left"><p>必要</p></td>
               <td align="left"><p>MBAM recovery 服務端點</p></td>
               </tr>
               <tr class="even">
               <td align="left"><p>-StatusReportingServiceEndpoint</p></td>
               <td align="left"><p>選用</p></td>
               <td align="left"><p>MBAM 狀態報表服務端點</p></td>
               </tr>
               <tr class="odd">
               <td align="left"><p>-EncryptionMethod</p></td>
               <td align="left"><p>選用</p></td>
               <td align="left"><p>加密方法（預設： AES 128）</p></td>
               </tr>
               <tr class="even">
               <td align="left"><p>-EncryptAndEscrowDataVolume</p></td>
               <td align="left"><p>切換</p></td>
               <td align="left"><p>指定加密資料量及保管資料量的資料量修復金鑰（s）</p></td>
               </tr>
               <tr class="odd">
               <td align="left"><p>-WaitForEncryptionToComplete</p></td>
               <td align="left"><p>切換</p></td>
               <td align="left"><p>指定等待加密完成</p></td>
               </tr>
               <tr class="even">
               <td align="left"><p>-DoNotResumeSuspendedEncryption</p></td>
               <td align="left"><p>切換</p></td>
               <td align="left"><p>指定部署腳本將不會繼續暫停加密</p></td>
               </tr>
               <tr class="odd">
               <td align="left"><p>-IgnoreEscrowOwnerAuthFailure</p></td>
               <td align="left"><p>切換</p></td>
               <td align="left"><p>指定以忽略 TPM 擁有者-驗證的保管失敗。 它應該用於 MBAM 無法讀取 TPM 擁有者驗證（例如，如果已啟用 TPM 自動預配）的情況。</p></td>
               </tr>
               <tr class="even">
               <td align="left"><p>-IgnoreEscrowRecoveryKeyFailure</p></td>
               <td align="left"><p>切換</p></td>
               <td align="left"><p>指定以忽略大量復原金鑰的保管失敗</p></td>
               </tr>
               <tr class="odd">
               <td align="left"><p>-IgnoreReportStatusFailure</p></td>
               <td align="left"><p>切換</p></td>
               <td align="left"><p>[指定以忽略狀態報表失敗]</p></td>
               </tr>
               </tbody>
               </table>

                 

**若要在 Windows 部署中使用 MBAM 2.5 或較舊版本啟用 BitLocker**

1.  安裝 MBAM 用戶端。 如需相關指示，請參閱[如何使用命令列部署 MBAM 用戶端](how-to-deploy-the-mbam-client-by-using-a-command-line.md)。

2.  將電腦加入網域（建議使用）。

    -   如果電腦未加入網域，則無法將恢復密碼儲存在 MBAM 金鑰復原服務中。 根據預設，除非能儲存復原金鑰，否則 MBAM 不允許進行加密。

    -   如果電腦在修復金鑰儲存在 MBAM 伺服器上之前以復原模式啟動，則不提供任何復原方法，且必須 reimaged 電腦。

3.  以系統管理員身分開啟命令提示字元，並停止 MBAM 服務。

4.  輸入下列命令，將服務設定為 [**手動**] 或 [按**需**]：

    **net stop mbamagent**

    **sc config mbamagent start = 要求**

5.  設定登錄值，讓 MBAM 用戶端忽略群組原則設定，而是設定加密，以啟動將 Windows 部署到該用戶端電腦的時間。

    **小心** 此步驟說明如何修改 Windows 註冊。 無法正確使用登錄編輯程式，可能會導致嚴重問題，可能需要您重新安裝 Windows。 我們無法保證因無法正確使用登錄編輯程式而造成的問題無法解決。 使用登錄編輯程式的風險由您自負。

    1.  設定**僅限作業系統加密**的 TPM、執行 Regedit.exe，然後從 C:\\program files Files\\Microsoft\\MDOP MBAM\\MBAMDeploymentKeyTemplate.reg. 匯入登錄機碼範本

    2.  在 Regedit.exe 中，移至 HKLM\\SOFTWARE\\Microsoft\\MBAM，並設定下表所列的設定。

        **記事** 您可以在這裡設定與 MBAM 相關的群組原則設定或登錄值。 這些設定會覆寫先前設定的值。

        登錄專案設定

        DeploymentTime

        0 = 關閉

        1 = 使用部署時間原則設定（預設）–在 Windows 部署到用戶端電腦時，請使用此設定來啟用加密。

        UseKeyRecoveryService

        0 = 不使用金鑰保管（這種情況下，不需要接下來的兩個登錄專案）

        1 = 在金鑰還原系統中使用金鑰委託（預設）

        這是建議的設定，可讓 MBAM 儲存修復金鑰。 電腦必須能夠與 MBAM 金鑰復原服務進行通訊。 繼續進行之前，請先確認電腦可以與服務進行通訊。

        KeyRecoveryOptions

        0 = 僅限上傳復原金鑰

        1 = 上傳復原金鑰和金鑰復原套件（預設）

        KeyRecoveryServiceEndPoint

        將此值設定為執行金鑰復原服務之伺服器的 URL，例如，HTTP://[ &lt; 電腦名稱稱] &gt; /MBAMRecoveryAndHardwareService/CoreService.svc。


6.  MBAM 用戶端將在 MBAM 用戶端部署期間重新開機系統。 當您準備好進行此重新開機時，請以系統管理員的命令提示字元執行下列命令：

    **net start mbamagent**

7.  當電腦重新開機且 BIOS 提示您時，請接受 TPM 變更。

8.  在 Windows 用戶端作業系統影像程式期間，當您準備好要開始加密時，請以系統管理員身分開啟命令提示字元，然後輸入下列命令，將 [開始] 設定為 [**自動**]，然後重新開機 MBAM 用戶端代理程式：

    **sc config mbamagent start = auto**

    **net start mbamagent**

9.  若要刪除旁路登錄值，請執行 Regedit.exe，然後移至 HKLM\\SOFTWARE\\Microsoft 登錄機碼目。 以滑鼠右鍵按一下 [ **MBAM** ] 節點，然後按一下 [**刪除**]。

## 相關主題

[部署 MBAM 2.5 用戶端](deploying-the-mbam-25-client.md)

[MBAM 2.5 用戶端部署規劃](planning-for-mbam-25-client-deployment.md)

## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。
