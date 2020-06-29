---
title: 了解 MBAM 2.5 獨立報告
description: 了解 MBAM 2.5 獨立報告
author: dansimp
ms.assetid: 78b5aaf4-8257-4722-8eb9-e0de48db6a11
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 45e84c7c3b2bcb1602890c7c5a09592324da691e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800178"
---
# 了解 MBAM 2.5 獨立報告


本主題說明當您在獨立拓撲中執行 Microsoft BitLocker 管理和監控（MBAM）時可使用的報表。

**注意**  
如果您是使用 Configuration Manager 整合拓朴執行 MBAM，則會從 Configuration Manager 產生報表，而不是從 MBAM。 如需有關這些報告的詳細資訊，請參閱[查看 Configuration Manager 整合拓朴的 MBAM 2.5 報告](viewing-mbam-25-reports-for-the-configuration-manager-integration-topology.md)。



## 瞭解 MBAM 獨立拓朴報告


MBAM 提供三種報告類型，您可以用來監視貴組織的 BitLocker 合規性：

-   [企業合規性報告](#bkmk-enterprisecompliance)

-   [電腦合規性報告](#bkmk-compliance)

-   [復原審核報告](#bkmk-recovery)

若要在獨立拓撲中執行 MBAM 時存取 MBAM 報表，請開啟網頁瀏覽器，然後開啟 [管理及監視] 網站。 選取左側功能表列中的 [**報表**]。 從上方的功能表列中，選取您要產生的報表類型。 如需有關產生這些報告的詳細資訊，請參閱[產生 MBAM 2.5 獨立報告](generating-mbam-25-stand-alone-reports.md)。

### <a href="" id="bkmk-enterprisecompliance"></a>企業合規性報告

使用此報告類型，收集貴組織中的整體 BitLocker 規範資訊。 您可以使用篩選來縮小搜尋結果的範圍，以深入瞭解貴組織中電腦的相容性狀態與錯誤狀態。

**企業合規性概述**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">欄名稱</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>受管理的電腦</p></td>
<td align="left"><p>MBAM 管理的電腦數。</p></td>
</tr>
<tr class="even">
<td align="left"><p>符合百分比</p></td>
<td align="left"><p>企業中合規性電腦的百分比。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>非相容性%</p></td>
<td align="left"><p>企業中不相容的電腦百分比。</p></td>
</tr>
<tr class="even">
<td align="left"><p>% 豁免</p></td>
<td align="left"><p>免除 BitLocker 加密需求的電腦所占的百分比。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>非豁免%</p></td>
<td align="left"><p>不受 BitLocker 加密需求免除的電腦百分比。</p></td>
</tr>
<tr class="even">
<td align="left"><p>達到</p></td>
<td align="left"><p>企業中合規性電腦的百分比。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>不相容</p></td>
<td align="left"><p>企業中不相容的電腦百分比。</p></td>
</tr>
<tr class="even">
<td align="left"><p>免除</p></td>
<td align="left"><p>免除 BitLocker 加密需求的電腦總數。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>非豁免</p></td>
<td align="left"><p>未免除 BitLocker 加密需求的電腦總數。</p></td>
</tr>
</tbody>
</table>



**企業規範電腦詳細資料**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">欄名稱</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>電腦名稱稱</p></td>
<td align="left"><p>由 MBAM 管理的使用者指定 DNS 名稱。</p></td>
</tr>
<tr class="even">
<td align="left"><p>網功能變數名稱稱</p></td>
<td align="left"><p>用戶端電腦所在的完整功能變數名稱，且由 MBAM 管理。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>合規性狀態</p></td>
<td align="left"><p>根據電腦所指定的原則，為電腦提供符合的狀態。 狀態是不相容且合規性。 如需有關如何解讀合規性狀態的詳細資訊，請參閱下列企業合規性報告相容性狀態資料表。</p></td>
</tr>
<tr class="even">
<td align="left"><p>免除</p></td>
<td align="left"><p>指出此電腦是否不受 BitLocker 原則免除的狀態。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>合規性狀態詳細資料</p></td>
<td align="left"><p>符合指定原則之電腦符合性狀態的錯誤與狀態訊息。</p></td>
</tr>
<tr class="even">
<td align="left"><p>最後一個連絡人</p></td>
<td align="left"><p>電腦上次與伺服器聯繫以報告合規性狀態的日期和時間。 連絡人頻率是可設定的。 如需詳細資訊，請參閱 MBAM 群組原則設定。</p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-compliance"></a>電腦合規性報告

使用此報告類型可收集電腦或使用者專用的資訊。

若要查看此報告，請按一下企業合規性報告中的電腦名稱稱，或在電腦合規性報告中輸入電腦名稱稱。 此報告顯示電腦上每個磁片磁碟機（作業系統及固定資料磁碟機）的詳細加密資訊。 它也會指出已套用到電腦上每個磁片磁碟機類型的原則。 若要查看每個磁片磁碟機的詳細資料，請展開 [電腦名稱稱] 專案。

**注意**  
在此報告中不會顯示 [可移動資料量] 加密狀態。



**電腦合規性報告欄位**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">欄名稱</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>電腦名稱稱</p></td>
<td align="left"><p>由 MBAM 管理的使用者指定 DNS 電腦名稱稱。</p></td>
</tr>
<tr class="even">
<td align="left"><p>網功能變數名稱稱</p></td>
<td align="left"><p>用戶端電腦所在的完整功能變數名稱，且由 MBAM 管理。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>電腦類型</p></td>
<td align="left"><p>電腦類型。 有效類型為非便攜且可移植。</p></td>
</tr>
<tr class="even">
<td align="left"><p>作業系統</p></td>
<td align="left"><p>在由 MBAM 管理的用戶端電腦上找到的作業系統類型。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>合規性狀態</p></td>
<td align="left"><p>由 MBAM 管理之電腦的整體合規性狀態。 有效的狀態是相容且不相容。</p>
<p>請注意，每個磁片磁碟機的相容性狀態（請參閱下表）可能表示不同的合規性狀態。 不過，這個欄位會根據指定的原則代表符合性狀態。</p></td>
</tr>
<tr class="even">
<td align="left"><p>原則密碼強度</p></td>
<td align="left"><p>系統管理員在 MBAM 原則規格期間選取的密碼強度（例如，使用擴散器的128位）。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>原則作業系統磁片磁碟機</p></td>
<td align="left"><p>表示作業系統是否需要加密，並顯示適當的保護器類型。</p></td>
</tr>
<tr class="even">
<td align="left"><p>原則-固定資料磁碟機</p></td>
<td align="left"><p>表示固定資料磁碟機是否需要加密。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>策略移除資料磁碟機</p></td>
<td align="left"><p>表示是否需要對移除磁片磁碟機進行加密。</p></td>
</tr>
<tr class="even">
<td align="left"><p>裝置使用者</p></td>
<td align="left"><p>由 MBAM 管理的電腦上的已知使用者。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>免除</p></td>
<td align="left"><p>指出此電腦是否不受 BitLocker 原則免除的狀態。</p></td>
</tr>
<tr class="even">
<td align="left"><p>製造商</p></td>
<td align="left"><p>電腦製造商名稱，如電腦 BIOS 所示。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>型號</p></td>
<td align="left"><p>電腦製造商模型名稱，如電腦 BIOS 所示。</p></td>
</tr>
<tr class="even">
<td align="left"><p>合規性狀態詳細資料</p></td>
<td align="left"><p>根據指定原則，瞭解電腦合規性狀態的錯誤與狀態訊息。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>最後一個連絡人</p></td>
<td align="left"><p>電腦上次取得伺服器以報告合規性狀態的日期和時間。 連絡人頻率是可設定的。 如需詳細資訊，請參閱 MBAM 群組原則設定。</p></td>
</tr>
</tbody>
</table>



**電腦合規性報告磁片磁碟機欄位**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">欄名稱</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>磁片磁碟機盤符</p></td>
<td align="left"><p>使用者指派給特定磁片磁碟機的電腦磁碟機盤符。</p></td>
</tr>
<tr class="even">
<td align="left"><p>磁片磁碟機類型</p></td>
<td align="left"><p>磁片磁碟機類型。 有效值為作業系統磁片磁碟機及固定資料磁片磁碟機。 這些是物理磁片磁碟機，而不是邏輯磁片磁碟機。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>密碼強度</p></td>
<td align="left"><p>管理員在 MBAM 原則規格期間選取的密碼強度。</p></td>
</tr>
<tr class="even">
<td align="left"><p>保護器類型</p></td>
<td align="left"><p>透過用來加密作業系統或固定資料量的群組原則設定所選取的保護者類型。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>保護器狀態</p></td>
<td align="left"><p>指示由 MBAM 管理的電腦已啟用原則中指定的保護器類型。 [有效] 狀態為 [開啟] 或 [關閉]。</p></td>
</tr>
<tr class="even">
<td align="left"><p>加密狀態</p></td>
<td align="left"><p>磁片磁碟機的加密狀態。 有效的狀態為 [已加密]、[未加密] 和 [加密]。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>合規性狀態</p></td>
<td align="left"><p>指出磁片磁碟機是否符合原則的狀態。 狀態為不相容且合規性。</p></td>
</tr>
<tr class="even">
<td align="left"><p>合規性狀態詳細資料</p></td>
<td align="left"><p>根據指定原則，電腦合規性狀態的錯誤與狀態訊息。</p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-recovery"></a>復原審核報告

使用此報告類型來審核已要求存取 BitLocker 復原金鑰的使用者。 報告根據所需的篩選準則提供數個篩選。 您可以篩選特定類型的使用者（技術支援人員或使用者）、是否已失敗或已成功、要求的特定金鑰類型，以及發生檢索的日期範圍。

**復原審核報告欄位**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">欄名稱</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>要求日期和時間</p></td>
<td align="left"><p>由最終使用者或技術支援人員使用者所做的金鑰檢索要求的日期和時間。</p></td>
</tr>
<tr class="even">
<td align="left"><p>審核要求來源</p></td>
<td align="left"><p>啟動要求的網站。 這個專案會有兩個值中的一個： <strong> 自助服務入口網站 </strong> 或 <strong> 支援人員 </strong> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>要求狀態</p></td>
<td align="left"><p>要求的狀態。 有效狀態為 [成功] （已檢索到金鑰），或失敗（未檢索到金鑰）。</p></td>
</tr>
<tr class="even">
<td align="left"><p>支援人員的使用者</p></td>
<td align="left"><p>已開始取得金鑰檢索要求的技術支援使用者。</p>
<div class="alert">
<strong>注意</strong><br/><p>如果 [高級支援人員] 使用者在不指定使用者的情況下就能修復金鑰，則 [ <strong> 使用者] </strong> 欄位會是空白的。 標準的支援人員使用者必須指定最終使用者，該使用者就會出現在此欄位中。</p>
<p>透過自助入口網站的復原將會在此欄位和 [使用者] 欄位中列出要求的最終使用者 <strong> </strong> 。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>使用者</p></td>
<td align="left"><p>已啟動金鑰取回要求的使用者。</p></td>
</tr>
<tr class="even">
<td align="left"><p>電腦</p></td>
<td align="left"><p>已復原電腦的電腦名稱稱。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>金鑰類型</p></td>
<td align="left"><p>技術支援人員使用者或使用者所要求的金鑰類型。 MBAM 收集的三種金鑰類型如下：</p>
<ul>
<li><p>復原金鑰密碼（用來在復原模式中復原電腦）</p></li>
<li><p>復原金鑰識別碼（用來代表另一個使用者在復原模式中復原電腦）</p></li>
<li><p>TPM 密碼雜湊（用於復原已鎖定的 TPM 的電腦）</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>原因描述</p></td>
<td align="left"><p>說明： [技術支援人員] 使用者或 [最終使用者] 要求指定的金鑰類型。 原因是在 [磁片磁碟機復原] 和 [管理及監視] 網站的 TPM 功能中指定。 有效的專案是使用者輸入的文字，或是下列其中一個原因代碼：</p>
<ul>
<li><p>作業系統啟動順序已變更</p></li>
<li><p>BIOS 已變更</p></li>
<li><p>已變更作業系統檔案</p></li>
<li><p>遺失的啟動金鑰</p></li>
<li><p>遺失的 PIN</p></li>
<li><p>TPM 重設</p></li>
<li><p>遺失密碼</p></li>
<li><p>遺失的智慧卡</p></li>
<li><p>重設 PIN 鎖定</p></li>
<li><p>開啟 TPM</p></li>
<li><p>關閉 TPM</p></li>
<li><p>變更 TPM 密碼</p></li>
<li><p>清除 TPM</p></li>
</ul></td>
</tr>
</tbody>
</table>



**注意**  
您可以按一下 [**報表**] 功能表列上的 [**匯出**] 按鈕，將報告結果儲存至檔案。




## 相關主題


[使用 MBAM 2.5 監視與報告 BitLocker 符合性](monitoring-and-reporting-bitlocker-compliance-with-mbam-25.md)

[產生 MBAM 2.5 獨立報告](generating-mbam-25-stand-alone-reports.md)



## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。 
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





