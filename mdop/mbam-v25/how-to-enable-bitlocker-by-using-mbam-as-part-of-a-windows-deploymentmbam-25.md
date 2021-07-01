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
ms.openlocfilehash: cd4086ca6bb2ea8d253ea3b743f4efe7efbbb6c1
ms.sourcegitcommit: 325c4b77f9a9df0f3de268457fed06184623bb94
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2021
ms.locfileid: "11626180"
---
# <a name="how-to-enable-bitlocker-by-using-mbam-as-part-of-a-windows-deployment"></a>如何使用 MBAM 做為 Windows 部署的一部分來啟用 BitLocker

> [!IMPORTANT]
> 這些指示與 Configuration Manager BitLocker 管理並不相關。 `Invoke-MbamClientDeployment.ps1`PowerShell 腳本不支援在 Configuration Manager 中與 BitLocker Management 一起使用。 這包括在 Configuration Manager 工作順序期間代管 BitLocker 修復金鑰。 此外，從 Configuration Manager Current Branch 2103 開始，Configuration Manager BitLocker Management 就不會再使用<a0></a0>的 <<a1></a1><a2>：</a2><a3></a3><a4></a4><a5>：</a5> <a6> </a6> <a7> </a7> 嘗試在 Configuration Manager Current Branch 2103 或更新版本使用 PowerShell 腳本可能會導致 `Invoke-MbamClientDeployment.ps1` Configuration Manager 網站發生嚴重問題。 已知問題包括建立大量針對所有裝置的策略，可能會導致策略暴風。 這會在 Configuration Manager 中導致主要在管理點SQL的績效嚴重降低。

