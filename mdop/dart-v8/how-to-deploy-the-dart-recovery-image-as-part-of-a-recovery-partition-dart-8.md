---
title: 如何部署 DaRT 復原映像做為修復磁碟分割的一部分
description: 如何部署 DaRT 復原映像做為修復磁碟分割的一部分
author: dansimp
ms.assetid: 07c5d539-51d9-4759-adc7-72b40d5d7bb3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: e3647d684f64a0635e2875314498bde841204369
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810521"
---
# <span data-ttu-id="962c1-103">如何部署 DaRT 復原映像做為修復磁碟分割的一部分</span><span class="sxs-lookup"><span data-stu-id="962c1-103">How to Deploy the DaRT Recovery Image as Part of a Recovery Partition</span></span>


<span data-ttu-id="962c1-104">當您執行完 Microsoft Diagnostics 與復原工具集（DaRT）8.0 恢復鏡像嚮導並建立復原影像之後，您可以從 ISO 映像檔中解壓縮 boot.ini 檔案，並將它部署為 Windows 8 影像中的復原分區。</span><span class="sxs-lookup"><span data-stu-id="962c1-104">After you have finished running the Microsoft Diagnostics and Recovery Toolset (DaRT) 8.0 Recovery Image wizard and created the recovery image, you can extract the boot.wim file from the ISO image file and deploy it as a recovery partition in a Windows 8 image.</span></span> <span data-ttu-id="962c1-105">建議使用分區，因為任何使 Windows 作業系統無法啟動的損壞問題，也會阻止復原映射的啟動。</span><span class="sxs-lookup"><span data-stu-id="962c1-105">A partition is recommended, because any corruption issues that prevent the Windows operating system from starting would also prevent the recovery image from starting.</span></span> <span data-ttu-id="962c1-106">個別的分區也不需要提供兩次 BitLocker 復原金鑰了。</span><span class="sxs-lookup"><span data-stu-id="962c1-106">A separate partition also eliminates the need to provide the BitLocker recovery key twice.</span></span> <span data-ttu-id="962c1-107">考慮隱藏式磁碟分割，避免使用者在檔案上儲存檔案。</span><span class="sxs-lookup"><span data-stu-id="962c1-107">Consider hiding the partition to prevent users from storing files on it.</span></span>

**<span data-ttu-id="962c1-108">在 Windows 8 映射的 [恢復] 分區中部署 DaRT</span><span class="sxs-lookup"><span data-stu-id="962c1-108">To deploy DaRT in the recovery partition of a Windows 8 image</span></span>**

1.  <span data-ttu-id="962c1-109">在您的 Windows 8 映射中建立一個等於或大於您使用**DaRT 8.0 [復原映像] 嚮導**所建立之 ISO 映像檔案大小的目標磁碟分割。</span><span class="sxs-lookup"><span data-stu-id="962c1-109">Create a target partition in your Windows 8 image that is equal to or greater than the size of the ISO image file that you created by using the **DaRT 8.0 Recovery Image wizard**.</span></span>

    <span data-ttu-id="962c1-110">DaRT 分區所需的最小大小是500MB，以適應 DaRT 中的遠端連線功能。</span><span class="sxs-lookup"><span data-stu-id="962c1-110">The minimum size required for a DaRT partition is 500MB to accommodate the remote connection functionality in DaRT.</span></span>

2.  <span data-ttu-id="962c1-111">從 DaRT ISO 映像檔解壓縮啟動 .wim 檔案。</span><span class="sxs-lookup"><span data-stu-id="962c1-111">Extract the boot.wim file from the DaRT ISO image file.</span></span>

    1.  <span data-ttu-id="962c1-112">使用您公司的慣用方法，裝載您在 [**建立啟動映射**] 頁面上建立的 ISO 映像檔。</span><span class="sxs-lookup"><span data-stu-id="962c1-112">Using your company’s preferred method, mount the ISO image file that you created on the **Create Startup Image** page.</span></span>

    2.  <span data-ttu-id="962c1-113">開啟 ISO 映像檔，然後從裝載的影像中的 [\\sources] 資料夾將 boot.ini 檔案複製到電腦上或外部磁片磁碟機上的位置。</span><span class="sxs-lookup"><span data-stu-id="962c1-113">Open the ISO image file and copy the boot.wim file from the \\sources folder in the mounted image to a location on your computer or on an external drive.</span></span>

        <span data-ttu-id="962c1-114">**記事** 如果您燒錄了復原影像的 CD、DVD 或 USB，您可以在移除的媒體上開啟檔案，然後從 \\sources 資料夾中複製 boot.ini 檔案。</span><span class="sxs-lookup"><span data-stu-id="962c1-114">**Note** If you burned a CD, DVD, or USB of the recovery image, you can open the files on the removable media and copy the boot.wim file from the \\sources folder.</span></span> <span data-ttu-id="962c1-115">如果您複製 boot.ini 檔案，就不需要裝載影像。</span><span class="sxs-lookup"><span data-stu-id="962c1-115">If you copy boot.wim file, you don’t need to mount the image.</span></span>

         

3.  <span data-ttu-id="962c1-116">使用 boot.ini 檔案，透過您公司的標準方法建立自訂的 Windows RE 影像，以建立可引導的復原分區。</span><span class="sxs-lookup"><span data-stu-id="962c1-116">Use the boot.wim file to create a bootable recovery partition by using your company’s standard method for creating a custom Windows RE image.</span></span>

    <span data-ttu-id="962c1-117">如需如何建立或自訂恢復分區的詳細資訊，請參閱[自訂 WINDOWS RE 體驗](https://go.microsoft.com/fwlink/?LinkId=214222)。</span><span class="sxs-lookup"><span data-stu-id="962c1-117">For more information about how to create or customize a recovery partition, see [Customizing the Windows RE Experience](https://go.microsoft.com/fwlink/?LinkId=214222).</span></span>

4.  <span data-ttu-id="962c1-118">使用 [恢復] 分區取代 Windows 8 映射中的目標分區。</span><span class="sxs-lookup"><span data-stu-id="962c1-118">Replace the target partition in your Windows 8 image with the recovery partition.</span></span>

    <span data-ttu-id="962c1-119">如需有關如何部署恢復解決方案以在系統發生故障時重新安裝 factory 映射的詳細資訊，請參閱[部署系統復原影像](https://go.microsoft.com/fwlink/?LinkId=214221)。</span><span class="sxs-lookup"><span data-stu-id="962c1-119">For more information about how to deploy a recovery solution to reinstall the factory image in the event of a system failure, see [Deploy a System Recovery Image](https://go.microsoft.com/fwlink/?LinkId=214221).</span></span>

## <span data-ttu-id="962c1-120">相關主題</span><span class="sxs-lookup"><span data-stu-id="962c1-120">Related topics</span></span>


[<span data-ttu-id="962c1-121">建立 DaRT 8.0 復原映像</span><span class="sxs-lookup"><span data-stu-id="962c1-121">Creating the DaRT 8.0 Recovery Image</span></span>](creating-the-dart-80-recovery-image-dart-8.md)

[<span data-ttu-id="962c1-122">部署 DaRT 復原映像</span><span class="sxs-lookup"><span data-stu-id="962c1-122">Deploying the DaRT Recovery Image</span></span>](deploying-the-dart-recovery-image-dart-8.md)

[<span data-ttu-id="962c1-123">規劃 DaRT 8.0</span><span class="sxs-lookup"><span data-stu-id="962c1-123">Planning for DaRT 8.0</span></span>](planning-for-dart-80-dart-8.md)

 

 





