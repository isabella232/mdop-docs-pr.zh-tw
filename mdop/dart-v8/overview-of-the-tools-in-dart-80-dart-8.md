---
title: DaRT 8.0 中的工具簡介
description: DaRT 8.0 中的工具簡介
author: dansimp
ms.assetid: 1766c82e-c099-47d4-b186-4689b026a7e0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 10/03/2016
ms.openlocfilehash: a058f6018888f446782aa8f3a18ee89570840c2a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810664"
---
# <span data-ttu-id="b9cd9-103">DaRT 8.0 中的工具簡介</span><span class="sxs-lookup"><span data-stu-id="b9cd9-103">Overview of the Tools in DaRT 8.0</span></span>


<span data-ttu-id="b9cd9-104">從 Microsoft Diagnostics 和復原工具庫（DaRT）8.0 中的 [**診斷與修復工具集**] 視窗，您可以在建立 DaRT 8.0 恢復影像時，啟動您所包含的任何個別工具。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-104">From the **Diagnostics and Recovery Toolset** window in Microsoft Diagnostics and Recovery Toolset (DaRT) 8.0, you can start any of the individual tools that you include when you create the DaRT 8.0 recovery image.</span></span> <span data-ttu-id="b9cd9-105">如需如何存取 [**診斷與修復工具集**] 視窗的相關資訊，請參閱[如何使用 DaRT 復原影像來復原本機電腦](how-to-recover-local-computers-by-using-the-dart-recovery-image-dart-8.md)。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-105">For information about how to access the **Diagnostics and Recovery Toolset** window, see [How to Recover Local Computers by Using the DaRT Recovery Image](how-to-recover-local-computers-by-using-the-dart-recovery-image-dart-8.md).</span></span>

<span data-ttu-id="b9cd9-106">如果可用，您可以使用 [**診斷與修復工具集**] 視窗上的 [**方案嚮導**]，根據嚮導所提供的簡短訪談，選取最能解決您特定問題的工具。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-106">If it is available, you can use the **Solution Wizard** on the **Diagnostics and Recovery Toolset** window to select the tool that best addresses your particular issue, based on a brief interview that the wizard provides.</span></span>

## <span data-ttu-id="b9cd9-107">探索 DaRT 工具</span><span class="sxs-lookup"><span data-stu-id="b9cd9-107">Exploring the DaRT tools</span></span>


<span data-ttu-id="b9cd9-108">以下是 DaRT 8.0 工具的描述。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-108">A description of the DaRT 8.0 tools follows.</span></span>

### <span data-ttu-id="b9cd9-109">電腦管理</span><span class="sxs-lookup"><span data-stu-id="b9cd9-109">Computer Management</span></span>

<span data-ttu-id="b9cd9-110">[**電腦管理**] 是 Windows 系統管理工具的集合，可協助您針對問題電腦進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-110">**Computer Management** is a collection of Windows administrative tools that help you troubleshoot a problem computer.</span></span> <span data-ttu-id="b9cd9-111">您可以使用 DaRT 中的**電腦管理**工具來查看系統資訊和事件記錄、管理磁片、清單 autoruns，以及管理服務與驅動程式。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-111">You can use the **Computer Management** tools in DaRT to view system information and event logs, manage disks, list autoruns, and manage services and drivers.</span></span> <span data-ttu-id="b9cd9-112">已自訂 [**電腦管理] 主機**，以協助您診斷並修復可能阻礙 Windows 作業系統啟動的問題。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-112">The **Computer Management** console is customized to help you diagnose and repair problems that might be preventing the Windows operating system from starting.</span></span>

<span data-ttu-id="b9cd9-113">**記事** 不支援使用 DaRT 來恢復動態磁碟。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-113">**Note** The recovery of dynamic disks with DaRT is not supported.</span></span>

 

### <span data-ttu-id="b9cd9-114">故障分析程式</span><span class="sxs-lookup"><span data-stu-id="b9cd9-114">Crash Analyzer</span></span>

