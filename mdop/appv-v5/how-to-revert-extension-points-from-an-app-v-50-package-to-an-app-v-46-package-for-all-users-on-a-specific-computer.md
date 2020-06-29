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
# <span data-ttu-id="10a2e-103">如何為特定電腦上的所有使用者，將擴充點從 App-V 5.0 封裝移轉至 App-V 4.6 封裝</span><span class="sxs-lookup"><span data-stu-id="10a2e-103">How to Revert Extension Points from an App-V 5.0 Package to an App-V 4.6 Package For All Users on a Specific Computer</span></span>

<span data-ttu-id="10a2e-104">*注意：*\* App-V 4.6 已退出主流支援。</span><span class="sxs-lookup"><span data-stu-id="10a2e-104">*Note:*\* App-V 4.6 has exited Mainstream support.</span></span> <span data-ttu-id="10a2e-105">下列假設已安裝 app-v 4.6 SP3 用戶端。</span><span class="sxs-lookup"><span data-stu-id="10a2e-105">The following assumes that the App-V 4.6 SP3 client is already installed.</span></span>

<span data-ttu-id="10a2e-106">使用下列程式會使用部署設定檔，將 App V 5.0 套件中的延伸點復原至 App-v 4.6 檔案格式。</span><span class="sxs-lookup"><span data-stu-id="10a2e-106">Use the following procedure to revert extension points from an App-V 5.0 package to the App-V 4.6 file format using the deployment configuration file.</span></span>

**<span data-ttu-id="10a2e-107">若要還原套件</span><span class="sxs-lookup"><span data-stu-id="10a2e-107">To revert a package</span></span>**

1.  <span data-ttu-id="10a2e-108">確保將 App-v 4.6 套件發佈給使用者，但 FTAs 和快速鍵是由 App-v 5.0 套件（使用下列遷移方法），[如何將應用程式 v 4.6 套件中的延伸點遷移到針對特定電腦上的所有使用者所轉換的 app-v 5.0 套件中](how-to-migrate-extension-points-from-an-app-v-46-package-to-a-converted-app-v-50-package-for-all-users-on-a-specific-computer.md)。</span><span class="sxs-lookup"><span data-stu-id="10a2e-108">Ensure that App-V 4.6 package is published to the users but the FTAs and shortcuts have been assumed by App-V 5.0 package using the following migration method, [How to Migrate Extension Points From an App-V 4.6 Package to a Converted App-V 5.0 Package for All Users on a Specific Computer](how-to-migrate-extension-points-from-an-app-v-46-package-to-a-converted-app-v-50-package-for-all-users-on-a-specific-computer.md).</span></span>

    <span data-ttu-id="10a2e-109">在已轉換套件的部署設定檔的 [ **userConfiguration** ] 區段中，若要設定原則，請對**userConfiguration**區段進行下列更新： \*\*ManagingAuthority TakeoverExtensionPointsFrom46 = "FALSE" PackageName = &lt; 封裝識別碼 &gt; \*\*</span><span class="sxs-lookup"><span data-stu-id="10a2e-109">In the **userConfiguration** section of the deployment configuration file for the converted package, to set the policy, make the following update to the **userConfiguration** section: **ManagingAuthority TakeoverExtensionPointsFrom46="false" PackageName=&lt;Package ID&gt;**</span></span>

2.  <span data-ttu-id="10a2e-110">從提升許可權的命令提示字元輸入：</span><span class="sxs-lookup"><span data-stu-id="10a2e-110">From an elevated command prompt, type:</span></span>

    <span data-ttu-id="10a2e-111">PS &gt; **設定-AppvClientPackage $Pkg – DynamicDeploymentConfiguration** &lt; 到部署設定檔的路徑&gt;</span><span class="sxs-lookup"><span data-stu-id="10a2e-111">PS&gt;**Set-AppvClientPackage $pkg –DynamicDeploymentConfiguration** &lt;path to deployment configuration file&gt;</span></span>

    <span data-ttu-id="10a2e-112">PS &gt; **發佈-AppVClientPackage $Pkg – DynamicUserConfigurationType useDeploymentConfiguration**</span><span class="sxs-lookup"><span data-stu-id="10a2e-112">PS&gt;**Publish-AppVClientPackage $pkg –DynamicUserConfigurationType useDeploymentConfiguration**</span></span>

3.  <span data-ttu-id="10a2e-113">執行發佈重新整理，或等候 App-V 4.6 SP2 封裝的下一次排程發佈更新。</span><span class="sxs-lookup"><span data-stu-id="10a2e-113">Perform a publishing refresh, or wait for the next scheduled publishing refresh for the App-V 4.6 SP2 package.</span></span>

    <span data-ttu-id="10a2e-114">使用 FTAs 或快速鍵開啟應用程式。</span><span class="sxs-lookup"><span data-stu-id="10a2e-114">Open the application using FTAs or shortcuts.</span></span> <span data-ttu-id="10a2e-115">應用程式現在應該會使用 App-v 4.6 開啟。</span><span class="sxs-lookup"><span data-stu-id="10a2e-115">The Application should now open using App-V 4.6.</span></span>

    **<span data-ttu-id="10a2e-116">注意</span><span class="sxs-lookup"><span data-stu-id="10a2e-116">Note</span></span>**  
    <span data-ttu-id="10a2e-117">如果您不再需要 App-v 5.0 套件，您可以將 App-v 5.0 套件取消發佈，延伸點將會自動復原至 App-v 4.6。</span><span class="sxs-lookup"><span data-stu-id="10a2e-117">If you do not need the App-V 5.0 package anymore, you can unpublish the App-V 5.0 package and the extension points will automatically revert to App-V 4.6.</span></span>



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## <span data-ttu-id="10a2e-118">相關主題</span><span class="sxs-lookup"><span data-stu-id="10a2e-118">Related topics</span></span>


[<span data-ttu-id="10a2e-119">App-V 5.0 作業</span><span class="sxs-lookup"><span data-stu-id="10a2e-119">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)









