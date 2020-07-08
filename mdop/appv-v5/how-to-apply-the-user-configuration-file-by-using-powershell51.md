---
title: 如何使用 PowerShell 來套用使用者設定檔案
description: 如何使用 PowerShell 來套用使用者設定檔案
author: dansimp
ms.assetid: 986e638c-4a0c-4a7e-be73-f4615e8b8000
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 97b3db253993d6d855384ee5d9771a7f9ff5b64d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800591"
---
# 如何使用 PowerShell 來套用使用者設定檔案


當套件發佈至特定使用者並決定套件的執行方式時，就會套用動態使用者設定檔。

使用下列程式來指定使用者專用的設定檔。 下列程式是以範例為基礎：

**c:\\Packages\\Contoso\\MyApp.appv**

**若要套用使用者設定檔**

1.  若要使用 PowerShell 主控台將套件新增到電腦，請輸入以下命令：

    **AppVClientPackage c:\\Packages\\Contoso\\MyApp.appv**。

2.  使用下列命令將套件發佈給使用者，並指定更新的動態使用者設定檔案：

    **發佈-AppVClientPackage $pkg – DynamicUserConfigurationPath c:\\Packages\\Contoso\\config.xml**

    您**有應用程式-V 的建議**嗎？ 在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。 **有應用程式-V 問題嗎？** 使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相關主題


[App-V 5.1 作業](operations-for-app-v-51.md)

 

 





