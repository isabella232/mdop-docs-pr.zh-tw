---
title: MBAM 2.5 SP1 版本資訊
description: MBAM 2.5 SP1 版本資訊
author: dansimp
ms.assetid: 3ac424c8-c490-4d62-aba4-1b462c02e962
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 09/06/2017
ms.openlocfilehash: 837892897aeca341433de54aca1228c0faeee124
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810886"
---
# MBAM 2.5 SP1 版本資訊


若要搜尋這些版本筆記，請按 Ctrl + F。

在安裝 Microsoft BitLocker 管理與監控（MBAM） 2.5 SP1 之前，請先閱讀這些版本資訊。 這些版本資訊包含成功安裝 MBAM 所需的資訊，而且可能包含產品檔中不提供的資訊。 如果這些版本資訊與其他 MBAM 2.5 SP1 檔不同，請考慮將最新變更設為權威性。 這些版本資訊取代本產品隨附的內容。

## <a href="" id="---------mbam-2-5-sp1-known-issues"></a> MBAM 2.5 SP1 已知問題


本節包含適用于 MBAM 2.5 SP1 的版本資訊。

### <a href="" id="powershell-read-ad--cmdlets-do-not-provide-feedback-if-user-does-not-have-sufficient-rights"></a>PowerShell Read-AD \ * Cmdlet 不會在使用者沒有足夠許可權的情況中提供意見反應

如果您嘗試使用 PowerShell Read-AD \ * Cmdlet MBAM 伺服器沒有讀取 Active Directory 復原資訊的使用者權利，或無法讀取 TPM 資訊，則 Cmdlet 不會提供任何錯誤或警告的使用者。

因應措施 **：** 如果您擁有所需的使用者許可權，請只使用 PowerShell Read AD \ * Cmdlet。

### MBAM Active Directory （AD）遷移 Cmdlet 不會檢索大量恢復資訊

MBAM Active Directory （AD）遷移 Cmdlet 無法在組織單位（Ou）中檢索電腦的大量復原資訊（如果該反斜線字元（/）是組織單位名稱的一部分）。 當遇到此錯誤時，會發生重複的 AD 拉出，且有管線終止錯誤。

**技術詳細資料：** 執行命令時，您會看到這個錯誤：

``` syntax
Read-ADRecoveryInformation : Unknown error (0x80005000)
At line:1 char:1
+ Read-ADRecoveryInformation -Server "…" -SearchBase " ...
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [Read-ADRecoveryInformation], COMException
    + FullyQualifiedErrorId : System.Runtime.InteropServices.COMException,Microsoft.Mbam.Server.Commands.ADPullCommands.ReadADRecoveryInformationCommand
```

此外，例外狀況堆疊追蹤 `Error[0].Exception.StackTrace` 看起來會像這樣：

``` syntax
   at System.DirectoryServices.DirectoryEntry.Bind(Boolean throwIfFail)
   at System.DirectoryServices.DirectoryEntry.Bind()
   at System.DirectoryServices.DirectoryEntry.get_AdsObject()
   at System.DirectoryServices.PropertyValueCollection.PopulateList()
   at System.DirectoryServices.PropertyValueCollection..ctor(DirectoryEntry entry, String propertyName)
   at System.DirectoryServices.PropertyCollection.get_Item(String propertyName)
   at Microsoft.Mbam.Server.Commands.ADPullCommands.ReadCore.VerifySettingsConnectivity()
   at Microsoft.Mbam.Server.Commands.ADPullCommands.ReadCore.ExecuteRead()
   at Microsoft.Mbam.Server.Commands.ADPullCommands.ReadADInformationBase.ProcessRecord()
   at System.Management.Automation.CommandProcessor.ProcessRecord()
```

因應措施 **：** 若要解決此問題，請執行下列其中一項工作：

-   重新命名 OU 以移除正斜杠字元，然後執行腳本。

-   若要從備份程式中排除任何有問題的 OU，請找出名稱不含正斜線字元的 Ou 清單。 在這些 Ou 上執行腳本（一次一個 OU）。

### <a href="" id="-------------mbam-fails-to-encrypt-a-volume-and-reports-an-error-if-you-set-a-tpm---pin-protector-on-a-tablet-device"></a> 如果您在平板電腦裝置上設定 TPM + PIN 保護器，MBAM 無法加密某個卷，並報告錯誤

如果使用者嘗試在平板電腦裝置上設定 TPM + PIN 保護器，MBAM 無法加密，且會報告錯誤。 這個問題是因為平板電腦裝置沒有預啟動環境鍵盤。

