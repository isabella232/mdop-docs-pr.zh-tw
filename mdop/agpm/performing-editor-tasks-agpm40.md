---
title: 執行編輯器工作
description: 執行編輯器工作
author: dansimp
ms.assetid: 81976a01-2a95-4256-b703-9fb3c884ef34
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b8e23bb91d8762d19eed9ae817967ba5a57505a9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802605"
---
# 執行編輯器工作


在 [高級群組原則管理] （AGPM）中，編輯者是由 AGPM 系統管理員（完全控制）所授權的人員，用來變更群群組原則物件（Gpo）及建立 GPO 範本。 此外，編輯者還可以要求建立、刪除或還原 GPO。 核准者必須核准要實施的要求。 編輯工具可以將 GPO 匯出至檔案，以便將它複製到另一個樹林中的網域，並匯入從其他網域複製的 GPO。

**重要** 確認您是連線到 Gpo 的中央封存。 如需詳細資訊，請參閱[設定 AGPM 服務器](configure-an-agpm-server-connection-agpm40.md)連線。

 

-   [建立或控制 GPO](creating-or-controlling-a-gpo-agpm40-ed.md)

-   [編輯 GPO](editing-a-gpo-agpm40.md)

-   [使用測試環境](using-a-test-environment.md)

-   [要求部署 GPO](request-deployment-of-a-gpo-agpm40.md)

-   [建立範本和設定預設範本](creating-a-template-and-setting-a-default-template-agpm40.md)

-   [刪除或還原 GPO](deleting-or-restoring-a-gpo-agpm40.md)

**記事** 因為編輯者角色包含檢閱者角色的許可權，所以編輯工具也可以查看設定及比較 Gpo。 如需詳細資訊，請參閱[執行檢閱者](performing-reviewer-tasks-agpm40.md)工作。

 

### 其他考量

根據預設，系統會為 Editor 角色提供下列許可權：

-   清單內容

-   讀取設定

-   編輯設定

-   匯出 GPO

-   匯入 GPO

-   建立範本

 

 





