---
title: 重新命名 GPO 或範本
description: 重新命名 GPO 或範本
author: dansimp
ms.assetid: 19d17ddf-8b58-4677-929e-9550fa388b93
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 44d1cef33d8c0004ef3639311fbf135b4dea9d39
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801849"
---
# 重新命名 GPO 或範本


您可以重新命名受控的群組原則物件（GPO）或範本。

具有 [編輯者] 或 [AGPM 管理員] （完全控制）角色的使用者帳戶、建立 GPO 之核准者的使用者帳戶，或是必須具備高級群組原則管理（AGPM）中所需許可權的使用者帳戶才能完成此程式。 請參閱本主題中的「其他注意事項」中的詳細資料。

**重新命名 GPO 或範本**

1.  在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。

2.  在 [**內容**] 索引標籤上，按一下 [**控制**] 或 [**範本**] 索引標籤，顯示要重新命名的專案

3.  以滑鼠右鍵按一下要重新命名的 GPO 或範本，然後按一下 [**重新命名**]。

4.  輸入 GPO 或範本的新名稱和批註，然後按一下 **[確定]**。

5.  當**進度**視窗顯示整體進度完成時，請按一下 [**關閉**]。 GPO 或範本會出現在 [**目錄**] 索引標籤上的新名稱底下。

### 其他考量

-   根據預設，您必須是建立或控制 GPO、編輯器或 AGPM 系統管理員（完全控制）的核准者，才能執行此程式。 具體說來，您必須擁有該 GPO 的 [**清單內容**] 和 [**編輯設定**] 許可權。

-   當您重新命名已部署的 GPO 時，系統會立即在封存中變更該名稱。 只有在重新部署 GPO 時，才會在生產環境中變更名稱。 重新部署 GPO 之後（或刪除生產複本），舊名稱仍會在生產環境中使用，因此無法用於另一個 GPO。 同樣地，除非已部署 GPO （變更生產複本的名稱）或已刪除生產複本，否則不能將封存中的 GPO 重新命名回其原始名稱。

### 其他參考資料

-   [編輯 GPO](editing-a-gpo-agpm30ops.md)

 

 





