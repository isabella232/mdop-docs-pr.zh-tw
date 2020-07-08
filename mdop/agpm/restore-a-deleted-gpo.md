---
title: 還原刪除的 GPO
description: 還原刪除的 GPO
author: dansimp
ms.assetid: e6953296-7b7d-4d1e-ad82-d4a23044cdd7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2cba097ecd651a91f828901d8115a7020d6da819
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801806"
---
# 還原刪除的 GPO


[高級群組原則管理] （AGPM）可讓核准者從回收站還原已刪除的群組原則物件（GPO），並將其傳回封存。

具有 [編輯者]、[核准者] 或 [AGPM 管理員（完全控制）] 角色或 [高級群組原則管理] 中的必要許可權的使用者帳戶必須完成此程式。 請參閱本主題中的「其他注意事項」中的詳細資料。

**還原已刪除的 GPO**

1.  在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。

2.  在 [**內容**] 索引標籤上，按一下 [**回收站**] 索引標籤以顯示已刪除的 gpo。

3.  以滑鼠右鍵按一下要還原的 GPO，然後按一下 [**還原**]。

4.  輸入要顯示在 GPO 歷程記錄中的批註，然後按一下 **[確定]**。

5.  當**進度**視窗顯示整體進度完成時，請按一下 [**關閉**]。 該 GPO 隨即會從 [**回收站**] 索引標籤中移除，並顯示在 [**受控**] 索引標籤上。

**記事** 如果 GPO 已從生產環境中刪除，則將其還原到封存後，就不會自動將它重新部署到生產環境。 若要將 GPO 傳回生產環境，請部署 GPO。 如需詳細資訊，請參閱[部署 GPO](deploy-a-gpo.md)。

 

### 其他考量

-   根據預設，您必須是編輯者、核准者或 AGPM 系統管理員（完全控制），才能執行此程式。 具體說來，您必須擁有**清單內容**，並**編輯設定**、**部署 GPO**或刪除 gpo 的**gpo**許可權。

### 其他參考資料

-   [刪除、還原或摧毀 GPO](deleting-restoring-or-destroying-a-gpo.md)

 

 





