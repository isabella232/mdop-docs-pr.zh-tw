---
title: 檢視 Configuration Manager 整合拓撲的 MBAM 2.5 報告
description: 檢視 Configuration Manager 整合拓撲的 MBAM 2.5 報告
author: dansimp
ms.assetid: 60d11b2f-3a76-4023-8da4-f89e9f35b790
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3384fee62d302ac47775fe106265456ef119ab47
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810317"
---
# 檢視 Configuration Manager 整合拓撲的 MBAM 2.5 報告


本主題說明當您將 Microsoft BitLocker 管理和監控（MBAM）與 Configuration Manager 整合拓撲進行設定時，可用的報告。 報告會顯示企業及 MBAM 管理的個別電腦和裝置的 BitLocker 合規性。 報告提供表格式資訊和圖表，而且這些篩選可讓您從不同的觀點來查看資料。

在 Configuration Manager 整合拓撲中，您可以從 Configuration Manager （而不是從 [管理] 和 [監視] 網站）來查看報表，除了 [**恢復審核] 報告**以外，您還會從 [管理] 和 [監視] 網站繼續進行查看。

如需獨立拓朴 MBAM 報告的相關資訊，請參閱[針對獨立拓朴查看 MBAM 2.5 報告](viewing-mbam-25-reports-for-the-stand-alone-topology.md)。

## 在 Configuration Manager 中存取報表


若要存取 Configuration Manager 中的 [報表] 功能：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Configuration Manager 版本</th>
<th align="left">如何查看報表</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>SystemCenter2012 ConfigurationManager</p></td>
<td align="left"><ol>
<li><p>在左窗格中，選取 [ <strong> 監視] </strong> 工作區。</p></li>
<li><p>在樹狀結構中，展開 <strong> [總覽報表 </strong> &gt; <strong> </strong> &gt; <strong> 報告] </strong> &gt; <strong> MBAM </strong> 。</p></li>
<li><p>選取代表您要用來查看報表之語言的資料夾，然後從右窗格中選取報表。</p></li>
</ol></td>
</tr>
<tr class="even">
<td align="left"><p>Configuration Manager 2007</p></td>
<td align="left"><ol>
<li><p>在左窗格中，展開 [ <strong> 電腦管理 </strong> &gt; <strong> 報告 </strong> &gt; <strong> 服務] </strong> &gt; <strong> &lt; 伺服器名稱 &gt; </strong> &gt; <strong> 報告資料夾 </strong> &gt; <strong> MBAM </strong> 。</p></li>
<li><p>選取代表您要用來查看報表之語言的資料夾，然後從右窗格中選取報表。</p></li>
</ol></td>
</tr>
</tbody>
</table>

 

## Configuration Manager 中的報表描述


Configuration Manager 整合拓朴與獨立拓朴的報告有幾項細微的差異。 下列各節說明 Configuration Manager 整合拓朴的 MBAM 報告中的資料：

