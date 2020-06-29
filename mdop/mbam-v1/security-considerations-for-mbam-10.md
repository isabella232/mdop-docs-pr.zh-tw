---
title: MBAM 1.0 的安全性考量
description: MBAM 1.0 的安全性考量
author: dansimp
ms.assetid: 5e1c8b8c-235b-4a92-8b0b-da50dca17353
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: b06c343c8193293dde91bc7af2541f35f332d261
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811607"
---
# MBAM 1.0 的安全性考量


本主題包含帳戶與群組、記錄檔案，以及 Microsoft BitLocker 管理與監控的其他安全相關考慮（MBAM）的簡短概述。 如需詳細資訊，請參閱本文中的連結。

## 一般安全性考慮


**瞭解安全性風險。** MBAM 最嚴重的風險是，未經授權的使用者可能會劫持其功能，讓您可以在 MBAM 用戶端重新設定 BitLocker 加密並取得 BitLocker 加密金鑰資料。 不過，因拒絕服務攻擊而導致短時間內的 MBAM 功能遺失，通常不會產生災難性影響。

**在物理上保護您的電腦**。 安全性不完整，沒有實際的安全性。 對 MBAM 伺服器擁有物理存取權的任何人，都可能會攻擊整個用戶端基礎。 任何潛在的物理攻擊都必須被視為高風險，並適當地減輕問題。 MBAM 伺服器應該儲存在具有可控存取權的物理安全伺服器機房中。 使用作業系統鎖定電腦，或使用安全的螢幕保護裝置程式，在系統管理員沒有實際顯示的情況下，保護這些電腦的安全。

**將最新的安全性更新套用至所有電腦**。 訂閱安全性通知服務（），隨時瞭解作業系統、Microsoft SQL Server 及 MBAM 的新更新 <https://go.microsoft.com/fwlink/p/?LinkId=28819> 。

**使用強式密碼或密碼片語**。 針對所有 MBAM 及 MBAM 系統管理員帳戶，請務必使用具有15個或以上字元的強式密碼。 請勿使用空白密碼。 如需密碼概念的詳細資訊，請參閱 TechNet 上的「帳戶密碼及原則」白皮書 <https://go.microsoft.com/fwlink/p/?LinkId=30009> 。

## MBAM 中的帳戶和群組


使用者帳戶管理的最佳做法是建立網域全域群組，並在其中新增使用者帳戶。 然後，將網域通用帳戶新增到 MBAM 伺服器上必要的 MBAM 本機群組。

### ActiveDirectoryDomainServices 群組

在 MBAM 設定期間，不會自動建立群組。 不過，您應該建立下列 ActiveDirectoryDomainServices 全域群組，以管理 MBAM 作業。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">群組名稱</th>
<th align="left">詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>MBAM 高級支援人員的使用者</p></td>
<td align="left"><p>建立此群組以管理在 MBAM 設定期間建立的 MBAM 高級支援人員使用者當地群組的成員。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MBAM 合規性審核資料庫存取</p></td>
<td align="left"><p>建立此群組，以管理在 MBAM 設定期間建立的 MBAM 合規性審核資料庫存取本機群組的成員。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MBAM 硬體使用者</p></td>
<td align="left"><p>建立此群組以管理在 MBAM 設定期間建立的 MBAM 硬體使用者本機群組的成員。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MBAM 支援人員的使用者</p></td>
<td align="left"><p>建立此群組以管理在 MBAM 設定期間建立的 MBAM [支援的使用者] 本機群組的成員。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MBAM 恢復與硬體資料庫存取</p></td>
<td align="left"><p>建立此群組以管理在 MBAM 設定期間建立的 MBAM 復原與硬體資料庫存取本機群組的成員。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MBAM 報表使用者</p></td>
<td align="left"><p>建立此群組以管理在 MBAM 設定期間建立的 MBAM 報表使用者本機群組的成員。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MBAM 系統管理員</p></td>
<td align="left"><p>建立此群組以管理在 MBAM 設定期間建立的 MBAM 系統管理員本機群組的成員。</p></td>
</tr>
<tr class="even">
<td align="left"><p>BitLocker 加密免除</p></td>
<td align="left"><p>[建立此群組] 可管理要從其登入之電腦開始的 BitLocker 加密所免除的使用者帳戶。</p></td>
</tr>
</tbody>
</table>

 

### MBAM Server 本機群組

