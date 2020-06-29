---
title: 疑難排解 AGPM 升級
description: 疑難排解 AGPM 升級
author: dansimp
ms.assetid: 1abbf0c1-fd32-46a8-a3ba-c005f066523d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2089eac51803dca60da51f61ebdb112fbf0bda08
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801741"
---
# 疑難排解 AGPM 升級

本節列出當您將高級群組原則管理（AGPM）伺服器升級至較新版本（例如，AGPM 4.0 至 AGPM 4.3）時可能會遇到的常見問題。 若要診斷此處未列出的問題，請查看[疑難排解 AGPM](troubleshooting-agpm-agpm40.md)或 AGPM 系統管理員（完全控制），以使用記錄和追蹤功能。 如需詳細資訊，請參閱[設定記錄和追蹤](configure-logging-and-tracing-agpm40.md)。

## 您遇到什麼問題？

-   [無法產生 HTML GPO 差異報告（錯誤碼80004003）](#bkmk-error-80004003)

### <a href="" id="bkmk-error-80004003"></a>無法產生 HTML GPO 差異報告（錯誤碼80004003）

-   **原因**：您已使用錯誤的帳戶安裝 AGPM 升級套件。

-   **解決方案**：您必須是 AGPM 系統管理員才能修正這個問題。
    
    -   確定您知道**AGPM 服務帳戶**的使用者名稱 & 密碼。

    -   以您的 AGPM 服務帳戶的形式，以互動方式登入您的 AGPM 服務器。
        
        -   這極其重要，因為如果您使用不同的帳戶，安裝將會失敗。

    -   關閉 AGPM 服務。
    
    -   安裝必要的修復程式。
    
    -   使用 AGPM 用戶端連線至 AGPM，以測試您的差異報告現已正常運作。
    
## 安裝 Microsoft 高級群組原則管理 4.0 SP3 的修補程式套件1
    
**此修復程式中修正的問題**：當您控制或管理新的群組原則物件（gpo）時，AGPM 無法產生差異報告。

**如何取得此更新**：安裝最新版本的 Microsoft 桌面優化套件（[2017 年3月服務版本](https://www.microsoft.com/download/details.aspx?id=54967)）。 如需詳細資訊，請參閱[KB 4014009](https://support.microsoft.com/help/4014009/) 。

更明確地說，您可以選擇只下載第一個檔案， `AGPM4.0SP1_Server_X64_KB4014009.exe` 從按下 [下載] 按鈕之後所顯示的清單中。
      
您可以在[這裡](https://www.microsoft.com/download/details.aspx?id=54967)找到 Microsoft 桌面優化套件（2017年3月服務發行）的下載連結。
      
      
## 參照連結
https://support.microsoft.com/help/3127165/hotfix-package-1-for-microsoft-advanced-group-policy-management-4-0-sp
      
