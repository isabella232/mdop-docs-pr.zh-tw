---
title: 瞭解 MBAM 報告
description: 瞭解 MBAM 報告
author: dansimp
ms.assetid: 8778f333-760e-4f26-acb4-4e73b6fbb536
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3c3ca5e4da4cbcea80c87520f0ecd05e1e7d6be0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810179"
---
# 瞭解 MBAM 報告


如果您在安裝 Microsoft BitLocker 管理和監控（MBAM）時選擇獨立拓撲，您可以在 MBAM 中執行不同的報告，以監控 BitLocker 使用量與合規性。 MBAM 報告合規性，以及其所管理之所有電腦和裝置的其他相關資訊。 本主題中的資訊可用來協助您瞭解企業及個別電腦相容性的 Microsoft BitLocker 管理和監控報告，以及主要的復原活動。

**記事** 如果您在安裝 Microsoft BitLocker 管理和監控（MBAM）時選擇 Configuration Manager 拓撲，則會從 Configuration Manager 而不是從 MBAM 產生報告。 如需從 Configuration Manager 執行之報告的詳細資訊，請參閱[在 Configuration manager 中瞭解 MBAM 報告](understanding-mbam-reports-in-configuration-manager.md)。

 

## 瞭解報表


若要存取 Microsoft BitLocker 管理和監控的報告功能，請開啟網頁瀏覽器，然後開啟 [管理與監控] 網站。 選取左側功能表列中的 [**報表**]，然後從頂端功能表列選取您要產生的報表類型。

### 企業合規性報告

使用此報告類型，收集貴組織中的整體 BitLocker 合規性的相關資訊。 您可以使用不同的篩選，將搜尋結果縮小至合規性狀態和錯誤狀態。 報告資訊每6小時更新一次。

**企業合規性報告欄位**

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
<td align="left"><p>由 MBAM 管理的使用者指定的 DNS 名稱。</p></td>
</tr>
<tr class="even">
<td align="left"><p>網功能變數名稱稱</p></td>
<td align="left"><p>用戶端電腦所在的完整功能變數名稱，且由 MBAM 管理。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>合規性狀態</p></td>
<td align="left"><p>根據電腦所指定的原則，為電腦提供符合的狀態。 狀態是不相容且合規性。 如需有關如何解讀合規性狀態的詳細資訊，請參閱企業合規性報告合規性狀態資料表。</p></td>
</tr>
<tr class="even">
<td align="left"><p>合規性狀態詳細資料</p></td>
<td align="left"><p>根據指定原則，電腦符合性狀態的錯誤與狀態訊息。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>最後一個連絡人</p></td>
<td align="left"><p>電腦上次與伺服器聯繫以報告合規性狀態的日期和時間。 連絡人頻率可設定（請參閱 MBAM 原則設定）。</p></td>
</tr>
</tbody>
</table>

 

**企業合規性報告合規性狀態**

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">合規性狀態</th>
<th align="left">免除</th>
<th align="left">描述</th>
<th align="left">使用者動作</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>標準</p></td>
<td align="left"><p>未免除</p></td>
<td align="left"><p>根據指定的原則，電腦是不相容的。</p></td>
<td align="left"><p>按一下 [ <strong> 電腦名稱稱] </strong> ，並判斷每個磁片磁碟機的狀態是否符合指定原則，以展開電腦合規性報告詳細資料。 如果加密狀態指出電腦未加密，可能正在進行加密，或電腦上出現錯誤。 如果沒有錯誤，可能是因為電腦仍在連線或建立加密狀態的進程中。 稍後再次查看以判斷狀態是否變更。</p></td>
</tr>
<tr class="even">
<td align="left"><p>達到</p></td>
<td align="left"><p>未免除</p></td>
<td align="left"><p>根據指定的原則，電腦符合規範。</p></td>
<td align="left"><p>不需要任何動作;您可以透過查看電腦合規性報告來確認電腦的狀態。</p></td>
</tr>
</tbody>
</table>

 

### 電腦合規性報告

使用此報告類型可收集電腦或使用者專用的資訊。

