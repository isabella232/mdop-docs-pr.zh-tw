---
title: 規劃使用電子軟體發佈系統部署 App-V 5.1
description: 規劃使用電子軟體發佈系統部署 App-V 5.1
author: dansimp
ms.assetid: c26602c2-5e8d-44e6-90df-adacc593607e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: fde3f0ea4f1dec72b97143b4b27dd0b32a503b15
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800334"
---
# 規劃使用電子軟體發佈系統部署 App-V 5.1


如果您使用電子軟體發佈系統來部署 App-v 套件，請參閱下列規劃考慮。 如需使用 System Center Configuration Manager 來部署 App-v 的相關資訊，請參閱[Configuration Manager 中的應用程式管理簡介](https://go.microsoft.com/fwlink/?LinkId=281816)。

檢查下列元件與架構需求選項，這些選項會在您使用 ESD 部署 App-v 套件時套用：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">部署需求或選項</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>App-v 管理伺服器、管理資料庫及發佈伺服器不是必要的。</p></td>
<td align="left"><p>這些函數是由已實施的 ESD 解決方案來處理。</p></td>
</tr>
<tr class="even">
<td align="left"><p>您可以將 App-v 報表服務器與報告資料庫與 ESD 並行部署。</p></td>
<td align="left"><p>並行部署可讓您收集資料並產生報告。</p>
<p>如果您啟用應用程式 V 用戶端來傳送報告資訊，而您不是使用 App-v 報表服務器，則報告資料會儲存在相關聯的 .xml 檔案中。</p></td>
</tr>
</tbody>
</table>

 






## 相關主題


[規劃部署 App-V](planning-to-deploy-app-v51.md)

 

 





