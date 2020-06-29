---
title: 規劃 Application Virtualization Sequencer 實作
description: 規劃 Application Virtualization Sequencer 實作
author: dansimp
ms.assetid: 052f32fe-ad13-4921-a8ce-4a657eb2b2bf
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ac62991e290dcd2da1c42f025a19365bda239fb8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800910"
---
# <span data-ttu-id="bc97e-103">規劃 Application Virtualization Sequencer 實作</span><span class="sxs-lookup"><span data-stu-id="bc97e-103">Planning the Application Virtualization Sequencer Implementation</span></span>


<span data-ttu-id="bc97e-104">排序，應用程式虛擬化用來建立虛擬應用程式和應用程式套件的處理常式，需要使用已安裝 Application Virtualization Sequencer 軟體的電腦。</span><span class="sxs-lookup"><span data-stu-id="bc97e-104">Sequencing, the process used by Application Virtualization to create virtual applications and application packages, requires the use of a computer with the Application Virtualization Sequencer software installed.</span></span>

<span data-ttu-id="bc97e-105">在先後順序程式期間，Sequencer 會放在 [監視器] 模式中，而要排序的應用程式會安裝在先後順序電腦上。</span><span class="sxs-lookup"><span data-stu-id="bc97e-105">During the sequencing process, the Sequencer is placed in monitor mode, and the application to be sequenced is installed on the sequencing computer.</span></span> <span data-ttu-id="bc97e-106">接著，將會啟動已排序的應用程式，並使用其最重要及常用的函數，讓監視程式可以設定主要功能區塊，其中包含應用程式執行所需的應用程式套件中的最小內容。</span><span class="sxs-lookup"><span data-stu-id="bc97e-106">Next, the sequenced application is started, and its most important and commonly used functions are exercised so that the monitoring process can configure the primary feature block, which contains the minimum content in an application package that is necessary for an application to run.</span></span> <span data-ttu-id="bc97e-107">完成這些步驟後，系統就會停止監視模式，並儲存並測試已排序的應用程式，以驗證正確的操作。</span><span class="sxs-lookup"><span data-stu-id="bc97e-107">When these steps are complete, monitoring mode is stopped and the sequenced application is saved and tested to verify correct operation.</span></span>

<span data-ttu-id="bc97e-108">決定要為排序次序選擇哪些應用程式時，請記住某些應用程式無法排序。</span><span class="sxs-lookup"><span data-stu-id="bc97e-108">When deciding which applications to choose for sequencing, remember that certain applications cannot be sequenced.</span></span> <span data-ttu-id="bc97e-109">其中包括 Windows 作業系統的特定部分，例如 Internet Explorer、裝置驅動程式，以及在啟動時啟動服務的應用程式。</span><span class="sxs-lookup"><span data-stu-id="bc97e-109">These include certain parts of the Windows operating system, such as Internet Explorer, device drivers, and applications that start services at boot time.</span></span>

<span data-ttu-id="bc97e-110">如需安裝排序器的逐步資訊，請參閱[如何安裝 Application Virtualization 排序](how-to-install-the-application-virtualization-sequencer.md)器。</span><span class="sxs-lookup"><span data-stu-id="bc97e-110">For step-by-step information about installing the Sequencer, see [How to Install the Application Virtualization Sequencer](how-to-install-the-application-virtualization-sequencer.md).</span></span>

<span data-ttu-id="bc97e-111">**重要** 整個連續處理程式方案應該由您的公司安全小組審查並核准。</span><span class="sxs-lookup"><span data-stu-id="bc97e-111">**Important** The entire sequencing process plan should be reviewed and approved by your corporate security team.</span></span> <span data-ttu-id="bc97e-112">排序器作業通常會與實驗室中的生產環境保持分開。</span><span class="sxs-lookup"><span data-stu-id="bc97e-112">Sequencer operations would usually be kept separate from the production environment in a lab.</span></span> <span data-ttu-id="bc97e-113">根據您的業務需求，這可以根據您的需求簡單或完整。</span><span class="sxs-lookup"><span data-stu-id="bc97e-113">This can be as simple or as comprehensive as necessary, based on your business requirements.</span></span> <span data-ttu-id="bc97e-114">先後順序電腦需要連線到公司網路，才能將完成的套件複製到生產伺服器。</span><span class="sxs-lookup"><span data-stu-id="bc97e-114">The sequencing computers will need connectivity to the corporate network to copy finished packages over to the production servers.</span></span> <span data-ttu-id="bc97e-115">不過，由於它們通常是在沒有防防毒保護的情況下運作，因此它們不能在未受保護的商業網路上（例如，您可能可以在防火牆之後或獨立的網路區段上運作）。</span><span class="sxs-lookup"><span data-stu-id="bc97e-115">However, because they are typically operated without antivirus protection, they must not be on the corporate network unprotected—for example, you might be able to operate behind a firewall or on an isolated network segment.</span></span> <span data-ttu-id="bc97e-116">使用配置來共用隔離虛擬網路的虛擬機器也可能是可接受的方法。</span><span class="sxs-lookup"><span data-stu-id="bc97e-116">Using Virtual Machines configured to share an isolated virtual network might also be an acceptable approach.</span></span> <span data-ttu-id="bc97e-117">依照您公司的安全性原則來安全地解決這種情況。</span><span class="sxs-lookup"><span data-stu-id="bc97e-117">Follow your corporate security policies to safely address this situation.</span></span>

 

