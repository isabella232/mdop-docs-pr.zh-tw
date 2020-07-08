---
title: 如何只讓系統管理員使用 ESD 來發佈套件
description: 如何只讓系統管理員使用 ESD 來發佈套件
author: dansimp
ms.assetid: bbc9fda2-fc09-4d72-8d9a-e83d2fcfe234
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 22de7f62f540ceff274862c3f16b1f89d9459093
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800507"
---
# 如何只讓系統管理員使用 ESD 來發佈套件


從 App-v 5.0 SP3 開始，您可以設定 App-v 用戶端，讓只有系統管理員（而非最終使用者）可以發佈或取消發佈套件。 在舊版 App-v 中，您不能防止使用者執行這些工作。

**僅允許系統管理員發佈或取消發佈套件**

1.  流覽至下列群群組原則物件節點：

    **電腦配置 &gt;原則 &gt; 管理範本 &gt; 系統 &gt; app-v &gt; 發佈**。

2.  啟用 [**需要發佈為系統管理員**] 群群組原則設定。

    若要使用 PowerShell 來設定此專案，請參閱[如何使用 Powershell 管理在獨立電腦上](how-to-manage-app-v-51-packages-running-on-a-stand-alone-computer-by-using-powershell.md#bkmk-admins-pub-pkgs)執行的 App-v 5.1 套件。

    您**有應用程式-V 的建議**嗎？ 在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。 **有應用程式-V 問題嗎？** 使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

 

 





