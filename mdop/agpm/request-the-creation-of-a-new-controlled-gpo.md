---
title: 要求建立新的受控制 GPO
description: 要求建立新的受控制 GPO
author: dansimp
ms.assetid: e1875d81-8553-42ee-8f3a-023d6ced86ca
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b7994e1af80c0ae32940d52955f7e5f773d1ee6a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802566"
---
# 要求建立新的受控制 GPO


除非您是核准者或 AGPM 系統管理員（完全控制），否則如果要使用高級群組原則管理（AGPM）來管理新的群組原則物件（GPO），則必須要求建立。

必須具備高級組原則管理中具有編輯者或檢閱者角色或必要許可權的使用者帳戶，才能完成此程式。 請參閱本主題中的「其他注意事項」中的詳細資料。

**若要建立透過 AGPM 管理變更控制的新 GPO**

1.  在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。

2.  以滑鼠右鍵按一下 [**變更控制**] 節點，然後按一下 [**新增受控制的 GPO**]。

3.  除非您有建立 Gpo 的特殊許可權，否則您必須提交建立的要求。 在 [**新的受控 GPO** ] 對話方塊中：

    1.  若要接收要求的複本，請在 [**抄送**] 欄位中輸入您的電子郵件地址。

    2.  輸入新 GPO 的名稱。

    3.  [選用]：輸入新 GPO 的批註。

    4.  若要在核准後立即在生產環境中部署新的 GPO，請按一下 [**建立 live**]。 若要在離線時建立新的 GPO，而不想在核准時立即部署，請按一下 [**離線建立**]。

    5.  選取要用來做為新 GPO 起點的 GPO 範本。

    6.  按一下 **\[提交\]**。

4.  當**進度**視窗顯示整體進度完成時，請按一下 [**關閉**]。 新的 GPO 會顯示在 [**擱置**] 索引標籤的 [gpo] 清單中。當核准者核准您的要求之後，該 GPO 就會移至 [**受控**] 索引標籤。

### 其他考量

-   根據預設，您必須是編輯者或檢閱者，才能執行此程式。 具體說來，您必須擁有該網域的 [**清單內容**] 許可權。

-   若要在獲核准前收回您的要求，請按一下 [**待定**] 索引標籤。以滑鼠右鍵按一下該 GPO，然後按一下 [**收回**]。 GPO 將損毀。

### 其他參考資料

-   [建立、控制或匯入 GPO](creating-controlling-or-importing-a-gpo-editor.md)

 

 





