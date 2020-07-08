---
title: APP-V 5.0 的新功能
description: APP-V 5.0 的新功能
author: dansimp
ms.assetid: 79ff6e02-e926-4803-87d8-248a6b28099d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dabe264f033bd5c9897f07d931f799a42e6b72e9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800289"
---
# APP-V 5.0 的新功能


本節適用于已熟悉 App-v 的使用者，並且想要知道 App-V 5.0 中已變更的內容（如果您還不熟悉 App-v），請先閱讀[針對 app-v 5.0 的規劃規劃](planning-for-app-v-50-rc.md)。

## 標準功能的變更


下列各節包含 App-v 5.0 標準功能變更的相關資訊。

### 支援的作業系統變更

如需詳細資訊，請參閱[App-V 5.0 支援的](app-v-50-supported-configurations.md)設定。

## 排序器的變更


下列各節包含 App-v 5.0 排序器中變更的相關資訊。

### 排序器的特定變更

下表顯示有關 App-v 5.0 sequencer 所做的變更的相關資訊

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Sequencer 功能</th>
<th align="left">App-v 5.0 Sequencer 功能</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>重新開機處理</p></td>
<td align="left"><p>當應用程式提示重新開機時，您應該允許應用程式重新開機執行排序器的電腦。 執行排序器的電腦將會重新開機，且 sequencer 將會在 [監視] 模式中繼續。</p></td>
</tr>
<tr class="even">
<td align="left"><p>指定虛擬應用程式目錄</p></td>
<td align="left"><p>虛擬應用程式目錄是強制性參數。 為了獲得最佳結果，它應該符合應用程式安裝程式的安裝目錄。 這會產生更佳的效能和應用程式相容性。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>編輯快速鍵/FTAs</p></td>
<td align="left"><p>[快捷方式/FTA] 頁面位於 <strong> [ </strong> 排序嚮導] 完成後的 [高級編輯] 頁面上。</p></td>
</tr>
<tr class="even">
<td align="left"><p>變更歷程記錄索引標籤</p></td>
<td align="left"><p>App-V 5.0 已移除 [變更記錄] 索引標籤。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>OSD 索引標籤</p></td>
<td align="left"><p>已移除 App-v 5.0 的 [OSD] 索引標籤。</p></td>
</tr>
<tr class="even">
<td align="left"><p>虛擬服務索引標籤</p></td>
<td align="left"><p>App-V 5.0 已移除 [虛擬服務] 索引標籤。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>[檔案/虛擬檔案系統] 索引標籤</p></td>
<td align="left"><p>這些索引標籤會結合，並可讓您修改套件檔案。</p></td>
</tr>
<tr class="even">
<td align="left"><p>部署索引標籤</p></td>
<td align="left"><p>在套件中，沒有更長的選項可供您設定伺服器 URL。 您應該使用部署設定或管理伺服器來立即進行設定。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>封裝轉換器工具</p></td>
<td align="left"><p>您現在可以使用 PowerShell 來轉換在先前版本中建立的套件。</p></td>
</tr>
<tr class="even">
<td align="left"><p>附加元件/中介軟體</p></td>
<td align="left"><p>您可以在排序附加元件或中介軟體應用程式時，展開上層套件。 附加元件和中介軟體套件必須使用 App-v 5.0 中的連線群組進行連線。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>檔案輸出</p></td>
<td align="left"><p>下列檔案是使用 App-v 5.0、Windows Installer （.msi）、appv、部署配置、使用者設定及 Report.XML 建立。</p></td>
</tr>
<tr class="even">
<td align="left"><p>壓縮/安全性描述項/MSI 套件</p></td>
<td align="left"><p>壓縮和建立 Windows 安裝程式（.msi）檔案在所有套件中都是自動的，而且您不能再覆寫安全描述項。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>[工具]/[選項]</p></td>
<td align="left"><p>[診斷程式] 視窗已移除，以及幾個其他設定。</p></td>
</tr>
<tr class="even">
<td align="left"><p>安裝磁片磁碟機</p></td>
<td align="left"><p>安裝應用程式時，已不再需要安裝磁片磁碟機。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>OOS 串流</p></td>
<td align="left"><p>如果未執行任何資料流程優化，則在執行 App-v 5.0 用戶端的電腦要求資料包啟動前，套件會以資料流程的方式發生故障。</p></td>
</tr>
<tr class="even">
<td align="left"><p>問： &lt; /p&gt;</td>
<td align="left"><p>App-v 5.0 使用原生檔案系統，不再需要 Q:。</p></td>
</tr>
</tbody>
</table>

 

## 排序錯誤偵測


App-v 5.0 排序器可以在排序期間檢測一般的順序問題。 [順序] 嚮導末端的 [**安裝報告**] 頁面會根據問題的嚴重性，顯示分類為**錯誤**、**警告**及**資訊**的診斷訊息。

若要顯示事件的詳細資訊，請按兩下您要在報表中查看的專案。 先後順序問題，以及如何解決問題的相關建議。 當您完成建立套件時，系統準備報告和安裝報告中的資訊都會匯總。 下列清單顯示報表中可用的問題類型：

-   已排除的檔案。

-   驅動程式資訊。

-   COM + 系統差異。

-   並列（SxS）衝突。

-   命令介面延伸。

-   不支援服務的相關資訊。

-   封鎖.

## 連線群組


先前稱為「**動態套件組合**」的 app-v 功能現在稱為 app-v 5.0 中的連線**群組**。 如需有關使用連接群組的詳細資訊，請參閱[管理連線群組](managing-connection-groups.md)。

## 授權與測定功能


應用程式和授權功能已在 App-v 5.0 中移除。 您環境中實際的授權位置，取決於相關授權條款所授的特定軟體標題授權和使用權利。

## 檔案和應用程式快取


App-v 5.0 沒有可用的檔案或應用程式快取。






## 相關主題


[關於 App-V 5.0](about-app-v-50.md)

 

 





