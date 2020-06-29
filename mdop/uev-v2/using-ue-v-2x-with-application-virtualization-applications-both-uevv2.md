---
title: 使用 UE-V 2. x 與應用程式虛擬化應用程式
description: 使用 UE-V 2. x 與應用程式虛擬化應用程式
author: dansimp
ms.assetid: 4644b810-fc48-4fd0-96e4-2fc6cd64d8ad
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 221d21c5815b36b57a04a0299352e5fe64f657c5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812255"
---
# <span data-ttu-id="37036-103">使用 UE-V 2. x 與應用程式虛擬化應用程式</span><span class="sxs-lookup"><span data-stu-id="37036-103">Using UE-V 2.x with Application Virtualization Applications</span></span>


<span data-ttu-id="37036-104">Microsoft 使用者體驗虛擬化（UE-V）2.0、2.1 和 2.1 SP1 支援 Microsoft Application Virtualization （App-v）應用程式，而不需對 App-v 或 UE-V 範本進行任何必要的修改。</span><span class="sxs-lookup"><span data-stu-id="37036-104">Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, and 2.1 SP1 support Microsoft Application Virtualization (App-V) applications without any required modifications to either the App-V package or the UE-V template.</span></span> <span data-ttu-id="37036-105">不過，需要額外的步驟，因為您無法直接在虛擬化 App-v 應用程式上執行 UE-V 發生器。</span><span class="sxs-lookup"><span data-stu-id="37036-105">However, an additional step is required because you cannot run the UE-V Generator directly on a virtualized App-V application.</span></span> <span data-ttu-id="37036-106">相反地，您必須在本機安裝應用程式、產生範本，然後將範本套用至虛擬化的應用程式。</span><span class="sxs-lookup"><span data-stu-id="37036-106">Instead, you must install the application locally, generate the template, and then apply the template to the virtualized application.</span></span> <span data-ttu-id="37036-107">UE-V 支援 App-v 4.5、App-v 4.6，以及 App-v 5.0 套件。</span><span class="sxs-lookup"><span data-stu-id="37036-107">UE-V supports App-V 4.5, App-V 4.6, and App-V 5.0 packages.</span></span>

## <span data-ttu-id="37036-108">UE-V 設定對 App-v 應用程式的同步處理</span><span class="sxs-lookup"><span data-stu-id="37036-108">UE-V settings synchronization for App-V applications</span></span>


<span data-ttu-id="37036-109">如果應用程式是由程式名稱開啟，並根據檔案版本號碼和產品版本號碼來開啟，不論應用程式是在本機安裝，還是以應用程式為基礎安裝，都可以使用 UE-V 監視器。</span><span class="sxs-lookup"><span data-stu-id="37036-109">UE-V monitors when an application opens by the program name and, optionally, by file version numbers and product version numbers, whether the application is installed locally or virtually by using App-V.</span></span> <span data-ttu-id="37036-110">當應用程式啟動時，UE-V 會監視 App V 程式，套用儲存在使用者設定儲存路徑中的任何設定，然後讓應用程式正常啟動。</span><span class="sxs-lookup"><span data-stu-id="37036-110">When the application starts, UE-V monitors the App-V process, applies any settings that are stored in the user's settings storage path, and then enables the application to start normally.</span></span> <span data-ttu-id="37036-111">UE-V 會監視 App V 應用程式，並自動將相關的檔案和登錄路徑轉換成虛擬化的位置，而不是在 App-v 計算環境以外的物理位置。</span><span class="sxs-lookup"><span data-stu-id="37036-111">UE-V monitors App-V applications and automatically translates the relevant file and registry paths to the virtualized location as opposed to the physical location outside the App-V computing environment.</span></span>

 **<span data-ttu-id="37036-112">實現虛擬化應用程式的設定同步處理</span><span class="sxs-lookup"><span data-stu-id="37036-112">To implement settings synchronization for a virtualized application</span></span>**

1.  <span data-ttu-id="37036-113">執行 UE-V 發生器，收集您想要在電腦之間同步處理之設定的本機安裝應用程式的設定。</span><span class="sxs-lookup"><span data-stu-id="37036-113">Run the UE-V Generator to collect the settings of the locally installed application whose settings you want to synchronize between computers.</span></span> <span data-ttu-id="37036-114">這個程式會建立設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="37036-114">This process creates a settings location template.</span></span> <span data-ttu-id="37036-115">如果您使用的是內建範本（例如 Microsoft Office 2010 範本），請略過此步驟。</span><span class="sxs-lookup"><span data-stu-id="37036-115">If you use a built-in template such as the Microsoft Office 2010 template, skip this step.</span></span> <span data-ttu-id="37036-116">如需有關執行 UE-V 發生器的詳細資訊，請參閱[部署自訂應用程式的 ue-v 2.](deploy-ue-v-2x-for-custom-applications-new-uevv2.md#createcustomtemplates)</span><span class="sxs-lookup"><span data-stu-id="37036-116">For more information about running the UE-V Generator, see [Deploy UE-V 2.x for Custom Applications](deploy-ue-v-2x-for-custom-applications-new-uevv2.md#createcustomtemplates).</span></span>

2.  <span data-ttu-id="37036-117">安裝 App-v 應用程式套件（如果您尚未這麼做）。</span><span class="sxs-lookup"><span data-stu-id="37036-117">Install the App-V application package if you have not already done so.</span></span>

3.  <span data-ttu-id="37036-118">將範本發佈到設定範本目錄的位置，或使用 `Register-UEVTemplate` Windows PowerShell Cmdlet 手動安裝範本。</span><span class="sxs-lookup"><span data-stu-id="37036-118">Publish the template to the location of your settings template catalog or manually install the template by using the `Register-UEVTemplate` Windows PowerShell cmdlet.</span></span>

    <span data-ttu-id="37036-119">**記事** 如果您將新建立的範本發佈到 [設定] 範本目錄，用戶端就不會收到範本，直到同步處理提供者更新設定為止。</span><span class="sxs-lookup"><span data-stu-id="37036-119">**Note** If you publish the newly created template to the settings template catalog, the client does not receive the template until the sync provider updates the settings.</span></span> <span data-ttu-id="37036-120">若要手動開始此程式，請開啟 [**任務排程程式**]、[任務排程器文檔**庫**]、[ **Microsoft**]，然後展開 [ **ue-v**]。</span><span class="sxs-lookup"><span data-stu-id="37036-120">To manually start this process, open **Task Scheduler**, expand **Task Scheduler Library**, expand **Microsoft**, and expand **UE-V**.</span></span> <span data-ttu-id="37036-121">在 [結果] 窗格中，以滑鼠右鍵按一下 [**範本自動更新**]，然後按一下 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="37036-121">In the results pane, right-click **Template Auto Update**, and then click **Run**.</span></span>

     

4.  <span data-ttu-id="37036-122">啟動 App-v 封裝。</span><span class="sxs-lookup"><span data-stu-id="37036-122">Start the App-V package.</span></span>






## <span data-ttu-id="37036-123">相關主題</span><span class="sxs-lookup"><span data-stu-id="37036-123">Related topics</span></span>


[<span data-ttu-id="37036-124">管理 UE-V 2。</span><span class="sxs-lookup"><span data-stu-id="37036-124">Administering UE-V 2.x</span></span>](administering-ue-v-2x-new-uevv2.md)

 

 





