---
title: 使用 App-V 5.0 Client Management Console
description: 使用 App-V 5.0 Client Management Console
author: dansimp
ms.assetid: 36398307-57dd-40f3-9d4f-b09f44fd37c3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8541e5bc59334b9074a3940dad7cdf0114205d4c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800299"
---
# 使用 App-V 5.0 Client Management Console


本主題提供您如何設定和管理 App-v 5.0 用戶端的相關資訊。

## 修改 App-V 5.0 用戶端設定


App-V 5.0 用戶端具有相關設定，可設定為決定用戶端在您的環境中執行的方式。 您可以在執行用戶端或使用 PowerShell 或群組原則的電腦上管理這些設定。 如需有關如何使用 PowerShell 或群組原則設定修改用戶端的詳細資訊，請參閱[如何使用 Powershell 修改用戶端](how-to-modify-client-configuration-by-using-powershell.md)設定。

## <a href="" id="the-app-v-5-0-client-management-console-"></a>App-V 5.0 用戶端管理主控台


您可以取得 App-V 5.0 用戶端的相關資訊，或使用 App-v 5.0 用戶端管理主控台執行特定工作。 您可以在用戶端管理主控台執行的許多工作，您也可以使用 PowerShell 來執行。 每個動作的相關 PowerShell Cmdlet 也會顯示在下表中。 如需如何使用 PowerShell 的詳細資訊，請參閱[使用 Powershell 管理 App-V](administering-app-v-by-using-powershell.md)。

用戶端管理主控台包含下列所述的主要索引標籤。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Tab</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>概觀</p></td>
<td align="left"><p>[ <strong> 概覽] 索引標籤 </strong> 包含下列元素：</p>
<ul>
<li><p>更新–使用 <strong> 更新磚重新整理 </strong> 虛擬化的應用程式，或接收新的虛擬化套件。</p>
<p>[ <strong> 上一次重新整理] 會 </strong> 顯示目前的虛擬化套件版本。</p></li>
<li><p>下載所有虛擬應用程式–使用 [ <strong> 下載] </strong> 磚下載所有已預配至目前使用者的套件。</p>
<p>（相關聯的 PowerShell Cmdlet： <strong>Mount-AppvClientPackage </strong> ）</p>
<p></p></li>
<li><p>離線工作–使用此磚可禁止所有自動和手動虛擬應用程式更新。</p>
<p>（相關聯的 PowerShell Cmdlet： <strong>Set-AppvPublishServer – UserRefreshEnabled – GlobalRefreshEnabled </strong> ）</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>虛擬應用程式</p></td>
<td align="left"><p>[ <strong> 虛擬 app] 索引標籤 </strong> 會顯示已發佈給使用者的所有套件。 您也可以按一下特定套件，並查看屬於該套件的所有應用程式。 這會顯示目前使用中之套件的相關資訊，以及每個套件已下載到電腦的數量。 您也可以啟動和停止套件下載。 此外，您也可以修復使用者狀態。 修復會刪除與套件相關的所有使用者資料。</p>
<p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>App 連線群組</p></td>
<td align="left"><p>[ <strong> 應用程式連線群組] 索引標籤 </strong> 會顯示目前使用者可以使用的所有連線群組。 按一下特定的連線群組，以查看屬於所選群組的所有套件。 這會顯示已在使用中的連線群組資訊，以及將多少連線群組內容下載到電腦。 此外，您還可以啟動和停止連線群組下載。 您可以使用這個區段來啟動修復。 修復會移除所有與連接群組相關聯的使用者狀態。</p>
<p>（關聯的 PowerShell Cmdlet：下載- <strong>Mount-AppvClientConnectionGroup </strong> 。 修復- <strong> AppvClientConnectionGroup </strong> 。）</p>
<p></p></td>
</tr>
</tbody>
</table>

 

[如何存取 Client Management Console](how-to-access-the-client-management-console.md)

[如何設定用戶端以從發佈伺服器接收套件與連線群組更新](how-to-configure-the-client-to-receive-package-and-connection-groups-updates-from-the-publishing-server-beta.md)






## 相關主題


[App-V 5.0 作業](operations-for-app-v-50.md)

 

 





