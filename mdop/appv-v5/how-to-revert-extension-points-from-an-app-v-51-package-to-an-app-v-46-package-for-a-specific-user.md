---
title: 如何為特定使用者，將擴充點從 App-V 5.1 封裝移轉至 App-V 4.6 封裝
description: 如何為特定使用者，將擴充點從 App-V 5.1 封裝移轉至 App-V 4.6 封裝
author: dansimp
ms.assetid: bd53c5d6-7fd2-4816-b03b-d59da0a35819
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: a69d6fb5b180161f39aa89e03b52227f32ce4879
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800417"
---
# <span data-ttu-id="54702-103">如何為特定使用者，將擴充點從 App-V 5.1 封裝移轉至 App-V 4.6 封裝</span><span class="sxs-lookup"><span data-stu-id="54702-103">How to Revert Extension Points From an App-V 5.1 Package to an App-V 4.6 Package for a Specific User</span></span>


<span data-ttu-id="54702-104">使用下列程式可使用使用者設定檔，將 App-v 5.1 套件復原為 App-v 檔案格式。</span><span class="sxs-lookup"><span data-stu-id="54702-104">Use the following procedure to revert an App-V 5.1 package to the App-V file format using the user configuration file.</span></span>

**<span data-ttu-id="54702-105">若要還原套件</span><span class="sxs-lookup"><span data-stu-id="54702-105">To revert a package</span></span>**

1.  <span data-ttu-id="54702-106">確保將 App-v 4.6 套件發佈給使用者，但 FTAs 和快速鍵是由 App-v 5.1 套件所假設，使用下列的遷移方法，[如何將應用程式 v 4.6 套件中的延伸點遷移到適用于特定使用者的 app-v 5.1](how-to-migrate-extension-points-from-an-app-v-46-package-to-app-v-51-for-a-specific-user.md)。</span><span class="sxs-lookup"><span data-stu-id="54702-106">Ensure that App-V 4.6 package is published to the users but the FTAs and shortcuts have been assumed by App-V 5.1 package using the following migration method, [How to Migrate Extension Points From an App-V 4.6 Package to App-V 5.1 for a Specific User](how-to-migrate-extension-points-from-an-app-v-46-package-to-app-v-51-for-a-specific-user.md).</span></span>

    <span data-ttu-id="54702-107">在已轉換套件的部署設定檔的 [ **userConfiguration** ] 區段中，若要設定原則，請對**userConfiguration**區段進行下列更新： \*\*ManagingAuthority TakeoverExtensionPointsFrom46 = "FALSE" PackageName = &lt; 封裝識別碼 &gt; \*\*</span><span class="sxs-lookup"><span data-stu-id="54702-107">In the **userConfiguration** section of the deployment configuration file for the converted package, to set the policy, make the following update to the **userConfiguration** section: **ManagingAuthority TakeoverExtensionPointsFrom46="false" PackageName=&lt;Package ID&gt;**</span></span>

2.  <span data-ttu-id="54702-108">從提升許可權的命令提示字元輸入：</span><span class="sxs-lookup"><span data-stu-id="54702-108">From an elevated command prompt, type:</span></span>

    <span data-ttu-id="54702-109">PS &gt; **發佈-AppVClientPackage $Pkg – DynamicUserConfigurationPath** &lt; 到使用者設定檔的路徑&gt;</span><span class="sxs-lookup"><span data-stu-id="54702-109">PS&gt;**Publish-AppVClientPackage $pkg –DynamicUserConfigurationPath** &lt;path to user configuration file&gt;</span></span>

3.  <span data-ttu-id="54702-110">執行發佈重新整理，或等候 App-V 4.6 的下一個排程發佈更新。</span><span class="sxs-lookup"><span data-stu-id="54702-110">Perform a publishing refresh, or wait for the next scheduled publishing refresh for the App-V 4.6.</span></span> <span data-ttu-id="54702-111">使用 FTAs 或快速鍵開啟應用程式。</span><span class="sxs-lookup"><span data-stu-id="54702-111">Open the application using FTAs or shortcuts.</span></span> <span data-ttu-id="54702-112">應用程式現在應該會使用 App-v 4.6 開啟。</span><span class="sxs-lookup"><span data-stu-id="54702-112">The Application should now open using App-V 4.6.</span></span>

    **<span data-ttu-id="54702-113">注意</span><span class="sxs-lookup"><span data-stu-id="54702-113">Note</span></span>**  
    <span data-ttu-id="54702-114">如果您不再需要 App-v 5.1 套件，您可以將 App-v 5.1 套件取消發佈，延伸點將會自動復原至 App-v 4.6。</span><span class="sxs-lookup"><span data-stu-id="54702-114">If you do not need the App-V 5.1 package anymore, you can unpublish the App-V 5.1 package and the extension points will automatically revert to App-V 4.6.</span></span>



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## <span data-ttu-id="54702-115">相關主題</span><span class="sxs-lookup"><span data-stu-id="54702-115">Related topics</span></span>


[<span data-ttu-id="54702-116">App-V 5.1 作業</span><span class="sxs-lookup"><span data-stu-id="54702-116">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)









