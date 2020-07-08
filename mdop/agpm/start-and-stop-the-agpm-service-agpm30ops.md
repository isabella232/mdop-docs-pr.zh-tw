---
title: 啟動和停止 AGPM 服務
description: 啟動和停止 AGPM 服務
author: dansimp
ms.assetid: b9d26920-c439-4992-9a78-73e4fba8309d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2be1c2386bedd5888c0ed032479bf1237ce8289c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802529"
---
# 啟動和停止 AGPM 服務


AGPM 服務是一個充當安全性 proxy 的 Windows 服務，管理用戶端對封存和生產環境中的群組原則物件（Gpo）的存取權。

**重要** 停止或停用 AGPM 服務將會防止 AGPM 用戶端透過伺服器執行任何操作（例如列出或編輯 Gpo）。

 

需要擁有 AGPM 服務器存取權的使用者帳戶（安裝了 AGPM 服務的電腦），才能完成此程式。

**啟動或停止 AGPM 服務**

1.  在已安裝 Microsoft 高級群組原則管理-伺服器（以及 AGPM 服務）的電腦上，按一下 [**開始**]，按一下 [**控制台**]，按一下 [**管理工具**]，然後按一下 [**服務**]。

2.  在服務清單中，以滑鼠右鍵按一下 [ **AGPM 服務**]，然後選取 [**開始**]、[**重新開機**] 或 [**停止**]。

    **小心** 請勿透過作業系統中的 [**管理工具**] 和 [**服務**] 來修改 AGPM 服務的設定。 如此一來，就能防止 AGPM 服務啟動。

     

### 其他參考資料

-   [管理 AGPM 服務](managing-the-agpm-service-agpm30ops.md)

 

 