<span data-ttu-id="b9cd9-115">您可以在修復的 Windows 作業系統上分析記憶體傾印檔案，以使用 [**崩潰分析程式] 嚮導**快速判斷電腦發生故障的原因。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-115">Use the **Crash Analyzer Wizard** to quickly determine the cause of a computer failure by analyzing the memory dump file on the Windows operating system that you are repairing.</span></span> <span data-ttu-id="b9cd9-116">[當機**分析**程式] 會針對導致電腦失敗的驅動程式檢查記憶體傾印檔案。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-116">**Crash Analyzer** examines the memory dump file for the driver that caused a computer to fail.</span></span> <span data-ttu-id="b9cd9-117">接著，您可以使用 [**電腦管理**] 工具中的 [**服務與驅動**程式] 節點來停用有問題的裝置驅動程式。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-117">You can then disable the problem device driver by using the **Services and Drivers** node in the **Computer Management** tool.</span></span>

<span data-ttu-id="b9cd9-118">[**崩潰分析程式] 嚮導**需要 Windows 版調試工具，以及您要修復之作業系統的符號檔案。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-118">The **Crash Analyzer Wizard** requires the Debugging Tools for Windows and symbol files for the operating system that you are repairing.</span></span> <span data-ttu-id="b9cd9-119">您可以在建立 DaRT 復原影像時包含兩個需求。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-119">You can include both requirements when you create the DaRT recovery image.</span></span> <span data-ttu-id="b9cd9-120">如果不包含在復原映射中，而且您無法在修復的電腦上存取這些檔案，您可以將儲存體轉儲檔案複製到另一部電腦，並使用獨立版本的 [**崩潰分析**程式] 來診斷問題。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-120">If they are not included on the recovery image and you do not have access to them on the computer that you are repairing, you can copy the memory dump file to another computer and use the stand-alone version of **Crash Analyzer** to diagnose the problem.</span></span>

<span data-ttu-id="b9cd9-121">即使您打算重新建立電腦的映射，也能執行**系統崩潰分析**程式。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-121">Running **Crash Analyzer** is a good idea even if you plan to reimage the computer.</span></span> <span data-ttu-id="b9cd9-122">影像可能會有一個缺陷的驅動程式，導致您的環境發生問題。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-122">The image could have a defective driver that is causing problems in your environment.</span></span> <span data-ttu-id="b9cd9-123">您可以執行 [**崩潰分析**程式]，找出問題驅動程式並改善影像穩定性。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-123">By running **Crash Analyzer**, you can identify problem drivers and improve the image stability.</span></span>

<span data-ttu-id="b9cd9-124">如需有關**崩潰分析**程式的詳細資訊，請參閱[使用故障分析程式診斷系統失敗](diagnosing-system-failures-with-crash-analyzer--dart-8.md)。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-124">For more information about **Crash Analyzer**, see [Diagnosing System Failures with Crash Analyzer](diagnosing-system-failures-with-crash-analyzer--dart-8.md).</span></span>

### <span data-ttu-id="b9cd9-125">Defender</span><span class="sxs-lookup"><span data-stu-id="b9cd9-125">Defender</span></span>

<span data-ttu-id="b9cd9-126">**重要** 已部署 DaRT Defender 的環境應該改為使用 Microsoft Defender Offline （WDO）保護影像來偵測惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-126">**Important** Environments with the DaRT Defender deployed should instead use the Microsoft Defender Offline (WDO) protection image for malware detection.</span></span> <span data-ttu-id="b9cd9-127">根據 DaRT 工具整合到 DaRT 的方式，所有受支援的 DaRT 版本部署都無法將這些反惡意程式碼更新套用至其 DaRT 影像。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-127">Because of how the Defender tool integrates into DaRT, all supported DaRT version deployments cannot apply these anti-malware updates to their DaRT images.</span></span> <span data-ttu-id="b9cd9-128">如需詳細資訊，請參閱[Microsoft 診斷與修復工具組（DaRT）使用者應該使用 Microsoft Defender Offline （WDO）進行惡意程式碼偵測-->](use-windows-defender-offline-wdo-for-malware-protection-not-dart.md)。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-128">For more information, see  [Microsoft Diagnostics and Recovery Toolset (DaRT) users should use Microsoft Defender Offline (WDO) for malware detection-->](use-windows-defender-offline-wdo-for-malware-protection-not-dart.md).</span></span>

 

