---
title: 要求還原刪除的 GPO
description: 要求還原刪除的 GPO
author: dansimp
ms.assetid: dcc3baea-8af7-4886-a301-98b6ac5819cd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f85620ed7d9afe676caabe4ce0f7da4fd8d5ae13
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802589"
---
# 要求還原刪除的 GPO


除非您是 [核准者] 或 [AGPM 管理員（完全控制）]，否則您必須從 [回收站] 中要求還原已刪除的群組原則物件（GPO），才能將其傳回封存。

必須具備高級群組原則管理（AGPM）中具有編輯者角色或必要許可權的使用者帳戶，才能完成此程式。 請參閱本主題中的「其他注意事項」中的詳細資料。

**要求還原已刪除的 GPO**

1.  在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。

2.  在 [**內容**] 索引標籤上，按一下 [**回收站**] 索引標籤以顯示已刪除的 gpo。

3.  以滑鼠右鍵按一下您要還原的 GPO，然後按一下 [**還原**]。

4.  除非您有還原 Gpo 的特殊許可權，否則您必須提交已刪除 GPO 的還原要求。 若要接收申請的複本，請在 [**抄送**] 欄位中輸入您的電子郵件地址。 輸入要顯示在 GPO 的審核追蹤中的批註，然後按一下 [**提交**]。

5.  當**進度**視窗顯示整體進度完成時，請按一下 [**關閉**]。 該 GPO 隨即會從 [**回收站**] 索引標籤中移除，並顯示在 [**受控**] 索引標籤上。

**記事** 如果 GPO 已從生產環境中刪除，則將其還原到封存後，就不會自動將它重新部署到生產環境。 若要將 GPO 傳回生產環境，請部署 GPO。 如需詳細資訊，請參閱[部署 GPO](deploy-a-gpo-agpm30ops.md)。

 

### 其他考量

-   根據預設，您必須是編輯器才能執行此程式。 具體說來，您必須擁有該 GPO 的 [**清單內容**] 和 [**編輯設定**] 許可權。

-   若要在獲核准前收回您的要求，請按一下 [**待定**] 索引標籤。以滑鼠右鍵按一下該 GPO，然後按一下 [**收回**]。 GPO 將會傳回 [**回收站**] 索引標籤。

### 其他參考資料

-   [刪除、還原或摧毀 GPO](deleting-restoring-or-destroying-a-gpo-agpm30ops.md)

 

 





