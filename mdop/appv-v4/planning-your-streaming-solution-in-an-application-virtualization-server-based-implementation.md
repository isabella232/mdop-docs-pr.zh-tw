---
title: 在以 Application Virtualization 伺服器為基礎的實作中規劃您的串流解決方案
description: 在以 Application Virtualization 伺服器為基礎的實作中規劃您的串流解決方案
author: dansimp
ms.assetid: 3a57306e-5c54-4fde-8593-fe3b788f18d3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0d315f554eb99fc5c05c231630eaa41d4f505535
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800905"
---
# 在以 Application Virtualization 伺服器為基礎的實作中規劃您的串流解決方案


如果您想要將應用程式虛擬化資料流程伺服器與應用程式虛擬化管理伺服器的部署搭配使用，您可以選擇幾個替代方案，充分利用任何基礎結構已就緒。 例如，如果您已在欄位分支辦公室中擁有伺服器，您可以將應用程式虛擬化 \\CONTENT 共用放在這些伺服器上，然後將用戶端設定為使用該內容共用作為其應用程式內容來源。 如果您選擇只使用應用程式虛擬化管理伺服器（例如，因為您只有單一 office），則用戶端可以對流進行資料流程內容。

支援的選項包括使用檔案伺服器、IIS 伺服器或應用程式虛擬化資料流程伺服器。 您也可以在現有的檔案伺服器或 IIS 伺服器上安裝應用程式虛擬化資料流程伺服器。 下表摘要列出這些不同選項的特性。

**記事** [作用中升級] 功能可將新版本的應用程式新增至 App-v 管理伺服器或流式處理伺服器，而不會影響目前執行該應用程式的使用者。 App-V 用戶端會在使用者下次啟動應用程式時，從 App-v 管理伺服器或資料流程伺服器自動接收最新版本的應用程式。 此功能需要使用 RTSP （S）協定。

 

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">伺服器類型</th>
<th align="left">通訊協定</th>
<th align="left">優點</th>
<th align="left">缺點</th>
<th align="left">連結</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>檔案伺服器</p></td>
<td align="left"><p>SMB</p></td>
<td align="left"><ul>
<li><p>簡單的低成本解決方案，可使用 \CONTENT 共用來設定現有的檔案伺服器</p></li>
</ul></td>
<td align="left"><ul>
<li><p>沒有作用中升級</p></li>
</ul></td>
<td align="left"><p><a href="how-to-configure-the-file-server.md" data-raw-source="[How to Configure the File Server](how-to-configure-the-file-server.md)">如何設定檔案伺服器</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>IIS 伺服器</p></td>
<td align="left"><p>HTTP/HTTPS</p></td>
<td align="left"><ul>
<li><p>使用 HTTPS 通訊協定支援增強的安全性</p></li>
<li><p>支援透過網際網路在遠端電腦上傳送資料流程</p></li>
<li><p>在防火牆中只開啟一個埠</p></li>
<li><p>可</p></li>
<li><p>熟悉的通訊協定</p></li>
</ul></td>
<td align="left"><ul>
<li><p>需要管理 IIS</p></li>
<li><p>沒有作用中升級</p></li>
</ul></td>
<td align="left"><p><a href="how-to-configure-the-server-for-iis.md" data-raw-source="[How to Configure the Server for IIS](how-to-configure-the-server-for-iis.md)">如何設定伺服器使用 IIS</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>應用程式虛擬化資料流程伺服器</p></td>
<td align="left"><p>RTSP/RTSPS</p></td>
<td align="left"><ul>
<li><p>活動升級</p></li>
<li><p>使用 RTSPS 通訊協定支援增強的安全性</p></li>
<li><p>在防火牆中只開啟一個埠</p></li>
</ul></td>
<td align="left"><ul>
<li><p>雙基礎結構</p></li>
<li><p>伺服器管理需求</p></li>
</ul></td>
<td align="left"><p><a href="how-to-configure-the-application-virtualization-streaming-servers.md" data-raw-source="[How to Configure the Application Virtualization Streaming Servers](how-to-configure-the-application-virtualization-streaming-servers.md)">如何設定 Application Virtualization Streaming Server</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>應用程式虛擬化管理伺服器</p></td>
<td align="left"><p>RTSP/RTSPS</p></td>
<td align="left"><ul>
<li><p>活動升級</p></li>
<li><p>使用 RTSPS 通訊協定支援增強的安全性</p></li>
<li><p>在防火牆中只開啟一個埠</p></li>
</ul></td>
<td align="left"><ul>
<li><p>雙基礎結構</p></li>
<li><p>伺服器管理需求</p></li>
</ul></td>
<td align="left"><p><a href="how-to-configure-the-application-virtualization-management-servers.md" data-raw-source="[How to Configure the Application Virtualization Management Servers](how-to-configure-the-application-virtualization-management-servers.md)">如何設定 Application Virtualization Management Server</a></p></td>
</tr>
</tbody>
</table>

 

## 相關主題


[以 Application Virtualization 伺服器為基礎的案例](application-virtualization-server-based-scenario.md)

[Application Virtualization 系統元件概觀](overview-of-the-application-virtualization-system-components.md)

[使用 Application Virtualization Management Server 發佈虛擬應用程式](publishing-virtual-applications-using-application-virtualization-management-servers.md)

 

 





