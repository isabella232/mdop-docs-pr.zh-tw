---
title: Application Virtualization 概觀
description: Application Virtualization 概觀
author: dansimp
ms.assetid: 80545ef4-cf4c-420c-88d6-48e9f226051f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2f3719a817137edfd76b1b972e966c685581c58e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800944"
---
# Application Virtualization 概觀


Microsoft Application Virtualization （App-v）可以讓最終使用者電腦能使用應用程式，而不必直接在那些電腦上安裝應用程式。 您可以透過稱為*應用程式順序的程式*來進行這項工作，這可讓每個應用程式在自己的用戶端電腦上獨立的虛擬環境中執行。 順序化的應用程式彼此隔離。 這會消除應用程式衝突，但應用程式仍可與用戶端電腦互動。

App-v 用戶端是一個功能，可讓使用者在將應用程式發佈到電腦之後與它們互動。 用戶端管理虛擬化應用程式在每個電腦上執行的虛擬環境。 在電腦上安裝用戶端之後，您必須透過稱為*發佈*的程式，將應用程式提供給電腦，讓使用者能夠執行虛擬應用程式。 發佈程式會將虛擬應用程式圖示和快速鍵複製到電腦（通常是在 Windows 桌面或 [**開始**] 功能表上），同時也會將套件定義和檔案類型關聯資訊複製到電腦。 發佈也會將應用程式套件內容提供給最終使用者的電腦。

您可以將虛擬應用程式套件內容複寫到一或多個應用程式虛擬化伺服器上，讓它可以根據需求傳送到用戶端，並在本機上緩存。 檔案伺服器和 Web 服務器也可以用來做為流式處理伺服器，或可以直接將內容複寫到最終使用者的電腦上，例如，如果您使用的是電子軟體發佈系統（例如 Microsoft 端點設定管理員）。 在多重伺服器的實現中，維護封裝內容並在所有流式處理伺服器上保持在最新狀態，都需要綜合的套件管理解決方案。 視貴組織的規模而定，您可能需要有許多虛擬應用程式可供世界各地的最終使用者使用。 管理套件，以確保所有使用者都能存取適當的應用程式，而他們需要存取這些專案的時間，就是一項重要的需求。

## Microsoft Application Virtualization 系統功能


下表說明 Microsoft Application Virtualization 管理系統的主要功能。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">功能</th>
<th align="left">函式</th>
<th align="left">其他資訊</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft Application Virtualization 管理伺服器</p></td>
<td align="left"><p>負責流式處理封裝內容，並將快捷方式和檔案類型關聯發佈到應用程式虛擬化用戶端。</p></td>
<td align="left"><p>應用程式虛擬化管理伺服器支援作用中升級、授權管理，以及可用於報告的資料庫。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>內容 </strong> 資料夾</p></td>
<td align="left"><p>表示應用程式虛擬化套件的下載位置。</p></td>
<td align="left"><p>這個資料夾可以位於應用程式虛擬化管理伺服器上的共用位置。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft Application Virtualization 管理主控台</p></td>
<td align="left"><p>這個主控台是用來進行 Microsoft Application Virtualization Server 管理的 MMC 3.0 管理單元管理工具。</p></td>
<td align="left"><p>此工具可以安裝在 Microsoft Application Virtualization 伺服器上，或位於擁有 Microsoft 管理主控台（MMC）3.0 和 Microsoft 的個別工作站上。已安裝 NETFramework 2.0。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Application Virtualization 管理 Web 服務</p></td>
<td align="left"><p>負責將任何讀取和寫入要求傳達給應用程式虛擬化資料存放區。</p></td>
<td align="left"><p>管理 Web 服務可以安裝在 Microsoft Application Virtualization 管理伺服器或已安裝 Microsoft 網際網路資訊服務（IIS）的另一部電腦上。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft Application Virtualization 資料存放區</p></td>
<td align="left"><p>App-v SQL Server 資料庫，負責儲存與應用程式虛擬化基礎結構相關的所有資訊。</p></td>
<td align="left"><p>此資訊包含所有應用程式記錄、應用程式指派，以及哪些群組負責管理應用程式虛擬化環境。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Application Virtualization 串流伺服器</p></td>
<td align="left"><p>負責託管傳送給分支辦公室中用戶端的應用程式虛擬化套件，而該連結回到應用程式虛擬化管理伺服器，則會被視為廣域網路絡（WAN）連線。</p></td>
<td align="left"><p>此伺服器只包含流式處理功能，且既不提供應用程式虛擬化管理主控台，也不提供應用程式虛擬化管理 Web 服務。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft Application Virtualization 排序器</p></td>
<td align="left"><p>Sequencer 是用來監視及捕獲應用程式的安裝，以建立虛擬應用程式套件。</p></td>
<td align="left"><p>輸出包含應用程式的圖示、內含套件定義資訊的 .osd 檔案、封裝資訊清單檔案，以及包含應用程式內容檔案的 sft 檔案。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Application Virtualization 用戶端</p></td>
<td align="left"><p>應用程式虛擬化桌面用戶端和適用于遠端桌面服務的應用程式虛擬化用戶端提供及管理虛擬化應用程式的虛擬環境。</p></td>
<td align="left"><p>Microsoft Application Virtualization 用戶端會將套件資料流程管理到快取、發佈重新整理、傳輸，以及與應用程式虛擬化伺服器的所有互動。</p></td>
</tr>
</tbody>
</table>

 

 

 





