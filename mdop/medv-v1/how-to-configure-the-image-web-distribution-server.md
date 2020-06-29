---
title: 如何設定映像 Web 發佈伺服器
description: 如何設定映像 Web 發佈伺服器
author: dansimp
ms.assetid: 2d32ae79-dff5-4c05-a412-dd15452b6007
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 8a21b14fbaca6bbc09d4c35b4d8fb86365c42e3b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810988"
---
# 如何設定映像 Web 發佈伺服器


影像儲存庫是用來進行影像發佈的選用伺服器（在此情況下，系統管理員上傳新影像和用戶端電腦每15分鐘檢查一次伺服器，並在有新的映射時更新它）。

## <a href="" id="bkmk-configuringanimagereporitoryusingiis"></a>


影像發佈伺服器需要下列各項：

-   網際網路資訊服務（IIS）：如需詳細資訊，請參閱[網際網路資訊服務](https://go.microsoft.com/fwlink/?LinkId=142995)。

    在 IIS 安裝期間，在新增角色服務時，請選取下列支援的驗證方法：

    -   **基本驗證**

    -   **Windows 驗證**

    -   **用戶端憑證對應驗證**

    配置 IIS 時，請包含下列專案：

    -   使用名為**MEDVImages**的別名新增虛擬目錄。 實體路徑應該指向影像的位置。

    -   啟用 BITS。

    -   新增下列 MIME 類型：

        -   **. ckm （應用程式/八進位資料流程）**

        -   **. index （應用程式/八進位資料流程**）

    -   在 MED-V 網站上，新增 [讀取] 許可權給**所有人**。

    -   重新開機 IIS。

-   BITS 伺服器的 IIS 擴展：如需詳細資訊，請參閱[安裝 BITS 伺服器延伸](https://go.microsoft.com/fwlink/?LinkId=142996)。

## 相關主題


[支援的設定](supported-configurationsmedv-orientation.md)

[設計 MED-V 映像存放庫](design-the-med-v-image-repositories.md)

 

 





