---
title: DaRT 10 中的工具簡介
description: DaRT 10 中的工具簡介
author: dansimp
ms.assetid: 752467dd-b646-4335-82ce-9090d4651f65
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8bef2b92e998bebffae526d4288c76be081fe0a9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809687"
---
# <span data-ttu-id="38bf5-103">DaRT 10 中的工具簡介</span><span class="sxs-lookup"><span data-stu-id="38bf5-103">Overview of the Tools in DaRT 10</span></span>


<span data-ttu-id="38bf5-104">從 Microsoft Diagnostics 和復原工具庫（DaRT）10中的 [**診斷與修復工具集**] 視窗，您可以在建立 DaRT 10 復原影像時，啟動您所包含的任何個別工具。</span><span class="sxs-lookup"><span data-stu-id="38bf5-104">From the **Diagnostics and Recovery Toolset** window in Microsoft Diagnostics and Recovery Toolset (DaRT) 10, you can start any of the individual tools that you include when you create the DaRT 10 recovery image.</span></span> <span data-ttu-id="38bf5-105">如需如何存取 [**診斷與修復工具集**] 視窗的相關資訊，請參閱[如何使用 DaRT 復原影像來復原本機電腦](how-to-recover-local-computers-by-using-the-dart-recovery-image-dart-10.md)。</span><span class="sxs-lookup"><span data-stu-id="38bf5-105">For information about how to access the **Diagnostics and Recovery Toolset** window, see [How to Recover Local Computers by Using the DaRT Recovery Image](how-to-recover-local-computers-by-using-the-dart-recovery-image-dart-10.md).</span></span>

<span data-ttu-id="38bf5-106">如果可用，您可以使用 [**診斷與修復工具集**] 視窗上的 [**方案嚮導**]，根據嚮導所提供的簡短訪談，選取最能解決您特定問題的工具。</span><span class="sxs-lookup"><span data-stu-id="38bf5-106">If it is available, you can use the **Solution Wizard** on the **Diagnostics and Recovery Toolset** window to select the tool that best addresses your particular issue, based on a brief interview that the wizard provides.</span></span>

## <span data-ttu-id="38bf5-107">探索 DaRT 工具</span><span class="sxs-lookup"><span data-stu-id="38bf5-107">Exploring the DaRT tools</span></span>


<span data-ttu-id="38bf5-108">以下是 DaRT 10 工具的描述。</span><span class="sxs-lookup"><span data-stu-id="38bf5-108">A description of the DaRT 10 tools follows.</span></span>

### <span data-ttu-id="38bf5-109">電腦管理</span><span class="sxs-lookup"><span data-stu-id="38bf5-109">Computer Management</span></span>

<span data-ttu-id="38bf5-110">[**電腦管理**] 是 Windows 系統管理工具的集合，可協助您針對問題電腦進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="38bf5-110">**Computer Management** is a collection of Windows administrative tools that help you troubleshoot a problem computer.</span></span> <span data-ttu-id="38bf5-111">您可以使用 DaRT 中的**電腦管理**工具來查看系統資訊和事件記錄、管理磁片、清單 autoruns，以及管理服務與驅動程式。</span><span class="sxs-lookup"><span data-stu-id="38bf5-111">You can use the **Computer Management** tools in DaRT to view system information and event logs, manage disks, list autoruns, and manage services and drivers.</span></span> <span data-ttu-id="38bf5-112">已自訂 [**電腦管理] 主機**，以協助您診斷並修復可能阻礙 Windows 作業系統啟動的問題。</span><span class="sxs-lookup"><span data-stu-id="38bf5-112">The **Computer Management** console is customized to help you diagnose and repair problems that might be preventing the Windows operating system from starting.</span></span>

<span data-ttu-id="38bf5-113">**記事** 不支援使用 DaRT 來恢復動態磁碟。</span><span class="sxs-lookup"><span data-stu-id="38bf5-113">**Note** The recovery of dynamic disks with DaRT is not supported.</span></span>

 

