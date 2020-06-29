---
title: 設定電子郵件通知
description: 設定電子郵件通知
author: dansimp
ms.assetid: 06f19556-f296-4a80-86a4-4f446c992204
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 26b751a49d3d22f893c420be7fef9714b242d1f9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802041"
---
# 設定電子郵件通知


當編輯人員或檢閱者嘗試建立、部署或刪除群組原則物件（GPO）時，會將此動作的要求傳送至指定的電子郵件地址或位址，以便讓核准者評估該要求並執行或拒絕它。 您可以決定要傳送通知的電子郵件地址或位址，以及傳送通知的別名。

您必須具備高級群組原則管理（AGPM）中具有 AGPM 系統管理員（完全控制）角色或必要許可權的使用者帳戶，才能完成此程式。 請參閱本主題中的「其他注意事項」中的詳細資料。

**若要設定 AGPM 的電子郵件通知**

1.  在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。

2.  在 [詳細資料] 窗格中，按一下 [**網域委派**] 索引標籤。

3.  在 [**寄件者電子郵件地址**] 欄位中，輸入要傳送通知的 AGPM 電子郵件別名。

4.  在 [收**件者電子郵件地址**] 欄位中，輸入應接收核准要求的以逗號分隔的電子郵件地址清單。

5.  在 [ **SMTP 伺服器**] 欄位中，輸入有效的 SMTP 郵件伺服器。

6.  在 [**使用者名稱**] 和 [**密碼**] 欄位中，輸入擁有 SMTP 服務存取權的使用者認證。

7.  按一下 **\[Apply\]** (套用)。

### 其他考量

-   根據預設，您必須是 AGPM 系統管理員（完全控制）才能執行此程式。 具體說來，您必須擁有 [**清單內容**] 和 [修改網域的**選項**] 許可權。

-   AGPM 的電子郵件通知是網域層級設定。 您可以在每個網域的 [**網域委派**] 索引標籤上提供不同的核准者電子郵件地址或 AGPM 電子郵件別名，或在整個環境中使用相同的電子郵件地址。

-   根據預設，由於高級群組原則管理（AGPM）中的動作而傳送的電子郵件訊息並未加密。 不過，您可以使用登錄設定來設定 AGPM 的電子郵件安全性，以指定是否要使用安全通訊端層（SSL）加密，以及要使用哪個 SMTP 埠。 如需詳細資訊，請參閱[設定 AGPM 的電子郵件安全性](configure-e-mail-security-for-agpm-agpm40.md)。

### 其他參考資料

-   [設定進階群組原則管理](configuring-advanced-group-policy-management-agpm40.md)

 

 