<span data-ttu-id="b9cd9-129">**Defender**可協助偵測惡意程式碼與不想要的軟體，並針對安全性風險提出警告。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-129">**Defender** can help detect malware and unwanted software and warn you of security risks.</span></span> <span data-ttu-id="b9cd9-130">即使已安裝的 Windows 作業系統不在執行中，您也可以使用這個工具來掃描電腦並移除惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-130">You can use this tool to scan a computer for and remove malware even when the installed Windows operating system is not running.</span></span> <span data-ttu-id="b9cd9-131">當**Defender**偵測到惡意或不想要的軟體時，系統會提示您移除、隔離或允許每個專案。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-131">When **Defender** detects malicious or unwanted software, it prompts you to remove, quarantine, or allow for each item.</span></span>

<span data-ttu-id="b9cd9-132">使用 rootkit 的惡意程式碼可以將自身遮罩在正在執行的作業系統中。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-132">Malware that uses rootkits can mask itself from the running operating system.</span></span> <span data-ttu-id="b9cd9-133">如果電腦中有 rootkit 啟用的病毒或間諜軟體，大部分的即時掃描與移除工具都無法再看到或移除。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-133">If a rootkit-enabled virus or spyware is in a computer, most real-time scanning and removal tools can no longer see it or remove it.</span></span> <span data-ttu-id="b9cd9-134">因為您會將有問題的電腦引導至 DaRT，且已安裝的作業系統處於離線狀態，所以您可以偵測 rootkit，而不能自行遮罩本身。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-134">Because you boot the problem computer into DaRT and the installed operating system is offline, you can detect the rootkit without it being able to mask itself.</span></span>

### <span data-ttu-id="b9cd9-135">磁片指揮</span><span class="sxs-lookup"><span data-stu-id="b9cd9-135">Disk Commander</span></span>

<span data-ttu-id="b9cd9-136">**磁片指揮**可讓您使用下列其中一個恢復程式來復原及修復磁碟分割或卷：</span><span class="sxs-lookup"><span data-stu-id="b9cd9-136">**Disk Commander** lets you recover and repair disk partitions or volumes by using one of the following recovery processes:</span></span>

-   <span data-ttu-id="b9cd9-137">還原主開機記錄（MBR）</span><span class="sxs-lookup"><span data-stu-id="b9cd9-137">Restore the master boot record (MBR)</span></span>

-   <span data-ttu-id="b9cd9-138">復原一個或多個遺失的磁片卷</span><span class="sxs-lookup"><span data-stu-id="b9cd9-138">Recover one or more lost volumes</span></span>

-   <span data-ttu-id="b9cd9-139">從**磁片指揮**備份還原分區表</span><span class="sxs-lookup"><span data-stu-id="b9cd9-139">Restore partition tables from **Disk Commander** backup</span></span>

-   <span data-ttu-id="b9cd9-140">將分區表儲存至**磁片指揮**備份</span><span class="sxs-lookup"><span data-stu-id="b9cd9-140">Save partition tables to **Disk Commander** backup</span></span>

<span data-ttu-id="b9cd9-141">**警告** 我們建議您在使用「**磁片指揮**」進行修復之前，先備份磁片。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-141">**Warning** We recommend that you back up a disk before you use **Disk Commander** to repair it.</span></span> <span data-ttu-id="b9cd9-142">使用**磁片指揮**，您可能會損壞卷，並使其無法存取。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-142">By using **Disk Commander**, you can potentially damage volumes and make them inaccessible.</span></span> <span data-ttu-id="b9cd9-143">此外，因為磁片上的卷共用分區表，所以對某個磁片卷所做的變更可能會影響其他卷。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-143">Additionally, changes to one volume can affect other volumes because volumes on a disk share a partition table.</span></span>

 

