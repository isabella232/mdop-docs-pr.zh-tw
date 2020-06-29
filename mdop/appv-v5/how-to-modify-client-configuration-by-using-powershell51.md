---
title: 如何使用 PowerShell 來修改用戶端組態
description: 如何使用 PowerShell 來修改用戶端組態
author: dansimp
ms.assetid: c3a59592-bb0d-43b6-8f4e-44f3a2d5b7ea
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 368a0d12c12e10a623afad3f9040ae01cee6cb38
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800437"
---
# 如何使用 PowerShell 來修改用戶端組態


使用下列程式來設定 App-v 5.1 用戶端配置。

**使用 PowerShell 修改 App-v 5.1 用戶端設定**

1.  若要使用 PowerShell 設定用戶端設定，請使用**AppvClientConfiguration** Cmdlet。 如需安裝 PowerShell 及 Cmdlet 清單的詳細資訊，請參閱[如何載入 Powershell Cmdlet 及取得 Cmdlet 說明](how-to-load-the-powershell-cmdlets-and-get-cmdlet-help-51.md)。

2.  若要修改用戶端設定，請開啟 PowerShell 命令提示字元，並執行下列 Cmdlet **AppvClientConfiguration** ，並使用任何必要的參數。 例如：

    `$config = Get-AppvClientConfiguration`

    `Set-AppvClientConfiguration $config`

    `Set-AppvClientConfiguration –AutoLoad 2`

    您**有應用程式-V 的建議**嗎？ 在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。 **有應用程式-V 問題嗎？** 使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相關主題


[App-V 5.1 作業](operations-for-app-v-51.md)

 

 





