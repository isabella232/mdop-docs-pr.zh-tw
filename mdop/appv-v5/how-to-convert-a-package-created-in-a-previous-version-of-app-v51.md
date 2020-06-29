---
title: 如何轉換在舊版 App-V 中建立的套件
description: 如何轉換在舊版 App-V 中建立的套件
author: dansimp
ms.assetid: 3366d399-2891-491d-8de1-f8cfdf39bbab
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 402e64e3bdbc55eea1edb91d070bb7ebb11c912b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800573"
---
# <span data-ttu-id="dd626-103">如何轉換在舊版 App-V 中建立的套件</span><span class="sxs-lookup"><span data-stu-id="dd626-103">How to Convert a Package Created in a Previous Version of App-V</span></span>


<span data-ttu-id="dd626-104">您可以使用套件轉換器實用程式來升級已使用舊版 App-V 建立的虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="dd626-104">You can use the package converter utility to upgrade virtual application packages that have been created with previous versions of App-V.</span></span>

**<span data-ttu-id="dd626-105">注意</span><span class="sxs-lookup"><span data-stu-id="dd626-105">Note</span></span>**  
<span data-ttu-id="dd626-106">如果您執行的是64位架構的電腦，則必須使用 PowerShell 的 x86 版本。</span><span class="sxs-lookup"><span data-stu-id="dd626-106">If you are running a computer with a 64-bit architecture, you must use the x86 version of PowerShell.</span></span>



<span data-ttu-id="dd626-107">套件轉換器只能直接轉換使用 App-v 4.5 排序器或後續版本建立的套件。</span><span class="sxs-lookup"><span data-stu-id="dd626-107">The package converter can only directly convert packages that were created by using the App-V 4.5 sequencer or a subsequent version.</span></span> <span data-ttu-id="dd626-108">使用 App-v 4.5 之前的版本所建立的套件，必須先升級到 app-v 4.5 或 App-v 4.6 格式，然後再進行轉換。</span><span class="sxs-lookup"><span data-stu-id="dd626-108">Packages that were created using a version prior to App-V 4.5 must be upgraded to the App-V 4.5 or App-V 4.6 format before conversion.</span></span>

<span data-ttu-id="dd626-109">下列資訊提供轉換現有虛擬應用程式套件的方向。</span><span class="sxs-lookup"><span data-stu-id="dd626-109">The following information provides direction for converting existing virtual application packages.</span></span>

**<span data-ttu-id="dd626-110">重要</span><span class="sxs-lookup"><span data-stu-id="dd626-110">Important</span></span>**  
<span data-ttu-id="dd626-111">您必須設定套件轉換器，才能將套件要素檔案儲存到安全的位置和目錄。</span><span class="sxs-lookup"><span data-stu-id="dd626-111">You must configure the package converter to always save the package ingredients file to a secure location and directory.</span></span> <span data-ttu-id="dd626-112">只有系統管理員才能存取安全的位置。</span><span class="sxs-lookup"><span data-stu-id="dd626-112">A secure location is accessible only by an administrator.</span></span> <span data-ttu-id="dd626-113">此外，當您部署套件時，您應該將套件儲存至安全的位置，或確定在轉換過程中不允許其他使用者登入。</span><span class="sxs-lookup"><span data-stu-id="dd626-113">Additionally, when you deploy the package, you should save the package to a location that is secure, or make sure that no other user is allowed to be logged in during the conversion process.</span></span>



**<span data-ttu-id="dd626-114">App-v 4.6 安裝資料夾會重新導向至虛擬檔案系統根目錄</span><span class="sxs-lookup"><span data-stu-id="dd626-114">App-V 4.6 installation folder is redirected to virtual file system root</span></span>**

<span data-ttu-id="dd626-115">當您將套件從 App-v 4.6 轉換為5.1 時，App-v 5.1 套件可以存取您在建立4.6 套件時所需使用的硬驅式硬碟。</span><span class="sxs-lookup"><span data-stu-id="dd626-115">When you convert packages from App-V 4.6 to 5.1, the App-V 5.1 package can access the hardcoded drive that you were required to use when you created 4.6 packages.</span></span> <span data-ttu-id="dd626-116">磁碟機盤符就是您在4.6 順序電腦上選取為安裝磁碟機的磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="dd626-116">The drive letter will be the drive you selected as the installation drive on the 4.6 sequencing machine.</span></span> <span data-ttu-id="dd626-117">（預設的磁片磁碟機盤符為 Q:\\.）</span><span class="sxs-lookup"><span data-stu-id="dd626-117">(The default drive letter is Q:\\.)</span></span>

