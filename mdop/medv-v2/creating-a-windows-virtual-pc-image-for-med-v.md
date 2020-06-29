---
title: 建立 MED-V 的 Windows 虛擬電腦映像
description: 建立 MED-V 的 Windows 虛擬電腦映像
author: dansimp
ms.assetid: fd7c0b1a-0769-4e7b-ad1a-dad19cca081f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: f947479776e84a4c54edb10d583dd21d7ccf6f43
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800155"
---
# <span data-ttu-id="10050-103">建立 MED-V 的 Windows 虛擬電腦映像</span><span class="sxs-lookup"><span data-stu-id="10050-103">Creating a Windows Virtual PC Image for MED-V</span></span>


<span data-ttu-id="10050-104">在您可以將 MED-V 工作區傳送給使用者之前，您必須先準備好虛擬硬碟，以便為 Microsoft 企業版桌面虛擬化（MED-V）2.0 建立 MED-V 工作區安裝程式套件。</span><span class="sxs-lookup"><span data-stu-id="10050-104">Before you can deliver a MED-V workspace to users, you have to first prepare a virtual hard disk that you use to build the MED-V workspace installer package for Microsoft Enterprise Desktop Virtualization (MED-V) 2.0.</span></span> <span data-ttu-id="10050-105">若要準備必要的虛擬硬碟，您必須建立包含所需作業系統、更新和軟體的 Windows 虛擬電腦影像，讓您稍後將應用程式和 URL 重新導向資訊部署給使用者。</span><span class="sxs-lookup"><span data-stu-id="10050-105">To prepare the necessary virtual hard disk, you must create a Windows Virtual PC image that contains the required operating system, updates, and software to let you later deploy applications and URL redirection information to users.</span></span> <span data-ttu-id="10050-106">本節提供有關如何建立虛擬硬碟的指導方針。</span><span class="sxs-lookup"><span data-stu-id="10050-106">This section provides guidance about how to create the virtual hard disk.</span></span>

<span data-ttu-id="10050-107">若要建立 MED-V 的虛擬影像，您必須遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="10050-107">To create a virtual image for MED-V, you must follow these steps.</span></span>

