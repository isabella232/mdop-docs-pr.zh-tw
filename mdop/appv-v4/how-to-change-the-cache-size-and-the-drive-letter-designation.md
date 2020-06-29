---
title: 如何變更快取大小以及磁碟機代號的指定
description: 如何變更快取大小以及磁碟機代號的指定
author: dansimp
ms.assetid: e7d7b635-079e-41aa-a5e6-655f33b4e317
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cf972f114845064ecf3027cf52d1a038dc6a5118
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801657"
---
# 如何變更快取大小以及磁碟機代號的指定


您可以直接從應用程式虛擬化用戶端管理主控台的**應用程式虛擬化**節點變更快取大小與磁片磁碟機號符號。

**注意**  
設定快取大小之後，就不能變小。



**變更快取大小**

1.  以滑鼠右鍵按一下**應用程式虛擬化**節點，然後從快顯功能表中選取 [**屬性**]。

2.  選取 [**屬性**] 對話方塊上的 [檔案**系統**] 索引標籤。 在 [**用戶端**快取設定] 區段中，按一下下列其中一個選項按鈕，選擇如何管理快取空間：

    **重要**  
    如果您選取 [**使用可用磁碟空間閾值**] 設定，您所輸入的值會將快取大小設定為磁片總大小減去您所輸入的可用磁碟空間閾值。 如果您想要使用 [**使用最大**快取大小] 設定還原，您必須指定比現有快取大小更大的數位。 否則，就會出現「新大小必須大於現有的快取大小」錯誤。



~~~
-   **Use maximum cache size**

    Enter a numeric value from 100 to 1,048,576 (1 TB) in the **Maximum size (MB)** field to specify the maximum size of the cache. The value shown in **Reserved Cache Size** indicates the amount of cache in use.

-   **Use free disk space threshold**

    Enter a numeric value to specify the amount of free disk space, in MB, that the cache must leave available on the disk. This allows the cache to grow until the amount of free disk space reaches this limit. The value shown in **Free disk space remaining** indicates how much disk space is unused.
~~~

3. 按一下 **[確定]** **或**[套用] 來變更設定。

**若要變更磁片磁碟機字母指定**

1.  以滑鼠右鍵按一下**應用程式虛擬化**節點，然後從快顯功能表中選取 [**屬性**]。

2.  在 **[內容] 對話方塊的**[檔案**系統**] 索引標籤上，于 [**要使用的磁片磁碟機**] 欄位中，從可用的磁片磁碟機盤符下拉式清單中選取所需的磁碟機盤符。 當電腦重新開機時，此設定就會生效。

3.  按一下 **[確定]** **或**[套用] 來變更設定。

## 相關主題


[如何在 Application Virtualization Client 管理主控台中設定用戶端](how-to-configure-the-client-in-the-application-virtualization-client-management-console.md)









