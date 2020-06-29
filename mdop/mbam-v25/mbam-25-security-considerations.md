---
title: MBAM 2.5 安全性考量
description: MBAM 2.5 安全性考量
author: dansimp
ms.assetid: f6613c63-b32b-45fb-a6e8-673d6dae7d16
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 04/23/2017
ms.openlocfilehash: 86a756ab6f983fa1f22de6835b5993e1215d1dbe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811996"
---
# MBAM 2.5 安全性考量


本主題包含有關如何保護 Microsoft BitLocker 管理與監視（MBAM）的下列相關資訊：

-   [設定 MBAM 以保管 TPM 並儲存 OwnerAuth 密碼](#bkmk-tpm)

-   [設定 MBAM 在封鎖之後自動解除鎖定 TPM](#bkmk-autounlock)

-   [安全連線至 SQL Server](#bkmk-secure-databases)

-   [建立帳戶和群組](#bkmk-accts-groups)

-   [使用 MBAM 記錄檔](#bkmk-logfiles)

-   [審閱 MBAM 資料庫 TDE 考慮](#bkmk-tde)

-   [瞭解一般的安全性考慮](#bkmk-general-security)

## <a href="" id="bkmk-tpm"></a>設定 MBAM 以保管 TPM 並儲存 OwnerAuth 密碼

**記事**如果您使用的是 Windows 10 版本1607或更新版本，則只有 Windows 可以取得 TPM 擁有權。 此外，Windows 不會在預配 TPM 時保留 TPM 擁有者密碼。 如需詳細資訊，請參閱[TPM 擁有者密碼](https://docs.microsoft.com/windows/security/information-protection/tpm/change-the-tpm-owner-password)。

根據它的設定而定，受信任的平臺模組（TPM）會在某些情況下（例如當輸入了太多不正確的密碼），並在一段時間內保持鎖定。 在 TPM 封鎖期間，BitLocker 無法存取加密金鑰來執行解除鎖定或解密作業，要求使用者輸入其 BitLocker 復原金鑰來存取作業系統磁片磁碟機。 若要重設 TPM 封鎖，您必須提供 TPM OwnerAuth 密碼。

如果 MBAM 擁有 TPM，或如果它 escrows 密碼，則可以將 TPM OwnerAuth 密碼儲存在 MBAM 資料庫中。 當您必須從 TPM 封鎖中復原時，可以在 [管理] 和 [監視] 網站上輕鬆存取 OwnerAuth 密碼，不需要等到鎖定自行自行解決。

### Escrowing 在 Windows 8 及更高版本中的 TPM OwnerAuth

**記事**如果您使用的是 Windows 10 版本1607或更新版本，則只有 Windows 可以取得 TPM 擁有權。 在 addiiton 中，Windows 將不會在預配 TPM 時保留 TPM 擁有者密碼。 如需詳細資訊，請參閱[TPM 擁有者密碼](https://docs.microsoft.com/windows/security/information-protection/tpm/change-the-tpm-owner-password)。

在 Windows 8 或更高版本中，MBAM 不必須擁有 TPM，就能儲存 OwnerAuth 密碼（只要本機電腦上提供 OwnerAuth 即可）。

若要讓 MBAM 能夠進行保管，然後儲存 TPM OwnerAuth 密碼，您必須設定這些群組原則設定。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">群組原則設定</th>
<th align="left">設定</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>開啟 TPM 備份至 Active Directory 網域服務</p></td>
<td align="left"><p>停用或未設定</p></td>
</tr>
<tr class="even">
<td align="left"><p>設定作業系統可用的 TPM 擁有者授權資訊層級</p></td>
<td align="left"><p>已委派/無或未設定</p></td>
</tr>
</tbody>
</table>

 

這些群組原則設定的位置是 [**電腦**設定] &gt; 系統**管理範本** &gt; **系統** &gt; **受信任的平臺模組服務**。

**記事** 在 MBAM 成功 escrows 使用這些設定之後，Windows 會移除在本機的 OwnerAuth。

 

### 在 Windows 7 中 Escrowing TPM OwnerAuth

在 Windows 7 中，MBAM 必須擁有 TPM，才能在 MBAM 資料庫中自動委託 TPM OwnerAuth 資訊。 如果 MBAM 不擁有 TPM，您必須使用 MBAM Active Directory （AD）資料匯入 Cmdlet，將 TPM OwnerAuth 從 Active Directory 複製到 MBAM 資料庫。

### MBAM Active Directory 資料匯入 Cmdlet

MBAM Active Directory 資料匯入 Cmdlet 可讓您檢索儲存在 Active Directory 中的復原金鑰套件和 OwnerAuth 密碼。

MBAM 2.5 SP1 伺服器隨附四個 PowerShell Cmdlet，這些 Cmdlet 會使用儲存在 Active Directory 中的大量復原及 TPM 擁有者資訊預先填入 MBAM 資料庫。

針對批量復原金鑰和套件：

-   讀取 ADRecoveryInformation

-   寫入 MbamRecoveryInformation

針對 TPM 擁有者資訊：

-   讀取 ADTpmInformation

-   寫入 MbamTpmInformation

若要將使用者與電腦建立關聯：

-   寫入 MbamComputerUser

Read AD \ * Cmdlet 會讀取 Active Directory 中的資訊。 Write Mbam \ * Cmdlet 會將資料推入 MBAM 資料庫。 如需這些 Cmdlet 的詳細資訊（包括語法、參數及範例），請參閱[Microsoft Bitlocker 管理和監視2.5 的 Cmdlet 參考](https://technet.microsoft.com/library/dn459018.aspx)。

**建立使用者對電腦的關聯：** MBAM Active Directory 資料匯入 Cmdlet 會收集 Active Directory 中的資訊，並將資料插入 MBAM 資料庫中。 不過，它們不會將使用者與卷建立關聯。 您可以下載 Add-ComputerUser.ps1 PowerShell 腳本來建立使用者對電腦的關聯，這可讓使用者透過管理和監控網站或使用自助入口網站進行復原來重新取得電腦的存取權。 Add-ComputerUser.ps1 腳本會從 Active Directory （AD）、AD 中的物件擁有者，或從自訂的 CSV 檔案，收集**由受管理的 By**屬性所管理的資料。 然後，腳本會將已發現的使用者新增到復原資訊管道物件，必須傳遞到寫 MbamRecoveryInformation，才能將資料插入到損毀修復資料庫中。

從[Microsoft 下載中心](https://go.microsoft.com/fwlink/?LinkId=613122)下載 Add-ComputerUser.ps1 PowerShell 腳本。

您可以指定 [說明] **Add-ComputerUser.ps1**以取得腳本的說明，包括如何使用 Cmdlet 與腳本的範例。

若要在安裝 MBAM 伺服器之後建立使用者對電腦的關聯，請使用 MbamComputerUser PowerShell Cmdlet。 與 Add-ComputerUser.ps1 PowerShell 腳本類似，此 Cmdlet 可讓您指定可使用自助入口網站來取得特定電腦的 TPM OwnerAuth 資訊或大量復原密碼的使用者。

**記事** 當該電腦開始向伺服器進行報告時，MBAM 代理程式將會覆寫使用者對電腦的關聯。

 

**先決條件：** 只有當您以高許可權的使用者帳戶（例如網域系統管理員）執行，或以帳戶在已獲授權讀取資訊存取權的自訂安全性群組中時，Read AD \ * Cmdlet 才能從 AD 中檢索資訊（建議使用）。

[BitLocker 磁片磁碟機加密操作指南：使用 AD DS 復原加密的磁片](https://technet.microsoft.com/library/cc771778(WS.10).aspx)，提供建立自訂安全性群組（或多個群組）的詳細資料，並提供廣告資訊的讀取存取權。

**MBAM 復原與硬體 Web 服務寫入權限：** Mbam \ * Cmdlet 會接受 MBAM 復原與硬體服務的 URL，用來發佈復原或 TPM 資訊。 通常只有網域電腦服務帳戶可以與 MBAM 復原與硬體服務進行通訊。 在 MBAM 2.5 SP1 中，您可以使用名為 DataMigrationAccessGroup 的安全性群組來設定 MBAM 復原與硬體服務，其成員可以略過網域電腦服務帳戶檢查。 Write Mbam \ * Cmdlet 必須以屬於此設定群組的使用者身分執行。 （或者，您可以使用 Mbam \ * Cmdlet 中的– Credential 參數，指定已設定群組中個別使用者的認證。）

您可以使用下列其中一種方式，將 MBAM 復原與硬體服務設定為此安全群組的名稱：

-   在 Enable-MbamWebApplication – AgentService Powershell Cmdlet 的-DataMigrationAccessGroup 參數中，提供安全性群組（或個別）的名稱。

-   在 &lt; inetpub &gt; \\Microsoft Bitlocker 管理 Solution\\Recovery 和硬體 Service\\ 資料夾中編輯 web.config 檔案，以設定 MBAM 復原和硬體服務安裝之後的群組。

    ```xml
    <add key="DataMigrationUsersGroupName" value="<groupName>|<empty>" />
    ```

    在 &lt; 其中 &gt; 使用的網域和群組名稱（或個別使用者）取代將其設為允許從 Active Directory 進行資料移轉的位置。

-   使用 IIS 管理器中的 [設定編輯器] 來編輯此 appSetting。

在下列範例中，當您以 ADRecoveryInformation 群組和 [資料移轉使用者] 群組的成員身分執行時，會從 contoso.com 網域中的工作站組織單位（OU）中的電腦提取大量復原資訊，並使用在 mbam.contoso.com 伺服器上執行的 MBAM 復原與硬體服務，將它們寫入 MBAM 中。

``` syntax
PS C:\> Read-ADRecoveryInformation -Server contoso.com -SearchBase "OU=WORKSTATIONS,DC=CONTOSO,DC=COM" | Write-MbamRecoveryInformation -RecoveryServiceEndPoint "https://mbam.contoso.com/MBAMRecoveryAndHardwareService/CoreService.svc"
```

[已**讀-AD \ * Cmdlet** ] 接受託管伺服器電腦的 Active Directory 名稱或 IP 位址，以查詢復原或 TPM 資訊。 我們建議您提供將電腦物件作為 SearchBase 參數值駐留的廣告容器的可分辨名稱。 如果電腦儲存在多個 Ou 中，則 Cmdlet 可以接受每個容器執行一次的管線輸入。 AD 容器的辨識名稱看起來會像 OU = 機器、DC = contoso、DC = com。 針對特定容器執行搜尋會提供下列好處：

-   減少查詢大型 AD 資料集的電腦物件時，超時風險。

-   可以省略包含資料中心伺服器或其他可能不需要備份之電腦類別的 Ou。

另一個選項是提供包含或不使用選擇性 SearchBase 的 [遞迴] 旗標，在指定 SearchBase 或整個網域下的所有容器中分別搜尋電腦物件。 當您使用遞迴式旗標時，您也可以使用-MaxPageSize 參數來控制服務查詢所需的本機和遠端記憶體量。

這些 Cmdlet 會寫入類型 PsObject 的管道物件。 每個 PsObject 實例都包含單一的批量復原金鑰或 TPM 擁有者字串，並將其與電腦名稱稱、時間戳記及其他資訊發佈至 MBAM 資料存放區所需。

**寫入 Mbam \ * Cmdlet**會依屬性名稱從管線接受復原資訊參數值。 這可讓 Write Mbam \ * Cmdlet 接受 Read AD \ * Cmdlet 的管線輸出（例如，讀取-ADRecoveryInformation –伺服器 contoso.com-遞迴 |MbamRecoveryInformation – RecoveryServiceEndpoint mbam.contoso.com）。

**Write Mbam \ * Cmdlet**包含可提供容錯、詳細記錄及 WhatIf 和確認選項的選用參數。

**Write Mbam \ * Cmdlet**也會包含值為**DateTime**物件的可選*時間*參數。 此物件包含可設定為、或的*Kind*屬性 `Local` `UTC` `Unspecified` 。 從 Active Directory 取得的資料填入*時間*參數時，時間會轉換為 UTC，且會自動將此*Kind*屬性設定為 `UTC` 。 不過，使用其他來源（例如文字檔）來填充*Time*參數時，您必須明確地將*Kind*屬性設定為適當的值。

**記事** Read AD \ * Cmdlet 不能探索代表電腦使用者的使用者帳戶。 下列情況需要使用者帳戶關聯：

-   使用自助入口網站來復原大量密碼/套件的使用者

-   在安裝期間未在 MBAM 高級支援人員使用者安全性群組中定義的使用者，代表其他使用者復原

 

## <a href="" id="bkmk-autounlock"></a>設定 MBAM 在封鎖之後自動解除鎖定 TPM


您可以設定 MBAM 2.5 SP1，在鎖定時自動解除鎖定 TPM。 如果啟用 TPM 封鎖自動重設，MBAM 會偵測到使用者已被封鎖，然後從 MBAM 資料庫取得 OwnerAuth 密碼，以便自動解除鎖定使用者的 TPM。 只有當您使用自助服務入口網站或 [管理及監視] 網站來檢索該電腦的作業系統復原金鑰時，才能使用 TPM 封鎖自動重設。

**重要** 若要啟用 TPM 封鎖自動重設，您必須在伺服器端和用戶端的 [群群組原則] 中設定此功能。

 

-   若要在用戶端啟用 TPM 封鎖自動重設，請設定位於 [電腦設定] 中的 [設定 TPM 封鎖自動重設] 群組原則設定**系統** &gt; **管理範本** &gt; **Windows 元件** &gt; **MDOP MBAM** &gt; **用戶端管理**。

-   若要在伺服器端啟用 TPM 封鎖自動重設，您可以在安裝期間的 MBAM 伺服器設定向導中，選取 [啟用 TPM 封鎖自動重設]。

    您也可以在啟用代理服務網頁元件時，指定「-TPM 封鎖自動重設」開關，在 PowerShell 中啟用 TPM 封鎖自動重設。

使用者從自助服務入口網站或 [管理及監視] 網站輸入所取得的 BitLocker 復原金鑰之後，MBAM 代理程式會判斷 TPM 是否已鎖定。如果已鎖定，則會嘗試從 MBAM 資料庫檢索電腦的 TPM OwnerAuth。 如果 TPM OwnerAuth 已成功檢索，就會用來解除鎖定 TPM。 解鎖 TPM 會使 TPM 完全正常運作，且不會強制使用者在後續從 TPM 封鎖重新開機期間輸入恢復密碼。

預設會停用 TPM 封鎖自動重設。

**記事** 只有運行 TPM 版本1.2 的電腦才支援 TPM 封鎖自動重設。 TPM 2.0 提供內建的封鎖自動重設功能。

 

復原**審核報告**包含與 TPM 封鎖自動重設相關的事件。 如果從 MBAM 用戶端發出要求來檢索 TPM OwnerAuth 密碼，則會記錄事件以指示覆原。 審核專案會包含下列事件：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">級</th>
<th align="left">值</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>審核要求來源</p></td>
<td align="left"><p>代理 TPM 解除鎖定</p></td>
</tr>
<tr class="even">
<td align="left"><p>金鑰類型</p></td>
<td align="left"><p>TPM 密碼雜湊</p></td>
</tr>
<tr class="odd">
<td align="left"><p>原因描述</p></td>
<td align="left"><p>TPM 重設</p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-secure-databases"></a>安全連線至 SQL Server


在 MBAM 中，SQL Server 會與 SQL Server Reporting Services 以及管理和監控網站及自助服務入口網站的 web 服務進行通訊。 我們建議您保護與 SQL Server 的通訊。 如需詳細資訊，請參閱[加密連線至 SQL Server](https://technet.microsoft.com/library/ms189067.aspx)。

如需加強 MBAM 網站安全的詳細資訊，請參閱[規劃如何保護 MBAM 網站](planning-how-to-secure-the-mbam-websites.md)。

## <a href="" id="bkmk-accts-groups"></a>建立帳戶和群組


管理使用者帳戶的最佳做法是建立網域全域群組，並在其中新增使用者帳戶。 如需建議的帳戶和群組的描述，請參閱[規劃 MBAM 2.5 群組和帳戶](planning-for-mbam-25-groups-and-accounts.md)。

## <a href="" id="bkmk-logfiles"></a>使用 MBAM 記錄檔


本節說明 MBAM 伺服器和 MBAM 用戶端記錄檔。

**MBAM Server 安裝程式記錄檔**

在 MBAM 安裝期間， **MBAMServerSetup.exe**檔會在使用者的 **% temp%** 資料夾中產生下列記錄檔：

-   **Microsoft \ _BitLocker \ _Administration \ _and \ _Monitoring \ _ &lt; 數位 &gt; . 記錄**

    記錄在 MBAM 設定和 MBAM 伺服器功能設定期間所採取的動作。

-   **Microsoft \ _BitLocker \ _Administration \ _and \ _Monitoring \ _ &lt; 14 \ _numbers &gt;\_0\_MBAMServer.msi .log**

    記錄安裝期間採取的其他動作。

**MBAM 伺服器配置記錄檔**

-   **應用程式和服務記錄/Microsoft Windows/MBAM-設定**

    記錄您使用 Windows Powershell Cmdlet 時所發生的錯誤，或 MBAM 伺服器設定精靈來設定 MBAM 伺服器功能。

**MBAM 用戶端安裝記錄檔**

-   **MSI &lt; 5 隨機字元 &gt; 記錄**

    記錄在 MBAM 用戶端安裝期間所採取的動作。

**MBAM-Web 記錄檔**

-   顯示來自網頁入口網站和服務的活動。

## <a href="" id="bkmk-tde"></a>審閱 MBAM 資料庫 TDE 考慮


在 SQL Server 中提供的透明資料加密（TDE）功能，是一個可供裝載 MBAM 資料庫功能之資料庫實例的選擇性安裝。

有了 TDE，您就可以執行即時的完整資料庫層級加密。 TDE 是大量加密的最佳選擇，可滿足法規遵從性或公司資料安全性標準。 TDE 在檔層級運作，類似于兩個 Windows 功能： [加密檔案系統（EFS）] 和 [BitLocker 磁片磁碟機加密]。 這兩種功能也會對硬碟上的資料進行加密。 TDE 不會取代儲存格層級的加密、EFS 或 BitLocker。

在資料庫上啟用 TDE 時，所有備份都會經過加密。 因此，您必須採取特殊小心，以確保用來保護資料庫加密金鑰的憑證已在資料庫備份中備份及維護。 如果此憑證或憑證遺失，資料將無法讀取。

使用資料庫備份憑證。 每個證書備份都應該有兩個檔案。 這兩個檔案都應該封存。 理想的安全性，應該將它們與資料庫備份檔案分開備份。 您也可以考慮使用可擴展金鑰管理（EKM）功能（請參閱可擴展金鑰管理）來儲存和維護用於 TDE 的金鑰。

如需如何針對 MBAM 資料庫實例啟用 TDE 的範例，請參閱[瞭解透明資料加密（TDE）](https://technet.microsoft.com/library/bb934049.aspx)。

## <a href="" id="bkmk-general-security"></a>瞭解一般的安全性考慮


**瞭解安全性風險。** 當您使用 Microsoft BitLocker 管理和監控時，最嚴重的風險是，未經授權的使用者可能會利用此漏洞，在 MBAM 用戶端上重新設定 BitLocker 磁片磁碟機加密和取得 BitLocker 加密金鑰資料。 不過，由於拒絕服務攻擊而導致短時間的 MBAM 功能遺失，通常不會產生災難性影響，例如，遺失電子郵件或網路通訊或電源。

**在物理上保護您的電腦**。 沒有物理安全性的安全性。 取得 MBAM 伺服器實際存取權的攻擊者，可能會利用它來攻擊整個用戶端基礎。 所有可能的物理攻擊都必須視為高風險，並適當地減輕問題。 MBAM 伺服器應該儲存在安全的伺服器機房中，並具有可控存取權。 使用作業系統鎖定電腦，或使用安全的螢幕保護裝置程式，在系統管理員沒有實際顯示的情況下，保護這些電腦的安全。

**將最新的安全性更新套用至所有電腦**。 透過訂閱[安全性技術中心](https://go.microsoft.com/fwlink/?LinkId=28819)的安全性通知服務，隨時瞭解 Windows 作業系統、SQL SERVER 及 MBAM 的新更新。

**使用強式密碼或密碼片語**。 針對所有 MBAM 系統管理員帳戶，請務必將強式密碼搭配15個或更多個字元使用。 請勿使用空白密碼。 如需密碼概念的詳細資訊，請參閱[密碼原則](https://technet.microsoft.com/library/hh994572.aspx)。



## 相關主題


[規劃部署 MBAM 2.5](planning-to-deploy-mbam-25.md)

 
## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。
 





