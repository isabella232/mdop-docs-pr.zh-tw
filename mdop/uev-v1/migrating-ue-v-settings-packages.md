---
title: 移轉 UE-V 設定套件
description: 移轉 UE-V 設定套件
author: dansimp
ms.assetid: 93d99254-3e17-4e96-92ad-87059d8554a7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d0087f334e916c06e7611d2671d0b50e7d1dd916
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809818"
---
# 移轉 UE-V 設定套件


在 Microsoft 使用者體驗虛擬化（UE-V）部署的生命週期中，您可能需要在遷移到新的伺服器或進行備份時，重新置放使用者設定套件。 在下列案例中可能需要遷移設定套件：

-   將現有的伺服器硬體升級至更先進的伺服器。

-   將設定儲存位置從實驗室遷移到成品伺服器。

只要複製檔案和資料夾，就不會保留安全性設定和許可權。 下列描述的步驟會將設定套件檔案以 NTFS 許可權正確地複製到新的共用位置。

**如何在遷移到新伺服器時保留 UE-V 設定套件**

1.  在其他伺服器上的新位置中，建立新資料夾;例如，MySettings。

2.  停用舊伺服器上舊資料夾共用的共用。

3.  從命令列將現有的設定套件從 Robocopy 移至新的伺服器。 例如：

    ``` syntax
    c:\start robocopy "\\servername\E$\MySettings" "\\servername\E$\MySettings" /b /sec /secfix /e /LOG:D:\Robocopylogs\MySettings.txt
    ```

    **記事** 若要監視複製進度，請使用記錄檔案讀取器（例如 Trace32）開啟 MySettings.txt。

     

4.  授與新共用的共用層許可權。 離開由 Robocopy 設定的 NTFS 許可權。

    在執行 UE-V agent 的電腦上，更新 SettingsStoragePath 設定為新共用的 UNC 路徑。

## 相關主題


[管理 UE-V 1.0](administering-ue-v-10.md)

[UE-V 1.0 作業](operations-for-ue-v-10.md)

 

 





