---
title: DaRT 7.0 版本資訊
description: DaRT 7.0 版本資訊
author: dansimp
ms.assetid: fad227d0-5c22-4efd-9187-0e5922f7250b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 5114acfe5a46a2c78f722a2bb6394c0dbef55dd4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809549"
---
# <span data-ttu-id="1c895-103">DaRT 7.0 版本資訊</span><span class="sxs-lookup"><span data-stu-id="1c895-103">Release Notes for DaRT 7.0</span></span>


**<span data-ttu-id="1c895-104">若要搜尋這些版本筆記，請按 CTRL + F。</span><span class="sxs-lookup"><span data-stu-id="1c895-104">To search these release notes, press CTRL+F.</span></span>**

<span data-ttu-id="1c895-105">安裝 Microsoft Diagnostics 及修復工具集（DaRT）7之前，請先閱讀這些版本資訊。</span><span class="sxs-lookup"><span data-stu-id="1c895-105">Read these release notes thoroughly before you install Microsoft Diagnostics and Recovery Toolset (DaRT)7.</span></span>

## <span data-ttu-id="1c895-106">關於 Microsoft Diagnostics 和復原工具組7。0</span><span class="sxs-lookup"><span data-stu-id="1c895-106">About Microsoft Diagnostics and Recovery Toolset 7.0</span></span>


<span data-ttu-id="1c895-107">這些版本資訊包含成功安裝 DaRT7 所需的資訊，且包含產品檔中無法提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="1c895-107">These release notes contain information that is required to successfully install DaRT7 and contain information that is not available in the product documentation.</span></span> <span data-ttu-id="1c895-108">如果這些版本資訊與其他 DaRT 平臺檔有差異，最新的變更應該視為權威性。</span><span class="sxs-lookup"><span data-stu-id="1c895-108">If there is a difference between these release notes and other DaRT platform documentation, the latest change should be considered authoritative.</span></span> <span data-ttu-id="1c895-109">這些版本資訊取代本產品隨附的內容。</span><span class="sxs-lookup"><span data-stu-id="1c895-109">These release notes supersede the content included with this product.</span></span>

## <span data-ttu-id="1c895-110">關於產品檔</span><span class="sxs-lookup"><span data-stu-id="1c895-110">About the Product Documentation</span></span>


<span data-ttu-id="1c895-111">Microsoft 診斷與修復工具組（DaRT）7的檔會與產品一起發佈，並在 [連線] 網站上發佈。</span><span class="sxs-lookup"><span data-stu-id="1c895-111">Documentation for Microsoft Diagnostics and Recovery Toolset (DaRT)7 is distributed with the product and on the Connect site.</span></span>

<span data-ttu-id="1c895-112">如需如何在 DaRT7 中使用工具的詳細說明，請參閱 [**診斷與修復工具**] 功能表上的 [說明] 檔案。</span><span class="sxs-lookup"><span data-stu-id="1c895-112">For detailed help about how to use the tools in DaRT7, see the Help file available on the **Diagnostics and Recovery Toolset** menu.</span></span>

## <span data-ttu-id="1c895-113">提供意見反應</span><span class="sxs-lookup"><span data-stu-id="1c895-113">Providing feedback</span></span>


<span data-ttu-id="1c895-114">我們對您在 DaRT7 的意見反應感興趣。</span><span class="sxs-lookup"><span data-stu-id="1c895-114">We are interested in your feedback on DaRT7.</span></span> <span data-ttu-id="1c895-115">您可以將您的意見反應傳送給 dart7feedback@microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="1c895-115">You can send your feedback to dart7feedback@microsoft.com.</span></span> <span data-ttu-id="1c895-116">此電子郵件地址不是支援頻道，但您的意見反應將會協助我們規劃這些工具的未來變更，讓您日後能使用更實用的功能。</span><span class="sxs-lookup"><span data-stu-id="1c895-116">This email address is not a support channel, but your feedback will help us to plan future changes for these tools to make them more useful to you in the future.</span></span>

## <span data-ttu-id="1c895-117">防範安全性漏洞與病毒</span><span class="sxs-lookup"><span data-stu-id="1c895-117">Protect Against Security Vulnerabilities and Viruses</span></span>


