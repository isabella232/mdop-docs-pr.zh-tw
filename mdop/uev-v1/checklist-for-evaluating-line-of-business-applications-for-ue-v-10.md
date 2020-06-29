---
title: 評估適用於 UE-V 1.0 之企業營運應用程式的檢查清單
description: 評估適用於 UE-V 1.0 之企業營運應用程式的檢查清單
author: dansimp
ms.assetid: 3bfaab30-59f7-4099-abb1-d248ce0086b8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 133bc5d195763b7281fd8d152e153231ac4c4d47
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811768"
---
# 評估適用於 UE-V 1.0 之企業營運應用程式的檢查清單


若要評估您在 UE-V 部署中應包含哪一項行業應用程式，請考慮下列事項：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>此應用程式是否包含使用者可自訂的設定？</p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>這些設定漫遊的使用者是否很重要？</p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>這些使用者設定已經由應用程式管理或設定原則方案所管理嗎？ UE-V 在 [登入]、[解除鎖定] 或 [遠端連線] 事件中，在應用程式啟動和 Windows 設定中套用應用程式設定。 如果您將 UE-V 與其他設定原則方案搭配使用，使用者可能會遇到漫遊設定不一致的問題。</p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>電腦是否有特定的應用程式設定？ 與硬體或特定電腦配置相關聯的應用程式喜好設定和自訂，不會在多個會話中持續漫遊，而且可能會造成應用程式不佳的體驗。</p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>[應用程式檔案] 目錄或 [使用者 <strong> </strong> 名稱] \ <strong> AppData </strong>  \  <strong> LocalLow </strong> 目錄中的檔案目錄中的 [應用程式儲存] 設定 儲存在上述任一位置的應用程式資料通常不應與使用者漫遊，因為這項資料是針對電腦所專用，或因為資料太大而無法漫遊。</p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>應用程式會將任何設定儲存在檔案中，包含不應漫遊的其他應用程式資料？ UE-V 會將檔案同步處理為單一單元。 如果設定儲存在包括 [設定] 以外的應用程式資料的檔案中，則同步處理這項額外的資料可能會造成不佳的應用程式體驗。</p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>包含這些設定的檔案有多大？ 較大的檔案可能會影響設定同步處理的效能。 包括大型檔案會影響設定同步處理的效能。</p></td>
</tr>
</tbody>
</table>

 

## 相關主題


[為 UE-V 組態方法進行規劃](planning-for-ue-v-configuration-methods.md)

[為 UE-V 1.0 進行規劃](planning-for-ue-v-10.md)

 

 