### <span data-ttu-id="38bf5-114">故障分析程式</span><span class="sxs-lookup"><span data-stu-id="38bf5-114">Crash Analyzer</span></span>

<span data-ttu-id="38bf5-115">您可以在修復的 Windows 作業系統上分析記憶體傾印檔案，以使用 [**崩潰分析程式] 嚮導**快速判斷電腦發生故障的原因。</span><span class="sxs-lookup"><span data-stu-id="38bf5-115">Use the **Crash Analyzer Wizard** to quickly determine the cause of a computer failure by analyzing the memory dump file on the Windows operating system that you are repairing.</span></span> <span data-ttu-id="38bf5-116">[當機**分析**程式] 會針對導致電腦失敗的驅動程式檢查記憶體傾印檔案。</span><span class="sxs-lookup"><span data-stu-id="38bf5-116">**Crash Analyzer** examines the memory dump file for the driver that caused a computer to fail.</span></span> <span data-ttu-id="38bf5-117">接著，您可以使用 [**電腦管理**] 工具中的 [**服務與驅動**程式] 節點來停用有問題的裝置驅動程式。</span><span class="sxs-lookup"><span data-stu-id="38bf5-117">You can then disable the problem device driver by using the **Services and Drivers** node in the **Computer Management** tool.</span></span>

<span data-ttu-id="38bf5-118">[**崩潰分析程式] 嚮導**需要 Windows 版調試工具，以及您要修復之作業系統的符號檔案。</span><span class="sxs-lookup"><span data-stu-id="38bf5-118">The **Crash Analyzer Wizard** requires the Debugging Tools for Windows and symbol files for the operating system that you are repairing.</span></span> <span data-ttu-id="38bf5-119">您可以在建立 DaRT 復原影像時包含兩個需求。</span><span class="sxs-lookup"><span data-stu-id="38bf5-119">You can include both requirements when you create the DaRT recovery image.</span></span> <span data-ttu-id="38bf5-120">如果不包含在復原映射中，而且您無法在修復的電腦上存取這些檔案，您可以將儲存體轉儲檔案複製到另一部電腦，並使用獨立版本的 [**崩潰分析**程式] 來診斷問題。</span><span class="sxs-lookup"><span data-stu-id="38bf5-120">If they are not included on the recovery image and you do not have access to them on the computer that you are repairing, you can copy the memory dump file to another computer and use the stand-alone version of **Crash Analyzer** to diagnose the problem.</span></span>

<span data-ttu-id="38bf5-121">即使您打算重新建立電腦的映射，也能執行**系統崩潰分析**程式。</span><span class="sxs-lookup"><span data-stu-id="38bf5-121">Running **Crash Analyzer** is a good idea even if you plan to reimage the computer.</span></span> <span data-ttu-id="38bf5-122">影像可能會有一個缺陷的驅動程式，導致您的環境發生問題。</span><span class="sxs-lookup"><span data-stu-id="38bf5-122">The image could have a defective driver that is causing problems in your environment.</span></span> <span data-ttu-id="38bf5-123">您可以執行 [**崩潰分析**程式]，找出問題驅動程式並改善影像穩定性。</span><span class="sxs-lookup"><span data-stu-id="38bf5-123">By running **Crash Analyzer**, you can identify problem drivers and improve the image stability.</span></span>

<span data-ttu-id="38bf5-124">如需有關**崩潰分析**程式的詳細資訊，請參閱[使用故障分析程式診斷系統失敗](diagnosing-system-failures-with-crash-analyzer-dart-10.md)。</span><span class="sxs-lookup"><span data-stu-id="38bf5-124">For more information about **Crash Analyzer**, see [Diagnosing System Failures with Crash Analyzer](diagnosing-system-failures-with-crash-analyzer-dart-10.md).</span></span>

### <span data-ttu-id="38bf5-125">磁片指揮</span><span class="sxs-lookup"><span data-stu-id="38bf5-125">Disk Commander</span></span>

