---
title: 瞭解 MBAM 報告
description: 瞭解 MBAM 報告
author: dansimp
ms.assetid: 34e4aaeb-7f89-41a1-b816-c6fe8397b060
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fa64a4724c87a42774e569b556013bfec2ed5514
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809614"
---
# 瞭解 MBAM 報告


Microsoft BitLocker 管理和監控（MBAM）會產生各種報告，以監控 BitLocker 使用量與合規性。 本主題說明適用于企業合規性、個別電腦、硬體相容性及金鑰復原活動的 MBAM 報告。

## 瞭解報表


若要存取 MBAM 的報告功能，請開啟 MBAM 管理網站。 選取 [功能窗格] 中的 [**報表**]。 接著，在 [主要內容] 窗格中，按一下您報表類型的索引標籤：**企業規範報告**、**電腦合規性報告**、**硬體審核報告**，或復原**審核報告**。

### 企業合規性報告

企業合規性報告提供貴組織中的整體 BitLocker 合規性資訊。 此報告可用的篩選器可讓您根據合規性狀態和錯誤狀態來縮小搜尋結果。 此報告每6小時執行一次。

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
<td align="left"><p>由 MBAM 管理的使用者指定 DNS 名稱。</p></td>
</tr>
<tr class="even">
<td align="left"><p>網功能變數名稱稱</p></td>
<td align="left"><p>用戶端電腦所在的完整功能變數名稱，且由 MBAM 管理。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>合規性狀態</p></td>
<td align="left"><p>根據電腦所指定的原則，為電腦規範的狀態。 可能的狀態是不相容且合規性。 如需詳細資訊，請參閱本主題中的企業合規性報告合規性狀態。</p></td>
</tr>
<tr class="even">
<td align="left"><p>免除</p></td>
<td align="left"><p>電腦硬體的狀態，決定硬體類型的識別，以及電腦是否免除原則。 有三種可能的狀態：硬體未知（MBAM 未辨識硬體類型）、硬體免除（硬體類型已識別且已標示為不受 MBAM 原則的免除），而且不會免除（硬體已識別且不會免除原則）。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>裝置使用者</p></td>
<td align="left"><p>由 MBAM 管理的電腦上的已知使用者。</p></td>
</tr>
<tr class="even">
<td align="left"><p>合規性狀態詳細資料</p></td>
<td align="left"><p>符合指定原則之電腦合規性狀態的錯誤與狀態訊息。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>最後一個連絡人</p></td>
<td align="left"><p>電腦上次與伺服器聯繫以報告合規性狀態的日期和時間。 這次是可設定的。 請參閱 MBAM 原則設定。</p></td>
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
<td align="left"><p>根據指定的原則，電腦不相容，且未以策略免除該硬體類型。</p></td>
<td align="left"><p>按一下 [ <strong> 電腦名稱稱] </strong> ，展開電腦合規性報告，並判斷每個磁片磁碟機的狀態是否符合指定的原則。 如果加密狀態指出電腦未加密，可能仍在進行加密，或電腦上可能有錯誤。 如果沒有錯誤，可能是因為電腦仍在連線或建立加密狀態的進程中。 稍後再次查看以判斷狀態是否變更。</p></td>
</tr>
<tr class="even">
<td align="left"><p>達到</p></td>
<td align="left"><p>未免除</p></td>
<td align="left"><p>根據指定的原則，電腦符合規範。</p></td>
<td align="left"><p>不需要任何動作。 您也可以選擇查看電腦合規性報告，以確認電腦的狀態。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>達到</p></td>
<td align="left"><p>硬體豁免</p></td>
<td align="left"><p>如果硬體類型是免除的。 不論原則設定如何，或是每個硬驅的個別狀態，整體狀態都被認為是合規性的。</p></td>
<td align="left"><p>不需要任何動作。</p></td>
</tr>
<tr class="even">
<td align="left"><p>達到</p></td>
<td align="left"><p>硬體未知</p></td>
<td align="left"><p>MBAM 會辨識硬體類型，但 MBAM 不知道它是不例外與否。 如果系統管理員沒有設定硬體的相容狀態，就會發生這種情況。 因此，MBAM 預設會還原為相容性狀態。</p></td>
<td align="left"><p>這是新部署的 MBAM 用戶端的初始狀態。 通常只有暫時狀態。 即使系統管理員已將硬體標示為相容，在用戶端電腦傳回報告前，可能會有很大的延遲或可設定的等待時間。 記下最後一個聯絡人的時間，然後在指定的間隔之後再次查看，以查看狀態是否已變更。 如果狀態沒有變更，此電腦或硬體類型可能會有錯誤。</p></td>
</tr>
</tbody>
</table>

 