<span data-ttu-id="b9cd9-144">**記事** 不支援使用 DaRT 來恢復動態磁碟。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-144">**Note** The recovery of dynamic disks with DaRT is not supported.</span></span>

 

### <span data-ttu-id="b9cd9-145">磁片擦除</span><span class="sxs-lookup"><span data-stu-id="b9cd9-145">Disk Wipe</span></span>

<span data-ttu-id="b9cd9-146">您可以使用 [**磁片擦除**] 刪除磁片或卷上的所有資料，即使是在您重新格式化硬碟磁片磁碟機後留下的資料。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-146">You can use **Disk Wipe** to delete all data from a disk or volume, even the data that is left behind after you reformat a hard disk drive.</span></span> <span data-ttu-id="b9cd9-147">[**磁片擦除**] 可讓您從單遍覆寫或四次覆蓋（符合目前的美國國防部）標準進行選取。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-147">**Disk Wipe** lets you select from either a single-pass overwrite or a four-pass overwrite, which meets current U.S. Department of Defense standards.</span></span>

<span data-ttu-id="b9cd9-148">**警告** 擦除磁片或磁片卷之後，您將無法復原資料。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-148">**Warning** After wiping a disk or volume, you cannot recover the data.</span></span> <span data-ttu-id="b9cd9-149">在清除前，請先確認卷的大小和標籤。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-149">Verify the size and label of a volume before erasing it.</span></span>

 

### <span data-ttu-id="b9cd9-150">Explorer</span><span class="sxs-lookup"><span data-stu-id="b9cd9-150">Explorer</span></span>

<span data-ttu-id="b9cd9-151">流覽**器**工具可讓您流覽電腦的檔案系統和網路共用，以便在您嘗試修復或重新鏡像電腦之前，移除使用者儲存在本機磁片磁碟機上的重要資料。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-151">The **Explorer** tool lets you browse the computer’s file system and network shares so that you can remove important data that the user stored on the local drive before you try to repair or reimage the computer.</span></span> <span data-ttu-id="b9cd9-152">而且因為您可以將磁碟機盤符對應至網路共用，所以您可以輕鬆地將檔案從電腦複製並移到網路，以便將檔案從電腦或網路移至電腦，以進行還原。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-152">And because you can map drive letters to network shares, you can easily copy and move files from the computer to the network for safekeeping or from the network to the computer to restore them.</span></span>

### <span data-ttu-id="b9cd9-153">檔案還原</span><span class="sxs-lookup"><span data-stu-id="b9cd9-153">File Restore</span></span>

<span data-ttu-id="b9cd9-154">[檔案**還原**] 可讓您嘗試還原不小心刪除或太大，無法放入回收站的檔案。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-154">**File Restore** lets you try to restore files that were accidentally deleted or that were too big to fit in the Recycle Bin.</span></span> <span data-ttu-id="b9cd9-155">檔案**還原**不受限於一般磁片卷，但可以在遺失的磁片卷或由 BitLocker 加密的磁片上尋找並還原檔案。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-155">**File Restore** is not limited to regular disk volumes, but can find and restore files on lost volumes or on volumes that are encrypted by BitLocker.</span></span>

<span data-ttu-id="b9cd9-156">**記事** 不支援使用 DaRT 來恢復動態磁碟。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-156">**Note** The recovery of dynamic disks with DaRT is not supported.</span></span>

 

### <span data-ttu-id="b9cd9-157">檔案搜尋</span><span class="sxs-lookup"><span data-stu-id="b9cd9-157">File Search</span></span>

<span data-ttu-id="b9cd9-158">在複製電腦前，從本機硬碟復原檔案很重要，尤其是當使用者可能沒有在其他位置備份或儲存檔案時。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-158">Before reimaging a computer, recovering files from the local hard disk is important, especially when the user might not have backed up or stored the files elsewhere.</span></span>

