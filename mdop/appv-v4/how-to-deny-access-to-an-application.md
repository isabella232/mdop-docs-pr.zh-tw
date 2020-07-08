---
title: 如何拒絕應用程式的存取權
description: 如何拒絕應用程式的存取權
author: dansimp
ms.assetid: 14f5e201-7265-462c-b738-57938dc3fc30
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 56a89669ea8c6323023b585d6d58620cd203fc00
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801449"
---
# 如何拒絕應用程式的存取權


使用者必須在應用程式的**存取許可權**清單中，才能載入和使用應用程式。 雖然應用程式虛擬化伺服器管理主控台不支援明確拒絕使用者群組對應用程式的存取權，但您可以從應用程式的屬性中移除使用者群組，以達到此目的。

**拒絕存取應用程式**

1.  針對現有的應用程式，請按一下左窗格中的 [**應用程式**] 節點。

2.  在右窗格中，以滑鼠右鍵按一下應用程式，然後選擇 [**屬性**]。 然後選取 [**存取許可權**] 索引標籤。

3.  若要移除使用者群組的存取權，請醒目提示 [使用者] 群組，然後按一下 [**移除**]。

4.  按一下 \[確定\] ****。

    **記事** 若要控制對應用程式的存取，您也可以限制應用程式授權。 在 Active Directory 網域服務中設定適當的使用者群組，提供最簡單的方式來授與拒絕特定使用者組的存取權。

     

## 相關主題


[如何授與應用程式的存取權](how-to-grant-access-to-an-application.md)

[如何在伺服器管理主控台中管理應用程式授權](how-to-manage-application-licenses-in-the-server-management-console.md)

[如何在伺服器管理主控台中管理應用程式](how-to-manage-applications-in-the-server-management-console.md)

 

 





