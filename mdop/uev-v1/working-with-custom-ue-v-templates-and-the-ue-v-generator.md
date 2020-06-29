---
title: 使用自訂 UE-V 範本與 UE-V 產生器
description: 使用自訂 UE-V 範本與 UE-V 產生器
author: dansimp
ms.assetid: 7bb2583a-b032-4800-9bf9-eb33528e1d0d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: db5387254842bfdcf3898089bc12a8e929e3813a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810280"
---
# 使用自訂 UE-V 範本與 UE-V 產生器


為了在使用者電腦之間漫遊應用程式，Microsoft 使用者體驗虛擬化（UE-V）使用*設定位置範本*。 某些設定位置範本包含在使用者體驗虛擬化中。 您也可以使用 UE-V 發生器建立、編輯或驗證自訂設定位置範本。

UE-V 發生器會監視應用程式，以探索和捕獲應用程式儲存其設定的位置。 所監視的應用程式必須是傳統的應用程式。 UE-V 發生器無法為下列應用程式類型建立設定位置範本：

-   虛擬化應用程式

-   透過終端服務提供的應用程式

-   JAVA 應用程式

-   Windows 8 應用程式

## 使用 UE-V 產生器建立 UE-V 設定位置範本


如何使用 UE-V 發生器來建立設定位置範本。

[使用 UE-V 產生器建立 UE-V 設定位置範本](create-ue-v-settings-location-templates-with-the-ue-v-generator.md)

## 使用 UE-V 產生器編輯 UE-V 設定位置範本


如何使用 UE-V 發生器編輯設定位置範本。

[使用 UE-V 產生器編輯 UE-V 設定位置範本](edit-ue-v-settings-location-templates-with-the-ue-v-generator.md)

## 使用 UE-V 產生器驗證 UE-V 設定位置範本


如何使用 UE-V 發生器來驗證在 UE-V 發生器之外修改的設定位置範本。

[使用 UE-V 產生器驗證 UE-V 設定位置範本](validate-ue-v-settings-location-templates-with-ue-v-generator.md)

## <a href="" id="bkmk-standardnonstandardsettingslocations"></a>標準和非標準的設定位置


UE-V 發生器可協助您找出應用程式用來儲存設定資訊之設定檔和登錄設定的位置。 您可以使用 UE-V 發生器來開啟應用程式，以在標準位置中捕捉設定。 標準位置包括下列各項：

-   [**註冊表設定**]-[HKEY \] 下的 [註冊表位置] **_CURRENT \ _USER**

-   **應用程式設定**檔案–儲存在 \\**使用者**\\ [使用者名稱 \] 中的檔案檔案**AppData**  \\  **漫遊**

UE-V 發生器不包括通常儲存應用程式軟體檔案的位置，在使用者電腦或環境之間無法順利漫遊。 UE-V 發生器會將這些位置排除在一起。 [排除的位置] 如下所示：

-   HKEY \ _CURRENT \ _USER 登錄的使用者無法寫入值的登錄機碼和檔案

-   HKEY \ _CURRENT \ _USER 與 Windows 作業系統核心功能相關聯的登錄機碼和檔案

-   位於 HKEY \ _LOCAL \ _MACHINE hive 中的所有登錄機碼（需要系統管理員許可權，而且可能需要 UAC 協定才能設定）

-   位於 [程式檔案] 目錄中的檔案（需要系統管理員許可權，而且可能需要 UAC 協定才能設定）

-   檔案位於使用者 \\ [使用者名稱 \] \] \\ AppData \\ LocalLow

-   位於% systemroot% 中的 Windows 作業系統檔案（需要系統管理員許可權，而且可能需要 UAC 協定才能設定）

如果您需要儲存在這些位置的登錄機碼和檔案，才能漫遊應用程式設定，您可以在建立範本時，將排除的位置手動新增到 [設定位置] 範本。

## 此產品的其他資源


[UE-V 1.0 作業](operations-for-ue-v-10.md)

[管理 UE-V 1.0](administering-ue-v-10.md)

 

 





