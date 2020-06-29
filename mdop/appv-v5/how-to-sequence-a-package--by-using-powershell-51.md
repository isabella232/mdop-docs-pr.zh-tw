---
title: 如何使用 PowerShell 對套件進行排序
description: 如何使用 PowerShell 對套件進行排序
author: dansimp
ms.assetid: 6134c6be-937d-4609-a516-92d49154b290
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e1bc2933fdb64080dab3b514784e7f68b0236df9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800407"
---
# <span data-ttu-id="a68b6-103">如何使用 PowerShell 對套件進行排序</span><span class="sxs-lookup"><span data-stu-id="a68b6-103">How to Sequence a Package by Using PowerShell</span></span>


<span data-ttu-id="a68b6-104">使用下列程式來建立使用 PowerShell 的新 App-v 5.1 套件。</span><span class="sxs-lookup"><span data-stu-id="a68b6-104">Use the following procedure to create a new App-V 5.1 package using PowerShell.</span></span>

<span data-ttu-id="a68b6-105">**記事** 在您使用此程式之前，您必須先將相關聯的安裝程式檔案複製到執行排序器的電腦，並閱讀並瞭解[app-v 5.1 排序器和用戶端部署規劃](planning-for-the-app-v-51-sequencer-and-client-deployment.md)的排序器區段。</span><span class="sxs-lookup"><span data-stu-id="a68b6-105">**Note** Before you use this procedure you must copy the associated installer files to the computer running the sequencer and you have read and understand the sequencer section of [Planning for the App-V 5.1 Sequencer and Client Deployment](planning-for-the-app-v-51-sequencer-and-client-deployment.md).</span></span>

 

**<span data-ttu-id="a68b6-106">使用 PowerShell 建立新的虛擬應用程式</span><span class="sxs-lookup"><span data-stu-id="a68b6-106">To create a new virtual application using PowerShell</span></span>**

1.  <span data-ttu-id="a68b6-107">安裝 App-v 5.1 排序器。</span><span class="sxs-lookup"><span data-stu-id="a68b6-107">Install the App-V 5.1 sequencer.</span></span> <span data-ttu-id="a68b6-108">如需有關安裝排序器的詳細資訊，請參閱[如何安裝排序](how-to-install-the-sequencer-51beta-gb18030.md)器。</span><span class="sxs-lookup"><span data-stu-id="a68b6-108">For more information about installing the sequencer see [How to Install the Sequencer](how-to-install-the-sequencer-51beta-gb18030.md).</span></span>

2.  <span data-ttu-id="a68b6-109">若要開啟 PowerShell 主控台，請按一下 [**開始**]，然後輸入**powershell**。</span><span class="sxs-lookup"><span data-stu-id="a68b6-109">To open a PowerShell console click **Start** and type **PowerShell**.</span></span> <span data-ttu-id="a68b6-110">以滑鼠右鍵按一下 **Windows PowerShell**，並選取 **\[以系統管理員身分執行\]**。</span><span class="sxs-lookup"><span data-stu-id="a68b6-110">Right-click **Windows PowerShell** and select **Run as Administrator**.</span></span>

3.  <span data-ttu-id="a68b6-111">使用 PowerShell 主控台，輸入下列內容：匯**入-模組 appvsequencer**。</span><span class="sxs-lookup"><span data-stu-id="a68b6-111">Using the PowerShell console, type the following: **import-module appvsequencer**.</span></span>

