---
title: 規劃從舊版 App-V 移轉
description: 規劃從舊版 App-V 移轉
author: dansimp
ms.assetid: 4a058047-9674-41bc-8050-c58c97a80a9b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: d7f2496b355aee6a598fee44c84e7e8c0f755c4f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800351"
---
# 規劃從舊版 App-V 移轉


使用下列資訊來規劃如何從舊版 App-v 升級到 Microsoft Application Virtualization （App-v）5.1。

## 遷移需求


開始進行任何升級前，請先檢查下列需求：

-   如果您要從 App-v 4.6 SP2 之前的版本進行升級，請先升級到版本 App-V 4.6 SP3，再升級到 App-v 5.1 或更新版本。 在這種情況下，請先升級 App-v 用戶端，然後再升級伺服器元件。
**注意：** App-V 4.6 已退出主流支援。

-   App-v 5.1 只支援使用 5.0 App-v、app-v 5.1 或已轉換為**appv**格式的套件所建立的套件。

-   如果您要從 App-v 5.0 SP1 升級 app-v Server，請參閱[關於 app-v 5.1](about-app-v-51.md#bkmk-migrate-to-51)以取得相關指示。

## 同時執行 App-v 5.1 用戶端與 app-v 4。6


您可以在使用 App-v 4.6 SP3 用戶端的同一台電腦上同時執行 App-v 5.1 用戶端。

當您執行共存的 App-v 用戶端時，您可以：

-   當您同時執行兩個用戶端時，請將 App-v 4.6 SP3 套件轉換成 App-v 5.1 格式，併發布這兩個套件。

-   針對已轉換的套件定義遷移原則，以允許已轉換的 app-v 5.1 套件假設來自 App-v 4.6 套件的檔案類型關聯和快速鍵。

### 支援的共存案例

下表顯示受支援的 App-v 共存案例。 我們建議您在執行共存的用戶端時，安裝特定發行的最新可用更新。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">App-v 4.6 用戶端類型</th>
<th align="left">App-v 5.1 用戶端類型</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>App-V 4.6 SP3</p></td>
<td align="left"><p>App-V 5.1</p></td>
</tr>
<tr class="even">
<td align="left"><p>App-V 4.6 SP3 RDS</p></td>
<td align="left"><p>App-v 5.1 RDS</p></td>
</tr>
</tbody>
</table>

 

### 運行共存用戶端的需求

若要執行共存的用戶端，您必須：

-   安裝 App-v 4.6 用戶端，然後再安裝應用程式-V 5.1 用戶端。

-   啟用**App-V**用戶端共存節點中的 [**啟用移轉模式]** 群組原則設定 &gt; **Client Coexistence** 。 若要部署 admx 範本，請參閱[如何下載和部署 MDOP 組原則（admx）範本](https://technet.microsoft.com/library/dn659707.aspx)。

**記事** 如果您的 App-v 5.1 和4.6 安裝不共存，app-v 5.1 套件可以並存執行，以進行 app-v 4.6 套件。 不過，App-v 5.1 套件無法與相同虛擬環境中的 App-v 4.6 套件互動。

 

### 用戶端下載和檔

下表提供 App-V 4.6 用戶端下載，以及有關發行版本本的 TechNet 檔的連結。 下載內容包括 App-v "regular" 和 RDS 用戶端。 除非另行說明，否則應用程式-V 用戶端的 TechNet 檔會套用至這兩個用戶端。

<table>
<colgroup>
<col width="33%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">App-V 版本</th>
<th align="left">連結至 TechNet 檔</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>App-V 4.6 SP3</p></td>
<td align="left"><p><a href="https://technet.microsoft.com/library/dn511019.aspx" data-raw-source="[About Microsoft Application Virtualization 4.6 SP3](https://technet.microsoft.com/library/dn511019.aspx)">關於 Microsoft Application Virtualization 4.6 SP3</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>App-V 4.6 SP3</p></td>
<td align="left"><p><a href="about-app-v-51.md" data-raw-source="[About Microsoft Application Virtualization 5.1](about-app-v-51.md)">關於 Microsoft Application Virtualization 5。1</a></p></td>
</tr>
</tbody>
</table>

 

如需如何設定 App-V 5.1 用戶端共存的詳細資訊，請參閱：

-   [如何在同一部電腦上部署 app-v 4.6 和 App-v 5.1 用戶端](how-to-deploy-the-app-v-46-and-the-app-v--51-client-on-the-same-computer.md)

-   [App-v 5.0 共存與遷移](https://technet.microsoft.com/windows/jj835811.aspx)

## <a href="" id="converting--previous-version--packages-using-the-package-converter-"></a>使用套件轉換器轉換「舊版本」套件


將使用 App 4.6 SP2 或較舊版本的套件建立到 App-v 5.1 之前，請先查看下列需求：

-   您必須將套件轉換為**appv**檔案格式。

-   套件轉換器只支援使用 App-v 4.5 和更新版本所建立之套件的直接轉換。 若要在使用舊版本建立的套件上使用套件轉換器，您必須使用 sequencer 或更新版本的 sequencer 來升級套件，然後您就可以執行套件轉換。

如需使用套件轉換器轉換套件的詳細資訊，請參閱[如何轉換在舊版 app-v 中建立的套件](how-to-convert-a-package-created-in-a-previous-version-of-app-v51.md)。 轉換檔案之後，您可以將它部署到執行 App-v 5.1 用戶端的目的電腦。






## 相關主題


[規劃部署 App-V](planning-to-deploy-app-v51.md)

 

 