### 電腦合規性報告

電腦合規性報告會顯示電腦或使用者專用的資訊。

電腦合規性報告會針對電腦上的每個磁片磁碟機提供詳細的加密資訊和適當的原則，包括操作系統磁碟機和固定資料磁碟機。 若要查看此報告類型，請在企業合規性報告中按一下電腦名稱稱，或在電腦合規性報告中輸入電腦名稱稱。 若要查看每個磁片磁碟機的詳細資料，請展開 [電腦名稱稱] 專案。

**記事** 此報告不會提供可移除資料量的加密狀態。

 

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
<td align="left"><p>電腦的可攜性類型。 有效類型為非便攜且可移植。</p></td>
</tr>
<tr class="even">
<td align="left"><p>作業系統</p></td>
<td align="left"><p>在 MBAM managed 用戶端電腦上安裝的作業系統類型。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>合規性狀態</p></td>
<td align="left"><p>由 MBAM 管理之電腦的整體合規性狀態。 有效的狀態是相容且不相容。 雖然您可以在同一部電腦中擁有相容且不相容的磁片磁碟機，但這個欄位會指出每個指定原則的電腦總體相容性。</p></td>
</tr>
<tr class="even">
<td align="left"><p>原則 Cypher 強度</p></td>
<td align="left"><p>MBAM 原則規格期間管理員所選取的密碼強度。 例如，使用擴散器的128位</p></td>
</tr>
<tr class="odd">
<td align="left"><p>原則作業系統磁片磁碟機</p></td>
<td align="left"><p>指明 O/S 和保護器類型是否適用，是否需要加密。</p></td>
</tr>
<tr class="even">
<td align="left"><p>原則固定資料磁碟機</p></td>
<td align="left"><p>指出固定磁碟機是否需要加密。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>策略移除資料磁碟機</p></td>
<td align="left"><p>指出抽取式磁碟磁碟機是否需要加密。</p></td>
</tr>
<tr class="even">
<td align="left"><p>裝置使用者</p></td>
<td align="left"><p>提供電腦上已知使用者的身分識別。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>免除</p></td>
<td align="left"><p>指出電腦硬體類型是否可由 MBAM 辨識，如果已知，是否已將電腦指示為策略例外。 有三種狀態：硬體未知（MBAM 已找不到硬體類型）;硬體例外（硬體類型已識別且已標示為不受 MBAM 原則的免除）;而且不會免除（硬體已識別且不是從原則免除）。</p></td>
</tr>
<tr class="even">
<td align="left"><p>製造商</p></td>
<td align="left"><p>電腦製造商出現在電腦 BIOS 中的名稱。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>型號</p></td>
<td align="left"><p>電腦製造商模型名稱，顯示在電腦 BIOS 中。</p></td>
</tr>
<tr class="even">
<td align="left"><p>合規性狀態詳細資料</p></td>
<td align="left"><p>根據指定原則，電腦符合性狀態的錯誤與狀態訊息。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>最後一個連絡人</p></td>
<td align="left"><p>電腦上次取得伺服器以報告合規性狀態的日期和時間。 T</p></td>
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
<td align="left"><p>使用者指派給這個特定磁片磁碟機的電腦磁碟機盤符。</p></td>
</tr>
<tr class="even">
<td align="left"><p>磁片磁碟機類型</p></td>
<td align="left"><p>磁片磁碟機類型。 有效值為作業系統磁片磁碟機及固定資料磁片磁碟機。 這些是物理磁片磁碟機，而不是邏輯磁片磁碟機。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Cypher 強度</p></td>
<td align="left"><p>管理員在 MBAM 原則規格期間選取的密碼強度。</p></td>
</tr>
<tr class="even">
<td align="left"><p>保護器類型</p></td>
<td align="left"><p>透過用來加密作業系統或固定容量的原則所選取的保護者類型。 作業系統磁片磁碟機上的有效保護器類型為 [TPM] 或 [TPM + PIN]。 固定資料量的唯一有效保護器類型為 [密碼]。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>保護器狀態</p></td>
<td align="left"><p>此欄位會指出電腦是否已啟用原則中指定的保護器類型。 [有效] 狀態為 [開啟] 或 [關閉]。</p></td>
</tr>
<tr class="even">
<td align="left"><p>加密狀態</p></td>
<td align="left"><p>這是磁片的目前加密狀態。 有效的狀態為 [已加密]、[未加密] 和 [加密]。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>合規性狀態</p></td>
<td align="left"><p>指出磁片磁碟機是否符合原則。 狀態為不相容且合規性。</p></td>
</tr>
<tr class="even">
<td align="left"><p>合規性狀態詳細資料</p></td>
<td align="left"><p>包含有關電腦合規性狀態的錯誤與狀態訊息。</p></td>
</tr>
</tbody>
</table>

 