<span data-ttu-id="38bf5-126">**磁片指揮**可讓您使用下列其中一個恢復程式來復原及修復磁碟分割或卷：</span><span class="sxs-lookup"><span data-stu-id="38bf5-126">**Disk Commander** lets you recover and repair disk partitions or volumes by using one of the following recovery processes:</span></span>

-   <span data-ttu-id="38bf5-127">還原主開機記錄（MBR）</span><span class="sxs-lookup"><span data-stu-id="38bf5-127">Restore the master boot record (MBR)</span></span>

-   <span data-ttu-id="38bf5-128">復原一個或多個遺失的磁片卷</span><span class="sxs-lookup"><span data-stu-id="38bf5-128">Recover one or more lost volumes</span></span>

-   <span data-ttu-id="38bf5-129">從**磁片指揮**備份還原分區表</span><span class="sxs-lookup"><span data-stu-id="38bf5-129">Restore partition tables from **Disk Commander** backup</span></span>

-   <span data-ttu-id="38bf5-130">將分區表儲存至**磁片指揮**備份</span><span class="sxs-lookup"><span data-stu-id="38bf5-130">Save partition tables to **Disk Commander** backup</span></span>

<span data-ttu-id="38bf5-131">**警告** 我們建議您在使用「**磁片指揮**」進行修復之前，先備份磁片。</span><span class="sxs-lookup"><span data-stu-id="38bf5-131">**Warning** We recommend that you back up a disk before you use **Disk Commander** to repair it.</span></span> <span data-ttu-id="38bf5-132">使用**磁片指揮**，您可能會損壞卷，並使其無法存取。</span><span class="sxs-lookup"><span data-stu-id="38bf5-132">By using **Disk Commander**, you can potentially damage volumes and make them inaccessible.</span></span> <span data-ttu-id="38bf5-133">此外，因為磁片上的卷共用分區表，所以對某個磁片卷所做的變更可能會影響其他卷。</span><span class="sxs-lookup"><span data-stu-id="38bf5-133">Additionally, changes to one volume can affect other volumes because volumes on a disk share a partition table.</span></span>

 

<span data-ttu-id="38bf5-134">**記事** 不支援使用 DaRT 來恢復動態磁碟。</span><span class="sxs-lookup"><span data-stu-id="38bf5-134">**Note** The recovery of dynamic disks with DaRT is not supported.</span></span>

 

### <span data-ttu-id="38bf5-135">磁片擦除</span><span class="sxs-lookup"><span data-stu-id="38bf5-135">Disk Wipe</span></span>

<span data-ttu-id="38bf5-136">您可以使用 [**磁片擦除**] 刪除磁片或卷上的所有資料，即使是在您重新格式化硬碟磁片磁碟機後留下的資料。</span><span class="sxs-lookup"><span data-stu-id="38bf5-136">You can use **Disk Wipe** to delete all data from a disk or volume, even the data that is left behind after you reformat a hard disk drive.</span></span> <span data-ttu-id="38bf5-137">[**磁片擦除**] 可讓您從單遍覆寫或四次覆蓋（符合目前的美國國防部）標準進行選取。</span><span class="sxs-lookup"><span data-stu-id="38bf5-137">**Disk Wipe** lets you select from either a single-pass overwrite or a four-pass overwrite, which meets current U.S. Department of Defense standards.</span></span>

<span data-ttu-id="38bf5-138">**警告** 擦除磁片或磁片卷之後，您將無法復原資料。</span><span class="sxs-lookup"><span data-stu-id="38bf5-138">**Warning** After wiping a disk or volume, you cannot recover the data.</span></span> <span data-ttu-id="38bf5-139">在清除前，請先確認卷的大小和標籤。</span><span class="sxs-lookup"><span data-stu-id="38bf5-139">Verify the size and label of a volume before erasing it.</span></span>

 

### <span data-ttu-id="38bf5-140">Explorer</span><span class="sxs-lookup"><span data-stu-id="38bf5-140">Explorer</span></span>

