---
title: 如何為特定電腦上的所有使用者，將擴充點從 App-V 5.0 封裝移轉至 App-V 4.6 封裝
description: 如何為特定電腦上的所有使用者，將擴充點從 App-V 5.0 封裝移轉至 App-V 4.6 封裝
ms.assetid: 2a43ca1b-6847-4dd1-ade2-336ac4ac6af0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: 62542e5cd0b9dcb55f6e8f3db4d4f43c011a2839
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800416"
---
# 如何為特定電腦上的所有使用者，將擴充點從 App-V 5.0 封裝移轉至 App-V 4.6 封裝

*注意：** App-V 4.6 已退出主流支援。 下列假設已安裝 app-v 4.6 SP3 用戶端。

使用下列程式會使用部署設定檔，將 App V 5.0 套件中的延伸點復原至 App-v 4.6 檔案格式。

**若要還原套件**

1.  確保將 App-v 4.6 套件發佈給使用者，但 FTAs 和快速鍵是由 App-v 5.0 套件（使用下列遷移方法），[如何將應用程式 v 4.6 套件中的延伸點遷移到針對特定電腦上的所有使用者所轉換的 app-v 5.0 套件中](how-to-migrate-extension-points-from-an-app-v-46-package-to-a-converted-app-v-50-package-for-all-users-on-a-specific-computer.md)。

    在已轉換套件的部署設定檔的 [ **userConfiguration** ] 區段中，若要設定原則，請對**userConfiguration**區段進行下列更新： **ManagingAuthority TakeoverExtensionPointsFrom46 = "FALSE" PackageName = &lt; 封裝識別碼 &gt; **

2.  從提升許可權的命令提示字元輸入：

    PS &gt; **設定-AppvClientPackage $Pkg – DynamicDeploymentConfiguration** &lt; 到部署設定檔的路徑&gt;

    PS &gt; **發佈-AppVClientPackage $Pkg – DynamicUserConfigurationType useDeploymentConfiguration**

3.  執行發佈重新整理，或等候 App-V 4.6 SP2 封裝的下一次排程發佈更新。

    使用 FTAs 或快速鍵開啟應用程式。 應用程式現在應該會使用 App-v 4.6 開啟。

    **注意**  
    如果您不再需要 App-v 5.0 套件，您可以將 App-v 5.0 套件取消發佈，延伸點將會自動復原至 App-v 4.6。



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## 相關主題


[App-V 5.0 作業](operations-for-app-v-50.md)