<span data-ttu-id="dd626-118">在 App-V 5.1 之前，無法辨識4.6 根資料夾，且 App-v 5.0 套件無法存取。</span><span class="sxs-lookup"><span data-stu-id="dd626-118">Prior to App-V 5.1, the 4.6 root folder was not recognized and could not be accessed by App-V 5.0 packages.</span></span> <span data-ttu-id="dd626-119">現在，App-v 5.1 套件可透過完整路徑存取硬編碼檔案，或以程式設計方式列舉 App-v 4.6 安裝根目錄下的檔案。</span><span class="sxs-lookup"><span data-stu-id="dd626-119">Now, App-V 5.1 packages can access hardcoded files by their full path or can programmatically enumerate files under the App-V 4.6 installation root.</span></span>

<span data-ttu-id="dd626-120">**技術詳細資料：** App-v 5.1 套件轉換器將在 Filesystem 元素的 FilesystemMetadata.xml 檔案中儲存 App-V 4.6 安裝根資料夾和短資料夾名稱。</span><span class="sxs-lookup"><span data-stu-id="dd626-120">**Technical Details:** The App-V 5.1 package converter will save the App-V 4.6 installation root folder and short folder names in the FilesystemMetadata.xml file in the Filesystem element.</span></span> <span data-ttu-id="dd626-121">當 App-v 5.1 用戶端建立虛擬流程時，它會將 App-v 4.6 安裝根的要求對應至虛擬檔案系統根目錄。</span><span class="sxs-lookup"><span data-stu-id="dd626-121">When the App-V 5.1 client creates the virtual process, it will map requests from the App-V 4.6 installation root to the virtual file system root.</span></span>

**<span data-ttu-id="dd626-122">開始使用</span><span class="sxs-lookup"><span data-stu-id="dd626-122">Getting started</span></span>**

1.  <span data-ttu-id="dd626-123">在您的環境中的電腦上安裝 app-v 排序器。</span><span class="sxs-lookup"><span data-stu-id="dd626-123">Install the App-V Sequencer on a computer in your environment.</span></span> <span data-ttu-id="dd626-124">如需如何安裝排序器的詳細資訊，請參閱[如何安裝排序](how-to-install-the-sequencer-51beta-gb18030.md)器。</span><span class="sxs-lookup"><span data-stu-id="dd626-124">For information about how to install the Sequencer, see [How to Install the Sequencer](how-to-install-the-sequencer-51beta-gb18030.md).</span></span>

