---
title: 版本控制最佳做法
description: 版本控制最佳做法
author: dansimp
ms.assetid: 89067f6a-f7ea-4dad-999d-118284cf6c5a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ed91408faeb8968175976382f9dd97d45becddb5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802122"
---
# 版本控制最佳做法


Microsoft 高級群組原則管理（AGPM）提供群組原則物件（Gpo）的版本控制，就像 Microsoft Visual SourceSafe®提供原始程式碼的版本控制。 開發人員可以使用 Visual SourceSafe 來管理每個來源檔案的多個版本。 群組原則系統管理員可以使用 AGPM 來對 Gpo 執行相同的動作。 當您使用 AGPM 時，群組原則管理員應該瞭解適用于任何版本控制系統的最佳做法：

-   **日期及時間：** AGPM 會將每個版本的 GPO 標記為日期和時間。 若要確保歷程記錄準確無誤，尤其是當您在多部電腦上編輯 Gpo 時，請確定每個電腦都將它的時鐘與一個權威性時間源同步處理。

-   **完成編輯 gpo 時，請將其存回：** 常見的情況是，編輯者會取出 Gpo，並忘記將其存回封存。 不過，這可以防止其他群組原則管理員變更 GPO。 當您完成編輯時，請務必立即將 Gpo 檢入回 AGPM。

-   **經常儲存變更：** 當您編輯 GPO 時，請經常儲存變更。 大多數的編輯者會取出一個 GPO，進行許多變更，然後將該 GPO 檢查到封存。 請改為將 GPO 定期檢查到封存，然後再次查看該檔案。 在您變更每個設定（不建議）或在進行相關變更群組之後，在 GPO 中進行檢查時，其詳細資料可能相當小，就是在 GPO 中進行檢查。 結果是每個 GPO 的記錄，可協助您解決問題。

-   **經常部署 gpo：** 請勿讓尚未部署的新與編輯的 Gpo 積累在封存的大量數位中。 相反地，請儘快部署新的和編輯的 Gpo，讓它們在生產環境上的影響最小。 一次部署許多新的和已編輯的 Gpo 可能會危害生產環境。

-   **當您存回 gpo 時，請記錄變更的用途：** 任何檢閱者都可以比較 GPO 的版本，以查看兩者間的特定變更。 記錄這些特定變更時，不會加上任何值。 相反地，您可以透過查看差異報告，來記錄變更的目的和用途，而不是記錄審查者能看到哪些內容。 版本批註應該為比較報告增添價值，並協助審查員瞭解編輯者對 GPO 進行變更的原因。

-   在**部署之前先在實驗室中測試 gpo：** 將 Gpo 部署到生產環境，而不先進行測試，就會有風險。 您可以在實驗室環境中測試 Gpo，方法是將其連結至包含測試電腦和使用者的組織單位，然後確認它們正常運作。 在驗證實驗室中的每個 GPO 之後，將該 GPO 部署到生產環境。

### 其他參考資料

-   [Microsoft 進階群組原則管理 3.0 操作指南](operations-guide-for-microsoft-advanced-group-policy-management-30-agpm30ops.md)

 

 





