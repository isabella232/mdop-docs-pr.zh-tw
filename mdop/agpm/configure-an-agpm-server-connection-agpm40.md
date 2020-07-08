---
title: 設定 AGPM 伺服器連線
description: 設定 AGPM 伺服器連線
author: dansimp
ms.assetid: 409cbbcf-3b0e-459d-9bd2-75cb7b9430b0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d7fdc26045b478da14957cdfe6000d58ab72a064
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802074"
---
# 設定 AGPM 伺服器連線


若要確保您已連線至正確的中央封存，請查看 AGPM 服務器連線的設定。 如果 AGPM 系統管理員（完全控制）尚未為您設定 AGPM 服務器連線，則您必須手動設定。

**選取 AGPM 服務器**

1.  在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。

2.  在 [詳細資料] 窗格中，按一下 [ **AGPM 服務器**] 索引標籤：

    -   如果 [ **Agpm 伺服器**] 索引標籤上的選項無法使用，就是由 AGPM 系統管理員集中設定。

    -   如果 [ **Agpm server** ] 索引標籤上有可用的選項，請為 agpm 伺服器（例如 server.contoso.com）和 agpm 服務偵聽的埠（預設為埠4600）輸入完整的電腦名稱稱。 按一下 [套用] **，然後按一下** **[是]** 以確認。

### 其他考量

-   已選取的 AGPM 服務器會決定要顯示在 [**目錄**] 索引標籤上的 gpo，以及 [**網域委派**] 索引標籤設定的套用位置。 如果不是透過管理範本來集中管理，每個群組原則管理員都必須設定此設定，以指向網域的 AGPM 服務器。

### 其他參考資料

-   [執行檢閱者工作](performing-reviewer-tasks-agpm40.md)

 

 