### 硬體審計報告

此報告可協助您審核對特定電腦產生與模型的硬體相容性狀態所做的變更。 為了協助您縮小搜尋結果的範圍，此報告包含篩選準則的篩選，例如變更類型和時間發生的時間。 每個狀態變更都是依使用者及日期和時間進行追蹤。 硬體類型是由在用戶端電腦上執行的 MBAM 代理程式自動填入。 此報告會追蹤使用者對從 MBAM managed 電腦直接收集之資訊所做的變更。 典型的管理變更是從 [相容性] 變更為 [不相容]。 不過，系統管理員也可以修改任何欄位。

**硬體審計報告欄位**

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
<td align="left"><p>日期及時間</p></td>
<td align="left"><p>對硬體類型進行變更的日期和時間。 請注意，每個唯一的硬體類型都指派給至少一個專案。</p></td>
</tr>
<tr class="even">
<td align="left"><p>使用者</p></td>
<td align="left"><p>已針對特定專案進行變更的管理使用者。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>變更類型</p></td>
<td align="left"><p>對硬體類型資訊所做的變更類型。 有效值為加法（新增專案）、更新（變更現有專案）或刪除（移除現有的專案）。</p></td>
</tr>
<tr class="even">
<td align="left"><p>原始值</p></td>
<td align="left"><p>變更之前的硬體類型規格值。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>目前值</p></td>
<td align="left"><p>變更之後硬體類型規格的值。</p></td>
</tr>
</tbody>
</table>

 

### 復原審核報告

[恢復審核報告] 可協助您審核已要求存取復原金鑰的使用者。 此報告的篩選準則包括提出要求的使用者類型、要求的金鑰類型、發生時間、成功或失敗、發生時間及使用者要求的類型（說明服務台、最終使用者）。 此報告可讓系統管理員根據需要產生內容報告。

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
<td align="left"><p>要求的狀態。 有效狀態為成功（檢索到金鑰）或失敗（未檢索到金鑰）。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>支援人員的使用者</p></td>
<td align="left"><p>啟動金鑰取回要求的技術支援使用者。 如果技術支援人員代表使用者自行取得金鑰，則 [最終使用者] 欄位會是空白的。</p></td>
</tr>
<tr class="even">
<td align="left"><p>使用者</p></td>
<td align="left"><p>已啟動金鑰取回要求的最終使用者。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>金鑰類型</p></td>
<td align="left"><p>所要求的金鑰類型。 MBAM 會收集三個主要類型：復原金鑰密碼（在復原模式中復原電腦）;復原金鑰識別碼（代表另一個使用者在復原模式中復原電腦）;以及受信任的平臺模組（TPM）密碼雜湊（使用已鎖定的 TPM 復原電腦）。</p></td>
</tr>
<tr class="even">
<td align="left"><p>原因描述</p></td>
<td align="left"><p>要求指定的金鑰類型的原因。 原因是在系統管理網站的 [磁碟機復原] 和 [管理 TPM 功能] 中指定。 有效的專案包括使用者輸入的文字或下列其中一個原因代碼：</p>
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
</ul>
<p></p></td>
</tr>
</tbody>
</table>

 

**記事** 若要將報表結果儲存至檔案，請按一下 [報表] 功能表列上的 [**匯出**] 按鈕。

 

## 相關主題


[使用 MBAM 1.0 監視與報告 BitLocker 符合性](monitoring-and-reporting-bitlocker-compliance-with-mbam-10.md)

 

 





