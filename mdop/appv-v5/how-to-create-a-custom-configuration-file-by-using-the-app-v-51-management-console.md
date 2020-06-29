---
title: 如何使用 App-V 5.1 Management Console 建立自訂設定檔案
description: 如何使用 App-V 5.1 Management Console 建立自訂設定檔案
author: dansimp
ms.assetid: f5ab426a-f49a-47b3-93f3-b9d60aada8f4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 282207b5424442950e88c40a372194e9def768cb
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800565"
---
# 如何使用 App-V 5.1 Management Console 建立自訂設定檔案


您可以使用動態設定來自訂特定使用者的 app-v 5.1 套件。 不過，您必須先建立動態使用者配置（.xml）檔案或動態部署設定檔，才能使用這些檔案。 建立檔案是一個高級的手動操作。 如需有關動態使用者設定檔的一般資訊，請參閱[關於 app-v 5.1 動態](about-app-v-51-dynamic-configuration.md)設定。

使用下列程式來建立使用 App-v 5.1 管理主控台的動態使用者設定檔。

**建立動態使用者設定檔**

1.  以滑鼠右鍵按一下您想要查看之套件的名稱，然後選取 [**編輯 active directory 存取**]，以查看指派給特定使用者群組的配置。 或者，選取套件，然後按一下 [**編輯**]。

2.  在**Ad 實體**清單中使用 Access，選取您要自訂的廣告群組。 從下拉式清單中選取 [**自訂**] （如果尚未選取）。 隨即會顯示名為 [**編輯**] 的連結。

3.  按一下**編輯**。 隨即會顯示已指派給 AD 群組的動態使用者設定。

4.  按一下 [**高級**]，然後按一下 [**匯出配置**]。 輸入檔案名，然後按一下 [**儲存**]。 現在，您可以編輯檔案，為使用者設定套件。

    **注意**  
    若要在 Windows Server 上執行時匯出配置，您必須停用「IE 增強的安全性設定」。 如果啟用此選項並將其設為 [封鎖下載]，您就無法從 App-v Server 下載任何內容。



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## 相關主題


[App-V 5.1 作業](operations-for-app-v-51.md)









