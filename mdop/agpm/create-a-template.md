---
title: 建立範本
description: 建立範本
author: dansimp
ms.assetid: 6992bd55-4a4f-401f-9815-c468bac598ef
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9ad57204170fc3f49b01b571d82b00e1faf62de0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802869"
---
# 建立範本


建立範本可讓您儲存特定版本的群組原則物件（GPO）的所有設定，以做為建立新 Gpo 的起點。

**記事** 範本是一個無法編輯且靜態的 GPO 版本，以做為建立新的可編輯 Gpo 的起點。

 

具有 [編輯者] 或 [AGPM 管理員] （完全控制）角色或 [高級群組原則管理] 中的必要許可權的使用者帳戶必須完成此程式。 請參閱本主題中的「其他注意事項」中的詳細資料。

**根據現有的 GPO 建立範本**

1.  在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。

2.  在 [詳細資料] 窗格的 [**內容**] 索引標籤上，按一下 [**受控**] 或 [未**控制**] 索引標籤以顯示

3.  以滑鼠右鍵按一下您要建立範本的 GPO，然後按一下 [**另存為範本**]。

4.  輸入範本的名稱和批註，然後按一下 **[確定]**。

5.  當**進度**視窗顯示整體進度完成時，請按一下 [**關閉**]。 新範本隨即出現在 [**範本**] 索引標籤上。

### 其他考量

-   根據預設，您必須是編輯者或 AGPM 系統管理員（完全控制）才能執行此程式。 具體說來，您必須擁有**清單內容**，並為該網域**建立範本**許可權。

-   重新命名或刪除範本不會影響從該範本建立的 Gpo。

-   因為範本不能變更，所以範本沒有歷程記錄。

### 其他參考資料

-   [建立範本和設定預設範本](creating-a-template-and-setting-a-default-template.md)

-   [要求建立新的受控制 GPO](request-the-creation-of-a-new-controlled-gpo.md)

 

 