本主題說明如何在使用者電腦上啟用 BitLocker，在影像和部署過程中，使用 WINDOWS的一部分。 如果您在安裝階段結束) 之後重新開機 (時看到黑色螢幕，表示無法解除鎖定硬碟，請參閱先前 Windows 版本在 「設定 Windows 和 Configuration Manager」步驟之後，如果預布布位 BitLocker 已與 Windows 10 版本[1511](https://support.microsoft.com/en-us/help/4494799/earlier-windows-versions-don-t-start-after-you-use-pre-provision-bitlo)一起使用，請參閱先前 Windows 版本不會啟動。

**必要條件：**

-   必須Windows現有的映射部署程式 ：Microsoft 部署工具組 (MDT) 、Microsoft System Center Configuration Manager 或其他影像工具或程式

-   TPM 必須在BIOS 中啟用，且對作業系統可見

-   必須就地且易於訪問的 IBMM 伺服器基礎結構

-   必須建立 BitLocker 所需的系統磁碟分割

-   電腦在映射處理期間必須先加入網域，然後才完全啟用 BITLocker

**若要在部署中啟用 BITLocker，在部署時使用 WINDOWS 2.5 SP1**

1. 在 2.5 SP1 中，建議在部署期間啟用 BitLocker Windows使用 `Invoke-MbamClientDeployment.ps1` PowerShell 腳本。

   -   腳本 `Invoke-MbamClientDeployment.ps1` 在映射程式期間會啟動 BitLocker。 當 BitLocker 策略有需要時，當網域使用者第一次在映射後登錄時，該網域使用者會立即提示網域使用者建立 PIN 或密碼。

   -   輕鬆與 MDT、System Center Configuration Manager或獨立影像程式一起使用

   -   與 PowerShell 2.0 或更高版本相容

   -   使用 TPM 金鑰保護裝置加密作業系統音量

   -   完全支援 BitLocker 預置備

   -   選擇性加密 FDD

   -   針對第 7 Windows代管 TPM 擁有者驗證，PMM 必須擁有 TPM 以代管。
   對於 Windows 8.1，Windows 10 RTM Windows 10版本 1511，支援代管 TPM OwnerAuth。
   對於 Windows 10版本 1607 或更新版本，Windows才能取得 TPM 的擁有權。 在 addiiton 中Windows在配置 TPM 時，不會保留 TPM 擁有者密碼。 請參閱 [TPM 擁有者密碼以](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password) 進一步詳細資料。

   -   代管修復金鑰及修復金鑰套件

   -   立即報告加密狀態

   -   新的 WMI 提供者

   -   詳細記錄

   -   強大的錯誤處理

   您可以從下載中心 `Invoke-MbamClientDeployment.ps1` 下載 [Microsoft.com 腳本](https://www.microsoft.com/download/details.aspx?id=54439)。 這是部署系統會撥打的主要腳本，以設定 BitLocker 磁片磁碟機加密，以及使用 IBMM Server 記錄復原金鑰。

   **適用于 MMI 的 WMI 部署方法：** 下列 WMI 方法已新增到 ：在 2.5 SP1 中，以支援使用 PowerShell 腳本啟用 `Invoke-MbamClientDeployment.ps1` BitLocker。

   <a href="" id="mbam-machine-wmi-class"></a>**在 WMI 課程_MACHINE管理課程** 
   **PrepareTpmAndEscrowOwnerAuth：** 讀取 TPM OwnerAuth，然後使用 PMM 修復服務將其傳送至 PMM 修復資料庫。 如果 TPM 未擁有，且未啟動自動置備，則會產生 TPM OwnerAuth 並取得擁有權。 如果失敗，會返回錯誤碼以進行疑難排解。

   **附注**對於 Windows 10版本 1607 或更新版本，Windows才能取得 TPM 的擁有權。 在 addiiton 中Windows在配置 TPM 時，不會保留 TPM 擁有者密碼。 請參閱 [TPM 擁有者密碼以](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password) 進一步詳細資料。

| 參數 | 描述 |
| -------- | ----------- |
| RecoveryServiceEndPoint | 指定 ：指定此為 ：：一個字串，用於指定一個服務端點。 |

以下是常見錯誤訊息的清單：

| 常見的退貨值 | 錯誤訊息 |
| -------------------- | ------------- |
|  **S_OK**<br />0 (0x0)  | 方法已成功。 |
| **MBAM_E_TPM_NOT_PRESENT**<br />2147746304 (0x80040200)  | TPM 不在電腦中，或是在BIOS 組組中停用。 |
| **MBAM_E_TPM_INCORRECT_STATE**<br />2147746305 (0x80040201)  | TPM 在啟用、啟用 (且允許擁有者安裝時) 。 |
| **MBAM_E_TPM_AUTO_PROVISIONING_PENDING**<br />2147746306 (0x80040202)  | 由於自動置備擱置中，因此，PMM 無法取得 TPM 的擁有權。 完成自動置備之後，請再試一次。 |
| **MBAM_E_TPM_OWNERAUTH_READFAIL**<br />2147746307 (0x80040203)  | PMM 無法讀取 TPM 擁有者授權值。 成功代管之後，值可能已經移除。 在 Windows 7，如果 TPM 為其他人所擁有，則 PMM 無法讀取值。 |
| **MBAM_E_REBOOT_REQUIRED**<br />2147746308 (0x80040204)  | 電腦必須重新開機，才能將 TPM 設定為正確的狀態。 您可能需要手動重新開機電腦。 |
| **MBAM_E_SHUTDOWN_REQUIRED**<br />2147746309 (0x80040205)  | 電腦必須關閉並重新開啟，以將 TPM 設定為正確的狀態。 您可能需要手動重新開機電腦。 |
| **WS_E_ENDPOINT_ACCESS_DENIED**<br />2151481349 (0x803D0005)  | 遠端端點拒絕存取。 |
| **WS_E_ENDPOINT_NOT_FOUND**<br />2151481357 (0x803D000D)  | 遠端端點不存在或無法定位。 |
| **WS_E_ENDPOINT_FAILURE<br />2151481357 (0x803D000F)  | 遠端端點無法處理要求。 |
| **WS_E_ENDPOINT_UNREACHABLE**<br />2151481360 (0x803D0010)  | 無法到達遠端端點。 |
| **WS_E_ENDPOINT_FAULT_RECEIVED**<br />2151481363 (0x803D0013)  | 從遠端端點收到包含錯誤的訊息。 請確定您連接到正確的服務端點。 |
| **WS_E_INVALID_ENDPOINT_URL** 2151481376 (0x803D0020)  | 端點位址 URL 無效。 URL 必須以 "HTTP" 或 "HTTPs" 開始。 |

   **ReportStatus：** 讀取該卷的合規性狀態，然後使用 SQLM 狀態報表服務將其傳送至 狀態包括密碼強度、保護程式類型、保護程式狀態和加密狀態。 如果失敗，會返回錯誤碼以進行疑難排解。

   | 參數 | 描述 |
   | --------- | ----------- |
   | ReportingServiceEndPoint | 指定 ：指定一個字串，指定一個資料包報服務端點。 |

   以下是常見錯誤訊息的清單：

   | 常見的退貨值 | 錯誤訊息 |
   | -------------------- | ------------- |
   | **S_OK**<br /> 0 (0x0)  | 方法成功 |
   | **WS_E_ENDPOINT_ACCESS_DENIED**<br />2151481349 (0x803D0005)  | 遠端端點拒絕存取。|
   | **WS_E_ENDPOINT_NOT_FOUND**<br />2151481357 (0x803D000D)  | 遠端端點不存在或無法找到。 |
   | **WS_E_ENDPOINT_FAILURE**<br /> 2151481357 (0x803D000F)  | 遠端端點無法處理要求。 |
   | **WS_E_ENDPOINT_UNREACHABLE**<br />2151481360 (0x803D0010)  | 無法到達遠端端點。 |
   | **WS_E_ENDPOINT_FAULT_RECEIVED**<br />2151481363 (0x803D0013)  | 從遠端端點收到包含錯誤的訊息。 請確定您連接到正確的服務端點。 |
   | **WS_E_INVALID_ENDPOINT_URL**<br />2151481376 (0x803D0020)  | 端點位址 URL 無效。 URL 必須以 "HTTP" 或 "HTTPs" 開始。 |

   <a href="" id="mbam-volume-wmi-class"></a>**MBAM\_Volume WMI Class** **EscrowRecoveryKey:** Reads the recovery numerical password and key package of the volume and sends them to the MBAM recovery database by using the MBAM recovery service. 如果失敗，會返回錯誤碼以進行疑難排解。

   | 參數 | 描述 |
   | --------- | ----------- |
   | RecoveryServiceEndPoint | 指定 ：指定此為 ：：一個字串，用於指定一個服務端點。 |

   以下是常見錯誤訊息的清單：

   | 常見的退貨值 | 錯誤訊息 |
   | -------------------- | ------------- |
   | **S_OK**<br />0 (0x0)  | 方法成功 |
   | **FVE_E_LOCKED_VOLUME**<br />2150694912 (0x80310000)  | 音量已鎖定。 |
   | **FVE_E_PROTECTOR_NOT_FOUND**<br />2150694963 (0x80310033)  | 找不到音量的數值密碼保護程式。 |
   | **WS_E_ENDPOINT_ACCESS_DENIED**<br />2151481349 (0x803D0005)  | 遠端端點拒絕存取。 |
   | **WS_E_ENDPOINT_NOT_FOUND**<br />2151481357 (0x803D000D)  | 遠端端點不存在或無法找到。 |
   | **WS_E_ENDPOINT_FAILURE**<br />2151481357 (0x803D000F)  | 遠端端點無法處理要求。 |
   | **WS_E_ENDPOINT_UNREACHABLE**<br />2151481360 (0x803D0010)  | 無法到達遠端端點。 |
   | **WS_E_ENDPOINT_FAULT_RECEIVED**<br />2151481363 (0x803D0013)  | 從遠端端點收到包含錯誤的訊息。 請確定您連接到正確的服務端點。 |
   | **WS_E_INVALID_ENDPOINT_URL**<br />2151481376 (0x803D0020)  | 端點位址 URL 無效。 URL 必須以 "HTTP" 或 "HTTPs" 開始。 |
     

2. **使用 Microsoft 部署工具組和 PowerShell (MDT) 部署 MDM**

   1.  在 MDT 中，建立新的部署共用或開啟現有的部署共用。

       **注意**  
       `Invoke-MbamClientDeployment.ps1`PowerShell 腳本可用於任何影像程式或工具。 本節將說明如何使用 MDT 進行整合，但步驟與將其與其他程式或工具整合類似。

       **謹慎**  
       如果您使用的是 BitLocker 預配置 (WinPE) ，並想要維持 TPM 擁有者的授權值，您必須在 WinPE 中新增腳本，安裝重新開機至完整作業系統之前。 `SaveWinPETpmOwnerAuth.wsf` **如果您沒有使用此腳本，重新開機時就會失去 TPM 擁有者的授權值。**

   2.  複製到 `Invoke-MbamClientDeployment.ps1` ** &lt; DeploymentShare &gt; \\Scripts**。 如果您使用的是預部署，請複製檔案 `SaveWinPETpmOwnerAuth.wsf` 至** &lt; DeploymentShare &gt; \\Scripts**。

   3.  在部署共用中的應用程式節點中新增一個 ：將<a0>2.5 SP1 SP1 用戶端應用程式新增到應用程式節點 。</a1>

       1.  在 [ **應用程式節點」** 下，按一下 **[新增應用程式**> 。

       2.  選取 **具有來源檔案的應用程式**。 按 **\[下一步\]**。

       3.  在 **應用程式名稱中**，輸入「INM 2.5 SP1 用戶端」。 按 **\[下一步\]**。

       4.  流覽至包含 `MBAMClientSetup-<Version>.msi` 的目錄。 按 **\[下一步\]**。

       5.  輸入要建立之目錄的 「：「2.5 SP1 用戶端」。 按 **\[下一步\]**。

       6.  在 `msiexec /i MBAMClientSetup-<Version>.msi /quiet` 命令列輸入。 按 **\[下一步\]**。

       7.  接受其餘的預設值以完成新應用程式精靈。

   4.  在 MDT 中，以滑鼠右鍵按一下部署共用的名稱，然後按一下 [ **屬性**> 。 按一下 [ **規則>** 選項卡。新增下列行：

       `SkipBitLocker=YES``BDEInstall=TPM``BDEInstallSuppress=NO``BDEWaitForEncryption=YES`

       按一下 [確定> 以關閉視窗。

   5.  在任務順序節點下，編輯用於部署Windows順序。 您可以按一下滑鼠右鍵按一下任務順序節點、選取新的工作順序，然後**** 完成精靈，以建立**** 新工作順序。

       在所選 **工作順序** 的工作列上，執行下列步驟：

       1.  如果您希望在**** WinPE 中啟用**BitLocker，** 請啟用選擇性工作 ：啟用 BitLocker (離線) ，因為 WinPE 只會加密已使用的空間。

       2.  若要在使用預布建時保留 TPM OwnerAuth，允許稍後由 PMM 代管，請執行下列操作：

           1.  尋找 **安裝作業系統** 步驟

           2.  在之後 **新增執行命令列** 步驟

           3.  命名持續 **TPM 擁有者驗證的步驟**

           4.  將命令列設定為附注：Windows 10版本 1607 或更新版本，Windows才能取得 `cscript.exe "%SCRIPTROOT%/SaveWinPETpmOwnerAuth.wsf"`
            ** **TPM 的擁有權。 在 addiiton 中Windows在配置 TPM 時，不會保留 TPM 擁有者密碼。 請參閱 [TPM 擁有者密碼以](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password) 進一步詳細資料。

       3.  在狀態 **還原資料夾中** ，刪除啟用 **BitLocker** 工作。

       4.  In the **State Restore** folder under **Custom Tasks**, create a new **Install Application** task and name it **Install MBAM Agent**. 按一下 [ **安裝單一應用程式單** 一應用程式選項按鈕並流覽至先前所建立之的 [2.5 SP1 SP1 用戶端應用程式>。

       5.  在自訂**** 工作下的狀態還原**** 資料夾中，在使用下列設定)  (之後，使用下列設定 (建立新的執行**PowerShell 腳本**工作 (，並針對您的環境更新參數) ：

           -   名稱：設定 BITLocker for

           -   PowerShell 腳本： `Invoke-MbamClientDeployment.ps1`

           -   參數：

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
               <td align="left"><p>管理與修復服務端點</p></td>
               </tr>
               <tr class="even">
               <td align="left"><p>-StatusReportingServiceEndpoint</p></td>
               <td align="left"><p>選用</p></td>
               <td align="left"><p>資料包報服務端點的</p></td>
               </tr>
               <tr class="odd">
               <td align="left"><p>-EncryptionMethod</p></td>
               <td align="left"><p>選用</p></td>
               <td align="left"><p>預設加密 (：AES 128) </p></td>
               </tr>
               <tr class="even">
               <td align="left"><p>-EncryptAndEscrowDataVolume</p></td>
               <td align="left"><p>切換</p></td>
               <td align="left"><p>指定加密資料量 () 並代管資料量復原金鑰 () </p></td>
               </tr>
               <tr class="odd">
               <td align="left"><p>-WaitForEncryptionToComplete</p></td>
               <td align="left"><p>切換</p></td>
               <td align="left"><p>指定以等待加密完成</p></td>
               </tr>
               <tr class="even">
               <td align="left"><p>-DoNotResumeSuspendedEncryption</p></td>
               <td align="left"><p>切換</p></td>
               <td align="left"><p>指定部署腳本不會繼續暫停加密</p></td>
               </tr>
               <tr class="odd">
               <td align="left"><p>-IgnoreEscrowOwnerAuthFailure</p></td>
               <td align="left"><p>切換</p></td>
               <td align="left"><p>指定以忽略 TPM 擁有者-驗證代管失敗。 它應用於無法讀取 TPM 擁有者驗證的情況，例如已啟用 TPM 自動布建</p></td>
               </tr>
               <tr class="even">
               <td align="left"><p>-IgnoreEscrowRecoveryKeyFailure</p></td>
               <td align="left"><p>切換</p></td>
               <td align="left"><p>指定以忽略大量修復金鑰代管失敗</p></td>
               </tr>
               <tr class="odd">
               <td align="left"><p>-IgnoreReportStatusFailure</p></td>
               <td align="left"><p>切換</p></td>
               <td align="left"><p>指定以忽略狀態報表失敗</p></td>
               </tr>
               </tbody>
               </table>

                 

**若要在部署中啟用 BITLocker，在部署時使用 WINDOWS 2.5 或更Windows程式**

1.  安裝 <管理及管理用戶端。. 有關指示，請參閱[如何使用命令列來部署的。](how-to-deploy-the-mbam-client-by-using-a-command-line.md)

2.  將電腦加入網域， (建議) 。

    -   如果電腦未加入網域，則修復密碼不會儲存于 INM 金鑰修復服務中。 根據預設，除非可以儲存修復金鑰，否則，如果無法加密，則不會允許進行加密。

    -   如果電腦在將修復金鑰儲存于 IBMM Server 之前，會以復原模式啟動，則沒有可用的復原方法，而且必須重新想像電腦。

3.  以系統管理員的名符開啟命令提示，並停止該服務。

4.  輸入下列命令，**** 將服務**設定為**手動或隨用：

    **net stop 的**

    **sc config 的啟動= demand**

5.  設定註冊表值，讓 B0 電腦管理中心用戶端忽略群組原則設定，而是設定加密Windows部署至該用戶端電腦的時間。

    **謹慎**  
    此步驟說明如何修改Windows註冊表。 不正確地使用登錄編輯器可能會導致嚴重問題，而這些問題可能會要求您重新安裝Windows。 我們無法保證因不正確使用登錄編輯器而產生的問題可以解決。 請自行承擔使用登錄編輯程式的風險。

    1.  設定僅適用于作業系統的**** TPM 加密、執行 Regedit.exe，然後從 C：\\Program Files\\Microsoft\\MDOP MDM\\MDMDeploymentKeyTemplate.reg 導入註冊表金鑰範本。

    2.  在 Regedit.exe，請前往 HKLM\\SOFTWARE\\Microsoft\\\TM，並設定下表所列的設定。

        **注意**  
        您可以在這裡設定與 B0 電腦管理中心相關的群組原則設定或註冊表值。 這些設定會取代先前設定的值。

        登錄機碼目 設定設定

        DeploymentTime

        0 = 關閉

        1 = 使用部署時間 (設定) 預設設定 - 使用此設定在將 Windows部署到用戶端電腦時啟用加密。

        UseKeyRecoveryService

        0 = 請勿使用金鑰代管 (在此案例中，系統不需要接下來的兩個登錄機碼目) 

        1 = 在金鑰修復系統使用金鑰代管 (預設) 

        這是建議設定，可讓的 電腦必須能與管理管理中心金鑰修復服務通訊。 請確認電腦可以與服務通訊，然後再繼續進行。

        KeyRecoveryOptions

        0 = 僅上傳修復金鑰

        1 = 上傳修復金鑰和金鑰修復套件 (預設) 

        KeyRecoveryServiceEndPoint

        將此值設定為執行 Key Recovery 服務之伺服器的 URL，例如，HTTP:// &lt; 電腦名稱稱 &gt; /IBMMRecoveryAndWarewareService/CoreService.svc。


6.  在部署時，即會重新開機系統。 當您準備好重新開機時，請以系統管理員的指令提示執行下列命令：

    **net start 的**

7.  當電腦重新開機，而BIOS 提示您時，請接受 TPM 變更。

8.  在 Windows作業系統映射程式期間，當您準備好要開始加密時，請以系統管理員的方程式開啟命令提示，然後輸入下列命令，將開始設定為自動，並重新啟動**** 的 MRM 用戶端代理程式：

    **sc config 的啟動= auto**

    **net start 的**

9.  若要刪除忽略的註冊表值，請執行 Regedit.exe，然後前往 HKLM\\SOFTWARE\\Microsoft 登錄機碼目。 以滑鼠右鍵按一下 **[管理及** 管理及管理管理及管理管理> 節點，然後按一下 **[刪除**。

## <a name="related-topics"></a>相關主題

[部署 MBAM 2.5 用戶端](deploying-the-mbam-25-client.md)

[MBAM 2.5 用戶端部署規劃](planning-for-mbam-25-client-deployment.md)

## <a name="got-a-suggestion-for-mbam"></a>有關于 MM 的建議嗎？
- 在這裡新增或投票支援 [建議](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)。
- 針對的為 ：針對[的為 ：使用 ：：使用 ：。](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)
