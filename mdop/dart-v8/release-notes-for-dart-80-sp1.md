---
title: DaRT 8.0 SP1 版本資訊
description: DaRT 8.0 SP1 版本資訊
author: dansimp
ms.assetid: fa7512d8-fb00-4c27-8f65-c15f3a8ff1cc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a4c49d12fed07f507d2db4d56969d8e7b0559c64
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810755"
---
# <span data-ttu-id="04e3b-103">DaRT 8.0 SP1 版本資訊</span><span class="sxs-lookup"><span data-stu-id="04e3b-103">Release Notes for DaRT 8.0 SP1</span></span>


**<span data-ttu-id="04e3b-104">若要搜尋這些版本筆記，請按 CTRL + F。</span><span class="sxs-lookup"><span data-stu-id="04e3b-104">To search these release notes, press CTRL+F.</span></span>**

<span data-ttu-id="04e3b-105">安裝 Microsoft Diagnostics 和復原工具集（DaRT） 8.0 Service Pack 1 （SP1）之前，請仔細閱讀這些版本資訊。</span><span class="sxs-lookup"><span data-stu-id="04e3b-105">Read these release notes thoroughly before you install Microsoft Diagnostics and Recovery Toolset (DaRT) 8.0 Service Pack 1 (SP1).</span></span>

<span data-ttu-id="04e3b-106">這些版本資訊包含成功安裝診斷和修復工具組 8.0 SP1 所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="04e3b-106">These release notes contain information that is required to successfully install Diagnostics and Recovery Toolset 8.0 SP1.</span></span> <span data-ttu-id="04e3b-107">版本資訊中也包含產品檔中不提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="04e3b-107">The release notes also contain information that is not available in the product documentation.</span></span> <span data-ttu-id="04e3b-108">如果這些版本資訊與其他 DaRT 檔之間有差異，最新變更應視為權威性。</span><span class="sxs-lookup"><span data-stu-id="04e3b-108">If there is a difference between these release notes and other DaRT documentation, the latest change should be considered authoritative.</span></span> <span data-ttu-id="04e3b-109">這些版本資訊取代本產品隨附的內容。</span><span class="sxs-lookup"><span data-stu-id="04e3b-109">These release notes supersede the content that is included with this product.</span></span>

## <span data-ttu-id="04e3b-110">關於產品檔</span><span class="sxs-lookup"><span data-stu-id="04e3b-110">About the product documentation</span></span>


