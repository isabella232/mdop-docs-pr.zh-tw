---
title: 遷移 UE-V a.x 設定套件
description: 遷移 UE-V a.x 設定套件
author: dansimp
ms.assetid: f79381f4-e142-405c-b728-5c048502aa70
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0aa1f1c36594d69de40306dfa70a4a0cf5c86dbb
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811204"
---
# 遷移 UE-V a.x 設定套件


在 Microsoft 使用者體驗虛擬化（UE-V）2.0、2.1 或 2.1 SP1 部署的生命週期中，您可能必須在您遷移至新伺服器或執行備份時，重新置放使用者設定套件。 在下列情況下，可能需要遷移設定套件：

-   將現有的伺服器硬體升級至更先進的伺服器。

-   從測試伺服器到生產伺服器的設定儲存位置共用的遷移。

只要複製檔案和資料夾，就不會保留安全性設定和許可權。 下列步驟說明如何將設定套件及其 NTFS 檔案系統許可權正確地複製到新的共用位置。

**若要在遷移到新伺服器時保留 UE-V 2 設定套件**

1.  在其他伺服器上的新位置中，建立新的資料夾，例如 MySettings。

2.  停用舊伺服器上舊資料夾共用的共用。

3.  使用 Robocopy 將現有的設定套件複製到新伺服器

    ``` syntax
    C:\start robocopy "\\servername\E$\MySettings" "\\servername\E$\MySettings" /b /sec /secfix /e /LOG:D:\Robocopylogs\MySettings.txt
    ```

    **記事** 若要監視複製進度，請使用記錄檢視器（例如 Trace32）開啟 MySettings.txt。

     

4.  授與新共用的共用層許可權。 保留由 Robocopy 設定的 NTFS 檔案系統許可權。

    在執行 UE-V Agent 的電腦上，將**SettingsStoragePath**設定設定更新為新共用的通用命名慣例（UNC）路徑。

    **為 ue-v 提供建議**嗎？ 在[此](http://uev.uservoice.com/forums/280428-microsoft-user-experience-virtualization)新增或投票建議。 是否**有 ue-v 問題**？ 使用[Ue-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopuev)。

## 相關主題


[管理 UE-V 2。](administering-ue-v-2x-new-uevv2.md)

 

 





