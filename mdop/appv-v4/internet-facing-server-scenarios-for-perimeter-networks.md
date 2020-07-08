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
ms.openlocfilehash: fcb04e651341fa107c358eaabbd7992d7ea155ec
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800988"
---
# 適用於周邊網路的網際網路對向伺服器案例


App-v 4.5 支援網際網路伺服器案例，在這種情況下，未連接至公司網路的使用者或從網路中斷連線的使用者仍然可以使用 App-v。 如下圖所示，只支援在網際網路（RTSPS 及 HTTPS）上使用安全通訊協定。

![app-v 防火牆定點陣圖表](images/appvfirewalls.gif)

您可以使用 ISA 伺服器（在內部網路上有下列幾種方式）來設定網際網路程式解決方案：

-   為裝載 .ICO 和 OSD 檔案的 IIS 伺服器建立 Web 發佈規則，也可以選擇在內部網路上的 [資料流程套件]。 這裡提供詳細步驟 <https://go.microsoft.com/fwlink/?LinkId=151982> 。

-   為 App-V Web 管理伺服器（RTSPS）建立伺服器發佈規則。 這裡提供詳細步驟 [https://go.microsoft.com/fwlink/?LinkId=151983&](https://go.microsoft.com/fwlink/?LinkId=151983) 。

如下圖所示，如果基礎結構在用戶端與 ISA 伺服器之間或 ISA 伺服器與內部網路之間已實施其他防火牆，則必須建立 RTSPS （TCP 322）與 HTTPS （TCP 443）防火牆規則，才能支援流量流程。 此外，如果在 ISA 伺服器與內部網路之間已實施防火牆，則必須允許網域成員所需的預設流量透過防火牆（DNS、LDAP、Kerberos、SMB/CIFS）進行隧道。

![app-v 周邊網路防火牆圖表](images/appvperimeternetworkfirewall.gif)

由於防火牆解決方案與環境有所不同，本主題中所提供的指導方針說明在周邊網路中設定面向網際網路的 App-v 環境所需的流量。 此資訊也包括建議的內部網路伺服器。

將下列伺服器放在周邊網路：

-   App-v 管理伺服器

-   用於發佈及流式處理的 IIS 伺服器

**記事** 最佳做法是將管理伺服器與 IIS 伺服器放在不同的電腦上。

 

將下列伺服器放在內部網路：

-   內容伺服器

-   資料存放區（SQL Server）

-   Active Directory 網網域控制站

## 流量需求


下表列出從網際網路與周邊網路，以及從周邊網路到內部網路的通訊需求。

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
<td align="left"><p>RTSPS （發佈更新及流式處理套件）</p></td>
<td align="left"><p>預設為 TCP 322;此功能可以在 App-v Management Server 中變更。</p></td>
</tr>
<tr class="even">
<td align="left"><p>HTTPS （發佈 .ICO 和 OSD 檔案及流式套件）</p></td>
<td align="left"><p>預設為 TCP 443;這可以在 IIS 設定中變更。</p></td>
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
<td align="left"><p>TCP 1433 是預設值，但可以在 SQL Server 中設定。</p></td>
</tr>
<tr class="even">
<td align="left"><p>SMB/CIFS</p></td>
<td align="left"><p>如果內容目錄是從管理伺服器或 IIS 伺服器的遠端位置（建議使用）。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Kerberos</p></td>
<td align="left"><p>TCP 和 UDP 88</p></td>
</tr>
<tr class="even">
<td align="left"><p>適用</p></td>
<td align="left"><p>TCP 和 UDP 389</p></td>
</tr>
<tr class="odd">
<td align="left"><p>DNS</p></td>
<td align="left"><p>內部資源的名稱解析（在週邊網路伺服器上使用主機的檔案可以消除）</p></td>
</tr>
</tbody>
</table>

 

 

 





