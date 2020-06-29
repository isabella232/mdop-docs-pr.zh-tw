---
title: DaRT 8.1 版本資訊
description: DaRT 8.1 版本資訊
author: dansimp
ms.assetid: 44303107-60f4-485c-848a-7e0529f142d4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0d0ba817ddd5bbdefcf7fed833f4c47e7b9d9ce0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810749"
---
# <span data-ttu-id="d69be-103">DaRT 8.1 版本資訊</span><span class="sxs-lookup"><span data-stu-id="d69be-103">Release Notes for DaRT 8.1</span></span>


**<span data-ttu-id="d69be-104">若要搜尋這些版本筆記，請按 CTRL + F。</span><span class="sxs-lookup"><span data-stu-id="d69be-104">To search these release notes, press CTRL+F.</span></span>**

<span data-ttu-id="d69be-105">在安裝 Microsoft Diagnostics 與修復工具組（DaRT）8.1 之前，請先閱讀這些版本資訊。</span><span class="sxs-lookup"><span data-stu-id="d69be-105">Read these release notes thoroughly before you install Microsoft Diagnostics and Recovery Toolset (DaRT) 8.1.</span></span>

<span data-ttu-id="d69be-106">這些版本資訊包含成功安裝診斷和修復工具組8.1 所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="d69be-106">These release notes contain information that is required to successfully install Diagnostics and Recovery Toolset 8.1.</span></span> <span data-ttu-id="d69be-107">版本資訊中也包含產品檔中不提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="d69be-107">The release notes also contain information that is not available in the product documentation.</span></span> <span data-ttu-id="d69be-108">如果這些版本資訊與其他 DaRT 檔之間有差異，最新變更應視為權威性。</span><span class="sxs-lookup"><span data-stu-id="d69be-108">If there is a difference between these release notes and other DaRT documentation, the latest change should be considered authoritative.</span></span> <span data-ttu-id="d69be-109">這些版本資訊取代本產品隨附的內容。</span><span class="sxs-lookup"><span data-stu-id="d69be-109">These release notes supersede the content that is included with this product.</span></span>

## <span data-ttu-id="d69be-110">DaRT 8.1 的已知問題</span><span class="sxs-lookup"><span data-stu-id="d69be-110">Known issues with DaRT 8.1</span></span>


### <span data-ttu-id="d69be-111">Disk 指揮無法在 Windows 8.1 的物理分區中修復損壞的主要開機記錄</span><span class="sxs-lookup"><span data-stu-id="d69be-111">Disk Commander is unable to repair a corrupt master boot record in a physical partition in Windows 8.1</span></span>

<span data-ttu-id="d69be-112">在 Windows 8.1 中，[還原主要開機記錄（MBR）] 或 [GUID 分區表（GPT）] 選項在 [磁片] 中無法修復物理分區中損毀的主要開機記錄，因此無法啟動用戶端電腦。</span><span class="sxs-lookup"><span data-stu-id="d69be-112">In Windows 8.1, the “Restore the Master Boot Record (MBR) or the header of the GUID Partition Table (GPT)” option in Disk Commander is unable to repair a corrupt master boot record in a physical partition, and therefore is unable to boot the client computer.</span></span>

<span data-ttu-id="d69be-113">因應措施 **：** 啟動**啟動修復**，按一下 [**疑難排解**]，按一下 [**高級選項**]，然後按一下 [**開始修復**]。</span><span class="sxs-lookup"><span data-stu-id="d69be-113">**Workaround:** Start **Startup Repair**, click **Troubleshoot**, click **Advanced options**, and then click **Start repair**.</span></span>

### <span data-ttu-id="d69be-114">針對同一磁片磁碟機進行的磁片擦除多個實例會導致除最後一個實例以外的所有實例報告失敗</span><span class="sxs-lookup"><span data-stu-id="d69be-114">Multiple instances of Disk Wipe that target the same drive cause all instances except the last one to report a failure</span></span>

<span data-ttu-id="d69be-115">如果您啟動磁片擦除的多個實例，然後嘗試使用兩個不同的磁片擦放實例來拭除同一磁片磁碟機，除了最後一個以外的所有實例，都無法擦除磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="d69be-115">If you start multiple instances of Disk Wipe, and then try to wipe the same drive by using two separate Disk Wipe instances, all instances except the last one report a failure to wipe the drive.</span></span>

<span data-ttu-id="d69be-116">因應措施 **：** 所有.</span><span class="sxs-lookup"><span data-stu-id="d69be-116">**Workaround:** None.</span></span>

### <span data-ttu-id="d69be-117">磁片擦除可能無法清除具有快閃記憶體之固態磁片磁碟機上的所有資料</span><span class="sxs-lookup"><span data-stu-id="d69be-117">Disk Wipe may not clear all data on solid-state drives that have flash memory</span></span>

<span data-ttu-id="d69be-118">如果您在具有快閃記憶體的固態磁片磁碟機（SSD）上使用 [磁片擦除] 來清除資料，則所有資料都可能無法清除。</span><span class="sxs-lookup"><span data-stu-id="d69be-118">If you use Disk Wipe to clear data on a solid-state drive (SSD) that has flash memory, all of the data may not be erased.</span></span> <span data-ttu-id="d69be-119">之所以會發生這個問題，是因為 SSD 固件在執行磁片擦除時控制寫入的物理位置。</span><span class="sxs-lookup"><span data-stu-id="d69be-119">This issue occurs because the SSD firmware controls the physical location of writes while Disk Wipe is running.</span></span>

<span data-ttu-id="d69be-120">因應措施 **：** 所有.</span><span class="sxs-lookup"><span data-stu-id="d69be-120">**Workaround:** None.</span></span>

