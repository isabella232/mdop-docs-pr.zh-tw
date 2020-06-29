---
title: 部署 GPO
description: 部署 GPO
author: dansimp
ms.assetid: a6febeaa-144b-4c02-99af-d972f0f2b544
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 208fd95ec48f81b6c3a2a59bf92f53128eb3d529
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801922"
---
# 部署 GPO


核准者可以在生產環境中部署新的或已編輯的群組原則物件（GPO）。 如需重新部署舊版 GPO 的相關資訊，請參閱[回滾舊版的 gpo](roll-back-to-an-earlier-version-of-a-gpo-agpm40.md)。

使用者帳戶必須有核准者或 AGPM 管理員（完全控制）角色或高級群組原則管理（AGPM）中的必要許可權，才能完成此程式。 請參閱本主題中的「其他注意事項」中的詳細資料。

**將 GPO 部署到生產環境**

1.  在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。

2.  在 [**內容**] 索引標籤上，按一下 [**受控**] 索引標籤以顯示受控制的 gpo。

3.  以滑鼠右鍵按一下要部署的 GPO，然後按一下 [**部署**]。

4.  若要查看 GPO 的連結，請按一下 [**高級**]。 將滑鼠指標暫停在樹狀結構中的專案上，以顯示詳細資料。

    -   根據預設，所有的 GPO 連結都會還原。

    -   若要防止連結被還原，請清除該連結的核取方塊。

    -   若要避免還原所有連結，請清除 [**部署 GPO** ] 對話方塊中的 [**還原連結**] 核取方塊。

5.  按一下 **\[是\]**。 當**進度**視窗顯示整體進度完成時，請按一下 [**關閉**]。

**記事** 若要確認是否已部署最新版本的 GPO，請在 [**受控**] 索引標籤上，按兩下該 gpo 以顯示其歷程**記錄**。 在 GPO 的歷程**記錄**中，[ **State** ] （狀態）欄會指出 GPO 是否已部署。

 

### 其他考量

-   根據預設，您必須是 [核准者] 或 [AGPM 管理員（完全控制）]，才能執行此程式。 具體說來，您必須擁有**清單內容**並**部署**gpo 的 gpo 許可權。

### 其他參考資料

-   [執行核准者工作](performing-approver-tasks-agpm40.md)

 

 