<span data-ttu-id="38bf5-141">流覽**器**工具可讓您流覽電腦的檔案系統和網路共用，以便在您嘗試修復或重新鏡像電腦之前，移除使用者儲存在本機磁片磁碟機上的重要資料。</span><span class="sxs-lookup"><span data-stu-id="38bf5-141">The **Explorer** tool lets you browse the computer’s file system and network shares so that you can remove important data that the user stored on the local drive before you try to repair or reimage the computer.</span></span> <span data-ttu-id="38bf5-142">而且因為您可以將磁碟機盤符對應至網路共用，所以您可以輕鬆地將檔案從電腦複製並移到網路，以便將檔案從電腦或網路移至電腦，以進行還原。</span><span class="sxs-lookup"><span data-stu-id="38bf5-142">And because you can map drive letters to network shares, you can easily copy and move files from the computer to the network for safekeeping or from the network to the computer to restore them.</span></span>

### <span data-ttu-id="38bf5-143">檔案還原</span><span class="sxs-lookup"><span data-stu-id="38bf5-143">File Restore</span></span>

<span data-ttu-id="38bf5-144">[檔案**還原**] 可讓您嘗試還原不小心刪除或太大，無法放入回收站的檔案。</span><span class="sxs-lookup"><span data-stu-id="38bf5-144">**File Restore** lets you try to restore files that were accidentally deleted or that were too big to fit in the Recycle Bin.</span></span> <span data-ttu-id="38bf5-145">檔案**還原**不受限於一般磁片卷，但可以在遺失的磁片卷或由 BitLocker 加密的磁片上尋找並還原檔案。</span><span class="sxs-lookup"><span data-stu-id="38bf5-145">**File Restore** is not limited to regular disk volumes, but can find and restore files on lost volumes or on volumes that are encrypted by BitLocker.</span></span>

<span data-ttu-id="38bf5-146">**記事** 不支援使用 DaRT 來恢復動態磁碟。</span><span class="sxs-lookup"><span data-stu-id="38bf5-146">**Note** The recovery of dynamic disks with DaRT is not supported.</span></span>

 

### <span data-ttu-id="38bf5-147">檔案搜尋</span><span class="sxs-lookup"><span data-stu-id="38bf5-147">File Search</span></span>

<span data-ttu-id="38bf5-148">在複製電腦前，從本機硬碟復原檔案很重要，尤其是當使用者可能沒有在其他位置備份或儲存檔案時。</span><span class="sxs-lookup"><span data-stu-id="38bf5-148">Before reimaging a computer, recovering files from the local hard disk is important, especially when the user might not have backed up or stored the files elsewhere.</span></span>

<span data-ttu-id="38bf5-149">[**搜尋**工具] 會開啟 [檔案**搜尋**] 視窗，當您不知道檔案路徑或要在所有本機硬碟上搜尋一般類型的檔案時，您可以用來尋找檔。</span><span class="sxs-lookup"><span data-stu-id="38bf5-149">The **Search** tool opens a **File Search** window that you can use to find documents when you do not know the file path or to search for general kinds of files across all local hard disks.</span></span> <span data-ttu-id="38bf5-150">您可以在特定路徑中搜尋特定的檔案名模式。</span><span class="sxs-lookup"><span data-stu-id="38bf5-150">You can search for specific file-name patterns in specific paths.</span></span> <span data-ttu-id="38bf5-151">您也可以將結果限制為日期範圍或大小範圍。</span><span class="sxs-lookup"><span data-stu-id="38bf5-151">You can also limit results to a date range or size range.</span></span>

### <span data-ttu-id="38bf5-152">修補程式卸載</span><span class="sxs-lookup"><span data-stu-id="38bf5-152">Hotfix Uninstall</span></span>