<span data-ttu-id="1c895-118">為了協助防範安全性漏洞和病毒，我們建議您針對任何安裝的新軟體，安裝最新的可用安全更新。</span><span class="sxs-lookup"><span data-stu-id="1c895-118">To help protect against security vulnerabilities and viruses, we recommend that you install the latest available security updates for any new software being installed.</span></span> <span data-ttu-id="1c895-119">如需詳細資訊，請參閱[Microsoft 安全性](https://go.microsoft.com/fwlink/?LinkId=3482)（ https://go.microsoft.com/fwlink/?LinkId=3482) 。</span><span class="sxs-lookup"><span data-stu-id="1c895-119">For more information, see [Microsoft Security](https://go.microsoft.com/fwlink/?LinkId=3482) (https://go.microsoft.com/fwlink/?LinkId=3482).</span></span>

## <span data-ttu-id="1c895-120">DaRT 7.0 的已知問題</span><span class="sxs-lookup"><span data-stu-id="1c895-120">Known Issues with DaRT 7.0</span></span>


### <span data-ttu-id="1c895-121">如果已開啟獨立系統 Sweeper，則無法啟動 SFC 掃描</span><span class="sxs-lookup"><span data-stu-id="1c895-121">SFC Scan cannot start if Standalone System Sweeper is open</span></span>

<span data-ttu-id="1c895-122">如果獨立系統 Sweeper 正在執行，則無法啟動或執行 SFC 掃描，因為兩個工具之間發生資源衝突。</span><span class="sxs-lookup"><span data-stu-id="1c895-122">If the Standalone System Sweeper is running, SFC Scan cannot start or run because of a resource conflict between the two tools.</span></span>

<span data-ttu-id="1c895-123">因應措施 **：** 在您嘗試開啟或執行 SFC 掃描工具之前，請先關閉獨立的系統 Sweeper。</span><span class="sxs-lookup"><span data-stu-id="1c895-123">**Workaround:** Close the Standalone System Sweeper before you try to open or run the SFC Scan tool.</span></span>

### <span data-ttu-id="1c895-124">Unicode 字元可能不會顯示在檔案名中</span><span class="sxs-lookup"><span data-stu-id="1c895-124">Unicode characters may not be displayed in file names</span></span>

<span data-ttu-id="1c895-125">如果您刪除檔案名中有 Unicode 字元的檔案，並嘗試使用 [檔案還原] 工具還原檔案，則找不到該檔案。</span><span class="sxs-lookup"><span data-stu-id="1c895-125">If you delete a file that has Unicode characters in its file name and try to restore the file by using the File Restore tool, the file is not found.</span></span> <span data-ttu-id="1c895-126">只有當您使用的語言不是用來建立復原影像之 Windows DVD 語言以外的語言字元時，才會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="1c895-126">This only occurs when you use characters from a language other than the language of the Windows DVD that was used to create the recovery image.</span></span>

<span data-ttu-id="1c895-127">因應措施 **：** 確定 DaRT 所使用的語言符合您嘗試還原檔案之作業系統所使用的語言的語言。</span><span class="sxs-lookup"><span data-stu-id="1c895-127">**Workaround:** Make sure that the language that is used by DaRT matches the language that is used by the operating system from which it is trying to restore files.</span></span>

### <span data-ttu-id="1c895-128">DaRT 命令列安裝可能無法悄悄地失敗</span><span class="sxs-lookup"><span data-stu-id="1c895-128">DaRT command-line installation may fail silently</span></span>

<span data-ttu-id="1c895-129">如果使用 [安靜模式] 選項執行，則 DaRT 命令列安裝會失敗，除非是使用提升的管理員許可權執行。</span><span class="sxs-lookup"><span data-stu-id="1c895-129">DaRT command-line installation fails silently if run with the quiet mode option unless it is run by using elevated administrator permissions.</span></span>

<span data-ttu-id="1c895-130">因應措施 **：** 使用提升的管理員許可權來執行命令列安裝。</span><span class="sxs-lookup"><span data-stu-id="1c895-130">**Workaround:** Run the command-line installation by using elevated administrator permissions.</span></span> <span data-ttu-id="1c895-131">DaRT 安裝支援命令列安裝的典型 Windows 安裝程式選項。</span><span class="sxs-lookup"><span data-stu-id="1c895-131">DaRT installation supports the typical Windows Installer options for command-line installation.</span></span> <span data-ttu-id="1c895-132">請參閱適用于 Windows 安裝程式的[命令列選項](https://go.microsoft.com/fwlink/?LinkId=160689)，以取得幾個可用開關的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="1c895-132">Please see [Command-Line Options](https://go.microsoft.com/fwlink/?LinkId=160689) for Windows Installer for more information about the several available switches.</span></span>

### <span data-ttu-id="1c895-133">檔案搜尋無法將資料夾移至不同的卷</span><span class="sxs-lookup"><span data-stu-id="1c895-133">File Search cannot move a folder to a different volume</span></span>

<span data-ttu-id="1c895-134">檔案搜尋應用程式不支援在不同的磁片卷之間移動資料夾。</span><span class="sxs-lookup"><span data-stu-id="1c895-134">Moving folders between volumes is not supported by the File Search application.</span></span> <span data-ttu-id="1c895-135">如果您嘗試在 [檔案搜尋] 中將資料夾移至不同的卷，則會傳回下列錯誤：「寫入檔案\* &lt; 檔案名 &gt; \*時發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="1c895-135">If you try to move a folder to a different volume in File Search, the following error is returned: "An error occurred while writing the file *&lt;filename&gt;*.</span></span> <span data-ttu-id="1c895-136">請確定磁片磁碟機有足夠的空間，且目的地路徑可以存取。</span><span class="sxs-lookup"><span data-stu-id="1c895-136">Make sure that the drive has sufficient space and the destination path is accessible."</span></span>

<span data-ttu-id="1c895-137">因應措施 **：** 使用瀏覽器將資料夾移至不同的卷。</span><span class="sxs-lookup"><span data-stu-id="1c895-137">**Workaround:** Use the Explorer to move a folder to a different volume.</span></span>

### <span data-ttu-id="1c895-138">部分資料可能無法在重新映射磁碟機盤符的電腦上使用</span><span class="sxs-lookup"><span data-stu-id="1c895-138">Some data may not be available on computers where the drive letters are remapped</span></span>

<span data-ttu-id="1c895-139">這個問題可能會發生在支援 BitLocker 的電腦和多重開機電腦上。</span><span class="sxs-lookup"><span data-stu-id="1c895-139">This problem can occur on BitLocker-enabled computers and multiboot computers.</span></span> <span data-ttu-id="1c895-140">發生這種情況是因為離線登錄中的某些資訊有硬式編碼磁碟機盤符，而 DaRT 在相同的標籤上使用不同的字母。</span><span class="sxs-lookup"><span data-stu-id="1c895-140">This occurs because some information in the offline registry has hard-coded drive letters, and DaRT uses different letters for the same volumes.</span></span> <span data-ttu-id="1c895-141">常見的效果包括無法在 [登錄編輯程式] 中存取某些本機使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="1c895-141">The typical effects include not having access to certain local user accounts in Registry Editor.</span></span> <span data-ttu-id="1c895-142">此外，某些工具可能無法取得依賴解析檔路徑的屬性。</span><span class="sxs-lookup"><span data-stu-id="1c895-142">Additionally, some tools may be unable to obtain properties that rely on resolving file paths.</span></span>

<span data-ttu-id="1c895-143">因應措施 **：** 在 DaRT 啟動時，使用此選項重新映射磁碟機盤符。</span><span class="sxs-lookup"><span data-stu-id="1c895-143">**Workaround:** Use the option to remap the drive letters as DaRT starts.</span></span> <span data-ttu-id="1c895-144">這通常會將一般的磁片磁碟機字母與預期相符。</span><span class="sxs-lookup"><span data-stu-id="1c895-144">This usually aligns the typical drive letters to what is expected.</span></span>

### <span data-ttu-id="1c895-145">修補程式卸載可能無法卸載某些更新</span><span class="sxs-lookup"><span data-stu-id="1c895-145">Hotfix Uninstall might not uninstall certain updates</span></span>

<span data-ttu-id="1c895-146">部分更新和 service pack 無法卸載，因為它們標示為無法安裝，或因為需要從 Windows 7 中卸載。</span><span class="sxs-lookup"><span data-stu-id="1c895-146">Some updates and service packs cannot be uninstalled because they are marked as un-installable or because they need to be uninstalled from within Windows 7.</span></span> <span data-ttu-id="1c895-147">在這些情況下，修復程式卸載工具可能會指出已卸載這些更新，即使它們尚未安裝也一樣。</span><span class="sxs-lookup"><span data-stu-id="1c895-147">In these instances, the Hotfix Uninstall tool may indicate that these updates have been uninstalled even though they have not been.</span></span>

<span data-ttu-id="1c895-148">因應措施 **：** 從 Windows 7 卸載這些問題更新。</span><span class="sxs-lookup"><span data-stu-id="1c895-148">**Workaround:** Uninstall these problematic updates from Windows 7.</span></span>

### <span data-ttu-id="1c895-149">磁片擦除：無法刪除含有合併磁碟區、帶區卷或鏡像磁碟區的磁片</span><span class="sxs-lookup"><span data-stu-id="1c895-149">Disk Wipe: Disks with spanned volumes, striped volumes, or mirrored volumes cannot be deleted</span></span>

<span data-ttu-id="1c895-150">磁片擦除不支援在一個或多個卷上刪除跨區、鏡像或分割的磁片。</span><span class="sxs-lookup"><span data-stu-id="1c895-150">Disk Wipe does not support deleting disks that are spanned, mirrored, or striped across one or more volumes.</span></span>

<span data-ttu-id="1c895-151">因應措施 **：** 單獨選取並刪除卷中的每個磁片。</span><span class="sxs-lookup"><span data-stu-id="1c895-151">**Workaround:** Select and delete each disk in the volume separately.</span></span>

## <span data-ttu-id="1c895-152">版本資訊版權資訊</span><span class="sxs-lookup"><span data-stu-id="1c895-152">Release Notes Copyright Information</span></span>


<span data-ttu-id="1c895-153">本檔是以「原樣」提供。</span><span class="sxs-lookup"><span data-stu-id="1c895-153">This document is provided “as-is”.</span></span> <span data-ttu-id="1c895-154">本檔中所述的資訊和視圖，包括 URL 及其他網際網路網站參考，可能會隨之變更，恕不另行通知。</span><span class="sxs-lookup"><span data-stu-id="1c895-154">Information and views expressed in this document, including URL and other Internet website references, may change without notice.</span></span> <span data-ttu-id="1c895-155">您會承擔使用它的風險。</span><span class="sxs-lookup"><span data-stu-id="1c895-155">You bear the risk of using it.</span></span>

<span data-ttu-id="1c895-156">本文中描述的一些範例只提供給說明，且是虛構的。</span><span class="sxs-lookup"><span data-stu-id="1c895-156">Some examples depicted herein are provided for illustration only and are fictitious.</span></span><span data-ttu-id="1c895-157">沒有任何實際的關聯或連線是有意或無意的。</span><span class="sxs-lookup"><span data-stu-id="1c895-157">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="1c895-158">本文件不為您提供對任何 Microsoft 產品中的任何智慧財產的法定權利。</span><span class="sxs-lookup"><span data-stu-id="1c895-158">This document does not provide you with any legal rights to any intellectual property in any Microsoft product.</span></span> <span data-ttu-id="1c895-159">本檔針對 Microsoft 而言是保密且專屬的。</span><span class="sxs-lookup"><span data-stu-id="1c895-159">This document is confidential and proprietary to Microsoft.</span></span> <span data-ttu-id="1c895-160">我們已披露，且只能依照保密協定使用。</span><span class="sxs-lookup"><span data-stu-id="1c895-160">It is disclosed and can be used only pursuant to a nondisclosure agreement.</span></span>



<span data-ttu-id="1c895-161">Microsoft、Active Directory、ActiveSync、MS-DOS、Windows、WindowsServer 及 Windows Vista 是 Microsoft 公司群組的商標。</span><span class="sxs-lookup"><span data-stu-id="1c895-161">Microsoft, Active Directory, ActiveSync, MS-DOS, Windows, WindowsServer, and Windows Vista are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="1c895-162">所有其他商標都是其各自擁有者的財產。</span><span class="sxs-lookup"><span data-stu-id="1c895-162">All other trademarks are property of their respective owners.</span></span>

## <span data-ttu-id="1c895-163">相關主題</span><span class="sxs-lookup"><span data-stu-id="1c895-163">Related topics</span></span>


[<span data-ttu-id="1c895-164">關於 DaRT 7.0</span><span class="sxs-lookup"><span data-stu-id="1c895-164">About DaRT 7.0</span></span>](about-dart-70-new-ia.md)

 

 





