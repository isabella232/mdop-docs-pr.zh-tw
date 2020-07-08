---
title: 關於 MBAM 2.5
description: 關於 MBAM 2.5
author: dansimp
ms.assetid: 1ce218ec-4d2e-4a75-8d1a-68d737a8f3c9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: d4c9ff0bc5ee3f7dc51a56cc428081a7c3783694
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810419"
---
# 關於 MBAM 2.5


Microsoft BitLocker 管理和監控（MBAM）2.5 提供簡化的 BitLocker 磁碟機加密管理介面。 BitLocker 針對遺失或被盜電腦的資料竊取或資料暴露提供增強型保護。 BitLocker 會加密儲存在 Windows 作業系統的磁片、磁碟機及已設定的資料磁碟機上的所有資料。

## MBAM 概覽


MBAM 2.5 具有下列功能：

-   可讓系統管理員自動處理整個企業用戶端電腦上的加密量。

-   可讓安全性監察官快速判斷個別電腦或甚至企業本身的合規性狀態。

-   使用 Microsoft System Center Configuration Manager 提供集中式報告及硬體管理。

-   減少支援中心的工作負荷，協助最終使用者使用 BitLocker PIN 和復原金鑰要求。

-   讓使用者能夠使用自助入口網站，獨立地復原加密的裝置。

-   讓安全官員能夠輕鬆地審核存取權，以復原金鑰資訊。

-   讓 Windows 企業使用者能在任何地方繼續運作，保證公司資料受到保護。

MBAM 會強制執行您針對企業所設定的 BitLocker 加密原則選項、監控用戶端電腦與這些原則的合規性，以及企業及個人電腦的加密狀態報表。 此外，MBAM 可讓您在使用者忘記其 PIN 或密碼時，或當他們的 BIOS 或開機記錄變更時，存取復原金鑰資訊。

下列群組可能會對使用 MBAM 來管理 BitLocker 感興趣：

-   管理員、IT 安全性專業人員，以及負責確保機密資料在未授權的情況下公開的合規性官員

-   負責遠端或分支辦公室中電腦安全性性的管理員

-   負責執行 Windows 之用戶端電腦的系統管理員