1.  [<span data-ttu-id="10050-108">建立 Windows 虛擬電腦影像</span><span class="sxs-lookup"><span data-stu-id="10050-108">Create a Windows Virtual PC image</span></span>](#bkmk-creatingavirtualmachinebyusingmicrosoftvirtualpc)

2.  [<span data-ttu-id="10050-109">在影像上安裝 Windows XP</span><span class="sxs-lookup"><span data-stu-id="10050-109">Install Windows XP on the image</span></span>](#bkmk-installingwindowsxpontovpc)

3.  [<span data-ttu-id="10050-110">在影像上安裝 .NET Framework</span><span class="sxs-lookup"><span data-stu-id="10050-110">Install the .NET Framework on the image</span></span>](#bkmk-installingnet)

4.  [<span data-ttu-id="10050-111">將更新套用至影像</span><span class="sxs-lookup"><span data-stu-id="10050-111">Apply updates to the image</span></span>](#bkmk-applypatchestovpc)

5.  [<span data-ttu-id="10050-112">安裝整合元件</span><span class="sxs-lookup"><span data-stu-id="10050-112">Install Integration Components</span></span>](#bkmk-installintegration)

## <a href="" id="bkmk-creatingavirtualmachinebyusingmicrosoftvirtualpc"></a><span data-ttu-id="10050-113">建立 Windows 虛擬電腦影像</span><span class="sxs-lookup"><span data-stu-id="10050-113">Creating a Windows Virtual PC Image</span></span>


<span data-ttu-id="10050-114">若要建立 Windows 虛擬電腦映射，請參閱 Windows 虛擬電腦檔：</span><span class="sxs-lookup"><span data-stu-id="10050-114">To create a Windows Virtual PC image, see the Windows Virtual PC documentation:</span></span>

-   <span data-ttu-id="10050-115">[Windows 虛擬 PC 首頁](https://go.microsoft.com/fwlink/?LinkId=148103)（ https://go.microsoft.com/fwlink/?LinkId=148103) 。</span><span class="sxs-lookup"><span data-stu-id="10050-115">[Windows Virtual PC Home Page](https://go.microsoft.com/fwlink/?LinkId=148103) (https://go.microsoft.com/fwlink/?LinkId=148103).</span></span>

-   <span data-ttu-id="10050-116">[Windows 虛擬電腦](https://go.microsoft.com/fwlink/?LinkId=182378)說明（ https://go.microsoft.com/fwlink/?LinkId=182378) 。</span><span class="sxs-lookup"><span data-stu-id="10050-116">[Windows Virtual PC Help](https://go.microsoft.com/fwlink/?LinkId=182378) (https://go.microsoft.com/fwlink/?LinkId=182378).</span></span>

<span data-ttu-id="10050-117">或者，如果您已經有想要用來做為虛擬影像基礎的 Windows Imaging （WIM）檔案，您可以將它轉換成您用來建立 MED-V 工作區的 VHD。</span><span class="sxs-lookup"><span data-stu-id="10050-117">Alternately, if you already have a Windows Imaging (WIM) file that you want to use as the basis for your virtual image, you can convert it to a VHD that you use to build the MED-V workspace.</span></span> <span data-ttu-id="10050-118">如需如何將 WIM 轉換成虛擬硬碟的詳細資訊，請參閱[Windows 7 中的原生 VHD 支援](https://go.microsoft.com/fwlink/?LinkId=195922)（ https://go.microsoft.com/fwlink/?LinkId=195922) 。</span><span class="sxs-lookup"><span data-stu-id="10050-118">For more information about how to convert a WIM to a virtual hard disk, see [Native VHD Support in Windows 7](https://go.microsoft.com/fwlink/?LinkId=195922) (https://go.microsoft.com/fwlink/?LinkId=195922).</span></span>

<span data-ttu-id="10050-119">**重要** MED-V 只支援每個虛擬機器一個虛擬硬碟，且每個虛擬磁片上只有一個磁碟分割。</span><span class="sxs-lookup"><span data-stu-id="10050-119">**Important** MED-V only supports one virtual hard disk per virtual machine and only one partition on each virtual disk.</span></span>

 

<span data-ttu-id="10050-120">建立虛擬硬碟之後，請在影像上安裝 Windows XP。</span><span class="sxs-lookup"><span data-stu-id="10050-120">After you have created your virtual hard disk, install Windows XP on the image.</span></span>

## <a href="" id="bkmk-installingwindowsxpontovpc"></a><span data-ttu-id="10050-121">在 Windows 虛擬電腦映射上安裝 Windows XP</span><span class="sxs-lookup"><span data-stu-id="10050-121">Installing Windows XP on a Windows Virtual PC Image</span></span>


<span data-ttu-id="10050-122">在建立 MED-V 工作區前，MED-V 需要在 Windows 虛擬電腦映射上安裝 Windows XP SP3。</span><span class="sxs-lookup"><span data-stu-id="10050-122">MED-V requires that Windows XP SP3 is installed on the Windows Virtual PC image before you build the MED-V workspace.</span></span>

<span data-ttu-id="10050-123">如需如何安裝 Windows XP 的詳細資訊，請參閱[建立虛擬機器並安裝客體作業系統](https://go.microsoft.com/fwlink/?LinkId=182379)（ https://go.microsoft.com/fwlink/?LinkId=182379) 。</span><span class="sxs-lookup"><span data-stu-id="10050-123">For more information about how to install Windows XP, see [Create a virtual machine and install a guest operating system](https://go.microsoft.com/fwlink/?LinkId=182379) (https://go.microsoft.com/fwlink/?LinkId=182379).</span></span>

## <a href="" id="bkmk-installingnet"></a><span data-ttu-id="10050-124">在 Windows 虛擬電腦影像上安裝 .NET Framework 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="10050-124">Installing the .NET Framework 3.5 SP1 on a Windows Virtual PC Image</span></span>


<span data-ttu-id="10050-125">您必須將 .NET Framework 3.5 SP1 和更新 KB959209 手動安裝到您準備搭配 MED-V 使用的 Windows 虛擬電腦映射中。</span><span class="sxs-lookup"><span data-stu-id="10050-125">You must manually install the .NET Framework 3.5 SP1 and the update KB959209 into the Windows Virtual PC image that you prepare for use with MED-V.</span></span> <span data-ttu-id="10050-126">更新[KB959209](https://go.microsoft.com/fwlink/?LinkId=204950) （ https://go.microsoft.com/fwlink/?LinkId=204950) 解決幾個已知的應用程式相容性問題。</span><span class="sxs-lookup"><span data-stu-id="10050-126">The update [KB959209](https://go.microsoft.com/fwlink/?LinkId=204950) (https://go.microsoft.com/fwlink/?LinkId=204950) addresses several known application compatibility issues.</span></span>

## <a href="" id="bkmk-applypatchestovpc"></a><span data-ttu-id="10050-127">將更新套用至 Windows 虛擬電腦影像</span><span class="sxs-lookup"><span data-stu-id="10050-127">Applying Updates to the Windows Virtual PC Image</span></span>


<span data-ttu-id="10050-128">在您的虛擬機器上安裝 Windows XP 之後，請在映射上安裝任何必要的 Windows XP 更新，例如 SP3。</span><span class="sxs-lookup"><span data-stu-id="10050-128">After you have installed Windows XP on your virtual machine, install any required Windows XP updates on the image, such as SP3.</span></span> <span data-ttu-id="10050-129">您也可以安裝特定的選擇性更新，以取得較佳的效能。</span><span class="sxs-lookup"><span data-stu-id="10050-129">You can also install certain optional updates for better performance.</span></span>

<span data-ttu-id="10050-130">**重要** MED-V 需要在客體作業系統上執行 Windows XP SP3。</span><span class="sxs-lookup"><span data-stu-id="10050-130">**Important** MED-V requires that Windows XP SP3 be running on the guest operating system.</span></span>

 

<span data-ttu-id="10050-131">**警告** 當您安裝 Windows XP 的更新時，請確定您已在要在 MED-V 工作區中使用的來賓中保留 Internet Explorer 版本。</span><span class="sxs-lookup"><span data-stu-id="10050-131">**Warning** When you install updates to Windows XP, make sure that you remain on the version of Internet Explorer in the guest that you intend to use in the MED-V workspace.</span></span> <span data-ttu-id="10050-132">例如，如果您想要在 MED-V 工作區中執行 Internet Explorer 6，請確認您目前安裝的任何更新不包括 Internet Explorer 7 或 Internet Explorer 8。</span><span class="sxs-lookup"><span data-stu-id="10050-132">For example, if you intend to run Internet Explorer 6 in the MED-V workspace, make sure that any updates that you install now do not include Internet Explorer 7 or Internet Explorer 8.</span></span> <span data-ttu-id="10050-133">此外，建議您設定登錄，以避免自動更新升級 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="10050-133">In addition, we recommend that you configure the registry to prevent automatic updates from upgrading Internet Explorer.</span></span>

 

### <span data-ttu-id="10050-134">安裝選用的效能更新</span><span class="sxs-lookup"><span data-stu-id="10050-134">Installing an Optional Performance Update</span></span>

<span data-ttu-id="10050-135">雖然是選擇性的，但我們建議您安裝下列[修補程式 KB972435](https://go.microsoft.com/fwlink/?LinkId=201077)更新（ https://go.microsoft.com/fwlink/?LinkId=201077) 。</span><span class="sxs-lookup"><span data-stu-id="10050-135">Although it is optional, we recommend that you install the following update for [hotfix KB972435](https://go.microsoft.com/fwlink/?LinkId=201077) (https://go.microsoft.com/fwlink/?LinkId=201077).</span></span> <span data-ttu-id="10050-136">此更新會提高終端服務會話中共用資料夾的效能：</span><span class="sxs-lookup"><span data-stu-id="10050-136">This update increases the performance of shared folders in a Terminal Services session:</span></span>

<span data-ttu-id="10050-137">**記事** 此更新公開提供。</span><span class="sxs-lookup"><span data-stu-id="10050-137">**Note** The update is publicly available.</span></span> <span data-ttu-id="10050-138">不過，系統可能會提示您接受 Microsoft 服務的合約。</span><span class="sxs-lookup"><span data-stu-id="10050-138">However, you might be prompted to accept an agreement for Microsoft Services.</span></span> <span data-ttu-id="10050-139">依照後續網頁上的提示進行，以取得此熱修復程式。</span><span class="sxs-lookup"><span data-stu-id="10050-139">Follow the prompts on the successive webpages to retrieve this hotfix.</span></span>

 

### <span data-ttu-id="10050-140">設定群組原則效能更新</span><span class="sxs-lookup"><span data-stu-id="10050-140">Configuring a Group Policy Performance Update</span></span>

<span data-ttu-id="10050-141">根據預設，群群組原則一次會下載到電腦一個位元組。</span><span class="sxs-lookup"><span data-stu-id="10050-141">By default, Group Policy is downloaded to a computer one byte at a time.</span></span> <span data-ttu-id="10050-142">當 MED-V 加入網域時，這會造成延遲。</span><span class="sxs-lookup"><span data-stu-id="10050-142">This causes delays while MED-V is being joined to the domain.</span></span> <span data-ttu-id="10050-143">若要提高群組原則的效能，請將下列登錄機碼值設定為 registry：</span><span class="sxs-lookup"><span data-stu-id="10050-143">To increase the performance of Group Policy, set the following registry key value to the registry:</span></span>

<span data-ttu-id="10050-144">登錄子機碼： HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon</span><span class="sxs-lookup"><span data-stu-id="10050-144">Registry subkey: HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon</span></span>

<span data-ttu-id="10050-145">專案： BufferPolicyReads</span><span class="sxs-lookup"><span data-stu-id="10050-145">Entry: BufferPolicyReads</span></span>

<span data-ttu-id="10050-146">類型： DWORD</span><span class="sxs-lookup"><span data-stu-id="10050-146">Type: DWORD</span></span>

<span data-ttu-id="10050-147">值：1</span><span class="sxs-lookup"><span data-stu-id="10050-147">Value: 1</span></span>

## <a href="" id="bkmk-installintegration"></a><span data-ttu-id="10050-148">安裝整合元件</span><span class="sxs-lookup"><span data-stu-id="10050-148">Installing Integration Components</span></span>


<span data-ttu-id="10050-149">Windows 虛擬電腦包含整合元件封裝。</span><span class="sxs-lookup"><span data-stu-id="10050-149">Windows Virtual PC includes the Integration Components package.</span></span> <span data-ttu-id="10050-150">這會提供可改善虛擬環境與物理電腦之間互動的功能。</span><span class="sxs-lookup"><span data-stu-id="10050-150">This provides features that improve the interaction between the virtual environment and the physical computer.</span></span> <span data-ttu-id="10050-151">例如，[整合元件套件] 可讓您在主機和來賓電腦之間移動滑鼠。</span><span class="sxs-lookup"><span data-stu-id="10050-151">For example, the Integration Components package lets your mouse move between the host and the guest computers.</span></span>

<span data-ttu-id="10050-152">**重要** MED-V 需要安裝 [整合元件套件]。</span><span class="sxs-lookup"><span data-stu-id="10050-152">**Important** MED-V requires the installation of the Integration Components package.</span></span>

 

<span data-ttu-id="10050-153">當您將虛擬影像設定為與 MED-V 搭配使用時，您必須在客體作業系統上手動安裝整合元件套件，以建立可供使用的整合功能。</span><span class="sxs-lookup"><span data-stu-id="10050-153">When you configure the virtual image to work with MED-V, you must manually install the Integration Components package on the guest operating system to make the integration features that are available.</span></span>

<span data-ttu-id="10050-154">如需有關如何安裝及使用整合元件套件的詳細資訊，請參閱下列內容：</span><span class="sxs-lookup"><span data-stu-id="10050-154">For more information about how to install and use the Integration Components package, see the following:</span></span>

-   <span data-ttu-id="10050-155">[安裝或升級整合元件套件](https://go.microsoft.com/fwlink/?LinkId=195923)（ https://go.microsoft.com/fwlink/?LinkId=195923) 。</span><span class="sxs-lookup"><span data-stu-id="10050-155">[Install or Upgrade the Integration Components Package](https://go.microsoft.com/fwlink/?LinkId=195923) (https://go.microsoft.com/fwlink/?LinkId=195923).</span></span>

-   <span data-ttu-id="10050-156">[關於整合功能](https://go.microsoft.com/fwlink/?LinkId=195924)（ https://go.microsoft.com/fwlink/?LinkId=195924) 。</span><span class="sxs-lookup"><span data-stu-id="10050-156">[About Integration Features](https://go.microsoft.com/fwlink/?LinkId=195924) (https://go.microsoft.com/fwlink/?LinkId=195924).</span></span>

### <span data-ttu-id="10050-157">安裝 RemoteApp 更新</span><span class="sxs-lookup"><span data-stu-id="10050-157">Installing RemoteApp Update</span></span>

<span data-ttu-id="10050-158">安裝整合元件套件之後，系統會提示您安裝下列更新：「Windows XP SP3 的更新以啟用 RemoteApp」。</span><span class="sxs-lookup"><span data-stu-id="10050-158">After you install the Integration Components package, you are prompted to install the following update: "Update for Windows XP SP3 to enable RemoteApp."</span></span> <span data-ttu-id="10050-159">這是 MED-V 所需的元件。</span><span class="sxs-lookup"><span data-stu-id="10050-159">This is a required component for MED-V.</span></span>

<span data-ttu-id="10050-160">**重要** 如果系統未提示您安裝 RemoteApp 更新，您必須手動下載並安裝。</span><span class="sxs-lookup"><span data-stu-id="10050-160">**Important** If you are not prompted to install the RemoteApp update, you must download and install it manually.</span></span> <span data-ttu-id="10050-161">如需有關如何下載此更新的詳細資訊和指示，請參閱[WINDOWS XP SP3 更新，以啟用 RemoteApp](https://go.microsoft.com/fwlink/?LinkId=195925) （ https://go.microsoft.com/fwlink/?LinkId=195925) 。</span><span class="sxs-lookup"><span data-stu-id="10050-161">For more information and instructions about how to download this update, see [Update for Windows XP SP3 to enable RemoteApp](https://go.microsoft.com/fwlink/?LinkId=195925) (https://go.microsoft.com/fwlink/?LinkId=195925).</span></span>

 

### <span data-ttu-id="10050-162">啟用遠端桌面</span><span class="sxs-lookup"><span data-stu-id="10050-162">Enabling Remote Desktop</span></span>

<span data-ttu-id="10050-163">根據預設，在您安裝整合元件套件之後，就會啟用遠端桌面。</span><span class="sxs-lookup"><span data-stu-id="10050-163">By default, Remote Desktop is enabled after you install the Integration Components package.</span></span> <span data-ttu-id="10050-164">如果 MED-V 要運作，請確定已啟用遠端桌面，而且不要發佈任何停用的群組原則。</span><span class="sxs-lookup"><span data-stu-id="10050-164">For MED-V to be operational, ensure that Remote Desktop is enabled, and do not distribute any Group Policy that disables it.</span></span>

<span data-ttu-id="10050-165">如需如何啟用遠端桌面的相關資訊，請參閱[啟用或停用遠端桌面](https://go.microsoft.com/fwlink/?LinkId=201162)（ https://go.microsoft.com/fwlink/?LinkId=201162) 。</span><span class="sxs-lookup"><span data-stu-id="10050-165">For information about how to enable Remote Desktop, see [Enable or disable Remote Desktop](https://go.microsoft.com/fwlink/?LinkId=201162) (https://go.microsoft.com/fwlink/?LinkId=201162).</span></span>

## <span data-ttu-id="10050-166">使用 Internet Explorer 管理工具組自訂 Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="10050-166">Customizing Internet Explorer by Using the Internet Explorer Administration Kit</span></span>


<span data-ttu-id="10050-167">如有需要，您可以使用 Internet Explorer 管理工具組，在客體作業系統上自訂 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="10050-167">If you want, you can use the Internet Explorer Administration Kit to customize Internet Explorer on the guest operating system.</span></span> <span data-ttu-id="10050-168">如需詳細資訊，請參閱[Internet Explorer 6 管理工具組與部署指南](https://go.microsoft.com/fwlink/?LinkId=200007)（HTTP://go.microsoft.com/fwlink/?LinkId=200007）。</span><span class="sxs-lookup"><span data-stu-id="10050-168">For more information, see the [Internet Explorer 6 Administration Kit and Deployment Guide](https://go.microsoft.com/fwlink/?LinkId=200007) (http:// go.microsoft.com/fwlink/?LinkId=200007).</span></span>

<span data-ttu-id="10050-169">**警告** 您應該考慮在 MED-V 工作區中自訂 Internet Explorer 所帶來的安全性考慮。</span><span class="sxs-lookup"><span data-stu-id="10050-169">**Warning** You should consider security concerns associated with customizing Internet Explorer in the MED-V workspace.</span></span> <span data-ttu-id="10050-170">如需詳細資訊，請參閱[Med-v 運算的安全性最佳作法](security-best-practices-for-med-v-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="10050-170">For more information, see [Security Best Practices for MED-V Operations](security-best-practices-for-med-v-operations.md).</span></span>

 

<span data-ttu-id="10050-171">使用最新的客體作業系統安裝虛擬硬碟之後，您就可以在影像上安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="10050-171">After your virtual hard disk is installed with an up-to-date guest operating system, you can install applications on the image.</span></span>

## <span data-ttu-id="10050-172">相關主題</span><span class="sxs-lookup"><span data-stu-id="10050-172">Related topics</span></span>


[<span data-ttu-id="10050-173">在 Windows 虛擬電腦映像上安裝應用程式</span><span class="sxs-lookup"><span data-stu-id="10050-173">Installing Applications on a Windows Virtual PC Image</span></span>](installing-applications-on-a-windows-virtual-pc-image.md)

[<span data-ttu-id="10050-174">設定 MED-V 的 Windows 虛擬電腦映像</span><span class="sxs-lookup"><span data-stu-id="10050-174">Configuring a Windows Virtual PC Image for MED-V</span></span>](configuring-a-windows-virtual-pc-image-for-med-v.md)

 

 





