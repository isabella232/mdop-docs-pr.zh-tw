---
title: 如何為特定電腦上的所有使用者，將擴充點從 App-V 4.6 封裝移轉至轉換的 App-V 5.1 封裝
description: 如何為特定電腦上的所有使用者，將擴充點從 App-V 4.6 封裝移轉至轉換的 App-V 5.1 封裝
author: dansimp
ms.assetid: 4ef823a5-3106-44c5-aecc-29edf69c2fbb
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: 7bac244804b46309a0e0a75cb3742dfe22e92e8f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800454"
---
# 如何為特定電腦上的所有使用者，將擴充點從 App-V 4.6 封裝移轉至轉換的 App-V 5.1 封裝


使用下列程式，將應用程式-V 4.6 套件中的延伸點移到使用部署設定檔的 App-v 5.1 套件中。

**記事** 這個程式假設您執行的是最新版本的 App-V 4.6。  
下列程式不需要 App-v 5.1 管理伺服器。

 

**使用部署設定檔，將來自 App-v 4.6 套件之套件中的延伸點遷移到已轉換的應用程式 V 5.1 套件**

1. 找出包含您要遷移之套件之部署設定檔的目錄。 若要設定原則，請對**userConfiguration**區段進行下列更新：

   **ManagingAuthority TakeoverExtensionPointsFrom46 = "true" PackageName = &lt; PACKAGE ID&gt;**

   以下是部署設定檔中的內容範例：

   &lt;？ xml 版本 = "1.0"？&gt;

   &lt;DeploymentConfiguration

   xmlns = " <https://schemas.microsoft.com/appv/2010/deploymentconfiguration> " PackageId = &lt; Package ID &gt; DisplayName DisplayName = &lt; 顯示名稱&gt;

   &lt;MachineConfiguration/&gt;

   &lt;UserConfiguration&gt;

   &lt;ManagingAuthority TakeoverExtensionPointsFrom46 = "true"

   PackageName = &lt; 封裝識別碼&gt;

   &lt;/UserConfiguration&gt;

   &lt;/DeploymentConfiguration&gt;

2. 若要新增 App-v 5.1 套件，請在提升許可權的 PowerShell 命令提示字元中輸入：

   PS &gt; **$pkg = Add-AppvClientPackage** **–** &lt; 到套件位置的路徑路徑至 &gt;  - **DynamicDeploymentConfiguration** &lt; 部署設定檔的路徑&gt;

   PS &gt; **發佈-AppVClientPackage $pkg**

3. 若要測試遷移，請使用相關聯的 FTAs 或快速鍵開啟虛擬應用程式。 應用程式隨即開啟，並會出現 App-v 5.1。 在這兩者中，App-v 4.6 套件與已轉換的 app-v 5.1 套件都會發佈給使用者，但應用程式的 FTAs 和快速鍵都是由 App-v 5.1 套件所採用。

   您**有應用程式-V 的建議**嗎？ 在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。 **有應用程式-V 問題嗎？** 使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相關主題


[如何為特定電腦上的所有使用者，將擴充點從 App-V 5.1 封裝移轉至 App-V 4.6 封裝](how-to-revert-extension-points-from-an-app-v-51-package-to-an-app-v-46-package-for-all-users-on-a-specific-computer.md)

[App-V 5.1 作業](operations-for-app-v-51.md)

 

 





