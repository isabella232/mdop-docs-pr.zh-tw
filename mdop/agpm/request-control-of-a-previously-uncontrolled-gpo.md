---
title: 要求控制先前不受控制的 GPO
description: 要求控制先前不受控制的 GPO
author: dansimp
ms.assetid: 00e8725d-5d7f-4eed-a5e6-c3631632cfbd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a92db48d87398568900fc0031e688c862a69b417
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801826"
---
# 要求控制先前不受控制的 GPO


若要使用高級群組原則管理（AGPM）來為現有的群群組原則物件（GPO）提供變更控制，必須使用 AGPM 來控制 GPO。 除非您是核准者或 AGPM 系統管理員（完全控制），否則您必須要求對 GPO 進行控制。

必須具備高級組原則管理中具有編輯者或檢閱者角色或必要許可權的使用者帳戶，才能完成此程式。 請參閱本主題中的「其他注意事項」中的詳細資料。

**控制先前不受管理的 GPO**

1.  在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。

2.  在 [詳細資料] 窗格的 [**內容**] 索引標籤上，按一下 [**失控**資料] 索引標籤以顯示不受

3.  以滑鼠右鍵按一下要使用 AGPM 進行控制的 GPO，然後按一下 [**控制**]。

4.  除非您有控制 Gpo 的特殊許可權，否則您必須提交控制權要求。 若要接收申請的複本，請在 [**抄送**] 欄位中輸入您的電子郵件地址。 輸入要顯示在 GPO 歷程**記錄**中的批註，然後按一下 [**提交**]。

5.  當**進度**視窗顯示整體進度完成時，請按一下 [**關閉**]。 GPO 會從 [無法**控制**] 索引標籤上的清單中移除，並新增至 [**擱置**] 索引標籤。當核准者核准您的要求之後，該 GPO 就會移至 [**受控**] 索引標籤。

### 其他考量

-   根據預設，您必須是編輯者或檢閱者，才能執行此程式。 具體說來，您必須擁有 [**清單內容**] 和 [**讀取設定**] 許可權給網域。

-   若要在獲核准前收回您的要求，請按一下 [**待定**] 索引標籤。以滑鼠右鍵按一下該 GPO，然後按一下 [**收回**]。 GPO 將會傳回 [無法**控制**] 索引標籤。

### 其他參考資料

-   [建立、控制或匯入 GPO](creating-controlling-or-importing-a-gpo-editor.md)

 

 





