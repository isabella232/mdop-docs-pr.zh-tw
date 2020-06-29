---
title: 在電子軟體發佈實作中規劃您的串流解決方案
description: 在電子軟體發佈實作中規劃您的串流解決方案
author: dansimp
ms.assetid: bc18772a-f169-486f-adb1-7af1a31845aa
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c49d6fc0b5f8f5dee347ead3bb899ce9b0387024
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800903"
---
# 在電子軟體發佈實作中規劃您的串流解決方案


如果您決定將流式處理伺服器與 ESD 系統搭配使用，以讓應用程式內容可供您的最終使用者電腦使用，您可以選擇幾個替代方案，充分利用任何基礎結構。 例如，如果您的 ESD 系統在欄位分支辦公室中的伺服器上有軟體發佈共用，您可以將應用程式虛擬化 \\CONTENT 共用放在這些伺服器上，然後將用戶端設定為使用該內容共用作為其應用程式內容來源。 支援的選項包括使用檔案伺服器或 IIS 伺服器。 您也可以在現有的檔案伺服器或 IIS 伺服器上安裝應用程式虛擬化資料流程伺服器。

應用程式虛擬化資料流程伺服器提供應用程式虛擬化中的作用中升級功能支援。 [作用中升級] 功能可將新版本的應用程式新增至 App-v 管理伺服器或流式處理伺服器，而不會影響目前執行該應用程式的使用者。 App-V 用戶端會在使用者下次啟動應用程式時，從 App-v 管理伺服器或資料流程伺服器自動接收最新版本的應用程式。 此功能需要使用 RTSP （S）協定。 如果您選擇不使用應用程式虛擬化資料流程伺服器，您將需要使用 ESD 系統來明確管理應用程式套件升級。

**記事** 應用程式的存取權是由 Active Directory 網域服務中的安全性群組所控制，因此您必須規劃一個處理每個虛擬應用程式的安全性群組，以及管理要新增至每個群組的使用者。 應用程式虛擬化系統管理員會將 Acl 設定為使用這些 Active Directory 群組，方法是將 Acl 套用至內容共用底下的應用程式目錄，控制對套件的存取權（根據 Active Directory 群組成員資格）。

 

下表摘要列出可用的 [資料流程] 選項的特性。

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
<td align="left"><p><a href="how-to-configure-the-application-virtualization-management-servers.md" data-raw-source="[How to Configure the Application Virtualization Management Servers](how-to-configure-the-application-virtualization-management-servers.md)">如何設定 Application Virtualization Management Server</a></p></td>
</tr>
</tbody>
</table>

 

## 相關主題


[如何針對以 ESD 為基礎的部署設定伺服器](how-to-configure-servers-for-esd-based-deployment.md)

[安全性與保護概觀](security-and-protection-overview.md)

[使用電子軟體發佈來發佈虛擬應用程式](publishing-virtual-applications-using-electronic-software-distribution.md)

 

 





