---
title: 如何為特定電腦上的所有使用者，將擴充點從 App-V 5.1 封裝移轉至 App-V 4.6 封裝
description: 如何為特定電腦上的所有使用者，將擴充點從 App-V 5.1 封裝移轉至 App-V 4.6 封裝
author: dansimp
ms.assetid: 64640b8e-de6b-4006-a33e-353d285af15e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: ce8d5cc0e79be46fd9680a3bea0236bbeb93ea83
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800415"
---
# <span data-ttu-id="97b2e-103">如何為特定電腦上的所有使用者，將擴充點從 App-V 5.1 封裝移轉至 App-V 4.6 封裝</span><span class="sxs-lookup"><span data-stu-id="97b2e-103">How to Revert Extension Points from an App-V 5.1 Package to an App-V 4.6 Package For All Users on a Specific Computer</span></span>


<span data-ttu-id="97b2e-104">使用下列程式會使用部署設定檔，將 App V 5.1 套件中的延伸點復原至 App-v 4.6 檔案格式。</span><span class="sxs-lookup"><span data-stu-id="97b2e-104">Use the following procedure to revert extension points from an App-V 5.1 package to the App-V 4.6 file format using the deployment configuration file.</span></span>

**<span data-ttu-id="97b2e-105">若要還原套件</span><span class="sxs-lookup"><span data-stu-id="97b2e-105">To revert a package</span></span>**

1.  <span data-ttu-id="97b2e-106">確保將 App-v 4.6 套件發佈給使用者，但 FTAs 和快速鍵是由 App-v 5.1 套件（使用下列遷移方法），[如何將應用程式 v 4.6 套件中的延伸點遷移到針對特定電腦上的所有使用者所轉換的 app-v 5.1 套件中](how-to-migrate-extension-points-from-an-app-v-46-package-to-a-converted-app-v-51-package-for-all-users-on-a-specific-computer.md)。</span><span class="sxs-lookup"><span data-stu-id="97b2e-106">Ensure that App-V 4.6 package is published to the users but the FTAs and shortcuts have been assumed by App-V 5.1 package using the following migration method, [How to Migrate Extension Points From an App-V 4.6 Package to a Converted App-V 5.1 Package for All Users on a Specific Computer](how-to-migrate-extension-points-from-an-app-v-46-package-to-a-converted-app-v-51-package-for-all-users-on-a-specific-computer.md).</span></span>

    <span data-ttu-id="97b2e-107">在已轉換套件的部署設定檔的 [ **userConfiguration** ] 區段中，若要設定原則，請對**userConfiguration**區段進行下列更新： \*\*ManagingAuthority TakeoverExtensionPointsFrom46 = "FALSE" PackageName = &lt; 封裝識別碼 &gt; \*\*</span><span class="sxs-lookup"><span data-stu-id="97b2e-107">In the **userConfiguration** section of the deployment configuration file for the converted package, to set the policy, make the following update to the **userConfiguration** section: **ManagingAuthority TakeoverExtensionPointsFrom46="false" PackageName=&lt;Package ID&gt;**</span></span>

2.  <span data-ttu-id="97b2e-108">從提升許可權的命令提示字元輸入：</span><span class="sxs-lookup"><span data-stu-id="97b2e-108">From an elevated command prompt, type:</span></span>

    <span data-ttu-id="97b2e-109">PS &gt; **設定-AppvClientPackage $Pkg – DynamicDeploymentConfiguration** &lt; 到部署設定檔的路徑&gt;</span><span class="sxs-lookup"><span data-stu-id="97b2e-109">PS&gt;**Set-AppvClientPackage $pkg –DynamicDeploymentConfiguration** &lt;path to deployment configuration file&gt;</span></span>

    <span data-ttu-id="97b2e-110">PS &gt; **發佈-AppVClientPackage $Pkg – DynamicUserConfigurationType useDeploymentConfiguration**</span><span class="sxs-lookup"><span data-stu-id="97b2e-110">PS&gt;**Publish-AppVClientPackage $pkg –DynamicUserConfigurationType useDeploymentConfiguration**</span></span>

3.  <span data-ttu-id="97b2e-111">執行發佈重新整理，或等候 App-V 4.6 套件的下一個排程發佈更新。</span><span class="sxs-lookup"><span data-stu-id="97b2e-111">Perform a publishing refresh, or wait for the next scheduled publishing refresh for the App-V 4.6 package.</span></span>

    <span data-ttu-id="97b2e-112">使用 FTAs 或快速鍵開啟應用程式。</span><span class="sxs-lookup"><span data-stu-id="97b2e-112">Open the application using FTAs or shortcuts.</span></span> <span data-ttu-id="97b2e-113">應用程式現在應該會使用 App-v 4.6 開啟。</span><span class="sxs-lookup"><span data-stu-id="97b2e-113">The Application should now open using App-V 4.6.</span></span>

    **<span data-ttu-id="97b2e-114">注意</span><span class="sxs-lookup"><span data-stu-id="97b2e-114">Note</span></span>**  
    <span data-ttu-id="97b2e-115">如果您不再需要 App-v 5.1 套件，您可以將 App-v 5.1 套件取消發佈，延伸點將會自動復原至 App-v 4.6。</span><span class="sxs-lookup"><span data-stu-id="97b2e-115">If you do not need the App-V 5.1 package anymore, you can unpublish the App-V 5.1 package and the extension points will automatically revert to App-V 4.6.</span></span>



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## <span data-ttu-id="97b2e-116">相關主題</span><span class="sxs-lookup"><span data-stu-id="97b2e-116">Related topics</span></span>


[<span data-ttu-id="97b2e-117">App-V 5.1 作業</span><span class="sxs-lookup"><span data-stu-id="97b2e-117">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)