-   [BitLocker Enterprise 合規性儀表板](#bkmk-dashboard)

-   [BitLocker 企業合規性詳細資料](#bkmk-compliancedetails)

-   [BitLocker Enterprise 合規性摘要](#bkmk-compliancesummary)

-   [BitLocker 電腦合規性報告](#bkmk-compliancereport)

### <a href="" id="bkmk-dashboard"></a>BitLocker Enterprise 合規性儀表板

BitLocker Enterprise 合規性儀表板提供下列圖表，在整個企業中顯示 BitLocker 合規性狀態：

-   合規性狀態發佈

-   不相容的錯誤發佈

-   依磁片磁碟機類型進行合規性狀態發佈

**合規性狀態發佈**

此圓形圖顯示企業內部電腦的合規性狀態。 它也會顯示電腦的百分比，與所選集合中擁有該符合性狀態之電腦總數的比較。 也會顯示每個狀態的實際電腦數。 圓形圖顯示下列合規性狀態：

-   達到

-   不符合

-   使用者豁免

-   暫時使用者豁免

-   未強制執行原則

-   清楚. 這些電腦報告狀態錯誤，或它們是集合的一部分，但從未報告其符合性狀態。 如果電腦斷開與組織的連線，則無法使用合規性狀態。

**不相容的錯誤發佈**

此圓形圖顯示企業中不符合 BitLocker 磁碟機加密原則的電腦類別，並顯示每個類別中的電腦數。 每個類別百分比是從集合中不相容電腦的總數計算而來。

-   使用者已延遲加密

-   找不到相容的 TPM

-   系統磁碟分割無法使用或太大

-   原則衝突

-   正在等待 TPM 自動預配

-   發生未知的錯誤

-   沒有任何資訊。 這些電腦沒有安裝 MBAM 用戶端，或已安裝 MBAM 用戶端，但尚未啟用（例如，服務無法運作）。

**依磁片磁碟機類型進行合規性狀態發佈**

此橫條圖顯示 [依磁片磁碟機類型列出目前的 BitLocker 合規性狀態]。 狀態**符合規範**且**不相容**。 會顯示 [固定資料磁碟機] 和 [作業系統磁片磁碟機] 的橫條圖。 包括沒有固定資料磁碟機的電腦，而且只會顯示**作業系統磁片磁碟機**列中的值。 圖表不包括已從 BitLocker 磁碟機加密原則或 [無原則] 類別獲授權的使用者。

### <a href="" id="bkmk-compliancedetails"></a>BitLocker 企業合規性詳細資料

此報告會在您的企業中顯示針對以 BitLocker 為目標的電腦集合的整個 BitLocker 規範的相關資訊。

**BitLocker 企業合規性詳細資料欄位**

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
<td align="left"><p>% 的未知規範</p></td>
<td align="left"><p>相容性狀態為未知的電腦所占的百分比。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>% 豁免</p></td>
<td align="left"><p>免除 BitLocker 加密需求的電腦所占的百分比。</p></td>
</tr>
<tr class="even">
<td align="left"><p>非豁免%</p></td>
<td align="left"><p>不受 BitLocker 加密需求免除的電腦百分比。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>達到</p></td>
<td align="left"><p>企業中合規性電腦的百分比。</p></td>
</tr>
<tr class="even">
<td align="left"><p>不相容</p></td>
<td align="left"><p>企業中不相容的電腦百分比。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>未知的合規性</p></td>
<td align="left"><p>相容性狀態為未知的電腦所占的百分比。</p></td>
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

 

**BitLocker Enterprise 合規性詳細資料狀態**

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">合規性狀態</th>
<th align="left">免除</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>標準</p></td>
<td align="left"><p>未免除</p></td>
<td align="left"><p>根據指定的原則，電腦是不相容的。</p></td>
</tr>
<tr class="even">
<td align="left"><p>達到</p></td>
<td align="left"><p>未免除</p></td>
<td align="left"><p>根據指定的原則，電腦符合規範。</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="bkmk-compliancesummary"></a>BitLocker Enterprise 合規性摘要

您可以使用此報告類型來顯示整個企業的 BitLocker 合規性相關資訊，以及顯示針對 BitLocker 使用之電腦集合中的個別電腦的相容性。

**BitLocker Enterprise 合規性摘要欄位**

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
<td align="left"><p>% 的未知規範</p></td>
<td align="left"><p>相容性狀態為未知的電腦所占的百分比。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>% 豁免</p></td>
<td align="left"><p>免除 BitLocker 加密需求的電腦所占的百分比。</p></td>
</tr>
<tr class="even">
<td align="left"><p>非豁免%</p></td>
<td align="left"><p>不受 BitLocker 加密需求免除的電腦百分比。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>達到</p></td>
<td align="left"><p>企業中合規性電腦的百分比。</p></td>
</tr>
<tr class="even">
<td align="left"><p>不相容</p></td>
<td align="left"><p>企業中不相容的電腦百分比。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>未知的合規性</p></td>
<td align="left"><p>相容性狀態為未知的電腦所占的百分比。</p></td>
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

 

**BitLocker Enterprise 合規性摘要電腦詳細資料**

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
<td align="left"><p>用戶端電腦駐留且由 MBAM 管理的完整功能變數名稱。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>合規性狀態</p></td>
<td align="left"><p>由 MBAM 管理之電腦的整體合規性狀態。 有效的狀態是相容且不相容。 請注意，每個磁片磁碟機的相容性狀態（請參閱後面的資料表）可能會指出不同的合規性狀態。 不過，這個欄位會根據指定的原則來代表符合性狀態。</p></td>
</tr>
<tr class="even">
<td align="left"><p>免除</p></td>
<td align="left"><p>此狀態表示使用者是否已免除或未免除 BitLocker 原則。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>裝置使用者</p></td>
<td align="left"><p>裝置的使用者。</p></td>
</tr>
<tr class="even">
<td align="left"><p>合規性狀態詳細資料</p></td>
<td align="left"><p>符合指定原則之電腦符合性狀態的錯誤與狀態訊息。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>最後一個連絡人</p></td>
<td align="left"><p>電腦上次取得伺服器以報告合規性狀態的日期和時間。 連絡人頻率可透過 [群組原則] 設定進行設定。</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="bkmk-compliancereport"></a>BitLocker 電腦合規性報告

使用此報告類型可收集電腦專用的資訊。 BitLocker 電腦合規性報告提供電腦上每個磁片磁碟機的詳細加密資訊（作業系統及固定資料磁碟機）。 它也會提供應用於電腦上每個磁片磁碟機類型的原則的指示。 若要查看每個磁片磁碟機的詳細資料，請展開 [電腦名稱稱] 專案。

**記事** 此報告中不會顯示 [移除資料量] 加密狀態。

 

**BitLocker 電腦合規性報告： [電腦詳細資料] 欄位**

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
<td align="left"><p>用戶端電腦駐留且由 MBAM 管理的完整功能變數名稱。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>電腦類型</p></td>
<td align="left"><p>電腦類型。 有效類型為非便攜且可移植。</p></td>
</tr>
<tr class="even">
<td align="left"><p>作業系統</p></td>
<td align="left"><p>在 MBAM managed 用戶端電腦上找到的作業系統類型。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>整體合規性</p></td>
<td align="left"><p>由 MBAM 管理之電腦的整體合規性狀態。 有效的狀態是相容且不相容。 請注意，每個磁片磁碟機的相容性狀態（請參閱後面的資料表）可能會指出不同的合規性狀態。 不過，這個欄位會根據指定的原則來代表符合性狀態。</p></td>
</tr>
<tr class="even">
<td align="left"><p>作業系統合規性</p></td>
<td align="left"><p>由 MBAM 管理之作業系統的合規性狀態。 有效的狀態是相容且不相容。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>固定資料磁碟機合規性</p></td>
<td align="left"><p>由 MBAM 管理的固定資料磁碟機的合規性狀態。 有效的狀態是相容且不相容。</p></td>
</tr>
<tr class="even">
<td align="left"><p>上次更新日期</p></td>
<td align="left"><p>電腦上次取得伺服器以報告合規性狀態的日期和時間。 連絡人頻率可透過 [群組原則] 設定進行設定。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>免除</p></td>
<td align="left"><p>此狀態表示使用者是否已免除或未免除 BitLocker 原則。</p></td>
</tr>
<tr class="even">
<td align="left"><p>免除的使用者</p></td>
<td align="left"><p>從 BitLocker 原則免除的使用者。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>免除日期</p></td>
<td align="left"><p>授與免除的日期。</p></td>
</tr>
<tr class="even">
<td align="left"><p>合規性狀態詳細資料</p></td>
<td align="left"><p>符合指定原則之電腦符合性狀態的錯誤與狀態訊息。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>原則密碼強度</p></td>
<td align="left"><p>系統管理員在 MBAM 原則規格期間選取的密碼強度（例如，使用擴散器的128位）。</p></td>
</tr>
<tr class="even">
<td align="left"><p>原則：作業系統磁片磁碟機</p></td>
<td align="left"><p>表示作業系統是否需要加密，以及適當的保護器類型。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>原則：固定資料磁片磁碟機</p></td>
<td align="left"><p>表示固定資料磁碟機是否需要加密。</p></td>
</tr>
<tr class="even">
<td align="left"><p>製造商</p></td>
<td align="left"><p>電腦製造商出現在電腦 BIOS 中的名稱。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>型號</p></td>
<td align="left"><p>電腦製造商模型名稱，如電腦 BIOS 中所示。</p></td>
</tr>
<tr class="even">
<td align="left"><p>裝置使用者</p></td>
<td align="left"><p>由 MBAM 管理的電腦上的已知使用者。</p></td>
</tr>
</tbody>
</table>

 

**BitLocker 電腦合規性報告： [電腦卷] 欄位**

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
<td align="left"><p>透過用來加密作業系統或固定資料磁碟機之原則所選取的保護者類型。 作業系統的有效保護器類型為 [TPM] 或 [TPM + PIN]。 固定資料磁碟機的有效保護器類型是密碼。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>保護器狀態</p></td>
<td align="left"><p>指示由 MBAM 管理的電腦已啟用原則中指定的保護器類型。 [有效] 狀態為 [開啟] 或 [關閉]。</p></td>
</tr>
<tr class="even">
<td align="left"><p>加密狀態</p></td>
<td align="left"><p>磁片磁碟機的加密狀態。 有效的狀態為 [已加密]、[未加密] 和 [加密]。</p></td>
</tr>
</tbody>
</table>

 

## 相關主題


[使用 MBAM 2.5 監視與報告 BitLocker 符合性](monitoring-and-reporting-bitlocker-compliance-with-mbam-25.md)

 

## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。 
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





