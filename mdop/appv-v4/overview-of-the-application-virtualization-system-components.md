---
title: Application Virtualization 系統元件概觀
description: Application Virtualization 系統元件概觀
author: dansimp
ms.assetid: 75d88ef7-44d8-4fa7-b7f5-9153f37e570d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cab0065b9966094da687cce2f5e94069922189fc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800942"
---
# Application Virtualization 系統元件概觀


下表說明 Microsoft Application Virtualization 管理系統的主要元件。 如需有關部署這些系統元件的詳細資訊，請參閱[應用程式虛擬化伺服器案例](application-virtualization-server-based-scenario.md)。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">元件</th>
<th align="left">函式</th>
<th align="left">其他資訊</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft Application Virtualization 管理伺服器</p></td>
<td align="left"><p>負責對流內容進行流式處理的元件，以及將快捷方式和檔案類型關聯發佈至應用程式虛擬化用戶端。</p></td>
<td align="left"><p>應用程式虛擬化管理伺服器支援作用中升級、授權管理，以及可用於報告的資料庫。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>內容 </strong> 資料夾</p></td>
<td align="left"><p>[流式處理] 應用程式虛擬化套件的位置。</p></td>
<td align="left"><p>這個資料夾可以位於應用程式虛擬化管理伺服器上的共用位置。 資料夾也可位於儲存區域網路（SAN）上。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft Application Virtualization 管理主控台</p></td>
<td align="left"><p>適用于 Microsoft Application Virtualization Server 管理的 MMC 3.0 管理單元管理公用程式。</p></td>
<td align="left"><p>此元件可以安裝在 Microsoft Application Virtualization 伺服器上，或位於裝有 MMC 3.0 和的個別工作站上。已安裝 NET 2.0。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Application Virtualization 管理 Web 服務</p></td>
<td align="left"><p>負責將任何讀/寫要求與應用程式虛擬化資料存放區進行通訊的元件。</p></td>
<td align="left"><p>此元件可以安裝在 Microsoft Application Virtualization 伺服器上，或安裝在裝有 IIS 的個別電腦上。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft Application Virtualization 資料存放區</p></td>
<td align="left"><p>儲存在 SQL 資料庫中的元件，負責儲存與應用程式虛擬化基礎結構相關的所有資訊。</p></td>
<td align="left"><p>此資訊包含所有應用程式記錄、應用程式指派，以及哪些群組負責管理應用程式虛擬化環境。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Application Virtualization 串流伺服器</p></td>
<td align="left"><p>負責將應用程式虛擬化套件託管至分支辦公室中的用戶端的元件，其中連結回到應用程式虛擬化管理伺服器，並被視為 WAN。</p></td>
<td align="left"><p>此伺服器只包含流式處理功能，且既不提供應用程式虛擬化管理主控台，也不提供應用程式虛擬化管理 Web 服務。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft Application Virtualization 排序器</p></td>
<td align="left"><p>用來監視及捕獲應用程式安裝的元件，以建立虛擬應用程式套件。</p></td>
<td align="left"><p>輸出包含應用程式的圖示、內含封裝定義資訊的 OSD 檔案、套件資訊清單檔案，以及包含應用程式內容檔案的 SFT 檔案。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Application Virtualization 用戶端</p></td>
<td align="left"><p>在應用程式虛擬化桌面用戶端或應用程式虛擬化用戶端上安裝的元件（以前稱為 [終端服務]），並提供虛擬化應用程式的虛擬環境。</p></td>
<td align="left"><p>Microsoft Application Virtualization 用戶端會將套件資料流程管理到快取、發佈重新整理、傳輸，以及與應用程式虛擬化伺服器的所有互動。</p></td>
</tr>
</tbody>
</table>

 

## 相關主題


[以 Application Virtualization 伺服器為基礎的案例](application-virtualization-server-based-scenario.md)

[在以 Application Virtualization 伺服器為基礎的實作中規劃您的串流解決方案](planning-your-streaming-solution-in-an-application-virtualization-server-based-implementation.md)

[使用 Application Virtualization Management Server 發佈虛擬應用程式](publishing-virtual-applications-using-application-virtualization-management-servers.md)

 

 