<span data-ttu-id="38bf5-153">**修復程式卸載嚮導**可讓您在修復的電腦上，從 Windows 作業系統移除修補程式或 service pack。</span><span class="sxs-lookup"><span data-stu-id="38bf5-153">The **Hotfix Uninstall Wizard** lets you remove hotfixes or service packs from the Windows operating system on the computer that you are repairing.</span></span> <span data-ttu-id="38bf5-154">在懷疑作業系統無法啟動時，請使用此工具。</span><span class="sxs-lookup"><span data-stu-id="38bf5-154">Use this tool when a hotfix or service pack is suspected in preventing the operating system from starting.</span></span>

<span data-ttu-id="38bf5-155">我們建議您一次只卸載一個熱修復程式，即使該工具可讓您卸載一個以上的修補程式也一樣。</span><span class="sxs-lookup"><span data-stu-id="38bf5-155">We recommend that you uninstall only one hotfix at a time, even though the tool lets you uninstall more than one.</span></span>

<span data-ttu-id="38bf5-156">**重要** 在安裝修複程式之後安裝或更新的程式可能無法在您卸載修復程式後正常運作。</span><span class="sxs-lookup"><span data-stu-id="38bf5-156">**Important** Programs that were installed or updated after a hotfix was installed might not work correctly after you uninstall a hotfix.</span></span>

 

### <span data-ttu-id="38bf5-157">Locksmith</span><span class="sxs-lookup"><span data-stu-id="38bf5-157">Locksmith</span></span>

<span data-ttu-id="38bf5-158">您可以在 [ **Locksmith] 嚮導**中設定或變更您正在分析或修復之 Windows 作業系統上任何本機帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="38bf5-158">The **Locksmith Wizard** lets you set or change the password for any local account on the Windows operating system that you are analyzing or repairing.</span></span> <span data-ttu-id="38bf5-159">您不需要知道目前的密碼。</span><span class="sxs-lookup"><span data-stu-id="38bf5-159">You do not have to know the current password.</span></span> <span data-ttu-id="38bf5-160">不過，您設定的密碼必須符合本機組策略物件所定義的任何需求。</span><span class="sxs-lookup"><span data-stu-id="38bf5-160">However, the password that you set must comply with any requirements that are defined by a local Group Policy Object.</span></span> <span data-ttu-id="38bf5-161">這包括密碼長度與複雜性。</span><span class="sxs-lookup"><span data-stu-id="38bf5-161">This includes password length and complexity.</span></span>

<span data-ttu-id="38bf5-162">當本機帳戶（例如，本機系統管理員帳戶）的密碼為未知時，您可以使用**Locksmith** 。</span><span class="sxs-lookup"><span data-stu-id="38bf5-162">You can use **Locksmith** when the password for a local account, such as the local Administrator account, is unknown.</span></span> <span data-ttu-id="38bf5-163">您無法使用**Locksmith**來設定網域帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="38bf5-163">You cannot use **Locksmith** to set passwords for domain accounts.</span></span>

### <span data-ttu-id="38bf5-164">登錄編輯程式</span><span class="sxs-lookup"><span data-stu-id="38bf5-164">Registry Editor</span></span>

<span data-ttu-id="38bf5-165">您可以使用 [**登錄編輯程式**] 來存取及變更您正在分析或修復之 Windows 作業系統的註冊。</span><span class="sxs-lookup"><span data-stu-id="38bf5-165">You can use **Registry Editor** to access and change the registry of the Windows operating system that you are analyzing or repairing.</span></span> <span data-ttu-id="38bf5-166">這包括新增、移除及編輯金鑰和值，以及匯入註冊表（.reg）檔案。</span><span class="sxs-lookup"><span data-stu-id="38bf5-166">This includes adding, removing, and editing keys and values, and importing registry (.reg) files.</span></span>

