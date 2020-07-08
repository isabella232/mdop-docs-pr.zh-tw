---
title: 如何使用 Management Console 發佈套件
description: 如何使用 Management Console 發佈套件
author: dansimp
ms.assetid: 7c6930fc-5c89-4519-a901-512dae155fd2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 832dd95edbb0f4cd6b6ae242a81859141ebcb279
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800430"
---
# 如何使用 Management Console 發佈套件


使用下列程式發佈 App-v 5.0 套件。 發佈套件後，執行 App-V 5.0 用戶端的電腦就可以存取並執行該套件中的應用程式。

**記事** 從 App-v 5.0 SP3 開始，只支援將系統管理員發佈或取消發佈套件（如下所述）的功能。

 

**發佈 app-v 5.0 套件**

1.  在 App-V 5.0 管理主控台中。 以滑鼠右鍵按一下要發佈的套件名稱，然後選取 [**發佈**]。

2.  請查看 [**狀態**] 欄，確認套件已發佈且現已推出。 如果套件可用，就會顯示 [**已發佈**] 狀態。

    如果套件未順利發佈，就會顯示**未發佈**狀態，以及解釋套件無法使用之原因的錯誤文字。

**僅允許系統管理員發佈或取消發佈套件**

1.  流覽至下列群群組原則物件節點：

    **電腦配置 &gt;原則 &gt; 管理範本 &gt; 系統 &gt; app-v &gt; 發佈**。

2.  啟用 [**需要發佈為系統管理員**] 群群組原則設定。

    若要使用 PowerShell 來設定此專案，請參閱[如何使用 Powershell 管理在獨立電腦上](how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md#bkmk-admins-pub-pkgs)執行的 App-v 5.0 套件。

    您**有應用程式-V 的建議**嗎？ 在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。 **有應用程式-V 問題嗎？** 使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相關主題


[App-V 5.0 作業](operations-for-app-v-50.md)

[如何使用 Management Console 設定對套件的存取權](how-to-configure-access-to-packages-by-using-the-management-console-50.md)

 

 