<span data-ttu-id="bc97e-118">規劃先後順序程式的主要步驟包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="bc97e-118">Key steps for planning the sequencing process include the following:</span></span>

-   <span data-ttu-id="bc97e-119">考慮您預計每個月處理的應用程式數、這些應用程式的大小，以及新增排序後續更新的余量。</span><span class="sxs-lookup"><span data-stu-id="bc97e-119">Consider the number of applications you expect to process each month, the size of those applications, and add an allowance for sequencing future updates.</span></span> <span data-ttu-id="bc97e-120">套件的大小最多可達 4 GB，且已壓縮或未壓縮。</span><span class="sxs-lookup"><span data-stu-id="bc97e-120">Packages can be up to 4 GB in size, compressed or uncompressed.</span></span>

-   <span data-ttu-id="bc97e-121">在排序每個應用程式時，準備並記錄貴組織要追蹤的可重複程式。</span><span class="sxs-lookup"><span data-stu-id="bc97e-121">Prepare and document a methodical, repeatable process for your organization to follow when sequencing each application.</span></span> <span data-ttu-id="bc97e-122">這應該包括在每個執行中使用檢查清單，以及版本控制程式。</span><span class="sxs-lookup"><span data-stu-id="bc97e-122">This should include the use of a checklist for each run, as well as a version control process.</span></span> <span data-ttu-id="bc97e-123">在調查套件可能的技術問題時，對每個已排序的應用程式使用追蹤記錄也很有説明。</span><span class="sxs-lookup"><span data-stu-id="bc97e-123">The use of a tracking log for each sequenced application is also very helpful when investigating possible technical issues with a package.</span></span>

-   <span data-ttu-id="bc97e-124">針對應用程式排序，請使用最適合處理輸送量的高性能電腦，其中至少有 4 GB 的 RAM 與快速 CPU （3 GHz 或更快的速度）。</span><span class="sxs-lookup"><span data-stu-id="bc97e-124">For sequencing applications, use high-performing computers that are optimized for processing throughput, with at least 4 GB of RAM and a fast CPU (3 GHz or faster).</span></span> <span data-ttu-id="bc97e-125">快速硬碟及個別磁片卷的使用也可以改善效能。</span><span class="sxs-lookup"><span data-stu-id="bc97e-125">Fast hard disks and the use of separate disk volumes can also improve performance.</span></span> <span data-ttu-id="bc97e-126">虛擬機器非常適合用來進行排序，因為它們很容易重設，或者您可以在本機分區上使用具有乾淨影像的物理電腦，在完成每個套件排序作業之後，進行快速重新影像。</span><span class="sxs-lookup"><span data-stu-id="bc97e-126">Virtual Machines are ideal for sequencing because they can easily be reset, or you can use a physical computer with a clean image on a local partition to enable rapid re-imaging after each package sequencing operation has been completed.</span></span>

    <span data-ttu-id="bc97e-127">**重要** 在安全模式中執行 App-v 排序器不受支援。</span><span class="sxs-lookup"><span data-stu-id="bc97e-127">**Important** Running the App-V sequencer in Safe Mode is not supported.</span></span>

     

-   <span data-ttu-id="bc97e-128">確認您瞭解已排序的應用程式的操作環境（包括 Microsoft Office 或 JAVA 執行時間環境等整合元素），因為這通常會判斷在排序應用程式之前，是否必須在順序電腦上安裝任何專案。</span><span class="sxs-lookup"><span data-stu-id="bc97e-128">Verify that you understand the sequenced application’s operating environment, including integration elements such as Microsoft Office or the Java Runtime Environment, because this will often determine whether anything has to be installed on the sequencing computer prior to sequencing the application.</span></span>

