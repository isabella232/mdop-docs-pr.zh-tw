---
title: 如何變更記錄報告層級以及重設記錄檔
description: 如何變更記錄報告層級以及重設記錄檔
author: dansimp
ms.assetid: 9561d6fb-b35c-491b-a355-000064583194
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7307dee0030d9c03a8107d9d0ceef2086a94df07
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801661"
---
# 如何變更記錄報告層級以及重設記錄檔


您可以使用下列程式，在應用程式虛擬化管理主控台中變更**應用程式虛擬化**節點的記錄報告層級。 當記錄檔案達到最大大小時（預設值為 256 MB），當下次寫入記錄時，就會強制執行重設。 [重設] 會建立新的記錄檔案，而舊的檔案會重新命名為 [備份]。

**變更記錄報告層級**

1.  以滑鼠右鍵按一下**應用程式虛擬化**節點，然後從快顯功能表中選取 [**屬性**]。

2.  在 **[內容] 對話方塊的**[**一般**] 索引標籤上，從 [**記錄層級**] 下拉式清單中，選取想要的記錄層級。

    **記事** 如果您選擇 [**詳細**] 作為記錄層級，記錄檔就會很快變大。 這可能會影響用戶端效能，所以最佳做法是只使用這個記錄層級來診斷特定問題。

     

3.  在 **[內容] 對話方塊的**[**一般**] 索引標籤上，從 [**系統記錄層級**] 下拉式清單中，選取想要的記錄層級。

    **記事** **系統記錄層級**設定控制傳送至系統事件記錄條的訊息層級。 記錄的訊息與記錄在用戶端事件日誌中的訊息完全相同，但會儲存在不同的位置。

     

4.  按一下 **[確定]** **或**[套用] 來變更設定。

**重設記錄檔**

1.  以滑鼠右鍵按一下**應用程式虛擬化**節點，然後從快顯功能表中選取 [**屬性**]。

2.  在 [**屬性**] 對話方塊的 [**一般**] 索引標籤上，按一下 [**重設記錄**] 以備份目前的記錄檔，並立即開始新的記錄檔。 備份記錄檔儲存在相同的資料夾中。

3.  按一下 **[確定]** **或**[套用] 來變更設定。

## 相關主題


[如何在 Application Virtualization Client 管理主控台中設定用戶端](how-to-configure-the-client-in-the-application-virtualization-client-management-console.md)

[Application Virtualization Client 中的使用者存取權限](user-access-permissions-in-application-virtualization-client.md)

 

 