<span data-ttu-id="b9cd9-159">[**搜尋**工具] 會開啟 [檔案**搜尋**] 視窗，當您不知道檔案路徑或要在所有本機硬碟上搜尋一般類型的檔案時，您可以用來尋找檔。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-159">The **Search** tool opens a **File Search** window that you can use to find documents when you do not know the file path or to search for general kinds of files across all local hard disks.</span></span> <span data-ttu-id="b9cd9-160">您可以在特定路徑中搜尋特定的檔案名模式。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-160">You can search for specific file-name patterns in specific paths.</span></span> <span data-ttu-id="b9cd9-161">您也可以將結果限制為日期範圍或大小範圍。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-161">You can also limit results to a date range or size range.</span></span>

### <span data-ttu-id="b9cd9-162">修補程式卸載</span><span class="sxs-lookup"><span data-stu-id="b9cd9-162">Hotfix Uninstall</span></span>

<span data-ttu-id="b9cd9-163">**修復程式卸載嚮導**可讓您在修復的電腦上，從 Windows 作業系統移除修補程式或 service pack。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-163">The **Hotfix Uninstall Wizard** lets you remove hotfixes or service packs from the Windows operating system on the computer that you are repairing.</span></span> <span data-ttu-id="b9cd9-164">在懷疑作業系統無法啟動時，請使用此工具。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-164">Use this tool when a hotfix or service pack is suspected in preventing the operating system from starting.</span></span>

<span data-ttu-id="b9cd9-165">我們建議您一次只卸載一個熱修復程式，即使該工具可讓您卸載一個以上的修補程式也一樣。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-165">We recommend that you uninstall only one hotfix at a time, even though the tool lets you uninstall more than one.</span></span>

<span data-ttu-id="b9cd9-166">**重要** 在安裝修複程式之後安裝或更新的程式可能無法在您卸載修復程式後正常運作。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-166">**Important** Programs that were installed or updated after a hotfix was installed might not work correctly after you uninstall a hotfix.</span></span>

 

### <span data-ttu-id="b9cd9-167">Locksmith</span><span class="sxs-lookup"><span data-stu-id="b9cd9-167">Locksmith</span></span>

<span data-ttu-id="b9cd9-168">您可以在 [ **Locksmith] 嚮導**中設定或變更您正在分析或修復之 Windows 作業系統上任何本機帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-168">The **Locksmith Wizard** lets you set or change the password for any local account on the Windows operating system that you are analyzing or repairing.</span></span> <span data-ttu-id="b9cd9-169">您不需要知道目前的密碼。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-169">You do not have to know the current password.</span></span> <span data-ttu-id="b9cd9-170">不過，您設定的密碼必須符合本機組策略物件所定義的任何需求。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-170">However, the password that you set must comply with any requirements that are defined by a local Group Policy Object.</span></span> <span data-ttu-id="b9cd9-171">這包括密碼長度與複雜性。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-171">This includes password length and complexity.</span></span>

<span data-ttu-id="b9cd9-172">當本機帳戶（例如，本機系統管理員帳戶）的密碼為未知時，您可以使用**Locksmith** 。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-172">You can use **Locksmith** when the password for a local account, such as the local Administrator account, is unknown.</span></span> <span data-ttu-id="b9cd9-173">您無法使用**Locksmith**來設定網域帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-173">You cannot use **Locksmith** to set passwords for domain accounts.</span></span>

### <span data-ttu-id="b9cd9-174">登錄編輯程式</span><span class="sxs-lookup"><span data-stu-id="b9cd9-174">Registry Editor</span></span>

<span data-ttu-id="b9cd9-175">您可以使用 [**登錄編輯程式**] 來存取及變更您正在分析或修復之 Windows 作業系統的註冊。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-175">You can use **Registry Editor** to access and change the registry of the Windows operating system that you are analyzing or repairing.</span></span> <span data-ttu-id="b9cd9-176">這包括新增、移除及編輯金鑰和值，以及匯入註冊表（.reg）檔案。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-176">This includes adding, removing, and editing keys and values, and importing registry (.reg) files.</span></span>