-   <span data-ttu-id="bc97e-129">確定每個新的順序作業都是以乾淨的基本影像開始。</span><span class="sxs-lookup"><span data-stu-id="bc97e-129">Ensure that each new sequencing operation always starts with a clean base image.</span></span> <span data-ttu-id="bc97e-130">在放棄所有變更之後，請確認已將已儲存的影像還原至物理電腦，或重新開機虛擬機器，以確保先後順序電腦已重設。</span><span class="sxs-lookup"><span data-stu-id="bc97e-130">Make sure that the sequencing computer has been reset, either by restoring the saved image to a physical computer or by restarting a virtual machine after discarding all changes.</span></span> <span data-ttu-id="bc97e-131">在儲存前，基本影像應該已從 Windows Update 套用最新的更新。</span><span class="sxs-lookup"><span data-stu-id="bc97e-131">The base image should have the latest updates applied from Windows Update before saving.</span></span>

-   <span data-ttu-id="bc97e-132">在順序電腦上關閉可能幹擾安裝監控程式（例如防病毒掃描程式和 Windows Update）的任何專案，因為在排序程式期間有一個穩定的平臺是必要的。</span><span class="sxs-lookup"><span data-stu-id="bc97e-132">Turn off anything on the sequencing computer that can interfere with the install monitoring process, such antivirus scanners and Windows Update, because having a stable platform during the sequencing process is essential.</span></span> <span data-ttu-id="bc97e-133">因為這個步驟會產生大量的安全性風險，所以請務必採取正確的預防措施來保護電腦和網路，以及已排序的應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="bc97e-133">Because this step incurs significant security risks, ensure that the correct precautions are taken to protect the computer and network as well as the sequenced application package.</span></span> <span data-ttu-id="bc97e-134">我們建議您在將應用程式套件排序前，先進行防病毒掃描。</span><span class="sxs-lookup"><span data-stu-id="bc97e-134">We recommend that you do an antivirus scan of application packages before sequencing them.</span></span>

-   <span data-ttu-id="bc97e-135">在排序之後包含測試每個應用程式的詳細程式。</span><span class="sxs-lookup"><span data-stu-id="bc97e-135">Include a detailed process for testing each application after sequencing.</span></span> <span data-ttu-id="bc97e-136">在將虛擬化應用程式部署到最終使用者之前，測試已排序的應用程式將會判斷它是否正常運作，且是程式的基本部分。</span><span class="sxs-lookup"><span data-stu-id="bc97e-136">Testing the sequenced application will determine whether it functions correctly and is an essential part of the process prior to deploying the virtualized application to end users.</span></span> <span data-ttu-id="bc97e-137">在橫向部署到最終使用者之前先測試的最後一個步驟，您也應該規劃試驗式部署至測試群組。</span><span class="sxs-lookup"><span data-stu-id="bc97e-137">As the final step in testing prior to wide-scale deployment to end users, you should also plan for a pilot deployment to a test group.</span></span>

-   <span data-ttu-id="bc97e-138">測試順序式應用程式時，請選擇相同類型的電腦設備，並執行在公司生產環境中使用的相同作業系統。</span><span class="sxs-lookup"><span data-stu-id="bc97e-138">When testing sequenced applications, choose computer equipment of the same type and running the same operating systems that are in use in the company production environment.</span></span> <span data-ttu-id="bc97e-139">只要正確設定，就可以使用虛擬電腦或物理電腦。</span><span class="sxs-lookup"><span data-stu-id="bc97e-139">As long as they are configured properly, either virtual machines or physical machines can be used.</span></span>

## <span data-ttu-id="bc97e-140">相關主題</span><span class="sxs-lookup"><span data-stu-id="bc97e-140">Related topics</span></span>


[<span data-ttu-id="bc97e-141">Application Virtualization Sequencer 硬體和軟體需求</span><span class="sxs-lookup"><span data-stu-id="bc97e-141">Application Virtualization Sequencer Hardware and Software Requirements</span></span>](application-virtualization-sequencer-hardware-and-software-requirements.md)

[<span data-ttu-id="bc97e-142">如何安裝 Application Virtualization Sequencer</span><span class="sxs-lookup"><span data-stu-id="bc97e-142">How to Install the Application Virtualization Sequencer</span></span>](how-to-install-the-application-virtualization-sequencer.md)

[<span data-ttu-id="bc97e-143">如何升級 Application Virtualization Sequencer</span><span class="sxs-lookup"><span data-stu-id="bc97e-143">How to Upgrade the Application Virtualization Sequencer</span></span>](how-to-upgrade-the-application-virtualization-sequencer.md)

[<span data-ttu-id="bc97e-144">安全性與保護概觀</span><span class="sxs-lookup"><span data-stu-id="bc97e-144">Security and Protection Overview</span></span>](security-and-protection-overview.md)

 

 





