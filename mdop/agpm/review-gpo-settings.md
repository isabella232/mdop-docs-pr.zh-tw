---
title: 檢閱 GPO 設定
description: 檢閱 GPO 設定
author: dansimp
ms.assetid: e82570b2-d8ce-4bf0-8ad7-8910409f3041
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 681492f423266ce3722bb1a657ee93527c6bdd7b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801774"
---
# 檢閱 GPO 設定


您可以在任何版本的群群組原則物件（GPO）中產生以 HTML 與 XML 為基礎的報告來檢查設定。

具有 [檢閱者]、[編輯]、[核准者] 或 [AGPM 管理員（完全控制）] 角色的使用者帳戶，或 [高級群組原則管理] 中的必要許可權必須完成此程式。 請參閱本主題中的「其他注意事項」中的詳細資料。

**若要查看任何版本的 GPO 中的設定**

1.  在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。

2.  在 [詳細資料] 窗格的 [**內容**] 索引標籤上，按一下索引標籤以顯示 [gpo]。

3.  按兩下該 GPO 以顯示其歷程記錄。

4.  以滑鼠右鍵按一下要查看其設定的 GPO 版本，按一下 [**設定**]，然後按一下 [ **HTML 報表**] 或 [ **XML 報表**]，以顯示 GPO 設定的摘要。

### 其他考量

-   根據預設，您必須是檢閱者、編輯者或 AGPM 管理員（完全控制），才能執行此程式。 具體來說，您必須擁有 [**清單內容**] 和 [**讀取設定**] 許可權給 GPO。 此外，若要顯示 Gpo 清單，您必須擁有該網域的 [**清單內容**] 許可權。

### 其他參考資料

-   [執行檢閱者工作](performing-reviewer-tasks.md)

 

 





