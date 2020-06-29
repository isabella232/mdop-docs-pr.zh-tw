---
title: 如何部署 DaRT 復原映像做為修復磁碟分割的一部分
description: 如何部署 DaRT 復原映像做為修復磁碟分割的一部分
author: dansimp
ms.assetid: 0d2192c1-4058-49fb-b0b6-baf4699ac7f5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: bc5f295d35dff1e4fc2a84c47188be40153b85c6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800251"
---
# <span data-ttu-id="b0521-103">如何部署 DaRT 復原映像做為修復磁碟分割的一部分</span><span class="sxs-lookup"><span data-stu-id="b0521-103">How to Deploy the DaRT Recovery Image as Part of a Recovery Partition</span></span>


<span data-ttu-id="b0521-104">當您執行完 Microsoft Diagnostics 與復原工具集（DaRT）10復原映射嚮導並建立復原映像之後，您可以從 ISO 映像檔中解壓縮 boot.ini 檔案，並將它部署為 Windows 10 影像中的復原分區。</span><span class="sxs-lookup"><span data-stu-id="b0521-104">After you have finished running the Microsoft Diagnostics and Recovery Toolset (DaRT) 10 Recovery Image wizard and created the recovery image, you can extract the boot.wim file from the ISO image file and deploy it as a recovery partition in a Windows 10 image.</span></span> <span data-ttu-id="b0521-105">建議使用分區，因為任何使 Windows 作業系統無法啟動的損壞問題，也會阻止復原映射的啟動。</span><span class="sxs-lookup"><span data-stu-id="b0521-105">A partition is recommended, because any corruption issues that prevent the Windows operating system from starting would also prevent the recovery image from starting.</span></span> <span data-ttu-id="b0521-106">個別的分區也不需要提供兩次 BitLocker 復原金鑰了。</span><span class="sxs-lookup"><span data-stu-id="b0521-106">A separate partition also eliminates the need to provide the BitLocker recovery key twice.</span></span> <span data-ttu-id="b0521-107">考慮隱藏式磁碟分割，避免使用者在檔案上儲存檔案。</span><span class="sxs-lookup"><span data-stu-id="b0521-107">Consider hiding the partition to prevent users from storing files on it.</span></span>

**<span data-ttu-id="b0521-108">在 Windows 10 影像的 [恢復] 分區中部署 DaRT</span><span class="sxs-lookup"><span data-stu-id="b0521-108">To deploy DaRT in the recovery partition of a Windows 10 image</span></span>**

1.  <span data-ttu-id="b0521-109">在您的 Windows 10 影像中建立一個等於或大於您使用**DaRT 10 [復原映像] 嚮導**所建立之 ISO 映像檔案大小的目標磁碟分割。</span><span class="sxs-lookup"><span data-stu-id="b0521-109">Create a target partition in your Windows 10 image that is equal to or greater than the size of the ISO image file that you created by using the **DaRT 10 Recovery Image wizard**.</span></span>

    <span data-ttu-id="b0521-110">DaRT 分區所需的最小大小是500MB，以適應 DaRT 中的遠端連線功能。</span><span class="sxs-lookup"><span data-stu-id="b0521-110">The minimum size required for a DaRT partition is 500MB to accommodate the remote connection functionality in DaRT.</span></span>

2.  <span data-ttu-id="b0521-111">從 DaRT ISO 映像檔解壓縮啟動 .wim 檔案。</span><span class="sxs-lookup"><span data-stu-id="b0521-111">Extract the boot.wim file from the DaRT ISO image file.</span></span>

    1.  <span data-ttu-id="b0521-112">使用您公司的慣用方法，裝載您在 [**建立啟動映射**] 頁面上建立的 ISO 映像檔。</span><span class="sxs-lookup"><span data-stu-id="b0521-112">Using your company’s preferred method, mount the ISO image file that you created on the **Create Startup Image** page.</span></span>

    2.  <span data-ttu-id="b0521-113">開啟 ISO 映像檔，然後從裝載的影像中的 [\\sources] 資料夾將 boot.ini 檔案複製到電腦上或外部磁片磁碟機上的位置。</span><span class="sxs-lookup"><span data-stu-id="b0521-113">Open the ISO image file and copy the boot.wim file from the \\sources folder in the mounted image to a location on your computer or on an external drive.</span></span>

        <span data-ttu-id="b0521-114">**記事** 如果您燒錄了復原影像的 CD、DVD 或 USB，您可以在移除的媒體上開啟檔案，然後從 \\sources 資料夾中複製 boot.ini 檔案。</span><span class="sxs-lookup"><span data-stu-id="b0521-114">**Note** If you burned a CD, DVD, or USB of the recovery image, you can open the files on the removable media and copy the boot.wim file from the \\sources folder.</span></span> <span data-ttu-id="b0521-115">如果您複製 boot.ini 檔案，就不需要裝載影像。</span><span class="sxs-lookup"><span data-stu-id="b0521-115">If you copy boot.wim file, you don’t need to mount the image.</span></span>

         

3.  <span data-ttu-id="b0521-116">使用 boot.ini 檔案，透過您公司的標準方法建立自訂的 Windows RE 影像，以建立可引導的復原分區。</span><span class="sxs-lookup"><span data-stu-id="b0521-116">Use the boot.wim file to create a bootable recovery partition by using your company’s standard method for creating a custom Windows RE image.</span></span>

    <span data-ttu-id="b0521-117">如需如何建立或自訂恢復分區的詳細資訊，請參閱[自訂 WINDOWS RE 體驗](https://go.microsoft.com/fwlink/?LinkId=214222)。</span><span class="sxs-lookup"><span data-stu-id="b0521-117">For more information about how to create or customize a recovery partition, see [Customizing the Windows RE Experience](https://go.microsoft.com/fwlink/?LinkId=214222).</span></span>

4.  <span data-ttu-id="b0521-118">使用 [恢復] 分區取代 Windows 10 影像中的目標分區。</span><span class="sxs-lookup"><span data-stu-id="b0521-118">Replace the target partition in your Windows 10 image with the recovery partition.</span></span>

    <span data-ttu-id="b0521-119">如需有關如何部署恢復解決方案以在系統發生故障時重新安裝 factory 映射的詳細資訊，請參閱[部署系統復原影像](https://go.microsoft.com/fwlink/?LinkId=214221)。</span><span class="sxs-lookup"><span data-stu-id="b0521-119">For more information about how to deploy a recovery solution to reinstall the factory image in the event of a system failure, see [Deploy a System Recovery Image](https://go.microsoft.com/fwlink/?LinkId=214221).</span></span>

## <span data-ttu-id="b0521-120">相關主題</span><span class="sxs-lookup"><span data-stu-id="b0521-120">Related topics</span></span>


[<span data-ttu-id="b0521-121">建立 DaRT 10 復原映像</span><span class="sxs-lookup"><span data-stu-id="b0521-121">Creating the DaRT 10 Recovery Image</span></span>](creating-the-dart-10-recovery-image.md)

[<span data-ttu-id="b0521-122">部署 DaRT 復原映像</span><span class="sxs-lookup"><span data-stu-id="b0521-122">Deploying the DaRT Recovery Image</span></span>](deploying-the-dart-recovery-image-dart-10.md)

[<span data-ttu-id="b0521-123">規劃 DaRT 10</span><span class="sxs-lookup"><span data-stu-id="b0521-123">Planning for DaRT 10</span></span>](planning-for-dart-10.md)

 

 





