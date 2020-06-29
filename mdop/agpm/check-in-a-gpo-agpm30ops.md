---
title: 存回 GPO
description: 存回 GPO
author: dansimp
ms.assetid: 437397db-c94b-4940-b1a4-05442619ebee
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8c37144cb7c2d150d46dd1172a37717743f76ee3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802117"
---
# 存回 GPO


通常，編輯人員應該在其修改完成時，檢查他們已編輯的群組原則物件（Gpo）。 （如需詳細資訊，請參閱在[離線編輯 GPO](edit-a-gpo-offline-agpm30ops.md)。）不過，如果編輯工具無法使用，核准者也可以在 GPO 中存回。

具有 [編輯者]、[核准者] 或 [AGPM 管理員（完全控制）] 角色的使用者帳戶，或 [高級群組原則管理] （AGPM）中的必要許可權，才能完成此程式。 請參閱本主題中的「其他注意事項」中的詳細資料。

**若要存回由編輯工具取出的 GPO**

1.  在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。

2.  在 [**內容**] 索引標籤上，按一下 [**受控**] 索引標籤以顯示受控制的 gpo。

    -   若要捨棄編輯器所做的任何變更，請以滑鼠右鍵按一下該 GPO，按一下 [**復原取出**]，然後按一下 **[是]** 以確認。

    -   若要保留編輯器所做的變更，請以滑鼠右鍵按一下該 GPO，然後按一下 [**存回**]。

3.  輸入要在 [GPO 審核追蹤] 中顯示的批註，然後按一下 **[確定]**。

4.  當**進度**視窗顯示整體進度完成時，請按一下 [**關閉**]。 在 [**受控**] 索引標籤上，GPO 的狀態會標示為 [**已核**取]。

### 其他考量

-   根據預設，您必須是編輯者、核准者或 AGPM 系統管理員（完全控制），才能執行此程式。 具體說來，您必須擁有**清單內容**，並**編輯設定**或為 gpo**部署 gpo**許可權。 如果您不是核准者或 AGPM 管理員（或具有「**部署 GPO** 」許可權的其他群組原則管理員），則您必須是已取出該 Gpo 的編輯者。

### 其他參考資料

-   [執行核准者工作](performing-approver-tasks-agpm30ops.md)

-   [離線編輯 GPO](edit-a-gpo-offline-agpm30ops.md)

 

 





