---
title: 備份封存
description: 備份封存
author: dansimp
ms.assetid: 538d85eb-3596-4c1d-bbd7-26bc28857c28
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8c6888d61e126d603aefa4e818f1070c5a493ea6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802126"
---
# 備份封存


若要在災難發生時協助恢復高級群組原則管理（AGPM），請經常備份 AGPM 系統管理員（完全控制）。 根據預設，會在%ProgramData%\\Microsoft\\AGPM. 中建立封存 不過，您可以在設定 Microsoft 高級群組原則管理-伺服器期間指定不同的路徑。

可存取 AGPM 服務器的使用者帳戶（已安裝 AGPM 服務的電腦），以及包含封存的資料夾需要完成此程式。

**若要備份封存**

1.  停止 AGPM 服務。 如需詳細資訊，請參閱[啟動和停止 AGPM 服務](start-and-stop-the-agpm-service-agpm40.md)。

2.  使用 Windows 資源管理器、Xcopy、Windows Server®備份或其他備份工具來備份 [封存] 資料夾。 請務必備份隱藏、系統和唯讀檔案。

3.  將封存備份儲存在安全的位置。

4.  重新開機 AGPM 服務。 如需詳細資訊，請參閱[啟動和停止 AGPM 服務](start-and-stop-the-agpm-service-agpm40.md)。

**記事** 如果 AGPM 管理員不經常備份封存，則封存備份中的群組原則物件（Gpo）不會是最新的。 若要更有效地確保封存備份是最新的，請在組織的每日備份策略中備份封存。

 

### 其他參考資料

-   [從備份還原封存](restore-the-archive-from-a-backup-agpm40.md)

-   [移動 AGPM 伺服器和封存](move-the-agpm-server-and-the-archive-agpm40.md)

-   [管理封存](managing-the-archive-agpm40.md)

 

 





