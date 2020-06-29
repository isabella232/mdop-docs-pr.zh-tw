---
title: '[應用程式虛擬化順序] 嚮導 [高級選項] 頁面'
description: '[應用程式虛擬化順序] 嚮導 [高級選項] 頁面'
author: dansimp
ms.assetid: 2c4c5d95-d55e-463d-a851-8486f6a724f2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 716fa27852f1cadfebec31a267ce1b9b581b8ff7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802281"
---
# <span data-ttu-id="663b9-103">[應用程式虛擬化順序] 嚮導 [高級選項] 頁面</span><span class="sxs-lookup"><span data-stu-id="663b9-103">Application Virtualization Sequencing Wizard Advanced Options Page</span></span>


<span data-ttu-id="663b9-104">使用 [應用程式虛擬化（App-v）順序嚮導] 的 [**高級選項**] 頁面，來指定要安裝之應用程式的高級選項。</span><span class="sxs-lookup"><span data-stu-id="663b9-104">Use the **Advanced Options** page of the Application Virtualization (App-V) Sequencing Wizard to specify advanced options for the application to be installed.</span></span> <span data-ttu-id="663b9-105">此頁面包含下表所述的元素。</span><span class="sxs-lookup"><span data-stu-id="663b9-105">The page contains the elements described in the following table.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="663b9-106">名稱</span><span class="sxs-lookup"><span data-stu-id="663b9-106">Name</span></span></th>
<th align="left"><span data-ttu-id="663b9-107">描述</span><span class="sxs-lookup"><span data-stu-id="663b9-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="663b9-108">區塊大小</span><span class="sxs-lookup"><span data-stu-id="663b9-108">Block Size</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="663b9-109">用來指定當您在網路上傳送時，要將 SFT 檔案分成多個區塊的大小。</span><span class="sxs-lookup"><span data-stu-id="663b9-109">Use to specify the size of blocks that the SFT file will be divided into when streamed across a network.</span></span> <span data-ttu-id="663b9-110">所有區塊都等於指定大小;不過，最後一個區塊可能小於指定的大小。</span><span class="sxs-lookup"><span data-stu-id="663b9-110">All blocks equal the specified size; however, the last block might be smaller than specified.</span></span> <span data-ttu-id="663b9-111">選取下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="663b9-111">Select one of the following values:</span></span></p>
<ul>
<li><p><strong><span data-ttu-id="663b9-112">4 KB</span><span class="sxs-lookup"><span data-stu-id="663b9-112">4 KB</span></span></strong></p></li>
<li><p><strong><span data-ttu-id="663b9-113">16 KB</span><span class="sxs-lookup"><span data-stu-id="663b9-113">16 KB</span></span></strong></p></li>
<li><p><strong><span data-ttu-id="663b9-114">32 KB</span><span class="sxs-lookup"><span data-stu-id="663b9-114">32 KB</span></span></strong></p></li>
<li><p><strong><span data-ttu-id="663b9-115">64 KB</span><span class="sxs-lookup"><span data-stu-id="663b9-115">64 KB</span></span></strong></p></li>
</ul>
<div class="alert">
<strong><span data-ttu-id="663b9-116">注意</span><span class="sxs-lookup"><span data-stu-id="663b9-116">Note</span></span></strong><br/><p><span data-ttu-id="663b9-117">當您選取區塊大小時，請考慮 SFT 檔案和網路頻寬的大小。</span><span class="sxs-lookup"><span data-stu-id="663b9-117">When you select a block size, consider the size of the SFT file and your network bandwidth.</span></span> <span data-ttu-id="663b9-118">區塊大小較小的檔案需要較長的時間，才能在網路上傳輸，但較少佔用頻寬。</span><span class="sxs-lookup"><span data-stu-id="663b9-118">A file with a smaller block size takes longer to stream over the network but is less bandwidth-intensive.</span></span> <span data-ttu-id="663b9-119">區塊大小較大的檔案速度可能較快，但使用的網路頻寬更多。</span><span class="sxs-lookup"><span data-stu-id="663b9-119">Files with larger block sizes might stream faster, but they use more network bandwidth.</span></span> <span data-ttu-id="663b9-120">透過實驗，您可以探索您網路上的資料流程應用程式的最佳區塊大小。</span><span class="sxs-lookup"><span data-stu-id="663b9-120">Through experimentation, you can discover the optimum block size for streaming applications on your network.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="663b9-121">在監視期間啟用 Microsoft 更新</span><span class="sxs-lookup"><span data-stu-id="663b9-121">Enable Microsoft Update During Monitoring</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="663b9-122">允許在順序嚮導&#39;s 監視階段中安裝 Microsoft 更新。</span><span class="sxs-lookup"><span data-stu-id="663b9-122">Enables installation of Microsoft Updates during the Sequencing Wizard&#39;s monitoring phase.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="663b9-123">變基 Dll</span><span class="sxs-lookup"><span data-stu-id="663b9-123">Rebase DLLs</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="663b9-124">可將支援的動態連結程式庫重新映射到 RAM 中的連續空間，儲存記憶體並改善效能。</span><span class="sxs-lookup"><span data-stu-id="663b9-124">Enables remapping of supported dynamic-link libraries to a contiguous space in RAM, saving memory and improving performance.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="663b9-125">向後</span><span class="sxs-lookup"><span data-stu-id="663b9-125">Back</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="663b9-126">存取 [排序] 嚮導&#39;s 前頁]。</span><span class="sxs-lookup"><span data-stu-id="663b9-126">Accesses the Sequencing Wizard&#39;s previous page.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="663b9-127">下一則</span><span class="sxs-lookup"><span data-stu-id="663b9-127">Next</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="663b9-128">存取 [順序] 嚮導&#39;s [下一頁]。</span><span class="sxs-lookup"><span data-stu-id="663b9-128">Accesses the Sequencing Wizard&#39;s next page.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="663b9-129">取消</span><span class="sxs-lookup"><span data-stu-id="663b9-129">Cancel</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="663b9-130">[結束排序嚮導] 的操作。</span><span class="sxs-lookup"><span data-stu-id="663b9-130">Terminates operation of the Sequencing Wizard.</span></span></p></td>
</tr>
</tbody>
</table>



