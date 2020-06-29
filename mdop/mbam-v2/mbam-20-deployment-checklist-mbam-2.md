---
title: MBAM 2.0 部署檢查清單
description: MBAM 2.0 部署檢查清單
author: dansimp
ms.assetid: 7905d31d-f21c-4683-b9c4-95b815e08fab
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5d8d0ce1a3ff48d4bf2f84e61b4a578b170264a0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811756"
---
# MBAM 2.0 部署檢查清單


此檢查清單可用來協助您在 Microsoft BitLocker 管理和監控（MBAM）部署中使用獨立拓撲。

**注意**  
此檢查清單概述在部署 Microsoft BitLocker 管理和監視功能時，建議的步驟和要考慮的高層次專案清單。 建議您將此檢查清單複製到試算表程式中，然後將它自訂為供您使用。



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
<td align="left"><p><a href="mbam-20-planning-checklist-mbam-2.md" data-raw-source="[MBAM 2.0 Planning Checklist](mbam-20-planning-checklist-mbam-2.md)">MBAM 2.0 規劃檢查清單</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>查看 MBAM 支援的設定資訊，確認已選取的用戶端和伺服器電腦支援 MBAM 功能安裝。</p></td>
<td align="left"><p><a href="mbam-20-supported-configurations-mbam-2.md" data-raw-source="[MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md)">MBAM 2.0 支援的組態</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>執行 MBAM 安裝程式，以下列順序部署 MBAM 伺服器功能：</p>
<ol>
<li><p>復原資料庫</p></li>
<li><p>合規性和審核資料庫</p></li>
<li><p>合規性審核與報告</p></li>
<li><p>自助服務伺服器</p></li>
<li><p>管理和監控伺服器</p></li>
<li><p>MBAM 群組原則範本</p></li>
</ol>
<div class="alert">
<strong>注意</strong><br/><p>追蹤每個安裝功能的伺服器名稱。 此資訊將會在整個安裝過程中使用。</p>
</div>
<div>

</div></td>
<td align="left"><p><a href="deploying-the-mbam-20-server-infrastructure-mbam-2.md" data-raw-source="[Deploying the MBAM 2.0 Server Infrastructure](deploying-the-mbam-20-server-infrastructure-mbam-2.md)">部署 MBAM 2.0 伺服器基礎結構</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>將在規劃階段建立的 Active Directory 網域服務安全性群組新增至適當的本機 MBAM 伺服器功能系統管理員群組（適用于適當的伺服器）。</p></td>
<td align="left"><p><a href="planning-for-mbam-20-administrator-roles-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Administrator Roles](planning-for-mbam-20-administrator-roles-mbam-2.md)">規劃 MBAM 2.0 系統管理員角色 </a> ，以及 <a href="how-to-manage-mbam-administrator-roles-mbam-2.md" data-raw-source="[How to Manage MBAM Administrator Roles](how-to-manage-mbam-administrator-roles-mbam-2.md)"> 如何管理 MBAM 系統管理員角色</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>建立及部署所需的 MBAM 群組原則物件。</p></td>
<td align="left"><p><a href="deploying-mbam-20-group-policy-objects-mbam-2.md" data-raw-source="[Deploying MBAM 2.0 Group Policy Objects](deploying-mbam-20-group-policy-objects-mbam-2.md)">部署 MBAM 2.0 群組原則物件</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>部署 MBAM 用戶端軟體。</p></td>
<td align="left"><p><a href="deploying-the-mbam-20-client-mbam-2.md" data-raw-source="[Deploying the MBAM 2.0 Client](deploying-the-mbam-20-client-mbam-2.md)">部署 MBAM 2.0 用戶端</a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



## 相關主題


[部署 MBAM 2.0](deploying-mbam-20-mbam-2.md)









