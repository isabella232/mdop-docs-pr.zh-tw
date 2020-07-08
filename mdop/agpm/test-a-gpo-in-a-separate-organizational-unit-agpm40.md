---
title: 在不同的組織單位測試 GPO
description: 在不同的組織單位測試 GPO
author: dansimp
ms.assetid: 9a9e6d22-74e6-41d8-ac2f-12a1b76ad5a0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 509721fdd775c8669399549f6dcc29cb9ebaea2f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801745"
---
# 在不同的組織單位測試 GPO


如果您在部署到生產環境之前，使用測試組織單位（OU）來測試同一個網域中的群組原則物件（Gpo），您必須具備存取測試 OU 所需的許可權。 使用測試 OU 是選用的。

**使用測試 OU**

1.  雖然您已取出 GPO 進行編輯，但在**群群組原則管理主控台**中，按一下您要管理 gpo 的林和網域中的 [**群組原則物件**]。

2.  按一下要測試之 GPO 的取出複本。 名稱前面會加上**\ [AGPM \]**。 （如果沒有列出，請按一下 [**動作**]，然後按一下 **[重新整理**]。 依字母順序排序名稱， **\ [AGPM \]** gpo 通常會出現在清單頂端。

3.  將 GPO 拖曳到測試 OU。

4.  在詢問是否要在測試 OU 中建立 GPO 連結的對話方塊中，按一下 **[確定**]。

### 其他考量

-   測試完成時，在 GPO 中檢入會自動刪除 GPO 的取出複本連結。

### 其他參考資料

-   [使用測試環境](using-a-test-environment.md)

 

 





