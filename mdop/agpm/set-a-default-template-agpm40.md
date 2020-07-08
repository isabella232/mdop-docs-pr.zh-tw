---
title: 設定預設範本
description: 設定預設範本
author: dansimp
ms.assetid: 07208b6b-cb3a-4f6c-9c84-36d4dc1486d8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 51a13c2c57e38adca883a6eb962d8c5eae4316db
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802534"
---
# 設定預設範本


就像編輯者一樣，您可以指定哪些可用範本將是為所有群組原則管理員建立新的群組原則物件（Gpo）所建議的預設範本。

**記事** 範本是一個無法編輯且靜態的 GPO 版本，以做為建立新的可編輯 Gpo 的起點。

 

具有 [編輯者] 或 [AGPM 管理員] （完全控制）角色的使用者帳戶，或 [高級群組原則管理] （AGPM）中的必要許可權，才能完成此程式。 請參閱本主題中的「其他注意事項」中的詳細資料。

**若要設定建立新 Gpo 時使用的預設範本**

1.  在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。

2.  在 [詳細資料] 窗格的 [**內容**] 索引標籤上，按一下 [**範本**] 索引標籤以顯示可用範本。

3.  以滑鼠右鍵按一下您要設定為預設值的範本，然後按一下 [**設成預設值**]。

4.  按一下 **[是]** 以進行確認。

5.  當**進度**視窗顯示整體進度完成時，請按一下 [**關閉**]。 預設範本具有藍色圖示，且狀態在 [**範本**] 索引標籤上會標示為 **[範本（預設）** ]。

### 其他考量

-   根據預設，您必須是編輯者或 AGPM 系統管理員（完全控制）才能執行此程式。 具體說來，您必須擁有**清單內容**，並為該網域**建立範本**許可權。

-   將範本設定為預設值後，該範本就會是初始在新的 [**受管理的 gpo** ] 對話方塊中選取的範本（當群組原則系統管理員建立新的 gpo 時）。 不過，它們會有選取任何其他 GPO 範本的選項，包括** &lt; 空白 gpo &gt; **，不包含任何設定。

-   重新命名或刪除範本不會影響從該範本建立的 Gpo。

-   因為範本不能變更，所以範本沒有歷程記錄。

### 其他參考資料

-   [建立範本和設定預設範本](creating-a-template-and-setting-a-default-template-agpm40.md)

-   [要求建立新的受控制 GPO](request-the-creation-of-a-new-controlled-gpo-agpm40.md)

 

 





