---
title: 評估 MBAM 2.0
description: 評估 MBAM 2.0
author: dansimp
ms.assetid: bfc77eec-0fd7-4fec-9c78-6870afa87152
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b7be883f44f5f09a904f619972ae3e7c35261d26
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810736"
---
# 評估 MBAM 2.0


在將 Microsoft BitLocker 管理和監控（MBAM）部署到生產環境之前，您應該先在測試環境中評估它。 本主題中的資訊可以用來在單一伺服器測試環境中設定 Microsoft BitLocker 管理和監控，僅供評估之用。 不建議在生產環境中使用單一伺服器拓撲。

如需在測試環境中部署 MBAM 的相關指示，請參閱[如何在單一伺服器上安裝和設定 MBAM](how-to-install-and-configure-mbam-on-a-single-server-mbam-2.md)。

## 設定測試環境


即使您要在測試環境中設定要評估的非生產 MBAM 實例，您仍然應該確認您已滿足系統必備與硬體及軟體需求。 開始安裝之前，請參閱[MBAM 2.0 部署先決條件](mbam-20-deployment-prerequisites-mbam-2.md)、 [MBAM 2.0 支援](mbam-20-supported-configurations-mbam-2.md)的設定，以及[為 MBAM 2.0 準備您的環境](preparing-your-environment-for-mbam-20-mbam-2.md)。

### 規劃 MBAM 評估部署

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
<td align="left"><p>查看 MBAM 的快速入門資訊，以深入瞭解開始部署規劃之前的產品。</p></td>
<td align="left"><p><a href="getting-started-with-mbam-20-mbam-2.md" data-raw-source="[Getting Started with MBAM 2.0](getting-started-with-mbam-20-mbam-2.md)">開始使用 MBAM 2.0</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>規劃 MBAM 2.0 部署必備元件並準備您的計算環境。</p></td>
<td align="left"><p><a href="mbam-20-deployment-prerequisites-mbam-2.md" data-raw-source="[MBAM 2.0 Deployment Prerequisites](mbam-20-deployment-prerequisites-mbam-2.md)">MBAM 2.0 部署必要條件</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>規劃及設定 MBAM 群組原則需求。</p></td>
<td align="left"><p><a href="planning-for-mbam-20-group-policy-requirements-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Group Policy Requirements](planning-for-mbam-20-group-policy-requirements-mbam-2.md)">MBAM 2.0 群組原則需求規劃</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>規劃及建立必要的 ActiveDirectoryDomainServices 安全性群組，並規劃 MBAM 的本機安全性群組成員資格需求。</p></td>
<td align="left"><p><a href="planning-for-mbam-20-administrator-roles-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Administrator Roles](planning-for-mbam-20-administrator-roles-mbam-2.md)">MBAM 2.0 系統管理員角色規劃</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>規劃部署 MBAM Server 功能部署。</p></td>
<td align="left"><p><a href="planning-for-mbam-20-server-deployment-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Server Deployment](planning-for-mbam-20-server-deployment-mbam-2.md)">MBAM 2.0 伺服器部署規劃</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>規劃部署 MBAM 用戶端部署。</p></td>
<td align="left"><p><a href="planning-for-mbam-20-client-deployment-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Client Deployment](planning-for-mbam-20-client-deployment-mbam-2.md)">MBAM 2.0 用戶端部署規劃</a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>

 

### 執行 MBAM 評估部署

完成所需的規劃和軟體必備元件安裝後，若要為 MBAM 安裝準備您的計算環境，您可以開始進行 MBAM 評估部署。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>查看 MBAM 支援的設定資訊，確認已選取 [用戶端和伺服器電腦] 支援 MBAM 功能安裝。</p></td>
<td align="left"><p><a href="mbam-20-supported-configurations-mbam-2.md" data-raw-source="[MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md)">MBAM 2.0 支援的組態</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>若要評估，請執行 MBAM 安裝程式，在單一伺服器上部署 MBAM 伺服器功能。</p></td>
<td align="left"><p><a href="how-to-install-and-configure-mbam-on-a-single-server-mbam-2.md" data-raw-source="[How to Install and Configure MBAM on a Single Server](how-to-install-and-configure-mbam-on-a-single-server-mbam-2.md)">如何在單一伺服器上安裝及設定 MBAM</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>將您在規劃階段建立的 ActiveDirectoryDomainServices 安全性群組新增至新 MBAM 伺服器上適當的本機 MBAM 伺服器功能本機群組。</p></td>
<td align="left"><p><a href="planning-for-mbam-20-administrator-roles-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Administrator Roles](planning-for-mbam-20-administrator-roles-mbam-2.md)">規劃 MBAM 2.0 系統管理員角色 </a> ，以及 <a href="how-to-manage-mbam-administrator-roles-mbam-2.md" data-raw-source="[How to Manage MBAM Administrator Roles](how-to-manage-mbam-administrator-roles-mbam-2.md)"> 如何管理 MBAM 系統管理員角色</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>建立及部署所需的 MBAM 群組原則物件。</p></td>
<td align="left"><p><a href="deploying-mbam-20-group-policy-objects-mbam-2.md" data-raw-source="[Deploying MBAM 2.0 Group Policy Objects](deploying-mbam-20-group-policy-objects-mbam-2.md)">部署 MBAM 2.0 群組原則物件</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>部署 MBAM 用戶端軟體。</p></td>
<td align="left"><p><a href="deploying-the-mbam-20-client-mbam-2.md" data-raw-source="[Deploying the MBAM 2.0 Client](deploying-the-mbam-20-client-mbam-2.md)">部署 MBAM 2.0 用戶端</a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>

 

## 設定實驗室電腦進行 MBAM 評估


本節包含可用於加速 MBAM 用戶端狀態報表的資訊。 不過，這些修改只能用於測試目的。

**記事** 下列各節中的資訊說明如何修改 Windows registry。 無法正確使用登錄編輯程式，可能會導致嚴重問題，可能需要重新安裝 Windows。 Microsoft 無法保證無法正確使用登錄編輯程式所造成的問題，因此無法解決。 使用登錄編輯程式的風險由您自負。

 

### 修改 MBAM 用戶端狀態報表頻率設定

使用群組原則設定 MBAM 用戶端喚醒和狀態報表頻率時，其最小值為90分鐘。 您可以在 MBAM 用戶端電腦上使用 Windows 登錄來將這些頻率變更為較低的值，以協助您加速測試。

若要修改 MBAM 用戶端狀態報表頻率設定：

1.  使用登錄編輯程式流覽至**HKLM\\Software\\Policies\\Microsoft\\FVE\\MDOPBitLockerManagement**。

2.  將**ClientWakeupFrequency**和**StatusReportingFrequency**的值變更為**1** ，以支援最小用戶端支援的值。 此變更會導致 MBAM 用戶端每分鐘報告一次。

3.  重新開機**BitLocker 管理用戶端服務**。

**記事** 若要設定這個低的值，您必須在登錄中手動設定。

 

### 修改 MBAM 用戶端服務啟動延遲

除了 MBAM 用戶端喚醒和狀態報表頻率之外，在用戶端電腦上啟動 MBAM 用戶端代理服務時，會有最多90分鐘的隨機延遲。 如果您不想要隨機延遲，請在 [ **HKLM\\Software\\Microsoft\\MBAM**] 下建立**NoStartupDelay**的**DWORD**值，將它的值設定為**1**，然後重新開機**BitLocker 管理用戶端服務**。

## 相關主題


[開始使用 MBAM 2.0](getting-started-with-mbam-20-mbam-2.md)

 

 





