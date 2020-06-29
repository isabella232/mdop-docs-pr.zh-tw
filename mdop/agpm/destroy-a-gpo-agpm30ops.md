---
title: 摧毀 GPO
description: 摧毀 GPO
author: dansimp
ms.assetid: bfabd71a-47f3-462e-b86f-5f15762b9e28
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 842a546c4db9cc6048908521baa05c6cc1a1a8a9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801914"
---
# 摧毀 GPO


核准者可以銷毀群組原則物件（GPO），並將它從 [回收站] 中移除，然後將它永久刪除，使其無法再還原。

使用者帳戶必須有核准者或 AGPM 管理員（完全控制）角色或高級群組原則管理（AGPM）中的必要許可權，才能完成此程式。 請參閱本主題中的「其他注意事項」中的詳細資料。

**若要永久刪除 GPO，使其無法再還原**

1.  在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。

2.  在 [**內容**] 索引標籤上，按一下 [**回收站**] 索引標籤以顯示已刪除的 gpo。

3.  以滑鼠右鍵按一下要銷毀的 GPO，然後按一下 [**銷毀**]。

4.  按一下 **[是]** 以確認您要從封存永久刪除選取的 GPO 及所有備份。

5.  當**進度**視窗顯示整體進度完成時，請按一下 [**關閉**]。 該 GPO 隨即會從 [**回收站**] 索引標籤中移除，且會永久刪除。

### 其他考量

-   根據預設，您必須是 [核准者] 或 [AGPM 管理員（完全控制）]，才能執行此程式。 具體說來，您必須擁有**清單內容**，並刪除 GPO 的**gpo**許可權。

### 其他參考資料

-   [刪除、還原或摧毀 GPO](deleting-restoring-or-destroying-a-gpo-agpm30ops.md)

 

 





