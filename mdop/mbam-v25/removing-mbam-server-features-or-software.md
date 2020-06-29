---
title: 移除 MBAM 伺服器功能或軟體
description: 移除 MBAM 伺服器功能或軟體
author: dansimp
ms.assetid: 5212ba3f-124d-43c5-824a-608e9a192e86
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 2e6e57c3d2a62a4e01242ade7a82a7bfa551da83
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810880"
---
# <span data-ttu-id="45df8-103">移除 MBAM 伺服器功能或軟體</span><span class="sxs-lookup"><span data-stu-id="45df8-103">Removing MBAM Server Features or Software</span></span>


<span data-ttu-id="45df8-104">這些指示說明如何從 Microsoft BitLocker 管理和監控（MBAM）移除軟體和功能。</span><span class="sxs-lookup"><span data-stu-id="45df8-104">These instructions explain how to remove software and features from Microsoft BitLocker Administration and Monitoring (MBAM).</span></span> <span data-ttu-id="45df8-105">如果您移除 MBAM 伺服器功能，則只會從伺服器移除已設定的功能，而不會從伺服器中移除 MBAM 伺服器軟體。</span><span class="sxs-lookup"><span data-stu-id="45df8-105">If you remove MBAM Server features, only the configured features are removed from the server, not the MBAM Server software.</span></span> <span data-ttu-id="45df8-106">如果您移除 MBAM 伺服器軟體，您在該伺服器上設定的軟體及任何 MBAM 伺服器功能都會被移除。</span><span class="sxs-lookup"><span data-stu-id="45df8-106">If you remove the MBAM Server software, the software and any MBAM Server features that you configured on that server are removed.</span></span>

<span data-ttu-id="45df8-107">**記事** 為了防止意外移除資料，MBAM 不提供移除資料庫的機制;您必須手動執行此動作。</span><span class="sxs-lookup"><span data-stu-id="45df8-107">**Note** To prevent the accidental removal of data, MBAM provides no mechanism for removing the databases; you must do that manually.</span></span>

 

## <a href="" id="bkmk-removeserverfeatures"></a><span data-ttu-id="45df8-108">移除 MBAM 伺服器功能</span><span class="sxs-lookup"><span data-stu-id="45df8-108">Removing MBAM Server features</span></span>


<span data-ttu-id="45df8-109">您可以使用下列其中一種方法，移除您已設定的 MBAM 伺服器功能：</span><span class="sxs-lookup"><span data-stu-id="45df8-109">You can use either of the following methods to remove MBAM Server features that you have configured:</span></span>

-   <span data-ttu-id="45df8-110">MBAM Server 設定精靈</span><span class="sxs-lookup"><span data-stu-id="45df8-110">MBAM Server Configuration wizard</span></span>

-   <span data-ttu-id="45df8-111">Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="45df8-111">Windows PowerShell cmdlets</span></span>

### <span data-ttu-id="45df8-112">使用 MBAM 伺服器設定精靈來移除功能</span><span class="sxs-lookup"><span data-stu-id="45df8-112">Using the MBAM Server Configuration wizard to remove features</span></span>

<span data-ttu-id="45df8-113">請依照下列指示使用 MBAM 伺服器設定向導，以從伺服器中移除已設定的 MBAM 伺服器功能。</span><span class="sxs-lookup"><span data-stu-id="45df8-113">Follow these instructions to use the MBAM Server Configuration wizard to remove configured MBAM Server features from a server.</span></span>

**<span data-ttu-id="45df8-114">使用嚮導來移除 MBAM 功能</span><span class="sxs-lookup"><span data-stu-id="45df8-114">To remove MBAM features by using the wizard</span></span>**

1.  <span data-ttu-id="45df8-115">在您要移除功能的伺服器上，選取 [ **MBAM 伺服器**設定] 以開啟 [設定] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="45df8-115">On the server where you want to remove features, select **MBAM Server Configuration** to open the configuration wizard.</span></span>

2.  <span data-ttu-id="45df8-116">按一下 [**移除功能**]，選取要移除的功能，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="45df8-116">Click **Remove Features**, select the features to remove, and then click **Next**.</span></span> <span data-ttu-id="45df8-117">[**摘要**] 頁面會顯示您選取要移除的功能。</span><span class="sxs-lookup"><span data-stu-id="45df8-117">A **Summary** page displays the features you selected for removal.</span></span>

3.  <span data-ttu-id="45df8-118">按一下 [**移除**] 以開始移除功能，然後按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="45df8-118">Click **Remove** to start removing the features, and then click **Close**.</span></span>