**記事** 在本 MBAM 檔中不詳細說明 BitLocker。 如需詳細資訊，請參閱[BitLocker 磁片磁碟機加密概述](https://go.microsoft.com/fwlink/p/?LinkId=225013)。

 

## <a href="" id="what-s-new-in-mbam-2-5"></a>MBAM 2.5 的新功能


本節將說明 MBAM 2.5 中的新功能。

### Microsoft SQL Server 2014 支援

除了舊版 MBAM 中支援的相同軟體之外，MBAM 也會新增 Microsoft SQL Server 2014 的支援。

### <a href="" id="-------------mbam-group-policy-templates-downloaded-separately"></a> MBAM 群組原則範本個別下載

MBAM 群組原則範本必須從 MBAM 安裝中單獨下載。 在舊版 MBAM 中，MBAM 安裝套裝程式含一個 MBAM 原則範本，其中包含所需的 MBAM 特定組原則物件（Gpo），這些物件定義 BitLocker 磁片磁碟機加密的 MBAM 實現設定。 這些 Gpo 已從 MBAM 安裝程式中移除。 您現在可以在開始 MBAM 用戶端安裝之前，先從[如何取得 MDOP 組原則（admx）範本](https://go.microsoft.com/fwlink/p/?LinkId=393941)下載 gpo，並將它們複製到伺服器或工作站。 您可以將群組原則範本複製到執行受支援版本的 Windows Server 或 Windows 作業系統的任何伺服器或工作站。

**重要** 請勿變更**BitLocker 磁片磁碟機加密**節點中的群組原則設定，否則 MBAM 將無法正常運作。 當您在**MDOP MBAM （BitLocker 管理）** 節點中設定群組原則設定時，MBAM 會自動為您設定 BitLocker 磁片磁碟機加密設定。

 

您需要複製到伺服器或工作站的範本檔案如下：

-   BitLockerManagement. adml

-   BitLockerManagement admx

-   BitLockerUserManagement. adml

-   BitLockerUserManagement admx

將範本檔案複製到最符合您需求的位置。 針對必須複製到語言特定資料夾的語言特定檔案，需要使用 [群組原則管理主控台] 來查看檔案。

- 若要在本機的伺服器或工作站上安裝範本檔案，請將檔案複製到下列其中一個位置。

  <table>
  <colgroup>
  <col width="50%" />
  <col width="50%" />
  </colgroup>
  <thead>
  <tr class="header">
  <th align="left">檔案類型</th>
  <th align="left">檔案位置</th>
  </tr>
  </thead>
  <tbody>
  <tr class="odd">
  <td align="left"><p>語言中立（admx）</p></td>
  <td align="left"><p><em>% systemroot% </em> \policyDefinitions</p></td>
  </tr>
  <tr class="even">
  <td align="left"><p>語言專用（adml）</p></td>
  <td align="left"><p><em>% systemroot% </em> \policyDefinitions [ <em> MUIculture </em> ] （例如，美國英文專用檔案將會儲存在 <em> % systemroot% &lt; /em &gt; policyDefinitions\en-us）中</p></td>
  </tr>
  </tbody>
  </table>

     

- 若要讓網域中的所有群組原則管理員都能使用這些範本，請將檔案複製到網網域控制站上下列其中一個位置。

  <table>
  <colgroup>
  <col width="50%" />
  <col width="50%" />
  </colgroup>
  <thead>
  <tr class="header">
  <th align="left">檔案類型</th>
  <th align="left">網網域控制站檔案位置</th>
  </tr>
  </thead>
  <tbody>
  <tr class="odd">
  <td align="left"><p>語言中立（admx）</p></td>
  <td align="left"><p><em>% systemroot% </em> sysvol\domain\policies\PolicyDefinitions</p></td>
  </tr>
  <tr class="even">
  <td align="left"><p>語言專用（adml）</p></td>
  <td align="left"><p><em>% systemroot% </em> \sysvol\domain\policies\PolicyDefinitions [ <em> MUIculture </em> ] （例如，美國英文語言專用檔案將會儲存在 <em> % systemroot% </em> \sysvol\domain\policies\PolicyDefinitions\en-us 中）</p></td>
  </tr>
  </tbody>
  </table>

     

如需範本檔案的詳細資訊，請參閱[管理群組原則 ADMX 檔案逐步指南](https://go.microsoft.com/fwlink/?LinkId=392818)。

### 能夠在作業系統和固定資料磁碟機上強制執行加密原則

MBAM 2.5 可讓您針對組織中的電腦強制執行加密原則和固定資料磁碟機，並限制最終使用者可要求的天數，以符合 MBAM 加密原則的需求。

若要讓您設定加密原則強制，已為作業系統磁片磁碟機及固定資料磁碟機新增了新的群組原則設定（稱為「加密原則強制執行設定」）。 此原則如下表所述。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">群組原則設定</th>
<th align="left">描述</th>
<th align="left">用來設定此設定的群組原則節點</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>加密原則強制設定（作業系統磁片磁碟機）</p></td>
<td align="left"><p>針對此設定，請使用選項 <strong> 設定作業系統磁片磁碟機設定寬限期的不符合寬限期間天數 </strong> 。</p>
<p>寬限期指定在第一次偵測到磁碟機之後，最終使用者可在其操作系統磁碟機中延遲遵守 MBAM 原則的天數。</p>
<p>在設定的寬限期到期後，使用者將無法延遲所需的動作，或要求它提出例外狀況。</p>
<p>如果需要使用者互動（例如，如果您使用的是受信任的平臺模組（TPM） + PIN 或使用密碼保護器），則會顯示對話方塊，且使用者無法關閉它，直到它們提供所需的資訊為止。 如果保護器只有 TPM，則在不使用使用者輸入的情況下，會立即在背景中開始加密。</p>
<p>使用者無法透過 BitLocker 加密嚮導要求免除。 相反地，他們必須與技術支援人員聯繫，或使用其組織針對豁免要求所使用的任何流程。</p></td>
<td align="left"><p>電腦設定 &gt; 策略系統 &gt; 管理範本 &gt; WINDOWS 元件 &gt; MDOP MBAM （BitLocker Management） &gt; 作業系統磁片磁碟機</p></td>
</tr>
<tr class="even">
<td align="left"><p>加密原則強制設定（固定資料磁碟機）</p></td>
<td align="left"><p>針對此設定，請使用選項 <strong> 設定固定磁碟機的不符合寬限期間天數 </strong> ，以設定寬限期。</p>
<p>寬限期指定在第一次偵測到磁碟機為不相容之後，最終使用者可以針對其固定磁片磁碟機的 MBAM 原則，將合規性延遲的天數。</p>
<p>寬限期的開始時間是將固定的磁片決定為不相容。 如果您使用的是自動解除鎖定，則必須符合操作系統磁碟機，才能強制執行原則。 不過，如果您不是使用自動解鎖，就可以在作業系統磁片磁碟機完全加密之前，先開始加密固定資料磁碟機。</p>
<p>在設定的寬限期到期後，使用者將無法延遲所需的動作，或要求它提出例外狀況。 如果需要使用者互動，就會出現對話方塊，且使用者必須提供所需的資訊，才能將其關閉。</p></td>
<td align="left"><p>電腦 &gt; 設定策略系統 &gt; 管理範本 &gt; WINDOWS 元件 &gt; MDOP MBAM （BitLocker Management）已 &gt; 固定的磁片磁碟機</p></td>
</tr>
</tbody>
</table>

 

### 能夠在 BitLocker 磁片磁碟機加密嚮導中提供 URL，以指向您的安全性原則

新的群組原則設定是**提供安全性原則連結的 url**，可讓您設定 url，以將其出示給最終使用者作為名為 [**公司安全性原則**] 的連結。 當 MBAM 提示使用者加密卷時，就會出現這個連結。

如果您啟用此原則設定，您可以設定 [**公司安全性原則**] 連結的 URL。 如果您停用或不設定此原則設定，系統就不會向使用者顯示 [**公司安全性原則**] 連結。

新的群組原則設定位於下列 GPO 節點： [電腦設定**Computer Configuration** &gt; **策略**] &gt; **管理範本** &gt; **Windows 元件** &gt; **MDOP MBAM （BitLocker Management） &gt; 用戶端管理**。

### 支援 FIPS 相容的修復金鑰

MBAM 2.5 支援執行 Windows 8.1 作業系統之裝置上的聯邦資訊處理標準（FIPS）相容的 BitLocker 復原金鑰。 在舊版 Windows 中，修復金鑰不符合 FIPS 規範。 此增強功能改善了需要 FIPS 合規性之組織中的磁片磁碟機復原程式，因為它能讓使用者使用自助入口網站或管理和監控網站（問訊台），在忘記其 PIN 或密碼或封鎖電腦的情況下，復原其硬碟。 新的 FIPS 相容性功能不會延伸到密碼保護器。

若要在貴組織中啟用 FIPS 相容性，您必須設定聯邦資訊處理標準（FIPS）群組原則設定。 如需配置指示，請參閱[BitLocker 群組原則設定](https://go.microsoft.com/fwlink/?LinkId=393560)。

對於執行 Windows8 或 Windows7 作業系統的用戶端電腦（沒有安裝的[BitLocker 修復程式](https://support.microsoft.com/kb/3015477)），IT 系統管理員會繼續在 FIPS 相容的環境中使用資料修復代理程式（DRA）保護器。 如需 DRA 的相關資訊，請參閱將[資料修復代理程式與 BitLocker 配合使用](https://go.microsoft.com/fwlink/?LinkId=393557)。

若要下載並安裝適用于 Windows 7 和 Windows 8 電腦的 BitLocker 修復程式，請參閱[BitLocker 管理和監視2.5 的修補程式套件 2](https://support.microsoft.com/kb/3015477) 。

### 支援高可用性部署

除了標準的雙伺服器與 Configuration Manager 整合拓朴之外，MBAM 還支援下列高可用性案例：

-   SQL Server AlwaysOn 可用性群組

-   SQL Server 群集

-   網路負載平衡（NLB）

-   SQL Server 鏡像

-   [卷影複製服務（VSS）] 備份

如需這些功能的詳細資訊，請參閱[規劃 MBAM 2.5 高可用性](planning-for-mbam-25-high-availability.md)。

### <a href="" id="management-of-roles-for-administration-and-monitoring-website-changed-"></a>管理和監控網站已變更的角色管理

在 MBAM 2.5 中，您必須在 Active Directory 網域服務（新增）中建立安全性群組，以管理提供管理和監視網站存取權的角色。 角色可讓特定安全群組中的使用者在網站中執行不同的工作，例如查看報表或協助使用者復原加密的磁碟機。 在舊版 MBAM 中，角色是使用本機群組來管理。

在 MBAM 2.5 中，「角色」一詞會取代舊版 MBAM 中使用的「管理員角色」一詞。 此外，在 MBAM 2.5 中，"MBAM 系統管理員" 角色已移除。

下表列出您必須在 AD DS 中建立的安全性群組。 您可以針對安全性群組使用任何名稱。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">角色</th>
<th align="left">此角色在 [管理] 和 [監視] 網站上的存取權限</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>MBAM 支援人員的使用者</p></td>
<td align="left"><p>提供存取 MBAM 管理和監控網站之 [管理 TPM] 和 [磁片磁碟機] 區域的許可權。 擁有這些區域存取權的使用者，在使用任一區域時，都必須填入所有欄位。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MBAM 報表使用者</p></td>
<td align="left"><p>提供管理和監控網站中報告的存取權。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MBAM 高級支援人員的使用者</p></td>
<td align="left"><p>提供管理和監控網站中所有區域的存取權。 這個群組中的使用者在協助使用者復原其磁碟機時，只需要輸入復原金鑰，而不是使用者的網域和使用者名稱。 如果使用者是 MBAM [支援人員] 群組和 MBAM [高級服務台使用者] 群組的成員，MBAM [高級支援人員] 群組許可權會覆寫 MBAM 的 [支援人員] 群組許可權。</p></td>
</tr>
</tbody>
</table>

 

在新增中建立安全性群組之後，請將使用者和/或群組指派給適當的安全性群組，以啟用管理與監視網站的對應層級存取。 若要讓每個角色的使用者都能存取 [管理] 和 [監視] 網站，您也必須在設定管理和監視網站時指定每個安全性群組。

### 用來設定 MBAM 伺服器功能的 Windows PowerShell Cmdlet

MBAM 2.5 的 Windows PowerShell Cmdlet 可讓您設定及管理 MBAM 伺服器功能。 每個功能都有對應的 Windows PowerShell Cmdlet，您可以用來啟用或停用功能，或是取得該功能的相關資訊。

如需使用 Windows PowerShell 的先決條件與先決條件，請參閱[使用 Windows powershell 設定 MBAM 2.5 伺服器功能](configuring-mbam-25-server-features-by-using-windows-powershell.md)。

**若要在安裝 MBAM 伺服器軟體後載入 Windows PowerShell Cmdlet 的 MBAM 2.5 說明**

1.  開啟 Windows PowerShell 或 Windows PowerShell 整合式腳本環境（ISE）。

2.  類型**更新-說明-MODULE MBAM**。

MBAM 的 Windows PowerShell 說明提供下列格式：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Windows PowerShell 說明格式</th>
<th align="left">詳細資訊</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>在 Windows PowerShell 命令提示字元中，輸入 <strong> get-help </strong> &lt; <em> Cmdlet</em>&gt;</p></td>
<td align="left"><p>若要上傳最新的 Windows PowerShell Cmdlet，請按照上一節中如何載入 MBAM 的 Windows PowerShell 說明一節中的指示進行。</p></td>
</tr>
<tr class="even">
<td align="left"><p>在 TechNet 上做為網頁</p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393498" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393498">https://go.microsoft.com/fwlink/?LinkId=393498</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>以單字 .docx 檔案的形式在下載中心</p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393497" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393497">https://go.microsoft.com/fwlink/?LinkId=393497</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>以 .pdf 檔案的形式在下載中心</p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393499" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393499">https://go.microsoft.com/fwlink/?LinkId=393499</a></p></td>
</tr>
</tbody>
</table>

 

### 支援僅限 ASCII 且增強的 Pin，以及防止順序及重複字元的能力

**允許 [啟動] 群組原則設定的增強型 Pin**

[群組原則] 設定是 [**允許增強的 pin 以進行啟動**]，可讓您設定是否與 BitLocker 搭配使用增強的啟動 pin。 增強的啟動 Pin 功能可讓使用者在完整的鍵盤上輸入任何按鍵，包括大寫及小寫字母、符號、數位和空格。 如果您啟用此原則設定，所有設定的新 BitLocker 啟動 Pin 都將是增強的 Pin。 如果您停用或不設定此原則設定，就無法使用增強的 Pin。

並非所有電腦都支援開機前執行環境（PXE）中的增強型 Pin 輸入。 在您的組織啟用此群組原則設定之前，請先執行 BitLocker 安裝程式期間的系統檢查，以確保電腦的 BIOS 支援在 PXE 中使用完整的鍵盤。 如需詳細資訊，請參閱[規劃 MBAM 2.5 群組原則需求](planning-for-mbam-25-group-policy-requirements.md)。

**[需要 ASCII 專用 Pin] 核取方塊**

[**允許啟動群組的增強型 pin** ] 群組原則設定也包含 [**需要 ASCII 專用 pin** ] 核取方塊。 如果貴組織中的電腦不支援在 PXE 中使用完整的鍵盤，您可以啟用 [**允許啟動**] 群群組原則設定的 [已增強的 pin]，然後選取 [**需要 ASCII 專用 pin** ] 核取方塊，以要求 [增強 pin] 只使用可列印的 ascii 字元。

**強制使用非順序和非重複字元**

MBAM 2.5 可防止最終使用者建立由重複數位（例如1111）或連續數位（例如1234）的 Pin。 如果使用者嘗試輸入包含三個或多個重複或連續數位的密碼，則 Bitlocker 磁片磁碟機加密嚮導會顯示錯誤訊息，並防止使用者輸入包含禁止字元的 PIN。

### 將 DRA 憑證加入 BitLocker 電腦合規性報告

已在 Configuration Manager 的 BitLocker 電腦合規性報告中新增了新的保護器類型，即資料復原代理程式（DRA）憑證。 此保護器類型適用于操作系統磁碟機，且出現在 [**保護類型**] 欄的 [**電腦卷**] 區段中。

### 支援多林支援部署

MBAM 2.5 支援下列多目錄林部署類型：

-   單一目錄林與單一網域

-   具有單一樹狀結構和多個網域的單一目錄林

-   具有多個樹和不連續命名空間的單一目錄林

-   中央目錄林拓撲中的多個林

-   資原始目錄林拓朴中的多個目錄林

不支援林遷移（從單一到多、多到單、資源到整個林等），或是升級或降級。

在多目錄林部署中部署 MBAM 的先決條件包括：

-   林中必須在支援的 Windows Server 版本上執行。

-   需要雙向或單向信任。 單向信任要求伺服器的網域信任用戶端的網域。 換句話說，伺服器的網域指向用戶端的網域。

### MBAM 加密硬碟的用戶端支援

MBAM 支援針對 Opal 和 IEEE 1667 標準提供 TCG 規格需求的加密硬碟磁碟機上的 BitLocker。 在這些裝置上啟用 BitLocker 時，它會在加密的磁片磁碟機上產生金鑰並執行管理功能。 如需詳細資訊，請參閱[加密的硬碟](https://technet.microsoft.com/library/hh831627.aspx)。

## 如何取得 MDOP 技術


MBAM 是 Microsoft Desktop 優化套件（MDOP）的一部分。 MDOP 是 Microsoft 軟體保證程式的一部分。 如需 Microsoft 軟體保證計畫的詳細資訊，以及如何取得 MDOP，請參閱[如何取得 mdop？](https://go.microsoft.com/fwlink/?LinkId=322049)。

## <a href="" id="---------mbam-2-5-release-notes"></a> MBAM 2.5 版本資訊


如需本檔中未包含的詳細資訊及最新資訊，請參閱[MBAM 2.5 的版本](release-notes-for-mbam-25.md)資訊。

## 取得 MBAM 的建議嗎？
- 在[這裡](https://support.microsoft.com/help/4021566/windows-10-send-feedback-to-microsoft-with-feedback-hub)傳送您的意見反應。 
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。

## 相關主題


[Microsoft BitLocker Administration and Monitoring 2.5](index.md)

[開始使用 MBAM 2.5](getting-started-with-mbam-25.md)

 

 





