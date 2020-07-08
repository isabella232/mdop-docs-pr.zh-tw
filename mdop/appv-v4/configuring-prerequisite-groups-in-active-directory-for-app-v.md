---
title: 在 Active Directory 中設定 App-V 的必要群組
description: 在 Active Directory 中設定 App-V 的必要群組
author: dansimp
ms.assetid: 0010d534-46c0-44a3-b5c1-621b4d5e2c31
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: aa1ab6393dee20203b715311d4e1dfdc4c22c679
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809009"
---
# 在 Active Directory 中設定 App-V 的必要群組


在您安裝 Microsoft Application Virtualization （App-v）管理伺服器之前，您必須在 Active Directory 中建立下列物件。 App-v 使用 Active Directory 群組來控制對應用程式和管理功能的存取權。 您將會在伺服器安裝程式中及發佈應用程式時使用這些群組。

## 在 Active Directory 中針對應用程式虛擬化設定必備群組


下表列出安裝 App-v 所需的 Active Directory 群組。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">物件</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>組織單位（OU）</p></td>
<td align="left"><p>針對應用程式 V 所需的特定群組，在 Active Directory 中建立一個 OU。</p></td>
</tr>
<tr class="even">
<td align="left"><p>App-v 系統管理群組</p></td>
<td align="left"><p>在安裝 App-v Management Server 期間，您必須選取 Active Directory 群組，以將管理存取權控制到管理主控台。 針對應用程式 V 管理員建立安全性群組，並將需要使用管理主控台的每位使用者新增至此群組。 您無法直接從 App-v Management Server 安裝程式建立此群組。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>App-v Users 群組</p></td>
<td align="left"><p>App-v 要求存取 App-v 函數的每個使用者帳戶，都是與單一群組相關聯的提供者原則的成員，用於一般平臺存取。 使用現有的群組;例如，如果所有使用者都能存取 app-v，或建立新的群組，則是網域使用者。</p></td>
</tr>
<tr class="even">
<td align="left"><p>應用程式群組</p></td>
<td align="left"><p>App-v 會將適當的應用程式關聯至使用 Active Directory 群組的個別應用程式。 針對每個應用程式建立 Active Directory 群組，並視需要將使用者指派給這些群組，以控制使用者對應用程式的存取權。</p></td>
</tr>
</tbody>
</table>

 

## 相關主題


[Application Virtualization 部署需求](application-virtualization-deployment-requirements.md)

[如何針對 App-V Management Server 設定 Windows Server 2008](how-to-configure-windows-server-2008-for-app-v-management-servers.md)

 

 





