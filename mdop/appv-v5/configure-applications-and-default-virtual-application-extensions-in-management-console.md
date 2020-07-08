---
title: 在管理主控台中設定應用程式和預設虛擬應用程式延伸模組
description: 如何使用 Management Console 檢視及設定應用程式與預設虛擬應用程式延伸模組
author: dansimp
ms.assetid: 1e1941d3-fb22-4077-8ec6-7a0cb80335d8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 09/26/2019
ms.openlocfilehash: 7c29ba0e40cf1adbc2b2297124cfb245a65a7ffe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800660"
---
#   在管理主控台中設定應用程式和預設虛擬應用程式延伸模組

使用下列程式來*查看*和*設定*預設套件延伸。

**若要查看和設定預設的虛擬應用程式擴充功能**

1.  若要查看您要設定的套件，請開啟 App-V 5.1 管理主控台。 選取您要設定的套件，以滑鼠右鍵按一下套件名稱，然後選取 [**編輯預設**設定]。

2.  若要查看包含在指定套件中的應用程式，請在 [**預設**設定] 窗格中按一下 [**應用程式**]。 若要查看該套件的快捷方式，請按一下 [**快速鍵**]。 若要查看該套件的檔案類型關聯，請按一下 [**檔案類型**]。

3.  若要啟用應用程式延伸，請選取 [**啟用**]。

    若要啟用快速鍵，請選取 [**啟用快速鍵**]。 若要為所選取的應用程式新增快速鍵，請在 [**快捷方式**] 窗格中以滑鼠右鍵按一下該應用程式，然後選取 [**新增快捷方式**]。 若要移除快速鍵，請在 [**快捷方式**] 窗格中以滑鼠右鍵按一下應用程式，然後選取 [**移除快捷方式**]。 若要編輯現有的快捷方式，請以滑鼠右鍵按一下該應用程式，然後選取 [**編輯快捷方式**]。

4.  若要查看任何其他應用程式延伸，請按一下 [**高級**]，然後按一下 [**匯出配置**]。 輸入檔案名，然後按一下 [**儲存**]。 您可以使用設定檔來查看與套件相關聯的所有應用程式擴充功能。

5.  若要編輯其他應用程式延伸，請修改設定檔，然後按一下 [匯**入並覆寫此**設定]。 選取已修改的檔案，然後按一下 [**開啟**]。 在對話方塊中，按一下 [**覆寫**] 以完成處理常式。

>**記事**如果上傳失敗且您的配置檔案大小超過4MB，您將需要增加伺服器所允許的最大檔案大小。 若要完成此動作，您可以將 maxRequestLength 屬性加上大於您配置檔案大小（KB）的值加到的 HTTPRuntime 元素 `C:\Program Files\Microsoft Application Virtualization Server\ManagementService\Web.config` 。  
例如， `<httpRuntime targetFramework="4.5"/>` 將 [變更為] `<httpRuntime targetFramework="4.5" maxRequestLength="8192"/>` 會將最大大小增加至8mb


您**有應用程式-V 的建議**嗎？ 在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。 **有應用程式-V 問題嗎？** 使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相關主題


[App-V 5.1 作業](operations-for-app-v-51.md)

 

 





