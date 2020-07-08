---
title: AGPM 伺服器索引標籤
description: AGPM 伺服器索引標籤
author: dansimp
ms.assetid: a6689437-233e-4f33-a0d6-f7d432c96c00
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7ffaa3f55d4ae1c2a59287d9dc302aec3dd00aed
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802154"
---
# AGPM 伺服器索引標籤


[**變更控制**] 窗格上的 [ **AGPM 服務器**] 索引標籤可讓您透過輸入完整的電腦名稱稱和埠來選取 agpm 伺服器，以及從封存刪除較舊版本的群組原則物件（gpo），以節省 AGPM 服務器的磁碟空間。

## 指定 AGPM 服務器


已選取的 AGPM 服務器決定要在 [**內容**] 索引標籤上顯示哪個封存，以及**將哪些**位置套用到哪個位置。 [高級群組原則管理（AGPM）] 的預設埠是埠4600。

如果 AGPM 服務器連線是使用系統管理範本設定來集中設定，則此索引標籤上用於設定連線的選項將無法使用。 如需詳細資訊，請參閱[設定 AGPM 服務器](configure-agpm-server-connections-agpm40.md)連線。

## 刪除舊的 GPO 版本


根據預設，每個受控制的 GPO 的所有版本都會保留在封存中。 不過，您可以設定 AGPM 服務來限制每個 GPO 保留的版本數，並在超過該限制時自動刪除最舊的版本。 只有 [歷程**記錄**] 視窗 [**唯一版本**] 索引標籤上顯示的 GPO 版本，才會計算出該限制。

**記事** 要儲存于每個 GPO 的唯一版本數上限不包括目前的版本，因此輸入0只保留目前的版本。 限制必須不超過999版本。

當 GPO 版本刪除時，該版本的記錄會保留在 GPO 的記錄中，但 GPO 版本本身已從封存中刪除。 您可以在歷程記錄中將其標示為不可刪除，以避免刪除 GPO 版本。

 

### 其他參考資料

-   [使用者介面：進階群組原則管理](user-interface-advanced-group-policy-management-agpm40.md)

-   [執行 AGPM 系統管理員工作](performing-agpm-administrator-tasks-agpm40.md)

-   [執行檢閱者工作](performing-reviewer-tasks-agpm40.md)

 

 