### <span data-ttu-id="45df8-119">使用 Windows PowerShell 移除功能</span><span class="sxs-lookup"><span data-stu-id="45df8-119">Using Windows PowerShell to remove features</span></span>

<span data-ttu-id="45df8-120">使用下列步驟做為使用 Windows PowerShell Cmdlet 來移除 MBAM 伺服器功能的一般指南。</span><span class="sxs-lookup"><span data-stu-id="45df8-120">Use the following steps as a general guide to remove MBAM Server features by using Windows PowerShell cmdlets.</span></span>

**<span data-ttu-id="45df8-121">使用 Windows PowerShell 來移除 MBAM 功能</span><span class="sxs-lookup"><span data-stu-id="45df8-121">To remove MBAM features by using Windows PowerShell</span></span>**

1.  <span data-ttu-id="45df8-122">在移除任何功能前，請參閱[使用 Windows powershell 設定 MBAM 2.5 Server 功能](configuring-mbam-25-server-features-by-using-windows-powershell.md)，以查看使用 windows powershell 的先決條件。</span><span class="sxs-lookup"><span data-stu-id="45df8-122">Before removing any features, see [Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md) to review the prerequisites for using Windows PowerShell.</span></span>

2.  <span data-ttu-id="45df8-123">使用下列 Cmdlet 來移除 MBAM 伺服器功能：</span><span class="sxs-lookup"><span data-stu-id="45df8-123">Use the following cmdlets to remove MBAM Server features:</span></span>

    -   <span data-ttu-id="45df8-124">Disable-MbamReport</span><span class="sxs-lookup"><span data-stu-id="45df8-124">Disable-MbamReport</span></span>

    -   <span data-ttu-id="45df8-125">Disable-MbamWebApplication</span><span class="sxs-lookup"><span data-stu-id="45df8-125">Disable-MbamWebApplication</span></span>

    -   <span data-ttu-id="45df8-126">Disable-MbamCMIntegration</span><span class="sxs-lookup"><span data-stu-id="45df8-126">Disable-MbamCMIntegration</span></span>

    <span data-ttu-id="45df8-127">若要取得 Windows powershell Cmdlet 的說明，請輸入**get-help** &lt; *Cmdlet* ， &gt; 或參閱適用于 windows powershell Cmdlet 的[Microsoft 桌面優化套件 [使用 Windows powershell](https://go.microsoft.com/fwlink/?LinkId=393498) MBAM] 頁面。</span><span class="sxs-lookup"><span data-stu-id="45df8-127">To get help with Windows PowerShell cmdlets, type **Get-Help** &lt;*cmdlet*&gt; or see the [Microsoft Desktop Optimization Pack Automation with Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=393498) page for the MBAM Windows PowerShell cmdlets.</span></span>

## <span data-ttu-id="45df8-128">移除 MBAM Server 軟體</span><span class="sxs-lookup"><span data-stu-id="45df8-128">Removing MBAM Server software</span></span>


<span data-ttu-id="45df8-129">使用下列步驟來移除 MBAM Server 軟體以及您在該伺服器上設定的任何 MBAM 伺服器功能。</span><span class="sxs-lookup"><span data-stu-id="45df8-129">Use the following steps to remove the MBAM Server software and any MBAM Server features that you configured on that server.</span></span>

**<span data-ttu-id="45df8-130">移除 MBAM 伺服器軟體</span><span class="sxs-lookup"><span data-stu-id="45df8-130">To remove the MBAM Server software</span></span>**

1.  <span data-ttu-id="45df8-131">在您要卸載 MBAM Server 軟體的伺服器上，執行**MBAMserversetup.exe**以啟動 Microsoft BitLocker 管理及監視設定向導。</span><span class="sxs-lookup"><span data-stu-id="45df8-131">On the server where you want to uninstall the MBAM Server software, run **MBAMserversetup.exe** to start the Microsoft BitLocker Administration and Monitoring Setup wizard.</span></span>

2.  <span data-ttu-id="45df8-132">選取 [**卸載**]，然後依照其餘的提示完成卸載 MBAM Server 軟體的程式。</span><span class="sxs-lookup"><span data-stu-id="45df8-132">Select **Uninstall**, and follow the remaining prompts to complete the process of uninstalling the MBAM Server software.</span></span>



## <span data-ttu-id="45df8-133">相關主題</span><span class="sxs-lookup"><span data-stu-id="45df8-133">Related topics</span></span>


[<span data-ttu-id="45df8-134">部署 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="45df8-134">Deploying MBAM 2.5</span></span>](deploying-mbam-25.md)

 

 

## <span data-ttu-id="45df8-135">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="45df8-135">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="45df8-136">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="45df8-136">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="45df8-137">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="45df8-137">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>



