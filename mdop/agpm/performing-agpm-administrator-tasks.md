---
title: 執行 AGPM 系統管理員工作
description: 執行 AGPM 系統管理員工作
author: dansimp
ms.assetid: 32e694a7-be64-4943-bce2-2a3a15e5341f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0daa8df93a88ed155e9f894011d4dd835761948b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802633"
---
# 執行 AGPM 系統管理員工作


AGPM 系統管理員（完全控制）可設定全域性選項，並將許可權委派給核准者、編輯人員、檢閱者及其他 AGPM 系統管理員。 根據預設，AGPM 管理員是完全控制的個體（所有高級群組原則管理 \ [AGPM \] 許可權），因此也可以執行與任何角色相關聯的工作。

在有多位人員開發群組原則物件（Gpo）的環境中，您可以選擇所有高級群組原則管理（AGPM）使用者是否執行相同的工作，以及是否具有相同的存取權，或是 AGPM 管理員委派許可權給編輯者，以及將 Gpo 部署到生產環境的核准者。 AGPM 管理員可以設定許可權，以符合貴組織的需求。

-   [設定 AGPM 伺服器連線](configure-the-agpm-server-connection.md)

-   [設定電子郵件通知](configure-e-mail-notification.md)

-   [委派管理網域層級存取權](delegate-domain-level-access.md)

-   [委派管理個別 GPO 的存取權](delegate-access-to-an-individual-gpo.md)

-   [設定記錄和追蹤](configure-logging-and-tracing.md)

-   [管理 AGPM 服務](managing-the-agpm-service.md)

    -   [啟動和停止 AGPM 服務](start-and-stop-the-agpm-service.md)

    -   [修改封存路徑](modify-the-archive-path.md)

    -   [修改 AGPM 服務帳戶](modify-the-agpm-service-account.md)

    -   [修改 AGPM 服務接聽的連接埠](modify-the-port-on-which-the-agpm-service-listens.md)

此外，因為 AGPM 系統管理員角色包含所有其他角色的許可權，所以 AGPM 管理員可以執行與其他任何角色相關聯的一般工作。

-   [執行核准者](performing-approver-tasks.md)工作，例如建立、部署或刪除 gpo

-   [執行編輯器](performing-editor-tasks.md)工作，例如編輯、重新命名、標記或匯入 gpo、建立範本或設定預設範本

-   [執行檢閱者](performing-reviewer-tasks.md)工作，例如審閱設定及比較 gpo

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

 

 





