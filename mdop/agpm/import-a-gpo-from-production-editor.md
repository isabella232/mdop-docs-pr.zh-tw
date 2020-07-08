---
title: 從生產匯入 GPO
description: 從生產匯入 GPO
author: dansimp
ms.assetid: ffa02b2a-2a43-4fc0-a06e-7d4b59022cc3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 239ac6938645325292bfc647ef89a77710c5f074
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802713"
---
# 從生產匯入 GPO


如果您在 [高級群組原則管理] （AGPM）外，在受管理的群群組原則物件（GPO）中進行變更，您可以從生產環境中匯入 GPO 複本，並將其儲存到封存，以使封存和生產環境保持一致的狀態。 （若要匯入不受管理的 GPO，請控制該 GPO。 請參閱[對先前不受管理的 GPO 的要求控制權](request-control-of-a-previously-uncontrolled-gpo.md)）。

具有 [編輯者]、[核准者] 或 [AGPM 管理員（完全控制）] 角色或 [高級群組原則管理] 中的必要許可權的使用者帳戶必須完成此程式。 請參閱本主題中的「其他注意事項」中的詳細資料。

**從生產環境匯入 GPO**

1.  在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。

2.  在 [**內容**] 索引標籤上，按一下 [**受控**] 索引標籤以顯示受控制的 gpo。

3.  以滑鼠右鍵按一下該 GPO，然後按一下 [**從生產匯入**]。

4.  輸入 GPO 之審核追蹤的批註，然後按一下 **[確定]**。

### 其他考量

-   根據預設，您必須是編輯者、核准者或 AGPM 系統管理員（完全控制），才能執行此程式。 具體說來，您必須擁有**清單內容**，並**編輯設定**、**部署 GPO**或刪除 gpo 的**gpo**許可權。

### 其他參考資料

-   [建立、控制或匯入 GPO](creating-controlling-or-importing-a-gpo-editor.md)

 

 





