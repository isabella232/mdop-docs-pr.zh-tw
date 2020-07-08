---
title: 如何使用 Management Console 新增或升級套件
description: 如何使用 Management Console 新增或升級套件
author: dansimp
ms.assetid: 62417b63-06b2-437c-8584-523e1dea97c3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4ac458a5e33b83e19d72fee39cf837aa6bd57bc5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800605"
---
# 如何使用 Management Console 新增或升級套件


您可以使用下列程式，將套件新增或升級到 App-v 5.1 管理主控台。 若要升級已存在於管理主控台中的套件，請使用下列步驟，並使用相同的套件**名稱**匯入升級後的套件。

**將套件新增到管理主控台**

1.  按一下管理主控台顯示的 [功能窗格] 中的 [**套件**] 索引標籤。

    主控台會顯示已新增到伺服器的套件清單，以及每個套件的狀態資訊。 選取套件時，套件窗格中會顯示有關**套件的詳細**資訊。

    按一下 [**取消**群組] 下拉式清單方塊，並指定套件在主控台中的顯示方式。 您也可以按一下相關聯的欄標題來排序套件。

2.  若要指定您想要新增的套件，請按一下 [**新增或升級套件**]。

3.  輸入您要新增之套件的完整路徑。 使用 UNC 或 HTTP 路徑格式，例如**\\\\servername\\sharename\\foldername\\packagename.appv**或 **http://server.1234/file.appv** ，然後按一下 [**新增**]。

    **重要** 您必須選取具有**appv**副檔名的套件。

     

4.  頁面會顯示 [**新增 &lt; Packagename &gt; **] 的狀態訊息。 按一下 [匯**入狀態**]，查看您已匯入之套件的狀態。

    按一下 **[確定]** 以新增套件，然後關閉 [**新增套件**] 頁面。 如果匯入期間發生錯誤，請按一下套件 [匯**入**] 頁面上的 [**詳細資料**] 以取得詳細資訊。 您現在可以在 [**套件**] 窗格中使用新新增的套件。

5.  按一下 [**關閉**]，關閉 [**新增或升級套件**] 頁面。

    您**有應用程式-V 的建議**嗎？ 在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。 **有應用程式-V 問題嗎？** 使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相關主題


[App-V 5.1 作業](operations-for-app-v-51.md)

 

 





