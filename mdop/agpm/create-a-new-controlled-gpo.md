---
title: 建立新的受控制 GPO
description: 建立新的受控制 GPO
author: dansimp
ms.assetid: b43ce0f4-4519-4278-83c4-c7d5163ddd11
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0a64e22036bfe99e1d5012d732e3f2e081acdcca
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802878"
---
# 建立新的受控制 GPO


透過**變更控制**節點建立的新群組原則物件（gpo）會自動受到控制，讓您使用高級的群組原則管理（AGPM）來管理它們。

使用者帳戶必須有核准者或 AGPM 系統管理員（完全控制）角色，或高級群組原則管理中的必要許可權，才能完成此程式。 請參閱本主題中的「其他注意事項」中的詳細資料。

**若要建立透過 AGPM 管理變更控制的新 GPO**

1.  在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。

2.  以滑鼠右鍵按一下 [**變更控制**] 節點，然後按一下 [**新增受控制的 GPO**]。

3.  在 [**新的受控 GPO** ] 對話方塊中：

    1.  輸入新 GPO 的名稱。

    2.  [選用]：輸入要在 GPO 的 [歷程**記錄**] 中顯示的新 GPO 的批註。

    3.  若要將新的 GPO 立即部署到生產環境，請按一下 [**建立 live**]。 若要在不立即部署的情況下建立新的 GPO，請按一下 [**離線建立**]。

    4.  選取要用來做為新 GPO 起點的 GPO 範本。

    5.  按一下 \[確定\] ****。

4.  當**進度**視窗顯示整體進度完成時，請按一下 [**關閉**]。 新的 GPO 會顯示在 [**受控**] 索引標籤的 [gpo] 清單中。

### 其他考量

-   根據預設，您必須是 [核准者] 或 [AGPM 管理員（完全控制）]，才能執行此程式。 具體說來，您必須擁有**清單內容**，並為網域**建立 GPO**許可權。

### 其他參考資料

-   [建立、控制或匯入 GPO](creating-controlling-or-importing-a-gpo-approver.md)

 

 