<span data-ttu-id="04e3b-111">如需有關 DaRT 檔的詳細資訊，請參閱 Microsoft TechNet 上的[DaRT 首頁](https://go.microsoft.com/fwlink/?LinkID=252096)。</span><span class="sxs-lookup"><span data-stu-id="04e3b-111">For information about documentation for DaRT, see the [DaRT home page](https://go.microsoft.com/fwlink/?LinkID=252096) on Microsoft TechNet.</span></span>

## <span data-ttu-id="04e3b-112">DaRT 8.0 SP1 的已知問題</span><span class="sxs-lookup"><span data-stu-id="04e3b-112">Known issues with DaRT 8.0 SP1</span></span>


### <span data-ttu-id="04e3b-113">當您執行 Locksmith 或登錄編輯程式時，系統還原失敗</span><span class="sxs-lookup"><span data-stu-id="04e3b-113">System restore fails when you run Locksmith or Registry Editor</span></span>

<span data-ttu-id="04e3b-114">如果您執行 Locksmith、[登錄編輯程式]，而且可能還有其他工具，系統還原就會失敗。</span><span class="sxs-lookup"><span data-stu-id="04e3b-114">If you run Locksmith, Registry Editor, and possibly other tools, System Restore fails.</span></span>

<span data-ttu-id="04e3b-115">因應措施 **：** 關閉並重新啟動 DaRT，然後啟動 [系統還原]。</span><span class="sxs-lookup"><span data-stu-id="04e3b-115">**Workaround:** Close and restart DaRT and then start System Restore.</span></span>

### <span data-ttu-id="04e3b-116">啟動並關閉 Locksmith 或電腦管理之後，SFC 掃描無法執行</span><span class="sxs-lookup"><span data-stu-id="04e3b-116">SFC scan fails to run after you launch and close Locksmith or Computer Management</span></span>

<span data-ttu-id="04e3b-117">如果您開始，然後關閉 Locksmith 或電腦管理工具，系統檔案檢查程式將無法執行。</span><span class="sxs-lookup"><span data-stu-id="04e3b-117">If you start and then close the Locksmith or Computer Management tools, System File Checker fails to run.</span></span>

<span data-ttu-id="04e3b-118">因應措施 **：** 關閉並重新啟動 DaRT，然後啟動 SFC。</span><span class="sxs-lookup"><span data-stu-id="04e3b-118">**Workaround:** Close and restart DaRT and then start SFC.</span></span>

### <a href="" id="-------------dart-installer-does-not-fail-when-adk-has-not-been-installed"></a> <span data-ttu-id="04e3b-119">尚未安裝 ADK 時，DaRT 安裝程式無法失敗</span><span class="sxs-lookup"><span data-stu-id="04e3b-119">DaRT installer does not fail when ADK has not been installed</span></span>

<span data-ttu-id="04e3b-120">如果您使用命令列執行 MSI 來安裝 DaRT 8.0 SP1，但尚未安裝 ADK，DaRT 安裝應該會失敗。</span><span class="sxs-lookup"><span data-stu-id="04e3b-120">If you install DaRT 8.0 SP1 by using the command line to run the MSI, and the ADK has not been installed, the DaRT installation should fail.</span></span> <span data-ttu-id="04e3b-121">目前，DaRT 8.0 SP1 安裝程式會安裝除 DaRT 復原影像以外的所有元件。</span><span class="sxs-lookup"><span data-stu-id="04e3b-121">Currently, the DaRT 8.0 SP1 installer installs all components except the DaRT recovery image.</span></span>

<span data-ttu-id="04e3b-122">因應措施 **：** 所有.</span><span class="sxs-lookup"><span data-stu-id="04e3b-122">**Workaround:** None.</span></span>

### <span data-ttu-id="04e3b-123">在 Locksmith、RegEdit、崩潰分析程式及電腦管理啟動後，無法啟動 Defender</span><span class="sxs-lookup"><span data-stu-id="04e3b-123">Defender cannot be launched after Locksmith, RegEdit, Crash Analyzer, and Computer Management are launched</span></span>

<span data-ttu-id="04e3b-124">如果您已啟動 Locksmith、RegEdit、故障分析程式及電腦管理，就不會啟動 Defender。</span><span class="sxs-lookup"><span data-stu-id="04e3b-124">Defender does not launch if you have already launched Locksmith, RegEdit, Crash Analyzer, and Computer Management.</span></span>

<span data-ttu-id="04e3b-125">因應措施 **：** 關閉並重新啟動 DaRT，然後啟動 Defender。</span><span class="sxs-lookup"><span data-stu-id="04e3b-125">**Workaround:** Close and restart DaRT and then launch Defender.</span></span>

### <span data-ttu-id="04e3b-126">Defender 可能會啟動緩慢</span><span class="sxs-lookup"><span data-stu-id="04e3b-126">Defender may be slow to launch</span></span>

<span data-ttu-id="04e3b-127">Defender 有時候需要幾分鐘的時間才能啟動。</span><span class="sxs-lookup"><span data-stu-id="04e3b-127">Defender sometimes takes a few minutes to launch.</span></span> <span data-ttu-id="04e3b-128">進度列會指出目前的載入狀態。</span><span class="sxs-lookup"><span data-stu-id="04e3b-128">The progress bar indicates the current loading status.</span></span>

<span data-ttu-id="04e3b-129">因應措施 **：** 所有.</span><span class="sxs-lookup"><span data-stu-id="04e3b-129">**Workaround:** None.</span></span>

## <span data-ttu-id="04e3b-130">版本資訊版權資訊</span><span class="sxs-lookup"><span data-stu-id="04e3b-130">Release notes copyright information</span></span>


<span data-ttu-id="04e3b-131">Microsoft、Active Directory、ActiveX、Bing、Excel、Silverlight、SQLServer、Windows、MicrosoftIntune 和 WindowsPowerShell 是 Microsoft 公司群組的商標。</span><span class="sxs-lookup"><span data-stu-id="04e3b-131">Microsoft, Active Directory, ActiveX, Bing, Excel, Silverlight, SQLServer, Windows, MicrosoftIntune, and WindowsPowerShell are trademarks of the Microsoft group of companies.</span></span> <span data-ttu-id="04e3b-132">所有其他商標都是其各自擁有者的財產。</span><span class="sxs-lookup"><span data-stu-id="04e3b-132">All other trademarks are property of their respective owners.</span></span>



## <span data-ttu-id="04e3b-133">相關主題</span><span class="sxs-lookup"><span data-stu-id="04e3b-133">Related topics</span></span>


[<span data-ttu-id="04e3b-134">關於 DaRT 8.0 SP1</span><span class="sxs-lookup"><span data-stu-id="04e3b-134">About DaRT 8.0 SP1</span></span>](about-dart-80-sp1.md)

 

 





