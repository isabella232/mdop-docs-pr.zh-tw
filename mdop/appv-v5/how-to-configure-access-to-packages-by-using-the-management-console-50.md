---
title: 如何使用 Management Console 設定對套件的存取權
description: 如何使用 Management Console 設定對套件的存取權
author: dansimp
ms.assetid: 8f4c91e4-f4e6-48cf-aa94-6085a054e8f7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0e1f5b51b118dc7b783a4a550e19fd39a61a0ab4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800589"
---
# 如何使用 Management Console 設定對套件的存取權


您必須先設定 Active Directory 網域服務（AD DS）安全性群組（可存取並執行應用程式），才能部署 app-v 5.0 虛擬化套件。 安全性群組可能包含電腦或使用者。 Entitling 套件至電腦群組會將套件全域發佈到群組中的所有電腦。

使用下列程式設定虛擬化套件的存取權。

**若要授與 app-v 5.0 套件的存取權**

1.  尋找您要設定的套件：

    1.  開啟 App-V 5.0 管理主控台。

    2.  若要顯示 [**廣告存取**] 頁面，請以滑鼠右鍵按一下要設定的套件，然後選取 [**編輯 active directory 存取**]。 或者，選取套件，然後按一下 [ **AD 存取**] 窗格中的 [**編輯**]。

2.  為套件提供安全性群組：

    1.  移至 [**尋找有效的 ACTIVE DIRECTORY 名稱並授與存取權**] 頁面。

    2.  使用 [格式化**mydomain**  \\  **groupname**組名]，輸入 Active Directory 群組物件的名稱或部分名稱，然後按一下 [**檢查**]。

        **記事** 請確定您為您要搜尋的群組提供相關聯的功能變數名稱。

         

3.  若要授與對套件的存取權，請選取想要的群組，然後按一下 **[准許存取**]。 新新增的群組會顯示在擁有 [存取] 窗格的 [ **AD 實體**] 中。

4.  

    若要接受預設設定並關閉 [**廣告存取**] 頁面，請按一下 [**關閉**]。

    若要自訂特定群組的設定，請按一下 [**指派**的設定] 下拉式清單，然後選取 [**自訂**]。 若要設定自訂設定，請按一下 [**編輯**]。 在您授與存取權之後，按一下 [**關閉**]。

**移除 App-v 5.0 套件的存取權**

1.  尋找您要設定的套件：

    1.  開啟 App-V 5.0 管理主控台。

    2.  若要顯示 [**廣告存取**] 頁面，請以滑鼠右鍵按一下要設定的套件，然後選取 [**編輯 active directory 存取**]。 或者，選取套件，然後按一下 [ **AD 存取**] 窗格中的 [**編輯**]。

2.  選取您要移除的群組，然後按一下 [**刪除**]。

3.  若要關閉 [**廣告存取**] 頁面，請按一下 [**關閉**]。

    您**有應用程式-V 的建議**嗎？ 在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。 **有應用程式-V 問題嗎？** 使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相關主題


[App-V 5.0 作業](operations-for-app-v-50.md)

 

 





