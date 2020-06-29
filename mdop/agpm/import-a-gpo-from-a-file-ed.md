---
title: 從檔案匯入 GPO
description: 從檔案匯入 GPO
author: dansimp
ms.assetid: 6e901a52-1101-4fed-9f90-3819b573b378
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e15704806f089bb0d8530cd84df64b0889413426
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802730"
---
# 從檔案匯入 GPO


在 [高級群組原則管理（AGPM）] 中，如果您已將群組原則物件（GPO）匯出到 CAB 檔案，您可以將該 GPO 的原則設定匯入另一個目錄林中網域中的現有 GPO。 將原則設定匯入現有的 GPO 會取代該 GPO 中的所有原則設定。 如需將 GPO 設定匯出到 CAB 檔案的相關資訊，請參閱[將 Gpo 匯出至](export-a-gpo-to-a-file.md)檔案。

具有 [編輯者] 或 [AGPM 管理員] （完全控制）角色的使用者帳戶，或 [高級群組原則管理] （AGPM）中的必要許可權，才能完成此程式。請參閱本主題中的「其他注意事項」中的詳細資料。

## <a href="" id="bkmk-existing"></a>


**將原則設定匯入現有的 GPO**

1.  在 [**群組原則管理] 主控台**樹狀結構中，按一下您要匯入原則設定的網域中的 [**變更控制**]。

2.  在 [**內容**] 索引標籤上，按一下 [**受控**] 索引標籤以顯示受控制的 gpo。

3.  取出您要匯入原則設定的目的地 GPO。

4.  以滑鼠右鍵按一下目的地 GPO，指向 [匯**入來源**]，然後**按一下 [** 檔案]。

5.  依照 [匯**入設定] 嚮導**中的指示來選取 GPO 備份、匯入其原則設定以取代目的地 gpo 中的那些，然後輸入目標 gpo 之審核追蹤的批註。 根據預設，當嚮導完成時，會檢入目的地 GPO。

### 其他考量

-   根據預設，您必須是編輯者或 AGPM 系統管理員（完全控制）才能執行此程式。 具體來說，您必須擁有**清單內容**、**編輯設定**及網域的匯**入 GPO**許可權，而且 GPO 必須由您取出。

-   雖然編輯程式無法在建立時將原則設定匯入到新的 GPO 中，但是編輯者可以要求建立新的 GPO，然後在建立之後將原則設定匯入到新的 gpo 中。

### 其他參考資料

-   [使用測試環境](using-a-test-environment.md)

 

 





