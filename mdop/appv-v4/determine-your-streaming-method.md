---
title: 決定您的串流方法
description: 決定您的串流方法
author: dansimp
ms.assetid: 50d5e0ec-7f48-4cea-8711-5882bd89153b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0acfd345ac55f11476cffe94b3a95b13c5d8f303
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10808894"
---
# 決定您的串流方法


當使用者第一次按兩下已透過發佈程式在電腦上放置的圖示時，應用程式虛擬化用戶端會從流式來源位置取得虛擬應用程式套件內容。

**記事** 
*串流*是用來描述取得順序式應用程式套件內容的程式，從主要功能區塊開始，然後視需要取得其他區塊。

 

流式來源位置通常是使用者電腦可存取的伺服器;不過，某些電子發佈系統（例如 Microsoft 端點設定管理員）可以將 SFT 檔案散佈到使用者的電腦，然後從該電腦的快取本機對流進行虛擬應用程式套件。

**記事** 虛擬套件的流式來源位置可以在不是伺服器的電腦上設定。 這在沒有伺服器的小型分支機搆中特別有用。

 

下表說明可用於儲存順序式應用程式的流式處理來源。

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
<td align="left"><p>檔案</p></td>
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
<li><p>使用 HTTPS 通訊協定支援增強的安全性。</p></li>
<li><p>支援透過網際網路在遠端電腦上傳送資料流程</p></li>
<li><p>在防火牆中只開啟一個埠</p></li>
<li><p>高度可伸縮</p></li>
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
<li><p>在防火牆中只開啟一個埠（僅限 RTSPS）</p></li>
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


[以電子軟體發佈為基礎的案例](electronic-software-distribution-based-scenario.md)

[以電子軟體發佈為基礎的案例概觀](electronic-software-distribution-based-scenario-overview.md)

[決定您的發佈方法](determine-your-publishing-method.md)

 

 