MBAM 安裝程式會建立本機群組以支援 MBAM 作業。 您應該將 ActiveDirectoryDomainServices 全域群組新增至適當的 MBAM 本機群組，以設定 MBAM 安全性與資料存取許可權。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">群組名稱</th>
<th align="left">詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>MBAM 高級支援人員的使用者</p></td>
<td align="left"><p>此群組的成員已展開存取 Microsoft BitLocker 管理和監控的支援人員功能。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MBAM 合規性審核資料庫存取</p></td>
<td align="left"><p>此群組包含可存取 MBAM 合規性審核資料庫的電腦。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MBAM 硬體使用者</p></td>
<td align="left"><p>此群組的成員可以存取 Microsoft BitLocker 管理和監控的一些硬體功能功能。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MBAM 支援人員的使用者</p></td>
<td align="left"><p>此群組的成員可以存取 Microsoft BitLocker 管理和監控中的某些技術支援人員功能。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MBAM 恢復與硬體資料庫存取</p></td>
<td align="left"><p>這個群組包含可存取 MBAM 復原與硬體資料庫的電腦。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MBAM 報表使用者</p></td>
<td align="left"><p>此群組的成員可以存取來自 Microsoft BitLocker 管理和監視的合規性和審核報告。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MBAM 系統管理員</p></td>
<td align="left"><p>此群組的成員可以存取 Microsoft BitLocker 管理和監控的所有功能。</p></td>
</tr>
</tbody>
</table>

 

### SSRS 報告存取帳戶

SQL Server Reporting Services （SSRS）報表服務帳戶會提供安全性內容，以執行透過 SSRS 提供的 MBAM 報告。 這個帳戶是在 MBAM 安裝期間設定。

## MBAM 記錄檔


在 MBAM 設定期間，下列 MBAM 安裝記錄檔案是在安裝的使用者的% temp% 資料夾中建立

**MBAM Server 安裝程式記錄檔**

<a href="" id="msi-five-random-characters--log"></a>MSI <em> &lt; 5 隨機字元 &gt; </em> 記錄  
記錄在 MBAM 設定和 MBAM 伺服器功能安裝期間所採取的動作。

<a href="" id="installcompliancedatabase-log"></a>InstallComplianceDatabase 記錄  
記錄建立 MBAM 合規性狀態資料庫設定所採取的動作。

<a href="" id="installkeycompliancedatabase-log"></a>InstallKeyComplianceDatabase 記錄  
記錄建立 MBAM 復原與硬體資料庫所採取的動作。

<a href="" id="addhelpdeskdbauditusers-log"></a>AddHelpDeskDbAuditUsers 記錄  
記錄在 MBAM 合規性狀態資料庫上建立 SQL Server 登入所採取的動作，以及授權支援人員的 web 服務至資料庫以取得報告。

<a href="" id="addhelpdeskdbusers-log"></a>AddHelpDeskDbUsers 記錄  
記錄針對金鑰復原授權 web 服務所採取的動作，並建立 MBAM 復原與硬體資料庫的登入。

<a href="" id="addkeycompliancedbusers-log"></a>AddKeyComplianceDbUsers 記錄  
記錄針對合規性報告進行授權 web 服務時所採取的動作，以 MBAM 合規性狀態資料庫。

<a href="" id="addrecoveryandhardwaredbusers-log"></a>AddRecoveryAndHardwareDbUsers 記錄  
記錄在授權 web 服務時所採取的動作，以 MBAM 復原及硬體資料庫，以取得金鑰復原能力。

**記事** 若要取得其他 MBAM 安裝記錄檔，您必須使用**msiexec**套件和 **/l** Location 選項來安裝 Microsoft BitLocker 管理和監視 &lt; &gt; 。 在指定的位置中建立記錄檔。

 

**MBAM 用戶端安裝記錄檔**

<a href="" id="msi-five-random-characters--log"></a>MSI <em> &lt; 5 隨機字元 &gt; </em> 記錄  
記錄在 MBAM 用戶端安裝期間所採取的動作。

## MBAM 資料庫 TDE 考慮


SQL Server 2008 中提供的透明資料加密（TDE）功能，是將裝載 MBAM 資料庫功能之資料庫實例所需的安裝必要。

有了 TDE，您就可以執行即時的完整資料庫層級加密。 TDE 是一種非常適合的大量加密選項，以符合法規規範或公司資料安全標準。 TDE 在檔層級運作，與兩個 Windows 功能類似： [加密檔案系統（EFS）] 和 [BitLocker 磁碟機加密]，這兩者也會對硬碟上的資料進行加密。 TDE 不會取代儲存格層級的加密、EFS 或 BitLocker。

在資料庫上啟用 TDE 時，所有備份都會經過加密。 因此，您必須採取特殊小心，以確保用來保護資料庫加密金鑰（DEK）的憑證已在資料庫備份中備份及維護。 如果沒有憑證，資料將無法讀取。 備份憑證及資料庫。 每個證書備份都應該有兩個檔案;這兩個檔案都應該封存。最好是將它們與資料庫備份檔案分開，以取得安全性。

如需如何針對 MBAM 資料庫實例啟用 TDE 的範例，請參閱[評估 MBAM 1.0](evaluating-mbam-10.md)。

如需有關 SQLServer 2008 中 TDE 的詳細資訊，請參閱[SQL Server 2008 Enterprise Edition 中的資料庫加密](https://go.microsoft.com/fwlink/?LinkId=269703)。

## 相關主題


[MBAM 1.0 的安全性與隱私權](security-and-privacy-for-mbam-10.md)

 

 





