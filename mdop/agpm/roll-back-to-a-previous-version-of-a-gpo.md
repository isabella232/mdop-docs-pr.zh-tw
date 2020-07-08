---
title: 回復至舊版 GPO
description: 回復至舊版 GPO
author: dansimp
ms.assetid: 028631c0-4cb9-4642-90ad-04cd813051b7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a71740eaa60a4b1292e47ca8aa57d4657231ab57
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802554"
---
# 回復至舊版 GPO


[高級群組原則管理] （AGPM）可讓核准者透過從其歷程記錄重新部署舊版的 GPO，來回滾變更至群組原則物件（GPO）。 部署舊版的 GPO 會覆寫目前在生產中的 GPO 版本。

使用者帳戶必須有核准者或 AGPM 系統管理員（完全控制）角色，或高級群組原則管理中的必要許可權，才能完成此程式。 請參閱本主題中的「其他注意事項」中的詳細資料。

**將舊版的 GPO 部署到生產環境**

1.  在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。

2.  在 [**內容**] 索引標籤上，按一下 [**受控**] 索引標籤以顯示受控制的 gpo。

3.  按兩下要部署的 GPO，以顯示其歷程**記錄**。

4.  以滑鼠右鍵按一下要部署的版本，按一下 [**部署**]，然後按一下 **[是]**。

5.  當**進度**視窗顯示整體進度完成時，請按一下 [**關閉**]。 在 [歷程**記錄**] 視窗中，按一下 [**關閉**]。

**記事** 若要確認重新部署的版本符合預期的版本，請檢查兩個版本的差異報告。 在 GPO 的 [歷程**記錄**] 視窗中，醒目提示兩個版本，然後按一下滑鼠右鍵，然後選取 [**差異**] 和 [ **HTML 報表**] 或 [ **XML 報表**]。

 

### 其他考量

-   根據預設，您必須是 [核准者] 或 [AGPM 管理員（完全控制）]，才能執行此程式。 具體說來，您必須擁有**清單內容**並**部署**gpo 的 gpo 許可權。

### 其他參考資料

-   [執行核准者工作](performing-approver-tasks.md)

 

 





