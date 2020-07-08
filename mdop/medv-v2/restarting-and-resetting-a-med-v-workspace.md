---
title: 重新啟動和重設 MED-V 工作區
description: 重新啟動和重設 MED-V 工作區
author: dansimp
ms.assetid: a959cdb3-a727-47c7-967e-e58f224e74de
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 48a644c2ed1668f87eb6e1a78521e780e8b783dd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811145"
---
# 重新啟動和重設 MED-V 工作區


在疑難排解期間，有時您可能會發現需要重新開機或重設 MED-V 工作區。 重新開機 MED-V 工作區與重新開機物理電腦基本相同。 重設 MED-V 工作區第一次重新安裝，並刪除儲存在虛擬機器中的所有資料。 由於已刪除所有已儲存的資料，因此您通常應該只重設 MED-V 工作區，以解決最嚴重的疑難排解問題，或將先前工作的 MED-V 工作區還原到工作狀態。

如需如何開啟 MED-V 管理工具組的相關資訊，請參閱[使用管理工具組在 med-v 中進行疑難排解](troubleshooting-med-v-by-using-the-administration-toolkit.md)。

**重新開機 MED-V 工作區**

1.  在 [ **med-v-v 管理工具**] 視窗中，按一下 [**重新開機 Med-v-V 工作區**]。 對話方塊視窗隨即開啟，您必須在其中確認您要重新開機 MED-V 工作區。

2.  按一下 [**重新開機**]。

    當 MED-V 工作區重新開機時，任何執行中的已發佈應用程式或開啟的網站，都將會關閉。

**重設 MED-V 工作區**

1.  在 [ **Med-v 管理工具**組] 視窗中，按一下 [**重設 Med-v-V 工作區**]。 對話方塊視窗隨即開啟，您必須在其中確認您要重設 MED-V 工作區。

    **警告** 重設 MED-V 工作區會導致第一次設定再次執行，進而重新載入原始的虛擬硬碟。 在第一次執行設定之後，所有儲存在 MED-V 工作區的資料，都將會被刪除。

     

2.  按一下 \[**重設**\]。

    當 MED-V 工作區重設時，任何執行中的已發佈應用程式或開啟的網站，都將會關閉。

## 相關主題


[檢視及設定 MED-V 記錄](viewing-and-configuring-med-v-logs.md)

[檢視 MED-V 工作區設定](viewing-med-v-workspace-configurations.md)

 

 