4.  <span data-ttu-id="a68b6-112">若要建立套件，請使用**AppvSequencerPackage** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a68b6-112">To create a package, use the **New-AppvSequencerPackage** cmdlet.</span></span> <span data-ttu-id="a68b6-113">建立套件需要下列參數：</span><span class="sxs-lookup"><span data-stu-id="a68b6-113">The following parameters are required to create a package:</span></span>

    -   <span data-ttu-id="a68b6-114">**Name （名稱**）-指定套件的名稱。</span><span class="sxs-lookup"><span data-stu-id="a68b6-114">**Name** - specifies the name of the package.</span></span>

    -   <span data-ttu-id="a68b6-115">**PrimaryVirtualApplicationDirectory** -指定將用來安裝應用程式的目錄路徑。</span><span class="sxs-lookup"><span data-stu-id="a68b6-115">**PrimaryVirtualApplicationDirectory** - specifies the path to the directory that will be used to install the application.</span></span> <span data-ttu-id="a68b6-116">這個路徑必須存在。</span><span class="sxs-lookup"><span data-stu-id="a68b6-116">This path must exist.</span></span>

    -   <span data-ttu-id="a68b6-117">**安裝**程式-指定關聯應用程式安裝程式的路徑。</span><span class="sxs-lookup"><span data-stu-id="a68b6-117">**Installer** - specifies the path to the associated application installer.</span></span>

    -   <span data-ttu-id="a68b6-118">**Path** -指定套件的輸出目錄。</span><span class="sxs-lookup"><span data-stu-id="a68b6-118">**Path** - specifies the output directory for the package.</span></span>

    <span data-ttu-id="a68b6-119">例如：</span><span class="sxs-lookup"><span data-stu-id="a68b6-119">For example:</span></span>

    **<span data-ttu-id="a68b6-120">新-AppvSequencerPackage- &lt; package &gt; -PrimaryVirtualApplicationDirectory 路徑的名稱， &lt; 這些路徑指向 &gt; &lt; 安裝程式可執行檔的安裝程式可執行檔 &gt; -OutputPath &lt; 目錄&gt;</span><span class="sxs-lookup"><span data-stu-id="a68b6-120">New-AppvSequencerPackage –Name &lt;name of Package&gt; -PrimaryVirtualApplicationDirectory &lt;path to the package root&gt; -Installer &lt;path to the installer executable&gt; -OutputPath &lt;directory of the output path&gt;</span></span>**

    <span data-ttu-id="a68b6-121">等待排序器建立套件。</span><span class="sxs-lookup"><span data-stu-id="a68b6-121">Wait for the sequencer to create the package.</span></span> <span data-ttu-id="a68b6-122">使用 PowerShell 建立套件可能需要一些時間。</span><span class="sxs-lookup"><span data-stu-id="a68b6-122">Creating a package using PowerShell can take time.</span></span> <span data-ttu-id="a68b6-123">如果未成功建立套件，則會傳回錯誤。</span><span class="sxs-lookup"><span data-stu-id="a68b6-123">If the package was not created successfully an error will be returned.</span></span>

    <span data-ttu-id="a68b6-124">下列清單顯示可搭配使用**AppvSequencerPackage** Cmdlet 使用的其他可選參數：</span><span class="sxs-lookup"><span data-stu-id="a68b6-124">The following list displays additional optional parameters that can be used with **New-AppvSequencerPackage** cmdlet:</span></span>

    -   <span data-ttu-id="a68b6-125">AcceleratorFilePath –指定要產生套件的加速器 .cab 檔案路徑。</span><span class="sxs-lookup"><span data-stu-id="a68b6-125">AcceleratorFilePath – specifies the path to the accelerator .cab file to generate a package.</span></span>

    -   <span data-ttu-id="a68b6-126">InstalledFilesPath-指定應用程式的本機已安裝檔案的儲存路徑。</span><span class="sxs-lookup"><span data-stu-id="a68b6-126">InstalledFilesPath - specifies the path to where the local installed files of the application are saved.</span></span>

    -   <span data-ttu-id="a68b6-127">InstallMediaPath-指定安裝媒體位置的路徑</span><span class="sxs-lookup"><span data-stu-id="a68b6-127">InstallMediaPath - specifies the path to where the installation media is</span></span>

    -   <span data-ttu-id="a68b6-128">TemplateFilePath-如果您想要自訂先後順序程式，請指定範本檔案的路徑。</span><span class="sxs-lookup"><span data-stu-id="a68b6-128">TemplateFilePath - specifies the path to a template file if you want to customize the sequencing process.</span></span>

    -   <span data-ttu-id="a68b6-129">FullLoad-指定套件必須完全下載到執行 App-v 5.1 的電腦，才能開啟 App。</span><span class="sxs-lookup"><span data-stu-id="a68b6-129">FullLoad - specifies that the package must be fully downloaded to the computer running the App-V 5.1 before it can be opened.</span></span>

    <span data-ttu-id="a68b6-130">您**有應用程式-V 的建議**嗎？</span><span class="sxs-lookup"><span data-stu-id="a68b6-130">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="a68b6-131">在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="a68b6-131">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="a68b6-132">有應用程式-V 問題嗎？</span><span class="sxs-lookup"><span data-stu-id="a68b6-132">Got an App-V issue?</span></span>** <span data-ttu-id="a68b6-133">使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="a68b6-133">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="a68b6-134">相關主題</span><span class="sxs-lookup"><span data-stu-id="a68b6-134">Related topics</span></span>


[<span data-ttu-id="a68b6-135">使用 PowerShell 管理 App-V 5.1</span><span class="sxs-lookup"><span data-stu-id="a68b6-135">Administering App-V 5.1 by Using PowerShell</span></span>](administering-app-v-51-by-using-powershell.md)

 

 





