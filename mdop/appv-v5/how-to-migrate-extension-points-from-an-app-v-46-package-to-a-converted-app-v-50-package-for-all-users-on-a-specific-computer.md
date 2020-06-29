---
title: 如何為特定電腦上的所有使用者，將擴充點從 App-V 4.6 封裝移轉至轉換的 App-V 5.0 封裝
description: 如何為特定電腦上的所有使用者，將擴充點從 App-V 4.6 封裝移轉至轉換的 App-V 5.0 封裝
ms.assetid: 3ae9996f-71d9-4ca1-9aab-25b599158e55
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: 3c53104907448edeb894cf4eb9dbb0a24d3229e4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800455"
---
# <span data-ttu-id="ba3a8-103">如何為特定電腦上的所有使用者，將擴充點從 App-V 4.6 封裝移轉至轉換的 App-V 5.0 封裝</span><span class="sxs-lookup"><span data-stu-id="ba3a8-103">How to Migrate Extension Points From an App-V 4.6 Package to a Converted App-V 5.0 Package for All Users on a Specific Computer</span></span>

<span data-ttu-id="ba3a8-104">**注意：** App-V 4.6 已退出主流支援。</span><span class="sxs-lookup"><span data-stu-id="ba3a8-104">**Note:** App-V 4.6 has exited Mainstream support.</span></span>

<span data-ttu-id="ba3a8-105">使用下列程式，將應用程式-V 4.6 套件中的延伸點移到使用部署設定檔的 App-v 5.0 套件中。</span><span class="sxs-lookup"><span data-stu-id="ba3a8-105">Use the following procedure to migrate extension points from an App-V4.6package to a App-V 5.0 package using the deployment configuration file.</span></span>

<span data-ttu-id="ba3a8-106">**記事** 下列程式不需要 App-v 5.0 管理伺服器。</span><span class="sxs-lookup"><span data-stu-id="ba3a8-106">**Note** The following procedure does not require an App-V 5.0 management server.</span></span>

 

**<span data-ttu-id="ba3a8-107">使用部署設定檔，將來自 App-v 4.6 套件之套件中的延伸點遷移到已轉換的應用程式 V 5.0 套件</span><span class="sxs-lookup"><span data-stu-id="ba3a8-107">To migrate extension points from a package from an App-V4.6 package to a converted App-V 5.0 package using the deployment configuration file</span></span>**

1. <span data-ttu-id="ba3a8-108">找出包含您要遷移之套件之部署設定檔的目錄。</span><span class="sxs-lookup"><span data-stu-id="ba3a8-108">Locate the directory that contains the deployment configuration file for the package you want to migrate.</span></span> <span data-ttu-id="ba3a8-109">若要設定原則，請對**userConfiguration**區段進行下列更新：</span><span class="sxs-lookup"><span data-stu-id="ba3a8-109">To set the policy, make the following update to the **userConfiguration** section:</span></span>

   **<span data-ttu-id="ba3a8-110">ManagingAuthority TakeoverExtensionPointsFrom46 = "true" PackageName = &lt; PACKAGE ID&gt;</span><span class="sxs-lookup"><span data-stu-id="ba3a8-110">ManagingAuthority TakeoverExtensionPointsFrom46="true" PackageName=&lt;Package ID&gt;</span></span>**

   <span data-ttu-id="ba3a8-111">以下是部署設定檔中的內容範例：</span><span class="sxs-lookup"><span data-stu-id="ba3a8-111">The following is an example of content from a deployment configuration file:</span></span>

   <span data-ttu-id="ba3a8-112">&lt;？ xml 版本 = "1.0"？&gt;</span><span class="sxs-lookup"><span data-stu-id="ba3a8-112">&lt;?xml version="1.0" ?&gt;</span></span>

   <span data-ttu-id="ba3a8-113">&lt;DeploymentConfiguration</span><span class="sxs-lookup"><span data-stu-id="ba3a8-113">&lt;DeploymentConfiguration</span></span>

   <span data-ttu-id="ba3a8-114">xmlns = " <https://schemas.microsoft.com/appv/2010/deploymentconfiguration> " PackageId = &lt; Package ID &gt; DisplayName DisplayName = &lt; 顯示名稱&gt;</span><span class="sxs-lookup"><span data-stu-id="ba3a8-114">xmlns="<https://schemas.microsoft.com/appv/2010/deploymentconfiguration>" PackageId=&lt;Package ID&gt; DisplayName=&lt;Display Name&gt;</span></span>

   <span data-ttu-id="ba3a8-115">&lt;MachineConfiguration/&gt;</span><span class="sxs-lookup"><span data-stu-id="ba3a8-115">&lt;MachineConfiguration/&gt;</span></span>

   <span data-ttu-id="ba3a8-116">&lt;UserConfiguration&gt;</span><span class="sxs-lookup"><span data-stu-id="ba3a8-116">&lt;UserConfiguration&gt;</span></span>

   <span data-ttu-id="ba3a8-117">&lt;ManagingAuthority TakeoverExtensionPointsFrom46 = "true"</span><span class="sxs-lookup"><span data-stu-id="ba3a8-117">&lt;ManagingAuthority TakeoverExtensionPointsFrom46="true"</span></span>

   <span data-ttu-id="ba3a8-118">PackageName = &lt; 封裝識別碼&gt;</span><span class="sxs-lookup"><span data-stu-id="ba3a8-118">PackageName=&lt;Package ID&gt;</span></span>

   <span data-ttu-id="ba3a8-119">&lt;/UserConfiguration&gt;</span><span class="sxs-lookup"><span data-stu-id="ba3a8-119">&lt;/UserConfiguration&gt;</span></span>

   <span data-ttu-id="ba3a8-120">&lt;/DeploymentConfiguration&gt;</span><span class="sxs-lookup"><span data-stu-id="ba3a8-120">&lt;/DeploymentConfiguration&gt;</span></span>