<span data-ttu-id="b9cd9-177">**警告** 如果您使用 [登錄**編輯器**] 無法正確變更登錄，可能會發生嚴重問題。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-177">**Warning** Serious problems can occur if you change the registry incorrectly by using **Registry Editor**.</span></span> <span data-ttu-id="b9cd9-178">這些問題可能需要您重新安裝作業系統。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-178">These problems might require you to reinstall the operating system.</span></span> <span data-ttu-id="b9cd9-179">在變更註冊表之前，您應該先備份電腦上任何有價值的資料。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-179">Before you make changes to the registry, you should back up any valued data on the computer.</span></span> <span data-ttu-id="b9cd9-180">變更註冊表的風險由您自行承擔。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-180">Change the registry at your own risk.</span></span>

 

### <span data-ttu-id="b9cd9-181">SFC 掃描</span><span class="sxs-lookup"><span data-stu-id="b9cd9-181">SFC Scan</span></span>

<span data-ttu-id="b9cd9-182">**SFC 掃描**工具會啟動 [**系統檔修復嚮導]** ，並讓您修復無法啟動已安裝的 Windows 作業系統的系統檔案。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-182">The **SFC Scan** tool starts the **System File Repair Wizard** and lets you repair system files that are preventing the installed Windows operating system from starting.</span></span> <span data-ttu-id="b9cd9-183">[**系統檔修復嚮導]** 可以自動修復損毀或遺失的系統檔案，或者在執行任何修復之前，提示您。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-183">The **System File Repair Wizard** can automatically repair system files that are corrupted or missing, or it can prompt you before it performs any repairs.</span></span>

### <span data-ttu-id="b9cd9-184">方案嚮導</span><span class="sxs-lookup"><span data-stu-id="b9cd9-184">Solution Wizard</span></span>

<span data-ttu-id="b9cd9-185">[**方案嚮導]** 會顯示一系列的問題，然後根據您的答案，推薦此情況的最佳工具。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-185">The **Solution Wizard** presents a series of questions and then recommends the best tool for the situation, based on your answers.</span></span> <span data-ttu-id="b9cd9-186">此嚮導可協助您判斷在您不熟悉 DaRT 中的工具時要使用的工具。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-186">This wizard helps you determine which tool to use when you are not familiar with the tools in DaRT.</span></span>

### <span data-ttu-id="b9cd9-187">TCP/IP Config</span><span class="sxs-lookup"><span data-stu-id="b9cd9-187">TCP/IP Config</span></span>

<span data-ttu-id="b9cd9-188">當您將有問題的電腦引導至 DaRT 時，系統會將它設為自動從動態主機設定通訊協定（DHCP）取得 TCP/IP 設定（IP 位址與 DNS 伺服器）。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-188">When you boot a problem computer into DaRT, it is set to automatically obtain its TCP/IP configuration (IP address and DNS server) from Dynamic Host Configuration Protocol (DHCP).</span></span> <span data-ttu-id="b9cd9-189">如果沒有 DHCP，您可以使用**Tcp/ip Config**工具手動設定 tcp/ip。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-189">If DHCP is unavailable, you can manually configure TCP/IP by using the **TCP/IP Config** tool.</span></span> <span data-ttu-id="b9cd9-190">您首先選取網路介面卡，然後設定該配接器的 IP 位址和 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="b9cd9-190">You first select a network adapter, and then configure the IP address and DNS server for that adapter.</span></span>

## <span data-ttu-id="b9cd9-191">相關主題</span><span class="sxs-lookup"><span data-stu-id="b9cd9-191">Related topics</span></span>


[<span data-ttu-id="b9cd9-192">開始使用 DaRT 8.0</span><span class="sxs-lookup"><span data-stu-id="b9cd9-192">Getting Started with DaRT 8.0</span></span>](getting-started-with-dart-80-dart-8.md)

 

 





