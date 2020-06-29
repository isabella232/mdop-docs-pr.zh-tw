---
title: 委派管理實際執行環境的存取權
description: 委派管理實際執行環境的存取權
author: dansimp
ms.assetid: c1ebae2e-909b-4e64-b368-b7d3cc67b1eb
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4667a23f1584d7aab6143860721e326da6407afb
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802846"
---
# 委派管理實際執行環境的存取權


您可以在生產環境中變更群組原則物件（Gpo）的存取權，取代這些 Gpo 上任何現有的許可權。 您可以在網域層級設定許可權，在客戶不使用群組原則管理主控台（GPMC）中的 [**變更控制**] 資料夾時，允許或防止使用者編輯、刪除或修改生產環境中的 gpo 的安全性。

**注意**  
-   委派對生產環境的存取不會影響使用者連結 Gpo 的能力。

-   當 Gpo 受到控制或部署時，除了具有 [**讀取**] 和 [套用] 許可權的帳戶之外 **，還會**移除任何其他帳戶的存取權。

 

您必須具備高級群組原則管理（AGPM）或 AGPM 管理員（完全控制）角色的使用者帳戶，才能完成此程式。 請參閱本主題中的「其他注意事項」中的詳細資料。

**若要變更對生產環境中 Gpo 的存取權**

1.  在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。

2.  按一下 [**生產委託**] 索引標籤。

3.  若要針對沒有生產環境存取權的使用者或群組新增許可權，或針對有存取權的使用者或群組取代許可權：

    1.  按一下 [**新增**]，選取使用者或群組，然後按一下 **[確定]**。

    2.  針對生產環境選取要委派給該使用者或群組的許可權，然後按一下 **[確定]**。

4.  若要移除使用者或群組對生產環境的擁有權限，請選取該使用者或群組，按一下 [**移除**]，然後按一下 **[確定]**。

### 其他考量

-   根據預設，您必須是 AGPM 系統管理員（完全控制）才能執行此程式。 具體說來，您必須具有網域的 [**修改安全性**] 許可權。

-   無法在 [**生產委派**] 索引標籤上變更 AGPM 服務帳戶的許可權。

-   根據預設，下列帳戶在生產環境中擁有 Gpo 的許可權：

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">帳戶</th>
    <th align="left">Gpo 的預設許可權</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>&lt;AGPM 服務帳戶&gt;</p></td>
    <td align="left"><p>編輯設定、刪除、修改安全性</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>已驗證使用者</p></td>
    <td align="left"><p>讀取、套用</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>網域管理員</p></td>
    <td align="left"><p>編輯設定、刪除、修改安全性</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>企業系統管理員</p></td>
    <td align="left"><p>編輯設定、刪除、修改安全性</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>企業網網域控制站</p></td>
    <td align="left"><p>讀取</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>系統</p></td>
    <td align="left"><p>編輯設定、刪除、修改安全性</p></td>
    </tr>
    </tbody>
    </table>

     

-   [群組原則建立人擁有者] 群組中的成員資格應該受到限制，不會使用 soit 來避開對 Gpo 存取的 AGPM 管理。 （在 [**群組原則管理主控台**] 中，按一下要管理 gpo 的林和網域中的 [**群組原則物件**]，按一下 [**委派**]，然後設定設定以符合貴組織的需求。）

### 其他參考資料

-   [設定進階群組原則管理](configuring-advanced-group-policy-management.md)

 

 





