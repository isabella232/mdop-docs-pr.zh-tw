---
title: App-V 前置安裝檢查清單
description: App-V 前置安裝檢查清單
author: dansimp
ms.assetid: 3af609b1-2c09-4edb-b083-b913b6d5e8c4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 70e71d3dea02daeadedb4cff78c58302ac743dda
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802357"
---
# App-V 前置安裝檢查清單


下列檢查清單是用來提供一個要考慮的高層次專案清單，並簡要說明您在安裝 Microsoft Application Virtualization （App-v）伺服器之前應該採取的步驟。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">步驟</th>
<th align="left">參考</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>確保您的計算環境符合 App-v 所需的支援設定。</p></td>
<td align="left"><p><a href="application-virtualization-deployment-requirements.md" data-raw-source="[Application Virtualization Deployment Requirements](application-virtualization-deployment-requirements.md)">Application Virtualization 部署需求</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>設定必要的 Active Directory 群組和帳戶。</p></td>
<td align="left"><p><a href="configuring-prerequisite-groups-in-active-directory-for-app-v.md" data-raw-source="[Configuring Prerequisite Groups in Active Directory for App-V](configuring-prerequisite-groups-in-active-directory-for-app-v.md)">在 Active Directory 中設定 App-V 的必要群組</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>在執行 IIS 的伺服器上設定 [網際網路資訊服務（IIS）] 設定。</p></td>
<td align="left"><p><a href="how-to-configure-windows-server-2008-for-app-v-management-servers.md" data-raw-source="[How to Configure Windows Server 2008 for App-V Management Servers](how-to-configure-windows-server-2008-for-app-v-management-servers.md)">如何針對 App-V Management Server 設定 Windows Server 2008</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>將執行 IIS 的伺服器設定為信任委派。</p>
<div class="alert">
<strong>注意</strong><br/><p>只有在您使用分散式系統結構（即，如果您在不同的電腦上安裝 App V 管理主控台、管理 Web 服務和資料庫）安裝 App V 管理伺服器時，才需要這麼做。</p>
</div>
<div>

</div></td>
<td align="left"><p><a href="how-to-configure-the-server-to-be-trusted-for-delegation.md" data-raw-source="[How to Configure the Server to be Trusted for Delegation](how-to-configure-the-server-to-be-trusted-for-delegation.md)">如何將伺服器設定成受信任可以委派</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>安裝 Microsoft SQL Server 2008。</p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=181924" data-raw-source="[Install SQL Server 2008](https://go.microsoft.com/fwlink/?LinkId=181924)">安裝 SQL Server 2008 </a> （ <a href="https://go.microsoft.com/fwlink/?LinkId=181924" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=181924"> https://go.microsoft.com/fwlink/?LinkId=181924 </a> ）。</p></td>
</tr>
</tbody>
</table>



## 相關主題


[Application Virtualization 部署與升級檢查清單](application-virtualization-deployment-and-upgrade-checklists.md)

[App-V 安裝檢查清單](app-v-installation-checklist.md)









