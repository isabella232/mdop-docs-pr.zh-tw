---
title: 如何為特定使用者，將擴充點從 App-V 4.6 封裝移轉至 App-V 5.1
description: 如何為特定使用者，將擴充點從 App-V 4.6 封裝移轉至 App-V 5.1
author: dansimp
ms.assetid: 19da3776-5ebe-41e1-9890-12b84ef3c1c7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: e2166b0f280153ad62709b21bb3477d0c4277fcd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800451"
---
# 如何為特定使用者，將擴充點從 App-V 4.6 封裝移轉至 App-V 5.1


使用下列程式，以使用使用者設定檔來遷移使用 App-v 建立的套件。

**記事** 這個程式假設您執行的是最新版本的 App-V 4.6。

**若要轉換套件**

1. 找出您要轉換之套件的使用者設定檔。 若要設定原則，請在**userConfiguration**區段中執行下列更新： **ManagingAuthority TakeoverExtensionPointsFrom46 = "true" PACKAGENAME = &lt; Package ID &gt; **。

   以下是使用者設定檔的範例：

   &lt;？ xml 版本 = "1.0"？&gt;

   &lt;UserConfiguration PackageId = &lt; PACKAGE ID &gt; DisplayName DisplayName = &lt; 套件的名稱&gt;

   xmlns = " <https://schemas.microsoft.com/appv/2010/userconfiguration"&gt> ; &lt;ManagingAuthority TakeoverExtensionPointsFrom46 = "true"

   PackageName = &lt; 封裝識別碼&gt;

   &lt;/UserConfiguration&gt;

2. 若要新增 App-v 5.1 套件，請在提升的 PowerShell 命令提示字元視窗中輸入下列內容：

   PS &gt; **$Pkg = Add-AppvClientPackage-** &lt; 指向套件位置的路徑路徑&gt;

   PS &gt; **-AppVClientPackage $Pkg-DynamicUserConfiguration** &lt; Path 到使用者設定檔&gt;

3. 立即使用 FTAs 或快速鍵開啟應用程式。 應用程式應該使用 App-v 5.1 來開啟。

   App-v 4.6 套件與已轉換的 app-v 5.1 套件會發佈給使用者，但應用程式的 FTAs 及快速鍵是由 App-v 5.1 套件所假設。

   您**有應用程式-V 的建議**嗎？ 在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。 **有應用程式-V 問題嗎？** 使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相關主題


[App-V 5.1 作業](operations-for-app-v-51.md)

[如何為特定使用者，將擴充點從 App-V 5.1 封裝移轉至 App-V 4.6 封裝](how-to-revert-extension-points-from-an-app-v-51-package-to-an-app-v-46-package-for-a-specific-user.md)

 

 





