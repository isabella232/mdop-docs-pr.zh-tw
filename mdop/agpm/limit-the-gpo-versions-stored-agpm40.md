---
title: 限制儲存的 GPO 版本
description: 限制儲存的 GPO 版本
author: dansimp
ms.assetid: d802c7b6-f303-4b23-aefd-f19f1300b0ff
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: df6f6df2e2b1bae2cd972b67b76c27905622a723
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802689"
---
# 限制儲存的 GPO 版本


根據預設，所有受控制的群群組原則物件（GPO）版本都會保留在 AGPM 服務器上的封存中。 不過，您可以限制每個 GPO 保留的版本數，並在超過該限制時刪除較舊的版本。 當 GPO 版本刪除時，版本的記錄會保留在 GPO 的記錄中，但 GPO 版本本身已從封存中刪除。

您必須具備高級群組原則管理（AGPM）中具有 AGPM 系統管理員（完全控制）角色或必要許可權的使用者帳戶，才能完成此程式。 請參閱本主題中的「其他注意事項」中的詳細資料。

**限制儲存的 GPO 版本數**

1.  在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。

2.  在 [詳細資料] 窗格中，按一下 [ **AGPM 服務器**] 索引標籤。

3.  選取 [**從封存刪除每個 gpo 的舊版版本**] 核取方塊，然後輸入要儲存的每個 gpo 的最大 gpo 版本數（不包括目前的版本）。 若要只保留目前的版本，請輸入0。 最大值不得大於999。

    **重要** 只有 [歷程**記錄**] 視窗 [**唯一版本**] 索引標籤上顯示的 GPO 版本，才會計算出該限制。

     

4.  按一下 [**套用**] 按鈕。

### 其他考量

-   根據預設，您必須是 AGPM 系統管理員（完全控制）才能執行此程式。 具體說來，您必須擁有 [**清單內容**] 和 [修改網域的**選項**] 許可權。

-   您可以在歷程記錄中將其標示為無法刪除，以防止 GPO 版本遭到刪除。 若要這樣做，請以滑鼠右鍵按一下 GPO 歷程記錄中的版本，然後按一下 [**不要刪除**]。

### 其他參考資料

-   [管理封存](managing-the-archive-agpm40.md)

 

 





