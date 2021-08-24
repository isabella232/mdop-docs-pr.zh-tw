---
title: 適用於周邊網路的網際網路對向伺服器案例
description: 適用於周邊網路的網際網路對向伺服器案例
author: dansimp
ms.assetid: 8a4da6e6-82c7-49e5-b9b1-1666cba02f65
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 7415cf7a97edc646653df552723667bac8d25fdc
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910688"
---
# <a name="internet-facing-server-scenarios-for-perimeter-networks"></a>適用於周邊網路的網際網路對向伺服器案例


App-V 4.5 支援網際網路伺服器案例，其中未連接到公司網路或中斷網路連接的使用者仍可使用 App-V。 如下圖所示，僅支援在網際網路上使用安全通訊協定 (RTSPS 和 HTTPS) 使用。

![App-v 防火牆位置圖表。](images/appvfirewalls.gif)

您可以使用 ISA Server 設定網際網路解決方案，其中 App-V 基礎結構位於內部網路上，方法如下：

-   為內部網路上託管 ICO 和 OSD 檔案的 IIS 伺服器建立 Web 發佈規則 ，並選擇性地建立串流套件。 詳細步驟會提供于 <https://go.microsoft.com/fwlink/?LinkId=151982> 。

-   為 RTSPS 中的 App-V Web 管理伺服器建立伺服器發佈 (規則) 。 詳細步驟會提供于 [https://go.microsoft.com/fwlink/?LinkId=151983&](https://go.microsoft.com/fwlink/?LinkId=151983) 。

如下圖所示，如果基礎結構在用戶端與 ISA Server 之間或 ISA Server 與內部網路之間已實施其他防火牆，則必須建立 RTSPS (TCP 322) 和 HTTPS (TCP 443) 防火牆規則，以支援流量。 此外，如果 ISA Server 與內部網路之間已建立防火牆，網域成員所需的預設流量必須允許透過防火牆 (DNS、LDAP、Kerberos、SMB/CIFS) 。

![App-v 周邊網路防火牆圖表。](images/appvperimeternetworkfirewall.gif)

由於防火牆解決方案因環境而異，本主題所提供的指南說明在周邊網路中設定網際網路型 App-V 環境所需的流量。 此資訊也包含建議的內部網路伺服器。

將下列伺服器放在周邊網路中：

-   App-V 管理伺服器

-   IIS 伺服器，用於發佈和串流

**注意**  
將管理伺服器和 IIS 伺服器放在不同的電腦上是最佳做法。

 

將下列伺服器放在內部網路中：

-   內容伺服器

-   資料儲存 (SQL Server) 

-   Active Directory 網域控制站

## <a name="traffic-requirements"></a>流量需求


下表列出網際網路和周邊網路，以及從周邊網路到內部網路之間通訊的流量需求。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">從網際網路到周邊網路的流量需求</th>
<th align="left">詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>RTSPS (發佈重新版和串流套件) </p></td>
<td align="left"><p>TCP 322 預設為這可以在 App-V 管理伺服器中變更。</p></td>
</tr>
<tr class="even">
<td align="left"><p>HTTPS (發佈 ICO 和 OSD 檔案，以及串流套件) </p></td>
<td align="left"><p>TCP 443 預設為這項功能可在 IIS 組配置中變更。</p></td>
</tr>
</tbody>
</table>

 

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">從周邊網路到內部網路的流量需求</th>
<th align="left">詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>SQL Server</p></td>
<td align="left"><p>TCP 1433 為預設值，但可以在 SQL Server。</p></td>
</tr>
<tr class="even">
<td align="left"><p>SMB/CIFS</p></td>
<td align="left"><p>如果內容目錄位於管理伺服器或 IIS (遠端) 建議 (建議) 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Kerberos</p></td>
<td align="left"><p>TCP 和 UDP 88</p></td>
</tr>
<tr class="even">
<td align="left"><p>LDAP</p></td>
<td align="left"><p>TCP 和 UDP 389</p></td>
</tr>
<tr class="odd">
<td align="left"><p>DNS</p></td>
<td align="left"><p>針對內部資源的名稱解析 (在周邊網路伺服器上使用主機的檔案，就可以) </p></td>
</tr>
</tbody>
</table>

 

 

 





