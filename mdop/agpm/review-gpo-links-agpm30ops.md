---
title: 檢閱 GPO 連結
description: 檢閱 GPO 連結
author: dansimp
ms.assetid: 5ae95afc-2b89-45cf-916c-efe2d43b2211
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6532a669c6841c2342514c0911f74bc0b1fbc86d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801785"
---
# 檢閱 GPO 連結


您可以顯示一個圖表，顯示您所選取的群組原則物件（GPO）或 Gpo 連結至組織單位的位置。 GPO 連結圖表會在每次控制、匯入或檢入 GPO 時進行更新。

具有 [檢閱者]、[編輯者] 或 [AGPM 管理員] （完全控制）角色的使用者帳戶，或需要高級群組原則管理（AGPM）中的必要許可權，才能完成此程式。 請參閱本主題中的「其他注意事項」中的詳細資料。

## 查看 GPO 連結


-   [一或多個 Gpo](#bkmk-gpos)

-   [針對一或多個 GPO 版本](#bkmk-gpo-versions)

### <a href="" id="bkmk-gpos"></a>

**顯示一個或多個 Gpo 的 GPO 連結**

1.  在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。

2.  在 [詳細資料] 窗格的 [**內容**] 索引標籤上，按一下 [**控制**]、[**待定**] 或 [**回收站**] 索引標籤以顯示 gpo

3.  選取一個或多個要顯示連結的 Gpo，以滑鼠右鍵按一下選取的 GPO，按一下 [**設定**]，然後按一下 [ **GPO 連結**]，以顯示包含所選 gpo 連結的網域和組織單位圖表。

### <a href="" id="bkmk-gpo-versions"></a>

**顯示一個或多個版本 GPO 的 GPO 連結**

1.  在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。

2.  在 [詳細資料] 窗格的 [**內容**] 索引標籤上，按一下 [**控制**] 或 [**回收站**] 索引標籤以顯示 gpo

3.  按兩下該 GPO 以顯示其歷程記錄。

4.  以滑鼠右鍵按一下要查看其設定的 GPO 版本，按一下 [**設定**]，然後按一下 [ **HTML 報表**] 或 [ **XML 報表**]，以顯示 GPO 設定的摘要。

### 其他考量

-   根據預設，您必須是檢閱者、編輯者或 AGPM 管理員（完全控制），才能執行此程式。 具體來說，您必須擁有 [**清單內容**] 和 [**讀取設定**] 許可權給 GPO。 此外，若要顯示 Gpo 清單，您必須擁有該網域的 [**清單內容**] 許可權。

### 其他參考資料

-   [執行檢閱者工作](performing-reviewer-tasks-agpm30ops.md)

 

 





