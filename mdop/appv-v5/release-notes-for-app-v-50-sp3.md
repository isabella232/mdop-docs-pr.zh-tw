---
title: App-V 5.0 SP3 版本資訊
description: App-V 5.0 SP3 版本資訊
author: dansimp
ms.assetid: bc4806e0-2aba-4c7b-9ecc-1b2cc54af1d0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5b6d5834e4d0c953365f955922403c1a7a2058b1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800315"
---
# App-V 5.0 SP3 版本資訊


下列是 Microsoft Application Virtualization （App-v） 5.0 SP3 中的已知問題。

## 在新的 App-v 5.0 SP3 伺服器安裝之後，無法刪除伺服器檔案


如果您卸載 App-v 5.0 SP1 Server，然後安裝 App-v 5.0 SP3 伺服器，安裝會失敗，且已安裝錯誤的管理伺服器版本。 隨即會顯示下列錯誤：

`[0A5C:06F8][2014-09-12T19:08:00]i102: Detected related bundle: {bee44f0f-05be-48e4-81dd-d34a83600b95}, type: Upgrade, scope: PerMachine, version: 5.0.1218.0, operation: MajorUpgrade``[0A5C:06F8][2014-09-12T19:08:00]i000: AppvUX: A previous version of this product is installed; requesting upgrade.``[0A5C:06F8][2014-09-12T19:08:00]i102: Detected related bundle: {e1ca9d65-0ebf-4fd5-98e5-00d6453967a4}, type: Upgrade, scope: PerMachine, version: 5.0.1224.0, operation: MajorUpgrade``[0A5C:06F8][2014-09-12T19:08:00]i000: AppvUX: A previous version of this product is installed; requesting upgrade.`

發生這個問題的原因是，當您卸載 App-v 5.0 SP1 時，伺服器檔案未被刪除，因此 App-v 5.0 SP3 安裝程式執行的是不是新安裝所需的升級。

**解決方法**：先刪除下列登錄機碼，然後再開始安裝 APP-V 5.0 SP3：

`HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Uninstall`

## 查詢 AD DS 可能導致某些應用程式無法正常運作


如果您透過查詢 Active Directory 網域服務以取得更新的群組成員資格來接收更新的套件，則如果應用程式是由使用者的存取權杖所決定，可能會導致某些應用程式無法正常運作。 此外，常用的群組成員資格查詢也可能會造成網網域控制站超載。 如需有關使用者存取權杖的詳細資訊，請參閱[存取權杖](https://msdn.microsoft.com/library/windows/desktop/aa374909.aspx)。

因應**措施：等到**使用者登出後再重新登入，然後再查詢已更新的群組成員資格。 請勿使用[Microsoft Application Virtualization 5.0 Service Pack 1 之修復程式套件 2](https://support.microsoft.com/kb/2897087)中所述的登錄機碼來查詢更新的群組成員資格。






## 相關主題


[關於 App-V 5.0 SP3](about-app-v-50-sp3.md)

 

 





