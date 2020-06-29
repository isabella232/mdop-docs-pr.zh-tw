---
title: 標示 GPO 的目前版本
description: 標示 GPO 的目前版本
author: dansimp
ms.assetid: 3845211a-0bc9-4875-9906-cb758c443825
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f9e656258591a56397c5a8053b2e98772f57949a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802709"
---
# 標示 GPO 的目前版本


您可以標示目前版本的群組原則物件（GPO），以便在其記錄中輕鬆識別。 如果發生問題，您可以使用標籤來找出您可以回滾的已知完好版本。 此外，您也可以一次將多個 Gpo 標示成相同的標籤，您可以將相關的 Gpo 標示為必須回滾到同一個點（如果稍後需要回滾）。

具有 [編輯者]、[核准者] 或 [AGPM 管理員（完全控制）] 角色的使用者帳戶，或 [高級群組原則管理] （AGPM）中的必要許可權，才能完成此程式。 請參閱本主題中的「其他注意事項」中的詳細資料。

**在其歷史記錄中標示目前的 Gpo 版本**

1.  在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。

2.  在 [**內容**] 索引標籤上，按一下 [**受控**] 索引標籤以顯示受控制的 gpo。

3.  按一下要為目前版本加上標籤的 GPO。 若要選取多個 Gpo，請按 SHIFT 鍵，然後按一下連續 Gpo 群組中的最後一個 GPO，或按下 CTRL 並按一下個別 Gpo。 以滑鼠右鍵按一下選取的 GPO，然後按一下 [**標籤**]。

4.  輸入要在選取的每個 GPO 之歷程記錄中顯示的標籤和批註，然後按一下 **[確定]**。

5.  當**進度**視窗顯示整體進度完成時，請按一下 [**關閉**]。

### 其他考量

-   根據預設，您必須是編輯者、核准者或 AGPM 系統管理員（完全控制），才能執行此程式。 具體說來，您必須擁有**清單內容**，並**編輯設定**或為 gpo**部署 gpo**許可權。

### 其他參考資料

-   [編輯 GPO](editing-a-gpo-agpm30ops.md)

 

 





