---
title: 控制不受控制的 GPO
description: 控制不受控制的 GPO
author: dansimp
ms.assetid: dc81545c-8da5-4b6f-b266-f01a82e27c6b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 418e2a4100e1d824198b7d05034443948ec8a44c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802002"
---
# 控制不受控制的 GPO


若要為群群組原則物件（GPO）提供變更控制，您必須先控制 GPO。

使用者帳戶必須有核准者或 AGPM 管理員（完全控制）角色或高級群組原則管理（AGPM）中的必要許可權，才能完成此程式。 請參閱本主題中的「其他注意事項」中的詳細資料。

**控制不受管理的 GPO**

1.  在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。

2.  在 [詳細資料] 窗格的 [**內容**] 索引標籤上，按一下 [**失控**資料] 索引標籤以顯示不受

3.  以滑鼠右鍵按一下要使用 AGPM 進行控制的 GPO，然後按一下 [**控制**]。

4.  輸入要顯示在 GPO 歷程記錄中的批註，然後按一下 **[確定]**。

5.  當**進度**視窗顯示整體進度完成時，請按一下 [**關閉**]。 GPO 會從 [無法**控制**] 索引標籤上的清單中移除，並新增至 [**受控**] 索引標籤。

### 其他考量

-   根據預設，您必須是 [核准者] 或 [AGPM 管理員（完全控制）]，才能執行此程式。 具體說來，您必須擁有**清單內容**，並為網域**建立 GPO**許可權。

### 其他參考資料

-   [建立或控制 GPO](creating-or-controlling-a-gpo-agpm40-app.md)

 

 





