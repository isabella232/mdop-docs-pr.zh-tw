---
title: 匯出 GPO 到檔案
description: 匯出 GPO 到檔案
author: dansimp
ms.assetid: 0d01b1f7-a6a4-4d0d-9aa7-2d6f1ae93d9d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4622930cb0e5b439649cc0445ae2b3d02d7d3224
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802782"
---
# 匯出 GPO 到檔案


您可以將受控的群組原則物件（GPO）匯出到 CAB 檔案，以便將它複製到另一個樹林中的網域，然後將該 GPO 匯入該網域中的 [高級組原則管理] （AGPM）。 如需如何將 GPO 設定匯入新的或現有的 GPO 的相關資訊，請參閱從檔案匯[入 gpo](import-a-gpo-from-a-file-ed.md)。

具有 [編輯者] 或 [AGPM 管理員] （完全控制）角色的使用者帳戶，或 [高級群組原則管理] （AGPM）中的必要許可權，才能完成此程式。請參閱本主題中的「其他注意事項」中的詳細資料。

**將 GPO 匯出至檔案**

1.  在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。

2.  在 [**內容**] 索引標籤上，按一下 [**受控**] 索引標籤以顯示受控制的 gpo。

3.  以滑鼠右鍵按一下該 GPO，然後按一下 [**匯出到**]。

4.  輸入您要匯出 GPO 之檔案的檔案名，然後按一下 [**匯出**]。 如果檔案不存在，就會建立檔案。 如果它已存在，則會被取代。

### 其他考量

-   根據預設，您必須是編輯者或 AGPM 系統管理員（完全控制）才能執行此程式。 具體說來，您必須擁有**清單內容**、**閱讀設定**及 gpo 的**匯出 gpo**許可權。

### 其他參考資料

-   [使用測試環境](using-a-test-environment.md)

 

 





