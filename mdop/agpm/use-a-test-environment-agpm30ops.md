---
title: 使用測試環境
description: 使用測試環境
author: dansimp
ms.assetid: 86295084-b39e-4040-bb3f-15c3c1e99b1a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1264d9fe6f922a7e61bcd069581c7bd5e39b7787
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801737"
---
# 使用測試環境


如果您在部署到生產環境之前，使用測試組織單位（OU）來測試群組原則物件（Gpo），您必須具備存取測試 OU 所需的許可權。 使用測試 OU 是選擇性的。

**使用測試 OU**

1.  當您已取出 GPO 進行編輯時，請在 [**群組原則管理主控台**] 中，按一下您管理 gpo 的林和網域中的 [**群組原則物件**]。

2.  按一下要測試之 GPO 的取出複本。 名稱前面會有**\ [已取出 \]**。 （如果沒有列出，請按一下 [**動作**]，然後按一下 **[重新整理**]。 依字母順序排序名稱， **\ [已取出的 \]** gpo 通常會顯示在清單頂端。

3.  將 GPO 拖放到測試 OU 中。

4.  按一下對話方塊中的 **[確定**]，詢問是否要在測試 OU 中建立 GPO 的連結。

### 其他考量

-   測試完成時，在 GPO 中檢入會自動刪除 GPO 的取出複本連結。

### 其他參考資料

-   [編輯 GPO](editing-a-gpo-agpm30ops.md)

 

 





