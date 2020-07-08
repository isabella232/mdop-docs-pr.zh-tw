---
title: 如何建立連線群組
description: 如何建立連線群組
author: dansimp
ms.assetid: 221e2eed-7ebb-42e3-b3d6-11c37c0578e6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7f20b3e71c7c0b72d66700bbad945860112ffd03
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800567"
---
# 如何建立連線群組


使用這些步驟來建立使用 App-v 管理主控台的連線群組。 若要使用 PowerShell 來建立連線群組，請參閱[如何使用 powershell 在獨立電腦上管理連線群組](how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell51.md)。

當您將套件放在連線群組中時，其套件根路徑會合並在一起。 如果您移除套件，則只有其餘的套件會維持合併的根。

**建立連線群組**

1.  在 App-V 5.1 管理主控台中，選取 [連線**群組**] 以顯示 [連線群組] 程式庫。

2.  選取 [**新增連接群組**] 來建立新的連線群組。

3.  在 [**新增**連線] 群組窗格中，輸入群組的描述。

4.  按一下 [連結的**套件**] 窗格中的 [**編輯**]，將新的應用程式新增至連線群組。

5.  在 [**封裝整個文件庫**] 窗格中，選取要新增的應用程式，然後按一下箭號以新增應用程式。

    若要移除應用程式，請在 [**套件**] 窗格中選取要移除的應用程式，然後按一下箭號。

    若要重設連線群組中的應用程式的優先順序，請使用 [**套件**] 窗格中的箭號。

    **重要** 根據預設，與特定應用程式相關聯的 Active Directory 網域服務存取設定並不會新增到連線群組中。 若要轉移 Active Directory 存取設定，請選取 [**新增套件存取權至群組存取**]，該群組位於 [套件] 窗格**中**。

     

6.  在新增所有應用程式並設定 Active Directory 存取之後，**按一下 [** 套用]。

    您**有應用程式-V 的建議**嗎？ 在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。 **有應用程式-V 問題嗎？** 使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相關主題


[App-V 5.1 作業](operations-for-app-v-51.md)

[管理連線群組](managing-connection-groups51.md)

 

 





