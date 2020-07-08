---
title: 如何使用 Management Console 自訂特定 AD 群組的虛擬應用程式延伸模組
description: 如何使用 Management Console 自訂特定 AD 群組的虛擬應用程式延伸模組
author: dansimp
ms.assetid: dd71df05-512f-4eb4-a55f-e5b93601323d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3bf086da3fbb6938a4fc602af5ab63adb1621532
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800548"
---
# 如何使用 Management Console 自訂特定 AD 群組的虛擬應用程式延伸模組


使用下列程式來自訂 Active Directory （AD）群組的虛擬應用程式擴充功能。

**自訂 AD 群組的虛擬應用程式擴充功能**

1.  若要查看您要設定的套件，請開啟 App-V 5.1 管理主控台。 若要查看指派給特定使用者群組的設定，請選取該套件，然後以滑鼠右鍵按一下套件名稱，然後選取 [**編輯 active directory 存取**]。 或者，選取套件，然後按一下 [ **AD 存取**] 窗格中的 [**編輯**]。

2.  若要自訂 AD 群組，您可以在**擁有 Access 的 AD 實體**清單中找到該群組。 接著，使用 [**指派**的設定] 窗格中的下拉式方塊，選取 [**自訂**]，然後按一下 [**編輯**]。

3.  若要停用指定應用程式的所有延伸，請清除 [**啟用**]。

    若要為選取的應用程式新增快捷方式，請在 [**快捷方式**] 窗格中以滑鼠右鍵按一下該應用程式，然後選取 [**新增快捷方式**]。 若要移除快速鍵，請在 [**快捷方式**] 窗格中以滑鼠右鍵按一下應用程式，然後選取 [**移除快捷方式**]。 若要編輯現有的快捷方式，請以滑鼠右鍵按一下該應用程式，然後選取 [**編輯快捷方式**]。

4.  若要查看任何其他應用程式延伸，請按一下 [**高級**]，然後按一下 [**匯出配置**]。 輸入檔案名，然後按一下 [**儲存**]。 您可以使用設定檔來查看與套件關聯的所有應用程式延伸。

5.  若要編輯其他應用程式擴充功能，請修改設定檔，然後按一下 [匯**入並覆寫此**設定]。 選取已修改的檔案，然後按一下 [**開啟**]。 在對話方塊中，按一下 [**覆寫**] 以完成處理常式。

    您**有應用程式-V 的建議**嗎？ 在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。 **有應用程式-V 問題嗎？** 使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相關主題


[App-V 5.1 作業](operations-for-app-v-51.md)

 

 





