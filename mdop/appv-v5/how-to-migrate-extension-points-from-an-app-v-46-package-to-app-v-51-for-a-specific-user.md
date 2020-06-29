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
# <span data-ttu-id="ee9e8-103">如何為特定使用者，將擴充點從 App-V 4.6 封裝移轉至 App-V 5.1</span><span class="sxs-lookup"><span data-stu-id="ee9e8-103">How to Migrate Extension Points From an App-V 4.6 Package to App-V 5.1 for a Specific User</span></span>


<span data-ttu-id="ee9e8-104">使用下列程式，以使用使用者設定檔來遷移使用 App-v 建立的套件。</span><span class="sxs-lookup"><span data-stu-id="ee9e8-104">Use the following procedure to migrate packages created with App-V using the user configuration file.</span></span>

<span data-ttu-id="ee9e8-105">**記事** 這個程式假設您執行的是最新版本的 App-V 4.6。</span><span class="sxs-lookup"><span data-stu-id="ee9e8-105">**Note** This procedure assumes that you are running the latest version of App-V 4.6.</span></span>

**<span data-ttu-id="ee9e8-106">若要轉換套件</span><span class="sxs-lookup"><span data-stu-id="ee9e8-106">To convert a package</span></span>**

1. <span data-ttu-id="ee9e8-107">找出您要轉換之套件的使用者設定檔。</span><span class="sxs-lookup"><span data-stu-id="ee9e8-107">Locate the user configuration file for the package you want to convert.</span></span> <span data-ttu-id="ee9e8-108">若要設定原則，請在**userConfiguration**區段中執行下列更新： \*\*ManagingAuthority TakeoverExtensionPointsFrom46 = "true" PACKAGENAME = &lt; Package ID &gt; \*\*。</span><span class="sxs-lookup"><span data-stu-id="ee9e8-108">To set the policy, perform the following updates in the **userConfiguration** section: **ManagingAuthority TakeoverExtensionPointsFrom46="true" PackageName=&lt;Package ID&gt;**.</span></span>

   <span data-ttu-id="ee9e8-109">以下是使用者設定檔的範例：</span><span class="sxs-lookup"><span data-stu-id="ee9e8-109">The following is an example of a user configuration file:</span></span>

   <span data-ttu-id="ee9e8-110">&lt;？ xml 版本 = "1.0"？&gt;</span><span class="sxs-lookup"><span data-stu-id="ee9e8-110">&lt;?xml version="1.0" ?&gt;</span></span>

   <span data-ttu-id="ee9e8-111">&lt;UserConfiguration PackageId = &lt; PACKAGE ID &gt; DisplayName DisplayName = &lt; 套件的名稱&gt;</span><span class="sxs-lookup"><span data-stu-id="ee9e8-111">&lt;UserConfiguration PackageId=&lt;Package ID&gt; DisplayName=&lt;Name of the Package&gt;</span></span>

   <span data-ttu-id="ee9e8-112">xmlns = " <https://schemas.microsoft.com/appv/2010/userconfiguration"&gt> ; &lt;ManagingAuthority TakeoverExtensionPointsFrom46 = "true"</span><span class="sxs-lookup"><span data-stu-id="ee9e8-112">xmlns="<https://schemas.microsoft.com/appv/2010/userconfiguration"&gt>; &lt;ManagingAuthority TakeoverExtensionPointsFrom46="true"</span></span>

   <span data-ttu-id="ee9e8-113">PackageName = &lt; 封裝識別碼&gt;</span><span class="sxs-lookup"><span data-stu-id="ee9e8-113">PackageName=&lt;Package ID&gt;</span></span>

   <span data-ttu-id="ee9e8-114">&lt;/UserConfiguration&gt;</span><span class="sxs-lookup"><span data-stu-id="ee9e8-114">&lt;/UserConfiguration&gt;</span></span>

2. <span data-ttu-id="ee9e8-115">若要新增 App-v 5.1 套件，請在提升的 PowerShell 命令提示字元視窗中輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="ee9e8-115">To add the App-V 5.1 package, type the following in an elevated PowerShell command prompt window:</span></span>

   <span data-ttu-id="ee9e8-116">PS &gt; **$Pkg = Add-AppvClientPackage-** &lt; 指向套件位置的路徑路徑&gt;</span><span class="sxs-lookup"><span data-stu-id="ee9e8-116">PS&gt;**$pkg= Add-AppvClientPackage –Path** &lt;Path to package location&gt;</span></span>

   <span data-ttu-id="ee9e8-117">PS &gt; **-AppVClientPackage $Pkg-DynamicUserConfiguration** &lt; Path 到使用者設定檔&gt;</span><span class="sxs-lookup"><span data-stu-id="ee9e8-117">PS&gt;**Publish-AppVClientPackage $pkg -DynamicUserConfiguration** &lt;Path to the user configuration file&gt;</span></span>

3. <span data-ttu-id="ee9e8-118">立即使用 FTAs 或快速鍵開啟應用程式。</span><span class="sxs-lookup"><span data-stu-id="ee9e8-118">Open the application using FTAs or shortcuts now.</span></span> <span data-ttu-id="ee9e8-119">應用程式應該使用 App-v 5.1 來開啟。</span><span class="sxs-lookup"><span data-stu-id="ee9e8-119">The application should open using App-V 5.1.</span></span>

   <span data-ttu-id="ee9e8-120">App-v 4.6 套件與已轉換的 app-v 5.1 套件會發佈給使用者，但應用程式的 FTAs 及快速鍵是由 App-v 5.1 套件所假設。</span><span class="sxs-lookup"><span data-stu-id="ee9e8-120">The App-V 4.6 package and the converted App-V 5.1 package are published to the user, but the FTAs and shortcuts for the applications have been assumed by the App-V 5.1 package.</span></span>

   <span data-ttu-id="ee9e8-121">您**有應用程式-V 的建議**嗎？</span><span class="sxs-lookup"><span data-stu-id="ee9e8-121">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="ee9e8-122">在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="ee9e8-122">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="ee9e8-123">有應用程式-V 問題嗎？</span><span class="sxs-lookup"><span data-stu-id="ee9e8-123">Got an App-V issue?</span></span>** <span data-ttu-id="ee9e8-124">使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="ee9e8-124">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="ee9e8-125">相關主題</span><span class="sxs-lookup"><span data-stu-id="ee9e8-125">Related topics</span></span>


[<span data-ttu-id="ee9e8-126">App-V 5.1 作業</span><span class="sxs-lookup"><span data-stu-id="ee9e8-126">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)

[<span data-ttu-id="ee9e8-127">如何為特定使用者，將擴充點從 App-V 5.1 封裝移轉至 App-V 4.6 封裝</span><span class="sxs-lookup"><span data-stu-id="ee9e8-127">How to Revert Extension Points From an App-V 5.1 Package to an App-V 4.6 Package for a Specific User</span></span>](how-to-revert-extension-points-from-an-app-v-51-package-to-an-app-v-46-package-for-a-specific-user.md)

 

 





