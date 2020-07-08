---
title: 執行 AGPM 系統管理員工作
description: 執行 AGPM 系統管理員工作
author: dansimp
ms.assetid: 9678b0f4-70a5-411e-a896-afa4dc9ea6c4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 26b412e5b22e46af938d127751fdca1da722a8c6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809345"
---
# 執行 AGPM 系統管理員工作


在 [高級群組原則管理] （AGPM）中，AGPM 系統管理員（完全控制）會設定全域性選項，並將許可權委派給核准者、編輯人員、檢閱者及其他 AGPM 管理員。 根據預設，AGPM 管理員是完全控制的個體（所有的 AGPM 許可權），因此誰可以執行與任何角色相關聯的工作。

在有多位人員開發群組原則物件（Gpo）的環境中，您可以選擇是否所有的 AGPM 使用者都執行相同的工作，以及是否擁有相同的存取層級，或者是否要讓 AGPM 系統管理員委派許可權來變更 Gpo，以及將 Gpo 部署到生產環境的核准者。 AGPM 管理員可以設定許可權，以符合貴組織的需求。

-   設定[高級的群組原則管理](configuring-advanced-group-policy-management.md)：設定 AGPM 服務器連線和電子郵件通知、委派在生產環境中 gpo 的存取權，以及設定記錄及追蹤以進行疑難排解。

-   [管理](managing-the-archive.md)封存：委派對封存中 gpo 的存取權，並限制儲存的每個 GPO 版本數。

-   [管理 Agpm 服務](managing-the-agpm-service-agpm30ops.md)：停止並啟動 agpm 服務，或變更您的 [agpm 服務] 帳戶，或 [Agpm] 服務所偵聽的埠。

-   [移動 Agpm 伺服器與](move-the-agpm-server-and-the-archive.md)封存：將 agpm 服務、封存或兩者移至不同的伺服器。

此外，因為 AGPM 系統管理員角色包含所有其他角色的許可權，所以 AGPM 管理員可以執行與其他任何角色相關聯的一般工作。

-   [執行核准者](performing-approver-tasks-agpm30ops.md)工作，例如建立、部署或刪除 gpo

-   [執行編輯器](performing-editor-tasks-agpm30ops.md)工作，例如編輯、重新命名、標記或匯入 gpo、建立範本或設定預設範本

-   [執行檢閱者](performing-reviewer-tasks-agpm30ops.md)工作，例如審閱設定及比較 gpo

### 其他考量

根據預設，AGPM 系統管理員角色擁有 [完全控制] 許可權（所有 AGPM 許可權）：

-   清單內容

-   讀取設定

-   編輯設定

-   建立 GPO

-   部署 GPO

-   刪除 GPO

-   修改選項

-   修改安全性

-   建立範本

[**修改選項**] 和 [**修改安全**許可權] 對於 [AGPM 管理員] 的角色而言是唯一的。

 

 