因應措施 **：** 啟用 [**啟用在平板電腦上使用 [在平板電腦上預啟動鍵盤輸入**] 策略設定的 BitLocker 驗證。 此設定是 BitLocker 群組原則設定，且無法在 MBAM 群組原則範本中使用。

### 所有服務帳戶都需要使用者主要名稱

您必須針對 MBAM 中的所有服務帳戶設定使用者主體名稱（UPN）。 如果您無法建立帳戶的 UPN，在設定過程中會出現錯誤訊息，指出在 Active Directory 中找不到該使用者或群組。

因應措施 **：** 將 UPN 新增至服務帳戶。

### 在您升級 IIS 至 .NET Framework 4.5 之後，無法開啟自助服務入口網站與管理和監控網站

當您將網際網路資訊服務（IIS）升級至 Microsoft .NET Framework 4.5 時，系統不會開啟自助入口網站與管理與監控網站。

因應措施 **：** 在[您安裝 .Net Framework 4.0：「無法載入類型 ' system.servicemodel. HttpModule ' 之後](https://go.microsoft.com/fwlink/?LinkId=393568)，請參閱文章錯誤訊息。

### [管理及監視網站] 會在未設定報表時顯示「找不到報表」的錯誤訊息

如果您設定了 [管理及監視] 網站，然後嘗試先查看報表，但不需先設定報表功能，則錯誤訊息會指出找不到該報表。

因應措施 **：** 設定 web 應用程式之前，請先設定 [報告] 功能。

### 如果未在 SSRS 中設定 SSL，系統管理和監控網站中的報告會顯示警告

如果 SQL Server Reporting Services （SSRS）未設定為使用安全通訊端層（SSL），當您設定 MBAM 伺服器時，會將報表功能的 URL 改為 HTTP，而不是 HTTPS。 如果您接著開啟 [管理及監視] 網站並選取報告，就會出現下列錯誤訊息：「只會顯示安全內容」。

因應措施 **：** 若要顯示報表，請按一下 [**顯示所有內容**]。 若要修正此問題，請移至安裝 SQL Server Reporting Services 的 MBAM 電腦，執行**Reporting Services Configuration Manager**，然後按一下 [ **Web 服務 URL**]。 針對伺服器選取適當的 SSL 憑證，輸入適當的 SSL 埠（預設埠是443），**然後按一下 [** 套用]。

### 按一下 [BitLocker 規範摘要] 報告中的 [上一步] 可能會引發錯誤

如果您向下切入 BitLocker 相容性摘要報告，然後按一下 SSRS 報表中的**Back**連結，可能會引發錯誤。

因應措施 **：** 所有.

### 密碼強度在 BitLocker 電腦合規性報告上無法正確顯示

如果您沒有在 [**選擇磁片磁碟機加密方法] 與 [密碼強度**] 群群組原則物件中設定特定的密碼強度，即使密碼強度使用預設的128位加密，Configuration Manager 整合拓撲中的 BitLocker 電腦合規性報告仍會顯示密碼強度 "unknown"。 如果您在群組原則物件中設定特定的密碼強度，報告會顯示正確的密碼強度。

因應措施 **：** 在 [**選擇磁片磁碟機加密方法及密碼強度**] 群群組原則物件中，一定要設定特定的密碼強度。

### 依磁片磁碟機類型進行合規性狀態發佈會在您更新設定專案後顯示舊資料

更新 SystemCenter2012 ConfigurationManager 中的 MBAM 設定專案之後，由 BitLocker Enterprise 合規性儀表板上的 [磁碟機類型] 橫條圖顯示的 [遵從性狀態發佈] 會顯示以舊版本的設定項目資訊為基礎的資料。

因應措施 **：** 所有. 不支援修改 MBAM 設定專案，而且報告可能不會如預期所示。

### [增強的安全性設定] 可能會導致報告無法正確顯示錯誤訊息

如果開啟 Internet Explorer 增強的安全性設定（ESC），當您嘗試在 MBAM 伺服器上查看報告時，可能會出現「拒絕存取」錯誤訊息。 根據預設，ESC 會開啟以保護伺服器，方法是將伺服器暴露在網頁內容和應用程式腳本中可能會發生的可能攻擊。

因應措施 **：** 當您嘗試在 MBAM 伺服器上查看報告時，如果出現「拒絕存取」錯誤訊息，您可以在影像中設定群組原則物件或手動變更預設值，以停用增強的安全性設定。 您也可以在未啟用 ESC 的另一部電腦上，查看報表。

### 支援 Bitlocker XTS-AES 加密演算法
Bitlocker 已在 Windows 10 版本1511中新增 XTS-AES 加密演算法的支援。 使用 HF02、MBAM 新增此 Bitlocker 選項和 HF04 中的用戶端支援，即會新增伺服器端支援。 不過，有一個已知的限制：

* 客戶必須在同一部電腦上使用相同的作業系統和資料量加密強度。
如果使用不同的加密強度，MBAM 會將電腦報告為**不相容**。

### 自助服務入口網站會自動在金鑰識別碼專案上新增 "-"
從 HF02，MBAM 自助服務入口網站會自動在金鑰識別碼專案加上 '-」。  
**注意：** 必須重新佈建服務器，才能使 JAVAscript 生效。

### MBAM 2.5 Sp1 報告無法正常運作/轉譯
當 SSRS 託管于 SQL Server 2016 edition 上時，無法正確呈現 [報告] 頁面。 
例如，流覽至 [支援人員] –按一下 [報表] （醒目提示的部分在其上有 "x"）使用這會進一步說明此情況：當您按一下 [報表] 時，它看起來就像是使用 HTML 4.0 轉譯格式來呼叫 SSRS 頁面。

因應措施 **：** 看看網站的主要程式碼，並注意到 X-UA 模式是 IE8。 因為 IE8 是在生活結束之後，而且客戶使用 IE11。 更新以下程式碼的設定。 這可讓網站利用 IE11 轉譯技術

    <meta http-equiv="X-UA-Compatible" content="IE=Edge" />

原始設定為： 

    <meta http-equiv="X-UA-Compatible" content="IE=8" />


這是使用其他瀏覽器（例如 Chrome、Firefox 等）無法看到問題的原因。



## 相關主題


[關於 MBAM 2.5](about-mbam-25.md)

 

## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。 
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