2. <span data-ttu-id="ba3a8-121">若要新增 App-v 5.0 套件，請在提升許可權的 PowerShell 命令提示字元中輸入：</span><span class="sxs-lookup"><span data-stu-id="ba3a8-121">To add the App-V 5.0 package, in an elevated PowerShell command prompt type:</span></span>

   <span data-ttu-id="ba3a8-122">PS &gt; **$pkg = Add-AppvClientPackage** **–** &lt; 到套件位置的路徑路徑至 &gt;  - **DynamicDeploymentConfiguration** &lt; 部署設定檔的路徑&gt;</span><span class="sxs-lookup"><span data-stu-id="ba3a8-122">PS&gt;**$pkg= Add-AppvClientPackage** **–Path** &lt;Path to package location&gt; -**DynamicDeploymentConfiguration** &lt;Path to the deployment configuration file&gt;</span></span>

   <span data-ttu-id="ba3a8-123">PS &gt; **發佈-AppVClientPackage $pkg**</span><span class="sxs-lookup"><span data-stu-id="ba3a8-123">PS&gt;**Publish-AppVClientPackage $pkg**</span></span>

3. <span data-ttu-id="ba3a8-124">若要測試遷移，請使用相關聯的 FTAs 或快速鍵開啟虛擬應用程式。</span><span class="sxs-lookup"><span data-stu-id="ba3a8-124">To test the migration, open the virtual application using associated FTAs or shortcuts.</span></span> <span data-ttu-id="ba3a8-125">應用程式隨即開啟，並會出現 App-v 5.0。</span><span class="sxs-lookup"><span data-stu-id="ba3a8-125">The application opens with App-V 5.0.</span></span> <span data-ttu-id="ba3a8-126">在這兩者中，App-v 4.6 套件與已轉換的 app-v 5.0 套件都會發佈給使用者，但應用程式的 FTAs 和快速鍵都是由 App-v 5.0 套件所採用。</span><span class="sxs-lookup"><span data-stu-id="ba3a8-126">Both, the App-V 4.6 package and the converted App-V 5.0 package are published to the user, but the FTAs and shortcuts for the applications have been assumed by the App-V 5.0 package.</span></span>

   <span data-ttu-id="ba3a8-127">您**有應用程式-V 的建議**嗎？</span><span class="sxs-lookup"><span data-stu-id="ba3a8-127">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="ba3a8-128">在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="ba3a8-128">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="ba3a8-129">有應用程式-V 問題嗎？</span><span class="sxs-lookup"><span data-stu-id="ba3a8-129">Got an App-V issue?</span></span>** <span data-ttu-id="ba3a8-130">使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="ba3a8-130">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="ba3a8-131">相關主題</span><span class="sxs-lookup"><span data-stu-id="ba3a8-131">Related topics</span></span>


[<span data-ttu-id="ba3a8-132">如何為特定電腦上的所有使用者，將擴充點從 App-V 5.0 封裝移轉至 App-V 4.6 封裝</span><span class="sxs-lookup"><span data-stu-id="ba3a8-132">How to Revert Extension Points from an App-V 5.0 Package to an App-V 4.6 Package For All Users on a Specific Computer</span></span>](how-to-revert-extension-points-from-an-app-v-50-package-to-an-app-v-46-package-for-all-users-on-a-specific-computer.md)

[<span data-ttu-id="ba3a8-133">App-V 5.0 作業</span><span class="sxs-lookup"><span data-stu-id="ba3a8-133">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

 

 





