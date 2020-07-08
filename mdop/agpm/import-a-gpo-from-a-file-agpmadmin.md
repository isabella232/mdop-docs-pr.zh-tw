---
title: 從檔案匯入 GPO
description: 從檔案匯入 GPO
author: dansimp
ms.assetid: 2cbcda72-4de3-47ad-aaf8-4fc7341d5a00
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 04819dacac8df73f0a61cace0dab8b9fa79b7307
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802742"
---
# 從檔案匯入 GPO


在高級群組原則管理（AGPM）中，如果您是 AGPM 系統管理員（完全控制），而您已將群組原則物件（GPO）匯出到 CAB 檔案，您可以將該 GPO 的原則設定匯入到新的 GPO，或另一個目錄林中網域中的現有 GPO。 如需將 GPO 設定匯出到 CAB 檔案的相關資訊，請參閱[將 Gpo 匯出至](export-a-gpo-to-a-file.md)檔案。

需要使用 AGPM 系統管理員角色的使用者帳戶，或在 AGPM 中所需的許可權，才能將原則設定匯入新的受控 GPO。 需要在 AGPM 中使用 [編輯者] 或 [AGPM 管理員角色] 或 [必要] 許可權的使用者帳戶，才能將原則設定匯入現有的 GPO。 請參閱本主題中的「其他注意事項」中的詳細資料。

## 從檔案匯入原則設定


從檔案匯入原則設定時，您可以將它們匯入到新的 GPO 或現有的 GPO 中。 不過，如果您將原則設定匯入到現有的 GPO 中，則會取代其中的所有原則設定。

-   [將原則設定匯入到新的受控 GPO](#bkmk-new)

-   [將原則設定匯入現有的 GPO](#bkmk-existing)

### <a href="" id="bkmk-new"></a>

**將原則設定匯入新的受控 GPO**

1.  在 [**群組原則管理] 主控台**樹狀結構中，按一下您要匯入原則設定的網域中的 [**變更控制**]。

2.  在 [**內容**] 索引標籤上，按一下 [**受控**] 索引標籤以顯示受控制的 gpo。

3.  建立新的受控 GPO。 在 [**新的受控 GPO** ] 對話方塊中，按一下 [匯**入**]，然後按一下 [**啟動嚮導]**。 如需如何建立 GPO 的詳細資訊，請參閱[建立新的受控 GPO](create-a-new-controlled-gpo-agpm40.md)。

4.  依照 [匯**入設定] 嚮導**中的指示來選取 GPO 備份，然後針對新的 gpo 匯入策略設定，然後輸入新 gpo 之審核追蹤的意見。

### <a href="" id="bkmk-existing"></a>

**將原則設定匯入現有的 GPO**

1.  在 [**群組原則管理] 主控台**樹狀結構中，按一下您要匯入原則設定的網域中的 [**變更控制**]。

2.  在 [**內容**] 索引標籤上，按一下 [**受控**] 索引標籤以顯示受控制的 gpo。

3.  取出您要匯入原則設定的目的地 GPO。

4.  以滑鼠右鍵按一下目的地 GPO，指向 [匯**入來源**]，然後**按一下 [** 檔案]。

5.  依照 [匯**入設定] 嚮導**中的指示來選取 GPO 備份、匯入其原則設定以取代目的地 gpo 中的那些，然後輸入目標 gpo 之審核追蹤的批註。 根據預設，當嚮導完成時，會檢入目的地 GPO。

### 其他考量

-   若要將原則設定匯入到新的受控 GPO，您必須擁有**清單內容**、匯**入 GPO**，以及為網域**建立 GPO**許可權。 根據預設，您必須是 AGPM 系統管理員才能執行此程式。

-   若要將原則設定匯入至現有的 GPO，您必須擁有**清單內容**、**編輯設定**及針對網域的匯**入 gpo**許可權，而且 GPO 必須由您取出。 根據預設，您必須是編輯者或 AGPM 系統管理員（完全控制）才能執行此程式。

### 其他參考資料

-   [管理封存](managing-the-archive-agpm40.md)

 

 





