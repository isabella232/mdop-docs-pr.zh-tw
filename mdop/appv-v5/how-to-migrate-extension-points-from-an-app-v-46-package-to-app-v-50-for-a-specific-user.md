---
title: 如何為特定使用者，將擴充點從 App-V 4.6 封裝移轉至 App-V 5.0
description: 如何為特定使用者，將擴充點從 App-V 4.6 封裝移轉至 App-V 5.0
ms.assetid: dad25992-3c75-4b7d-b4c6-c2edf43baaea
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: a17d9dad11092a4c8356983b70bea3c18da1be04
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800453"
---
# <span data-ttu-id="dc88c-103">如何為特定使用者，將擴充點從 App-V 4.6 封裝移轉至 App-V 5.0</span><span class="sxs-lookup"><span data-stu-id="dc88c-103">How to Migrate Extension Points From an App-V 4.6 Package to App-V 5.0 for a Specific User</span></span>

<span data-ttu-id="dc88c-104">*注意：*\* App-V 4.6 已退出主流支援。</span><span class="sxs-lookup"><span data-stu-id="dc88c-104">*Note:*\* App-V 4.6 has exited Mainstream support.</span></span>

<span data-ttu-id="dc88c-105">使用下列程式，以使用使用者設定檔來遷移使用 App-v 建立的套件。</span><span class="sxs-lookup"><span data-stu-id="dc88c-105">Use the following procedure to migrate packages created with App-V using the user configuration file.</span></span>

**<span data-ttu-id="dc88c-106">若要轉換套件</span><span class="sxs-lookup"><span data-stu-id="dc88c-106">To convert a package</span></span>**

1. <span data-ttu-id="dc88c-107">找出您要轉換之套件的使用者設定檔。</span><span class="sxs-lookup"><span data-stu-id="dc88c-107">Locate the user configuration file for the package you want to convert.</span></span> <span data-ttu-id="dc88c-108">若要設定原則，請在**userConfiguration**區段中執行下列更新： \*\*ManagingAuthority TakeoverExtensionPointsFrom46 = "true" PACKAGENAME = &lt; Package ID &gt; \*\*。</span><span class="sxs-lookup"><span data-stu-id="dc88c-108">To set the policy, perform the following updates in the **userConfiguration** section: **ManagingAuthority TakeoverExtensionPointsFrom46="true" PackageName=&lt;Package ID&gt;**.</span></span>

   <span data-ttu-id="dc88c-109">以下是使用者設定檔的範例：</span><span class="sxs-lookup"><span data-stu-id="dc88c-109">The following is an example of a user configuration file:</span></span>

   <span data-ttu-id="dc88c-110">&lt;？ xml 版本 = "1.0"？&gt;</span><span class="sxs-lookup"><span data-stu-id="dc88c-110">&lt;?xml version="1.0" ?&gt;</span></span>

   <span data-ttu-id="dc88c-111">&lt;UserConfiguration PackageId = &lt; PACKAGE ID &gt; DisplayName DisplayName = &lt; 套件的名稱&gt;</span><span class="sxs-lookup"><span data-stu-id="dc88c-111">&lt;UserConfiguration PackageId=&lt;Package ID&gt; DisplayName=&lt;Name of the Package&gt;</span></span>

   <span data-ttu-id="dc88c-112">xmlns = " <https://schemas.microsoft.com/appv/2010/userconfiguration"&gt> ; &lt;ManagingAuthority TakeoverExtensionPointsFrom46 = "true"</span><span class="sxs-lookup"><span data-stu-id="dc88c-112">xmlns="<https://schemas.microsoft.com/appv/2010/userconfiguration"&gt>; &lt;ManagingAuthority TakeoverExtensionPointsFrom46="true"</span></span>

   <span data-ttu-id="dc88c-113">PackageName = &lt; 封裝識別碼&gt;</span><span class="sxs-lookup"><span data-stu-id="dc88c-113">PackageName=&lt;Package ID&gt;</span></span>

   <span data-ttu-id="dc88c-114">&lt;/UserConfiguration&gt;</span><span class="sxs-lookup"><span data-stu-id="dc88c-114">&lt;/UserConfiguration&gt;</span></span>

2. <span data-ttu-id="dc88c-115">若要新增 App-V 5.0 套件，請在提升的 PowerShell 命令提示字元中輸入下列專案：</span><span class="sxs-lookup"><span data-stu-id="dc88c-115">To add the App-V 5.0 package type the following in an elevated PowerShell command prompt:</span></span>

   <span data-ttu-id="dc88c-116">PS &gt; **$Pkg = Add-AppvClientPackage-** &lt; 指向套件位置的路徑路徑&gt;</span><span class="sxs-lookup"><span data-stu-id="dc88c-116">PS&gt;**$pkg= Add-AppvClientPackage –Path** &lt;Path to package location&gt;</span></span>

   <span data-ttu-id="dc88c-117">PS &gt; **-AppVClientPackage $Pkg-DynamicUserConfiguration** &lt; Path 到使用者設定檔&gt;</span><span class="sxs-lookup"><span data-stu-id="dc88c-117">PS&gt;**Publish-AppVClientPackage $pkg -DynamicUserConfiguration** &lt;Path to the user configuration file&gt;</span></span>

3. <span data-ttu-id="dc88c-118">立即使用 FTAs 或快速鍵開啟應用程式。</span><span class="sxs-lookup"><span data-stu-id="dc88c-118">Open the application using FTAs or shortcuts now.</span></span> <span data-ttu-id="dc88c-119">應用程式應該使用 App-v 5.0 來開啟。</span><span class="sxs-lookup"><span data-stu-id="dc88c-119">The application should open using App-V 5.0.</span></span>

   <span data-ttu-id="dc88c-120">App-V SP2 套件與已轉換的 app-v 5.0 套件會發佈給使用者，但應用程式的 FTAs 和快速鍵都是由 App-v 5.0 套件所採用。</span><span class="sxs-lookup"><span data-stu-id="dc88c-120">The App-V SP2 package and the converted App-V 5.0 package are published to the user, but the FTAs and shortcuts for the applications have been assumed by the App-V 5.0 package.</span></span>

   <span data-ttu-id="dc88c-121">您**有應用程式-V 的建議**嗎？</span><span class="sxs-lookup"><span data-stu-id="dc88c-121">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="dc88c-122">在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="dc88c-122">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="dc88c-123">有應用程式-V 問題嗎？</span><span class="sxs-lookup"><span data-stu-id="dc88c-123">Got an App-V issue?</span></span>** <span data-ttu-id="dc88c-124">使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="dc88c-124">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="dc88c-125">相關主題</span><span class="sxs-lookup"><span data-stu-id="dc88c-125">Related topics</span></span>


[<span data-ttu-id="dc88c-126">App-V 5.0 作業</span><span class="sxs-lookup"><span data-stu-id="dc88c-126">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

 

 





