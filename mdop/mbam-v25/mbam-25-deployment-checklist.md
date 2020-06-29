---
title: MBAM 2.5 部署檢查清單
description: MBAM 2.5 部署檢查清單
author: dansimp
ms.assetid: 2ba7de17-e3a4-4798-99e0-cd1dc28c5b76
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 11609b3d6d44d62b032e35005e5d967ca6d4e83b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809591"
---
# MBAM 2.5 部署檢查清單


您可以使用此檢查清單來協助您在 Microsoft BitLocker 管理和監控（MBAM）部署中使用獨立拓撲。

**注意**  
此檢查清單概括了在您部署 Microsoft BitLocker 管理和監控功能時，所建議的步驟以及要考慮的高層次專案清單。 我們建議您將此檢查清單複製到試算表程式中，然後將它自訂為供您使用。



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
<td align="left"><p>複習並完成所有規劃步驟，以準備您的環境以進行 MBAM 部署。</p></td>
<td align="left"><p><a href="mbam-25-planning-checklist.md" data-raw-source="[MBAM 2.5 Planning Checklist](mbam-25-planning-checklist.md)">MBAM 2.5 規劃檢查清單</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>查看支援的設定資訊，以確保 MBAM 支援所選取的用戶端和伺服器電腦。</p></td>
<td align="left"><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)">MBAM 2.5 支援的組態</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>安裝 MBAM Server 軟體。</p></td>
<td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)">安裝 MBAM 2.5 伺服器軟體</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>設定 MBAM 伺服器功能：</p>
<ul>
<li><p>合規性與審核資料庫與復原資料庫</p></li>
<li><p>報告</p></li>
<li><p>Web 應用程式</p></li>
<li><p>Configuration Manager 整合拓朴（只有當您在此拓朴執行 MBAM 時才需要）</p></li>
</ul>
<div class="alert">
<strong>注意</strong><br/><p>記下您要設定每個功能的伺服器名稱。 您將會在整個配置程式中使用此資訊。</p>
</div>
<div>

</div></td>
<td align="left"><p><a href="configuring-the-mbam-25-server-features.md" data-raw-source="[Configuring the MBAM 2.5 Server Features](configuring-the-mbam-25-server-features.md)">設定 MBAM 2.5 伺服器功能</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>驗證 MBAM 設定。</p></td>
<td align="left"><p><a href="validating-the-mbam-25-server-feature-configuration.md" data-raw-source="[Validating the MBAM 2.5 Server Feature Configuration](validating-the-mbam-25-server-feature-configuration.md)">驗證 MBAM 2.5 伺服器功能設定</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>複製 MBAM 群組原則範本，並編輯群組原則設定。</p></td>
<td align="left"><p><a href="copying-the-mbam-25-group-policy-templates.md" data-raw-source="[Copying the MBAM 2.5 Group Policy Templates](copying-the-mbam-25-group-policy-templates.md)">複製 MBAM 2.5 群組原則範本 </a> ，並 <a href="editing-the-mbam-25-group-policy-settings.md" data-raw-source="[Editing the MBAM 2.5 Group Policy Settings](editing-the-mbam-25-group-policy-settings.md)"> 編輯 MBAM 2.5 群組原則設定</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>部署 MBAM 用戶端軟體。</p></td>
<td align="left"><p><a href="deploying-the-mbam-25-client.md" data-raw-source="[Deploying the MBAM 2.5 Client](deploying-the-mbam-25-client.md)">部署 MBAM 2.5 用戶端</a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>




## 相關主題


[部署 MBAM 2.5](deploying-mbam-25.md)




## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。 
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。