### <span data-ttu-id="d69be-121">當您執行 [Locksmith] 嚮導或 [登錄編輯程式] 時，系統還原失敗</span><span class="sxs-lookup"><span data-stu-id="d69be-121">System restore fails when you run Locksmith Wizard or Registry Editor</span></span>

<span data-ttu-id="d69be-122">如果您執行的是 [Locksmith] 嚮導、[登錄編輯程式]，而且可能還有其他工具，系統還原就會失敗。</span><span class="sxs-lookup"><span data-stu-id="d69be-122">If you run Locksmith Wizard, Registry Editor, and possibly other tools, System Restore fails.</span></span>

<span data-ttu-id="d69be-123">因應措施 **：** 關閉並重新啟動 DaRT，然後啟動 [系統還原]。</span><span class="sxs-lookup"><span data-stu-id="d69be-123">**Workaround:** Close and restart DaRT, and then start System Restore.</span></span>

### <span data-ttu-id="d69be-124">啟動及關閉 Locksmith 嚮導或電腦管理之後，系統檔案檢查（SFC）掃描無法執行</span><span class="sxs-lookup"><span data-stu-id="d69be-124">System File Checker (SFC) Scan fails to run after you start and close Locksmith Wizard or Computer Management</span></span>

<span data-ttu-id="d69be-125">如果您在 [電腦管理] 中開始然後關閉 [Locksmith 嚮導] 或 [工具]，系統檔案檢查程式將無法執行。</span><span class="sxs-lookup"><span data-stu-id="d69be-125">If you start and then close Locksmith Wizard or tools in Computer Management, System File Checker fails to run.</span></span>

<span data-ttu-id="d69be-126">因應措施 **：** 關閉並重新啟動 DaRT，然後啟動 [系統檔案檢查程式]。</span><span class="sxs-lookup"><span data-stu-id="d69be-126">**Workaround:** Close and restart DaRT, and then start System File Checker.</span></span>

### <a href="" id="-------------dart-installer-does-not-fail-when-the-windows-assessment-and-deployment-kit-is-not-installed"></a> <span data-ttu-id="d69be-127">在未安裝 Windows 評估與部署套件時，DaRT 安裝程式無法失敗</span><span class="sxs-lookup"><span data-stu-id="d69be-127">DaRT installer does not fail when the Windows Assessment and Deployment Kit is not installed</span></span>

<span data-ttu-id="d69be-128">如果您在安裝 DaRT 8.1 時使用命令列來執行 Windows 安裝程式（.msi），而且尚未安裝 Windows 評估與部署套件（WindowsADK），DaRT 安裝應該會失敗。</span><span class="sxs-lookup"><span data-stu-id="d69be-128">If you install DaRT 8.1 by using the command line to run the Windows Installer (.msi), and the Windows Assessment and Deployment Kit (WindowsADK) has not been installed, the DaRT installation should fail.</span></span> <span data-ttu-id="d69be-129">目前，DaRT 8.1 安裝程式會安裝 DaRT 恢復影像以外的所有元件。</span><span class="sxs-lookup"><span data-stu-id="d69be-129">Currently, the DaRT 8.1 installer installs all components except the DaRT recovery image.</span></span>

<span data-ttu-id="d69be-130">因應措施 **：** 所有.</span><span class="sxs-lookup"><span data-stu-id="d69be-130">**Workaround:** None.</span></span>

### <span data-ttu-id="d69be-131">Windows Defender 無法在 Locksmith 嚮導、[登錄編輯程式]、[崩潰] 分析程式及電腦管理啟動後啟動</span><span class="sxs-lookup"><span data-stu-id="d69be-131">Windows Defender cannot start after Locksmith Wizard, Registry Editor, Crash Analyzer, and Computer Management are started</span></span>

<span data-ttu-id="d69be-132">如果您已經啟動 Locksmith 嚮導、[登錄編輯程式]、[崩潰分析程式] 和 [電腦管理]，Windows Defender 就不會啟動。</span><span class="sxs-lookup"><span data-stu-id="d69be-132">Windows Defender does not start if you have already started Locksmith Wizard, Registry Editor, Crash Analyzer, and Computer Management.</span></span>

<span data-ttu-id="d69be-133">因應措施 **：** 關閉並重新啟動 DaRT，然後啟動 Windows Defender。</span><span class="sxs-lookup"><span data-stu-id="d69be-133">**Workaround:** Close and restart DaRT, and then start Windows Defender.</span></span>

### <span data-ttu-id="d69be-134">Windows Defender 啟動速度可能很慢</span><span class="sxs-lookup"><span data-stu-id="d69be-134">Windows Defender may be slow to start</span></span>

<span data-ttu-id="d69be-135">Windows Defender 有時候會需要幾分鐘的時間才能啟動。</span><span class="sxs-lookup"><span data-stu-id="d69be-135">Windows Defender sometimes takes a few minutes to start.</span></span> <span data-ttu-id="d69be-136">進度列會指出目前的載入狀態。</span><span class="sxs-lookup"><span data-stu-id="d69be-136">The progress bar indicates the current loading status.</span></span>

<span data-ttu-id="d69be-137">因應措施 **：** 所有.</span><span class="sxs-lookup"><span data-stu-id="d69be-137">**Workaround:** None.</span></span>

## <span data-ttu-id="d69be-138">相關主題</span><span class="sxs-lookup"><span data-stu-id="d69be-138">Related topics</span></span>


[<span data-ttu-id="d69be-139">關於 DaRT 8.1</span><span class="sxs-lookup"><span data-stu-id="d69be-139">About DaRT 8.1</span></span>](about-dart-81.md)

 

 