<span data-ttu-id="663b9-131">\ [範本標記值 \]</span><span class="sxs-lookup"><span data-stu-id="663b9-131">\[Template Token Value\]</span></span>

<span data-ttu-id="663b9-132">使用 App-v 先後順序嚮導的 [**高級選項**] 頁面，來指定您要排序之應用程式的高級選項。</span><span class="sxs-lookup"><span data-stu-id="663b9-132">Use the **Advanced Options** page of the App-V Sequencing Wizard to specify advanced options for the application you are sequencing.</span></span> <span data-ttu-id="663b9-133">此頁面包含下表所述的元素。</span><span class="sxs-lookup"><span data-stu-id="663b9-133">This page contains the elements described in the following table.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="663b9-134">名稱</span><span class="sxs-lookup"><span data-stu-id="663b9-134">Name</span></span></th>
<th align="left"><span data-ttu-id="663b9-135">描述</span><span class="sxs-lookup"><span data-stu-id="663b9-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="663b9-136">允許 Microsoft Update 在監視期間執行</span><span class="sxs-lookup"><span data-stu-id="663b9-136">Allow Microsoft Update to run during monitoring</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="663b9-137">指定是否要在應用程式排序期間的監視階段，將軟體更新套用到應用程式。</span><span class="sxs-lookup"><span data-stu-id="663b9-137">Specifies whether software updates will be applied to the application during the monitoring phase of application sequencing.</span></span> <span data-ttu-id="663b9-138">如果需要更新才能成功完成應用程式安裝，此選項很有説明。</span><span class="sxs-lookup"><span data-stu-id="663b9-138">This option is helpful if updates are required to successfully complete the application installation.</span></span> <span data-ttu-id="663b9-139">預設不會選取此選項。</span><span class="sxs-lookup"><span data-stu-id="663b9-139">This option is not selected by default.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="663b9-140">變基 Dll</span><span class="sxs-lookup"><span data-stu-id="663b9-140">Rebase Dlls</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="663b9-141">可將支援的動態連結程式庫重新映射至 RAM 中的連續空間。</span><span class="sxs-lookup"><span data-stu-id="663b9-141">Enables remapping of supported dynamic-link libraries to a contiguous space in RAM.</span></span> <span data-ttu-id="663b9-142">選取此選項可協助管理記憶體，並改善應用程式的效能。</span><span class="sxs-lookup"><span data-stu-id="663b9-142">Selecting this option can help manage memory and improve application performance.</span></span> <span data-ttu-id="663b9-143">預設不會選取此選項。</span><span class="sxs-lookup"><span data-stu-id="663b9-143">This option is not selected by default.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="663b9-144">向後</span><span class="sxs-lookup"><span data-stu-id="663b9-144">Back</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="663b9-145">移至上一頁的嚮導。</span><span class="sxs-lookup"><span data-stu-id="663b9-145">Goes to the previous page of the wizard.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="663b9-146">下一則</span><span class="sxs-lookup"><span data-stu-id="663b9-146">Next</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="663b9-147">移至嚮導的下一個頁面。</span><span class="sxs-lookup"><span data-stu-id="663b9-147">Goes to the next page of the wizard.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="663b9-148">取消</span><span class="sxs-lookup"><span data-stu-id="663b9-148">Cancel</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="663b9-149">捨棄設定並退出嚮導。</span><span class="sxs-lookup"><span data-stu-id="663b9-149">Discards the settings and exits the wizard.</span></span></p></td>
</tr>
</tbody>
</table>



<span data-ttu-id="663b9-150">\ [範本標記值 \]</span><span class="sxs-lookup"><span data-stu-id="663b9-150">\[Template Token Value\]</span></span>

## <span data-ttu-id="663b9-151">相關主題</span><span class="sxs-lookup"><span data-stu-id="663b9-151">Related topics</span></span>


[<span data-ttu-id="663b9-152">排序精靈</span><span class="sxs-lookup"><span data-stu-id="663b9-152">Sequencing Wizard</span></span>](sequencing-wizard.md)