2.  

    <span data-ttu-id="dd626-125">可使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="dd626-125">The following cmdlets are available:</span></span>

    -   <span data-ttu-id="dd626-126">Test-AppvLegacyPackage –此 Cmdlet 專用來檢查套件。</span><span class="sxs-lookup"><span data-stu-id="dd626-126">Test-AppvLegacyPackage – This cmdlet is designed to check packages.</span></span> <span data-ttu-id="dd626-127">它會傳回有關套件任何失敗的資訊，例如缺少**的 sft**檔案、不正確來源、 **osd**檔案錯誤，或套件版本無效。</span><span class="sxs-lookup"><span data-stu-id="dd626-127">It will return information about any failures with the package such as missing **.sft** files, an invalid source, **.osd** file errors, or invalid package version.</span></span> <span data-ttu-id="dd626-128">這個 Cmdlet 不會分析**sft**檔案或執行任何深度驗證。</span><span class="sxs-lookup"><span data-stu-id="dd626-128">This cmdlet will not parse the **.sft** file or do any in depth validation.</span></span> <span data-ttu-id="dd626-129">如需此 Cmdlet 之選項和基本功能的相關資訊，請使用 PowerShell cmdline 輸入 `Test-AppvLegacyPackage -?` 。</span><span class="sxs-lookup"><span data-stu-id="dd626-129">For information about options and basic functionality for this cmdlet, using the PowerShell cmdline, type `Test-AppvLegacyPackage -?`.</span></span>

    -   <span data-ttu-id="dd626-130">ConvertFrom-AppvLegacyPackage –若要轉換現有的套件，請輸入 `ConvertFrom-AppvLegacyPackage c:\contentStore c:\convertedPackages` 。</span><span class="sxs-lookup"><span data-stu-id="dd626-130">ConvertFrom-AppvLegacyPackage – To convert an existing package, type `ConvertFrom-AppvLegacyPackage c:\contentStore c:\convertedPackages`.</span></span> <span data-ttu-id="dd626-131">在這個命令中，會 `c:\contentStore` 代表現有套件的位置，也 `c:\convertedPackages` 就是將儲存產生的 app-v 5.1 虛擬應用程式套件檔案的輸出目錄。</span><span class="sxs-lookup"><span data-stu-id="dd626-131">In this command, `c:\contentStore` represents the location of the existing package and `c:\convertedPackages` is the output directory to which the resulting App-V 5.1 virtual application package file will be saved.</span></span> <span data-ttu-id="dd626-132">根據預設，如果您沒有指定新名稱，舊的套件名稱將會用於 App-v 5.1 檔案名。</span><span class="sxs-lookup"><span data-stu-id="dd626-132">By default, if you do not specify a new name, the old package name will be used for the App-V 5.1 filename.</span></span>

        <span data-ttu-id="dd626-133">此外，套件轉換器會將應用程式的套件設定為串流式 App-v 套件，以優化 App-v 5.1 中套件的效能。</span><span class="sxs-lookup"><span data-stu-id="dd626-133">Additionally, the package converter optimizes performance of packages in App-V 5.1 by setting the package to stream fault the App-V package.</span></span>  <span data-ttu-id="dd626-134">這比主要功能區塊更具性能，且完全下載套件。</span><span class="sxs-lookup"><span data-stu-id="dd626-134">This is more performant than the primary feature block and fully downloading the package.</span></span> <span data-ttu-id="dd626-135">[旗標**DownloadFullPackageOnFirstLaunch** ] 可讓您轉換套件，並將預設的套件設定為完全下載。</span><span class="sxs-lookup"><span data-stu-id="dd626-135">The flag **DownloadFullPackageOnFirstLaunch** allows you to convert the package and set the package to be fully downloaded by default.</span></span>

        **<span data-ttu-id="dd626-136">注意</span><span class="sxs-lookup"><span data-stu-id="dd626-136">Note</span></span>**  
        <span data-ttu-id="dd626-137">在您指定輸出目錄之前，您必須先建立輸出目錄。</span><span class="sxs-lookup"><span data-stu-id="dd626-137">Before you specify the output directory, you must create the output directory.</span></span>



~~~
**Advanced Conversion Tips**

-   Piping - PowerShell supports piping. Piping allows you to call `dir c:\contentStore\myPackage | Test-AppvLegacyPackage`. In this example, the directory object that represents `myPackage` will be given as input to the `Test-AppvLegacyPackage` command and bound to the `-Source` parameter. Piping like this is especially useful when you want to batch commands together; for example, `dir .\ | Test-AppvLegacyPackage | ConvertFrom-AppvLegacyAppvPackage -Target .\ConvertedPackages`. This piped command would test the packages and then pass those objects on to actually be converted. You can also apply a filter on packages without errors or only specify a directory which contains an **.sprj** file or pipe them to another cmdlet that adds the filtered package to the server or publishes them to the App-V 5.1 client.

-   Batching - The PowerShell command enables batching. More specifically, the cmdlets support taking a string\[\] object for the `-Source` parameter which represents a list of directory paths. This allows you to enter `$packages = dir c:\contentStore` and then call `ConvertFrom-AppvLegacyAppvPackage-Source $packages -Target c:\ConvertedPackages` or to use piping and call `dir c:\ContentStore | ConvertFrom-AppvLegacyAppvPackage -Target C:\ConvertedPackages`.

-   Other functionality - PowerShell has other built-in functionality for features such as aliases, piping, lazy-binding, .NET object, and many others. All of these are usable in PowerShell and can help you create advanced scenarios for the Package Converter.

**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## <span data-ttu-id="dd626-138">相關主題</span><span class="sxs-lookup"><span data-stu-id="dd626-138">Related topics</span></span>


[<span data-ttu-id="dd626-139">App-V 5.1 作業</span><span class="sxs-lookup"><span data-stu-id="dd626-139">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)









