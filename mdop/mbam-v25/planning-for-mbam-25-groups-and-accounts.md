---
title: MBAM 2.5 群組與帳戶規劃
description: MBAM 2.5 群組與帳戶規劃
author: dansimp
ms.assetid: 73bb9fe5-5900-4b6f-b271-ade62991fca1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 11/02/2016
ms.openlocfilehash: 3431c3602685a4f96cb4c1333700107ba9c38b96
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811373"
---
# MBAM 2.5 群組與帳戶規劃


本主題列出您必須在 Active Directory 網域服務（AD DS）中建立的角色和帳戶，以提供 Microsoft BitLocker 管理與監控（MBAM）資料庫、報表及 web 應用程式的安全性與存取權。 針對每個角色和帳戶，提供 MBAM 伺服器設定精靈中的對應欄位。 如需與這些帳戶相對應的 Windows PowerShell Cmdlet 和參數清單，請參閱[使用 Windows PowerShell 設定 MBAM 2.5 伺服器功能](configuring-mbam-25-server-features-by-using-windows-powershell.md#bkmk-reqd-posh-accts)。

**注意**  
MBAM 不支援使用受管理的服務帳戶。



## 資料庫帳戶


針對合規性和審核資料庫以及恢復資料庫建立下列帳戶。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">帳戶名稱和用途</th>
<th align="left">帳戶類型</th>
<th align="left">與此帳戶對應的 [MBAM 伺服器設定] 嚮導欄位</th>
<th align="left">對應至此帳戶的 [MBAM 伺服器設定] 嚮導欄位的描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>合規性與審計資料庫及復原資料庫已讀/寫使用者或群組的報告</p></td>
<td align="left"><p>使用者或群組</p></td>
<td align="left"><p>讀/寫存取網域使用者或群組</p></td>
<td align="left"><p>具備合規性和審核資料庫及復原資料庫之讀/寫存取權的網域使用者或群組，可讓 web 應用程式存取這些資料庫中的資料和報表。</p>
<p>如果您在此欄位中輸入使用者名稱，它必須與 <strong> </strong> [ <strong> 設定 web 應用程式] 頁面上的 [web 服務應用程式池網域帳戶] 欄位中的值相同 </strong> 。</p>
<p>如果您在此欄位中輸入組名，則 [ <strong> 設定 Web 應用程式] 頁面上的 [Web 服務應用程式群組網域帳戶] 欄位中的值 </strong> <strong> </strong> 必須是您在這個欄位中輸入之群組的成員。</p></td>
</tr>
<tr class="even">
<td align="left"><p>合規性和審核資料庫唯讀使用者或群組的報表</p></td>
<td align="left"><p>使用者或群組</p></td>
<td align="left"><p>唯讀存取網域使用者或群組</p></td>
<td align="left"><p>將對合規性和審核資料庫擁有唯讀存取權的使用者或群組的名稱，以讓報告能夠存取此資料庫中的合規性和審核資料。</p>
<p>如果您在此欄位中輸入使用者名稱，該使用者必須是您在 <strong> </strong> [設定報告] 頁面上的 [合規性和審核資料庫網域帳戶] 欄位中所指定的使用者 <strong> </strong> 。</p>
<p>如果您在此欄位中輸入組名，您在 <strong> [設定報告] 頁面上的 [合規性與審計資料庫網域帳戶] 欄位中指定的值， </strong> <strong> </strong> 必須是您在此欄位中指定之群組的成員。</p></td>
</tr>
</tbody>
</table>



## 報告帳戶


針對 [報告] 功能建立下列帳戶。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">帳戶名稱/用途</th>
<th align="left">帳戶類型</th>
<th align="left">與此帳戶對應的 [MBAM 伺服器設定] 嚮導欄位</th>
<th align="left">對應至此帳戶的 [MBAM 伺服器設定] 嚮導欄位的描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>報告唯讀網域存取群組</p></td>
<td align="left"><p>群組</p></td>
<td align="left"><p>報告角色網域群組</p></td>
<td align="left"><p>指定擁有 [管理及監視] 網站上的報告唯讀存取權的網域使用者群組。 您指定的群組必須是您在啟用 web 應用程式時為 [報告唯讀存取] 群組參數指定的群組。</p></td>
</tr>
<tr class="even">
<td align="left"><p>合規性與審計資料庫網域使用者帳戶</p></td>
<td align="left"><p>使用者</p></td>
<td align="left"><p>合規性與審計資料庫網域帳戶</p></td>
<td align="left"><p>本機 SQL Server Reporting Services 實例用來存取合規性和審核資料庫的網域使用者帳戶和密碼。 這個帳戶必須 <strong> 以批次許可權登入 </strong> 至 SQL Server Reporting Services 伺服器。</p>
<p>如果您在 <strong> [設定資料庫] 頁面上的 [唯讀存取網域使用者] 或 [群組] 欄位中輸入的值 </strong> <strong> </strong> 是使用者名稱，則您必須在這個欄位中輸入相同的值。</p>
<p>如果您在 <strong> [設定資料庫] 頁面上的 [唯讀存取網域使用者] 或 [群組] 欄位中輸入的值 </strong> <strong> </strong> 是群組名稱，則您在這個欄位中輸入的值必須是該群組的成員。</p>
<p>將此帳戶的密碼設定為永不過期。 使用者帳戶應該能夠存取 MBAM [報告使用者] 群組提供的所有資料。</p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-helpdesk-roles"></a>管理和監控網站（技術支援）帳戶


針對 [管理及監視] 網站建立下列帳戶。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">帳戶名稱/用途</th>
<th align="left">帳戶類型</th>
<th align="left">與此帳戶對應的 [MBAM 伺服器設定] 嚮導欄位</th>
<th align="left">對應至此帳戶的 [MBAM 伺服器設定] 嚮導欄位的描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Web 服務應用程式池網域帳戶</p></td>
<td align="left"><p>使用者</p></td>
<td align="left"><p>Web 服務應用程式池網域帳戶</p></td>
<td align="left"><p>要供 web 應用程式的應用程式池使用的網域使用者帳戶。</p>
<p>如果您在 <strong> [設定資料庫] 頁面上的 [讀/寫存取權網域使用者或群組] 欄位中輸入使用者名稱 </strong> <strong> </strong> ，您必須在這個欄位中輸入相同的值。</p>
<p>如果您在 <strong> [設定資料庫] 頁面上的 [讀/寫存取網域] 或 [群組] 欄位中輸入組名 </strong> <strong> </strong> ，您在這個欄位中輸入的值必須是該群組的成員。</p>
<p>如果您沒有指定認證，則會使用為先前啟用的任何 web 應用程式所指定的認證。 所有 web 應用程式都必須使用相同的應用程式池認證。 如果您針對不同的 web 應用程式指定不同的認證，則會使用最近指定的值。</p>
<div class="alert">
<strong>重要</strong><br/><p>若要提高安全性，請將認證中指定的帳號設定為擁有有限的使用者權限。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>MBAM 高級支援人員的使用者存取群組</p></td>
<td align="left"><p>群組</p></td>
<td align="left"><p>MBAM 高級支援人員的使用者</p></td>
<td align="left"><p>網域使用者群組，其成員可以存取 [管理] 和 [監視] 網站的所有恢復區域。 擁有此角色的使用者在協助使用者復原其磁碟機時，只需要輸入復原金鑰，而不是最終使用者的網域和使用者名稱。 如果使用者是 MBAM [支援人員] 群組和 MBAM [高級服務台使用者] 群組的成員，MBAM [高級支援人員] 群組許可權會覆寫 MBAM [服務台] 群組的許可權。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MBAM 支援人員的使用者存取群組</p></td>
<td align="left"><p>群組</p></td>
<td align="left"><p>MBAM 支援人員的使用者</p></td>
<td align="left"><p>網域使用者群組，其成員可以存取 MBAM 管理和監控網站的 [管理 TPM] 和 [磁碟機恢復] 區域。 擁有此角色的人員在使用任一選項時，都必須填入所有欄位，包括最終使用者的網域和帳戶名稱。</p>
<p>如果使用者是 MBAM [支援人員] 群組和 MBAM [高級服務台使用者] 群組的成員，MBAM [高級支援人員] 群組許可權會覆寫 MBAM [服務台] 群組的許可權。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MBAM 報表使用者存取群組</p></td>
<td align="left"><p>群組</p></td>
<td align="left"><p>MBAM 報表使用者</p></td>
<td align="left"><p>其成員對 [管理] 和 [監視] 網站的 [報表] 區域中的報表擁有唯讀存取權的網域使用者群組。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MBAM 資料移轉使用者群組</p></td>
<td align="left"><p>群組</p></td>
<td align="left"><p>MBAM 資料移轉使用者</p></td>
<td align="left"><p>其成員具有在 MBAM 伺服器上執行的 MBAM 復原與硬體服務，擁有將資料寫入 MBAM 之許可權的選用網域使用者群組。 這個帳戶通常與 Write Mbam * Cmdlet 搭配使用，以將復原及 TPM 資料從 Active Directory 寫入 MBAM 資料庫。</p>
<p>如需詳細資訊，請參閱 <a href="mbam-25-security-considerations.md" data-raw-source="[MBAM 2.5 Security Considerations](mbam-25-security-considerations.md)"> MBAM 2.5 安全性考慮 </a> 。</p></td>
</tr>
</tbody>
</table>




## 相關主題


[MBAM 2.5 的環境準備](preparing-your-environment-for-mbam-25.md)

[MBAM 2.5 部署必要條件](mbam-25-deployment-prerequisites.md)



## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。 
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