<span data-ttu-id="38bf5-167">**警告** 如果您使用 [登錄**編輯器**] 無法正確變更登錄，可能會發生嚴重問題。</span><span class="sxs-lookup"><span data-stu-id="38bf5-167">**Warning** Serious problems can occur if you change the registry incorrectly by using **Registry Editor**.</span></span> <span data-ttu-id="38bf5-168">這些問題可能需要您重新安裝作業系統。</span><span class="sxs-lookup"><span data-stu-id="38bf5-168">These problems might require you to reinstall the operating system.</span></span> <span data-ttu-id="38bf5-169">在變更註冊表之前，您應該先備份電腦上任何有價值的資料。</span><span class="sxs-lookup"><span data-stu-id="38bf5-169">Before you make changes to the registry, you should back up any valued data on the computer.</span></span> <span data-ttu-id="38bf5-170">變更註冊表的風險由您自行承擔。</span><span class="sxs-lookup"><span data-stu-id="38bf5-170">Change the registry at your own risk.</span></span>

 

### <span data-ttu-id="38bf5-171">SFC 掃描</span><span class="sxs-lookup"><span data-stu-id="38bf5-171">SFC Scan</span></span>

<span data-ttu-id="38bf5-172">**SFC 掃描**工具會啟動 [**系統檔修復嚮導]** ，並讓您修復無法啟動已安裝的 Windows 作業系統的系統檔案。</span><span class="sxs-lookup"><span data-stu-id="38bf5-172">The **SFC Scan** tool starts the **System File Repair Wizard** and lets you repair system files that are preventing the installed Windows operating system from starting.</span></span> <span data-ttu-id="38bf5-173">[**系統檔修復嚮導]** 可以自動修復損毀或遺失的系統檔案，或者在執行任何修復之前，提示您。</span><span class="sxs-lookup"><span data-stu-id="38bf5-173">The **System File Repair Wizard** can automatically repair system files that are corrupted or missing, or it can prompt you before it performs any repairs.</span></span>

### <span data-ttu-id="38bf5-174">方案嚮導</span><span class="sxs-lookup"><span data-stu-id="38bf5-174">Solution Wizard</span></span>

<span data-ttu-id="38bf5-175">[**方案嚮導]** 會顯示一系列的問題，然後根據您的答案，推薦此情況的最佳工具。</span><span class="sxs-lookup"><span data-stu-id="38bf5-175">The **Solution Wizard** presents a series of questions and then recommends the best tool for the situation, based on your answers.</span></span> <span data-ttu-id="38bf5-176">此嚮導可協助您判斷在您不熟悉 DaRT 中的工具時要使用的工具。</span><span class="sxs-lookup"><span data-stu-id="38bf5-176">This wizard helps you determine which tool to use when you are not familiar with the tools in DaRT.</span></span>

### <span data-ttu-id="38bf5-177">TCP/IP Config</span><span class="sxs-lookup"><span data-stu-id="38bf5-177">TCP/IP Config</span></span>

<span data-ttu-id="38bf5-178">當您將有問題的電腦引導至 DaRT 時，系統會將它設為自動從動態主機設定通訊協定（DHCP）取得 TCP/IP 設定（IP 位址與 DNS 伺服器）。</span><span class="sxs-lookup"><span data-stu-id="38bf5-178">When you boot a problem computer into DaRT, it is set to automatically obtain its TCP/IP configuration (IP address and DNS server) from Dynamic Host Configuration Protocol (DHCP).</span></span> <span data-ttu-id="38bf5-179">如果沒有 DHCP，您可以使用**Tcp/ip Config**工具手動設定 tcp/ip。</span><span class="sxs-lookup"><span data-stu-id="38bf5-179">If DHCP is unavailable, you can manually configure TCP/IP by using the **TCP/IP Config** tool.</span></span> <span data-ttu-id="38bf5-180">您首先選取網路介面卡，然後設定該配接器的 IP 位址和 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="38bf5-180">You first select a network adapter, and then configure the IP address and DNS server for that adapter.</span></span>

## <span data-ttu-id="38bf5-181">相關主題</span><span class="sxs-lookup"><span data-stu-id="38bf5-181">Related topics</span></span>


[<span data-ttu-id="38bf5-182">開始使用 DaRT 10</span><span class="sxs-lookup"><span data-stu-id="38bf5-182">Getting Started with DaRT 10</span></span>](getting-started-with-dart-10.md)

 

 