您可以按一下企業合規性報告中的電腦名稱稱，或在電腦合規性報告中輸入電腦名稱稱，以查看此報告。 電腦合規性報告提供電腦上每個磁片磁碟機（作業系統及固定資料磁碟機）的詳細加密資訊，以及針對電腦上的每個磁片磁碟機類型所套用的原則的指示。 若要查看每個磁片磁碟機的詳細資料，請展開 [電腦名稱稱] 專案。

**記事** 在報告中不會顯示 [可移動資料量] 加密狀態。

 

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
<td align="left"><p>用戶端電腦駐留且由 MBAM 管理的完整功能變數名稱。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>電腦類型</p></td>
<td align="left"><p>電腦類型。 有效類型為非便攜且可移植。</p></td>
</tr>
<tr class="even">
<td align="left"><p>作業系統</p></td>
<td align="left"><p>在 MBAM 管理的用戶端電腦上找到的作業系統類型。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>合規性狀態</p></td>
<td align="left"><p>由 MBAM 管理之電腦的整體合規性狀態。 有效的狀態是相容且不相容。 請注意，每個磁片磁碟機的相容性狀態（請參閱下表）可能表示不同的合規性狀態。 不過，這個欄位會根據指定的原則代表符合性狀態。</p></td>
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
<td align="left"><p>製造商</p></td>
<td align="left"><p>電腦製造商名稱，如電腦 BIOS 所示。</p></td>
</tr>
<tr class="even">
<td align="left"><p>型號</p></td>
<td align="left"><p>電腦製造商模型名稱，如電腦 BIOS 所示。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>合規性狀態詳細資料</p></td>
<td align="left"><p>符合指定原則的電腦合規性狀態的錯誤與狀態訊息。</p></td>
</tr>
<tr class="even">
<td align="left"><p>最後一個連絡人</p></td>
<td align="left"><p>電腦上次取得伺服器以報告合規性狀態的日期和時間。 連絡人頻率可設定（請參閱 MBAM 原則設定）。</p></td>
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
<td align="left"><p>透過用來加密作業系統或固定資料量的原則所選取的保護者類型。</p></td>
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

 

### 復原審核報告

使用此報告類型來審核已要求存取復原金鑰的使用者。 報告根據所需的篩選準則提供數個篩選。 使用者可以篩選特定類型的使用者（無論是技術支援人員的使用者或使用者）、要求失敗或已成功、所要求的特定金鑰類型，以及發生檢索的日期範圍。 系統管理員可以根據需要產生相關的報告。

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
<td align="left"><p>要求狀態</p></td>
<td align="left"><p>要求的狀態。 有效狀態為 [成功] （已檢索到金鑰），或失敗（未檢索到金鑰）。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>支援人員的使用者</p></td>
<td align="left"><p>已啟動金鑰檢索要求的技術支援使用者。 注意：如果技術支援人員的使用者是代表最終使用者來檢索索引鍵，則 [使用者] 欄位會是空白的。</p></td>
</tr>
<tr class="even">
<td align="left"><p>使用者</p></td>
<td align="left"><p>已啟動金鑰取回要求的使用者。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>金鑰類型</p></td>
<td align="left"><p>技術支援人員使用者或使用者所要求的金鑰類型。 MBAM 收集的三種金鑰類型有：復原金鑰密碼（用來在復原模式中復原電腦）、復原金鑰識別碼（用來以其他使用者的復原模式復原電腦），以及 TPM 密碼雜湊（用來復原已鎖定的 TPM 的電腦）。</p></td>
</tr>
<tr class="even">
<td align="left"><p>原因描述</p></td>
<td align="left"><p>說明： [技術支援人員] 使用者或 [最終使用者] 要求指定的金鑰類型。 原因是在 [磁片磁碟機復原] 和 [管理及監視] 網站的 TPM 功能中指定。 有效的專案為使用者輸入的文字，或下列其中一個原因代碼：</p>
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

 

**記事** 您可以按一下 [報表] 功能表列上的 [**匯出**] 按鈕，將報告結果儲存至檔案。 如需如何執行 MBAM 報告的詳細資訊，請參閱[如何產生 MBAM 報告](how-to-generate-mbam-reports-mbam-2.md)。

 

## 相關主題


[使用 MBAM 2.0 監視與報告 BitLocker 符合性](monitoring-and-reporting-bitlocker-compliance-with-mbam-20-mbam-2.md)

 

 





