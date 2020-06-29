---
title: MBAM 1.0 部署檢查清單
description: MBAM 1.0 部署檢查清單
author: dansimp
ms.assetid: 7e00be23-36a0-4b0f-8663-3c4f2c71546d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 96725183af2cb4e3d86d3f42973452c598497773
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800118"
---
# MBAM 1.0 部署檢查清單


此檢查清單旨在協助您部署 Microsoft BitLocker 管理和監控（MBAM）。

**注意**  
此檢查清單概括了建議的步驟，並提供在您部署 MBAM 功能時要考慮的專案的高層層次清單。 我們建議您將此檢查清單複製到試算表程式，並針對您的特定需求來自訂它。



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left">工作</th>
<th align="left">參考資料</th>
<th align="left">附註</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>完成規劃階段以準備 MBAM 部署的計算環境。</p></td>
<td align="left"><p><a href="mbam-10-planning-checklist.md" data-raw-source="[MBAM 1.0 Planning Checklist](mbam-10-planning-checklist.md)">MBAM 1.0 規劃檢查清單</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>請參閱 MBAM 支援的設定中的資訊，以確定您所選取的用戶端和伺服器電腦支援 MBAM 功能安裝。</p></td>
<td align="left"><p><a href="mbam-10-supported-configurations.md" data-raw-source="[MBAM 1.0 Supported Configurations](mbam-10-supported-configurations.md)">MBAM 1.0 支援的組態</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>執行 MBAM 安裝程式，以下列順序部署 MBAM 伺服器功能：</p>
<ol>
<li><p>恢復與硬體資料庫</p></li>
<li><p>合規性狀態資料庫</p></li>
<li><p>合規性審核與報告</p></li>
<li><p>管理和監控伺服器</p></li>
<li><p>MBAM 群組原則範本</p></li>
</ol>
<div class="alert">
<strong>注意</strong><br/><p>追蹤每個安裝功能的伺服器名稱。 您將會在整個安裝過程中使用此資訊。</p>
</div>
<div>

</div></td>
<td align="left"><p><a href="deploying-the-mbam-10-server-infrastructure.md" data-raw-source="[Deploying the MBAM 1.0 Server Infrastructure](deploying-the-mbam-10-server-infrastructure.md)">部署 MBAM 1.0 伺服器基礎結構</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>將在規劃階段建立的 Active Directory 網域服務安全性群組新增至適當的伺服器上適當的本機 MBAM 伺服器功能系統管理員群組。</p></td>
<td align="left"><p><a href="planning-for-mbam-10-administrator-roles.md" data-raw-source="[Planning for MBAM 1.0 Administrator Roles](planning-for-mbam-10-administrator-roles.md)">規劃 MBAM 1.0 系統管理員角色 </a> ，以及 <a href="how-to-manage-mbam-administrator-roles-mbam-1.md" data-raw-source="[How to Manage MBAM Administrator Roles](how-to-manage-mbam-administrator-roles-mbam-1.md)"> 如何管理 MBAM 系統管理員角色</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>建立及部署所需的 MBAM 群組原則物件。</p></td>
<td align="left"><p><a href="deploying-mbam-10-group-policy-objects.md" data-raw-source="[Deploying MBAM 1.0 Group Policy Objects](deploying-mbam-10-group-policy-objects.md)">部署 MBAM 1.0 群組原則物件</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>部署 MBAM 用戶端軟體。</p></td>
<td align="left"><p><a href="deploying-the-mbam-10-client.md" data-raw-source="[Deploying the MBAM 1.0 Client](deploying-the-mbam-10-client.md)">部署 MBAM 1.0 用戶端</a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



## 相關主題


[部署 MBAM 1.0](deploying-mbam-10.md)









