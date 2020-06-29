---
title: 從備份還原封存
description: 從備份還原封存
author: dansimp
ms.assetid: b83f6173-a236-4da2-b16e-8df20920d4cc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3a1b7039ad587cf9c8d7f914fe3b963e12ba8949
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801801"
---
# 從備份還原封存


如果發生災難，且 [高級] 群組原則管理（AGPM）的封存遭到損毀或損毀，則 AGPM 管理員（完全控制）可以先預先準備好的備份複本，然後從網域的生產環境中匯入，而不是封存中的任何群組原則物件（Gpo），或是生產環境中的版本比封存中的版本要更新。 如需有關如何將封存備份還原到其他伺服器的詳細資訊，請參閱[移動 AGPM 服務器和](move-the-agpm-server-and-the-archive-agpm40.md)封存。

可存取 AGPM 服務器的使用者帳戶（安裝 AGPM 服務的電腦），以及包含封存的資料夾必須完成此程式。

**從備份還原封存**

1.  停止 AGPM 服務。 如需詳細資訊，請參閱[啟動和停止 AGPM 服務](start-and-stop-the-agpm-service-agpm40.md)。

2.  移除現有封存。 根據預設，[封存] 資料夾是%ProgramData%\\Microsoft\\AGPM，不過安裝 Microsoft 高級群組原則管理的 AGPM 管理員，伺服器可能在安裝期間輸入了不同的位置。

3.  設定封存路徑、AGPM 服務帳戶、封存擁有者和偵聽埠，以重新建立 [封存] 資料夾。 您不需要使用在原始安裝期間所使用的相同值。 如需詳細資訊，請參閱[修改 AGPM 服務](modify-the-agpm-service-agpm40.md)。

4.  將封存備份的內容複寫到 [封存] 資料夾，複製子資料夾和檔案，以確定每個子資料夾和檔案都繼承 [封存] 資料夾的許可權。 請小心不要覆寫 [封存] 資料夾。

5.  如果您不確定封存備份中的 GPO 是否比生產中該 GPO 的複本還新，請產生差異報告並比較其設定。 如需詳細資訊，請參閱[識別 gpo、Gpo 版本或範本之間的差異](identify-differences-between-gpos-gpo-versions-or-templates-agpm40.md)。

6.  重新開機 AGPM 服務。 如需詳細資訊，請參閱[啟動和停止 AGPM 服務](start-and-stop-the-agpm-service-agpm40.md)。

### 其他參考資料

-   [備份封存](back-up-the-archive-agpm40.md)

-   [移動 AGPM 伺服器和封存](move-the-agpm-server-and-the-archive-agpm40.md)

-   [管理封存](managing-the-archive-agpm40.md)

 

 





