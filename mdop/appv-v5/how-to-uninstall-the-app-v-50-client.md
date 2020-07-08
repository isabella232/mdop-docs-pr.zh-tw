---
title: 如何解除安裝 App-V 5.0 Client
description: 如何解除安裝 App-V 5.0 Client
author: dansimp
ms.assetid: 7566fb19-8d52-439a-be42-e004d95fed6f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3794707b9342009b14eca37882c20873c38e522e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800399"
---
# 如何解除安裝 App-V 5.0 Client


使用下列程式從電腦卸載 app-v 5.0 用戶端。 當您卸載 App-v 5.0 用戶端時，所有發佈到執行用戶端之電腦的套件也都會被移除。 如果卸載操作沒有完成，則需要將套件重新發佈到執行 App-v 5.0 用戶端的電腦上。

**重要**  
在執行卸載程式之前，您應該先確定 App-V 5.0 用戶端服務正在執行。



**若要卸載應用程式-V 5.0 用戶端**

1.  在 [控制台] 中，按兩下 [**程式**  /  **卸載程式**]，然後按兩下 [ **Microsoft Application Virtualization 用戶端**]。

2.  在出現的對話方塊中，按一下 [**是**] 以繼續卸載程式。

    **重要**  
    無法取消或中斷卸載程式。



3.  進度列會顯示剩餘的時間。 完成這個步驟後，您必須重新開機電腦，才能停止所有相關聯的驅動程式來完成卸載程式。

    **注意**  
    您也可以使用命令列，以下列開關： **/uninstall**卸載 app-v 5.0 用戶端。



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## 相關主題


[部署 App-V 5.0](deploying-app-v-50.md)









