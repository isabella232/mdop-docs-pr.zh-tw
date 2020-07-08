---
ms.reviewer: ''
title: 如何為特定使用者，將擴充點從 App-V 5.0 封裝移轉至 App-V 4.6 封裝
description: 如何為特定使用者，將擴充點從 App-V 5.0 封裝移轉至 App-V 4.6 封裝
ms.assetid: f1d2ab1f-0831-4976-b49f-169511d3382a
author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: 2a0660024734806c508043cc2db030c96cfd16a2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800419"
---
# 如何為特定使用者，將擴充點從 App-V 5.0 封裝移轉至 App-V 4.6 封裝

*注意：** App-V 4.6 已退出主流支援。

使用下列程式可使用使用者設定檔，將 App-v 5.0 套件復原為 App-v 檔案格式。

**若要還原套件**

1.  確保將 App-v 4.6 套件發佈給使用者，但 FTAs 和快速鍵是由 App-v 5.0 套件所假設，使用下列的遷移方法，[如何將應用程式 v 4.6 套件中的延伸點遷移到適用于特定使用者的 app-v 5.0](how-to-migrate-extension-points-from-an-app-v-46-package-to-app-v-50-for-a-specific-user.md)。

    在已轉換套件的部署設定檔的 [ **userConfiguration** ] 區段中，若要設定原則，請對**userConfiguration**區段進行下列更新： **ManagingAuthority TakeoverExtensionPointsFrom46 = "FALSE" PackageName = &lt; 封裝識別碼 &gt; **

2.  從提升許可權的命令提示字元輸入：

    PS &gt; **發佈-AppVClientPackage $Pkg – DynamicUserConfigurationPath** &lt; 到使用者設定檔的路徑&gt;

3.  執行發佈重新整理，或等候 App-V 4.6 的下一個排程發佈更新。 使用 FTAs 或快速鍵開啟應用程式。 應用程式現在應該會使用 App-v 4.6 SP2 來開啟。

    **注意**  
    如果您不再需要 App-v 5.0 套件，您可以將 App-v 5.0 套件取消發佈，延伸點將會自動復原至 App-v 4.6。



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## 相關主題


[App-V 5.0 作業](operations-for-app-v-50.md)












