---
title: 如何在主機和 MED-V 工作區之間共用資料夾
description: 如何在主機和 MED-V 工作區之間共用資料夾
author: dansimp
ms.assetid: 3cb295f2-c07e-4ee6-aa3c-ce4c8c45c191
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 87f315c9894cd38834413d2549e652a36c5cc16d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811343"
---
# 如何在主機和 MED-V 工作區之間共用資料夾


您可以在主機與 MED-V 工作區之間共用資料夾。 共用資料夾可以儲存在下列各項：

-   網路上的外部電腦

-   主機電腦

下列程式示範如何在主機與 MED-V 工作區之間共用資料夾。

**共用位於網路上的資料夾**

1.  在完整桌面圖案中設定 MED-V。

2.  在 MED-V 管理的 [網路] 索引標籤上，按一下 [**使用與主機不同的 IP 位址] （橋接器）**。

3.  在主機電腦上執行下列動作：

    1.  在 [控制台] 中，按一下 [**查看網路狀態及**工作]，然後將**網路探索**設定為 [**開啟**]。

    2.  在 [開始] 功能表上，以滑鼠右鍵按一下 [**電腦**]，然後按一下 [**對應網路磁片磁碟機**]。

    3.  在 [**對應網路磁碟機**] 對話方塊的 [**磁碟機**] 欄位中，選取一個磁片磁碟機。

        **記事** 確定兩部電腦不使用相同的磁碟機盤符。

         

    4.  按一下 \[瀏覽\]。****

    5.  在 [**流覽資料夾**] 對話方塊中，流覽至共用的磁片磁碟機，然後按一下 **[確定]**。

    6.  按一下 **\[完成\]**。

4.  在 MED-V 工作區中重複步驟3。 指向主機電腦上的同一個磁片磁碟機。

**共用位於主機上的資料夾**

1.  將資料夾設定為與適當的許可權共用。

2.  從 MED-V 工作區，移至 [**網路位置**] 並找出共用資料夾。

3.  從 MED-V 工作區，找出共用資料夾。

**記事** 確定主機和 MED-V 工作區電腦都在同一個網域或工作組中。

 

 

 





