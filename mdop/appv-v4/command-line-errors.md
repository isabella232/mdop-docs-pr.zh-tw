---
title: 命令列錯誤
description: 命令列錯誤
author: dansimp
ms.assetid: eea62568-4e90-4877-9cc7-e27ef5c05068
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ab29a77dc15a8c7bd3590b918a7ca8c1ca6e8c0d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802205"
---
# <span data-ttu-id="ab87a-103">命令列錯誤</span><span class="sxs-lookup"><span data-stu-id="ab87a-103">Command-Line Errors</span></span>


<span data-ttu-id="ab87a-104">使用下列錯誤清單來找出命令列排序次序無法正常運作的原因。</span><span class="sxs-lookup"><span data-stu-id="ab87a-104">Use the following list of errors to identify the reasons why command-line sequencing is not working properly.</span></span> <span data-ttu-id="ab87a-105">您也可以透過查看排序器記錄檔，查看這些錯誤。</span><span class="sxs-lookup"><span data-stu-id="ab87a-105">You can also see these errors by viewing the sequencer log file.</span></span>

<span data-ttu-id="ab87a-106">**記事** 排序時可能會顯示一個以上的錯誤。</span><span class="sxs-lookup"><span data-stu-id="ab87a-106">**Note** More than one error might be displayed when sequencing.</span></span> <span data-ttu-id="ab87a-107">此外，顯示的錯誤碼可能是兩個錯誤代碼的總和。</span><span class="sxs-lookup"><span data-stu-id="ab87a-107">Furthermore, the error code displayed might be the sum of two error codes.</span></span> <span data-ttu-id="ab87a-108">例如，如果 */InstallPath*和 */outputfile*參數遺失，Microsoft System Center 應用程式虛擬化排序器將會傳回96（兩個錯誤碼的總和）。</span><span class="sxs-lookup"><span data-stu-id="ab87a-108">For example, if the */InstallPath* and */OutputFile* parameters are missing, the Microsoft System Center Application Virtualization Sequencer will return 96—the sum of the two error codes.</span></span>

 

<a href="" id="01"></a><span data-ttu-id="ab87a-109">01</span><span class="sxs-lookup"><span data-stu-id="ab87a-109">01</span></span>  
<span data-ttu-id="ab87a-110">出現未指定的錯誤。</span><span class="sxs-lookup"><span data-stu-id="ab87a-110">There is an unspecified error.</span></span>

<a href="" id="02"></a><span data-ttu-id="ab87a-111">2002</span><span class="sxs-lookup"><span data-stu-id="ab87a-111">02</span></span>  
<span data-ttu-id="ab87a-112">指定的安裝目錄（/INSTALLPACKAGE）無效。</span><span class="sxs-lookup"><span data-stu-id="ab87a-112">The specified installation directory (/INSTALLPACKAGE) specified is not valid.</span></span>

<a href="" id="04"></a><span data-ttu-id="ab87a-113">年</span><span class="sxs-lookup"><span data-stu-id="ab87a-113">04</span></span>  
<span data-ttu-id="ab87a-114">指定的套件根目錄（/INSTALLPATH）無效。</span><span class="sxs-lookup"><span data-stu-id="ab87a-114">The specified package root directory (/INSTALLPATH) is not valid.</span></span>

<a href="" id="08"></a><span data-ttu-id="ab87a-115">下半年</span><span class="sxs-lookup"><span data-stu-id="ab87a-115">08</span></span>  
<span data-ttu-id="ab87a-116">指定的 */outputfile*參數無效。</span><span class="sxs-lookup"><span data-stu-id="ab87a-116">The */OutputFile* parameter that was specified is not valid.</span></span>

<a href="" id="16"></a><span data-ttu-id="ab87a-117">位</span><span class="sxs-lookup"><span data-stu-id="ab87a-117">16</span></span>  
<span data-ttu-id="ab87a-118">未指定安裝目錄（/INSTALLPACKAGE）。</span><span class="sxs-lookup"><span data-stu-id="ab87a-118">The installation directory (/INSTALLPACKAGE) was not specified.</span></span>

<a href="" id="32"></a><span data-ttu-id="ab87a-119">32</span><span class="sxs-lookup"><span data-stu-id="ab87a-119">32</span></span>  
<span data-ttu-id="ab87a-120">未指定套件根目錄（/INSTALLPATH）。</span><span class="sxs-lookup"><span data-stu-id="ab87a-120">The package root directory (/INSTALLPATH) was not specified.</span></span>

<a href="" id="64"></a><span data-ttu-id="ab87a-121">64</span><span class="sxs-lookup"><span data-stu-id="ab87a-121">64</span></span>  
<span data-ttu-id="ab87a-122">未指定 */outputfile*參數。</span><span class="sxs-lookup"><span data-stu-id="ab87a-122">The */OutputFile* parameter was not specified.</span></span>

<a href="" id="128"></a><span data-ttu-id="ab87a-123">128</span><span class="sxs-lookup"><span data-stu-id="ab87a-123">128</span></span>  
<span data-ttu-id="ab87a-124">指定的應用程式虛擬化磁片磁碟機無效。</span><span class="sxs-lookup"><span data-stu-id="ab87a-124">The specified application virtualization drive is not valid.</span></span>

<a href="" id="256"></a><span data-ttu-id="ab87a-125">256</span><span class="sxs-lookup"><span data-stu-id="ab87a-125">256</span></span>  
<span data-ttu-id="ab87a-126">安裝程式失敗。</span><span class="sxs-lookup"><span data-stu-id="ab87a-126">The installer failed.</span></span>

<a href="" id="512"></a><span data-ttu-id="ab87a-127">512</span><span class="sxs-lookup"><span data-stu-id="ab87a-127">512</span></span>  
<span data-ttu-id="ab87a-128">排序應用程式失敗。</span><span class="sxs-lookup"><span data-stu-id="ab87a-128">Sequencing the application failed.</span></span>

<a href="" id="1024"></a><span data-ttu-id="ab87a-129">1024</span><span class="sxs-lookup"><span data-stu-id="ab87a-129">1024</span></span>  
<span data-ttu-id="ab87a-130">評估已安裝的快速鍵失敗。</span><span class="sxs-lookup"><span data-stu-id="ab87a-130">Evaluating installed shortcuts failed.</span></span>

<a href="" id="2048"></a><span data-ttu-id="ab87a-131">2048</span><span class="sxs-lookup"><span data-stu-id="ab87a-131">2048</span></span>  
<span data-ttu-id="ab87a-132">已排序的應用程式套件無法儲存。</span><span class="sxs-lookup"><span data-stu-id="ab87a-132">The sequenced application package cannot be saved.</span></span>

<a href="" id="4096"></a><span data-ttu-id="ab87a-133">4096</span><span class="sxs-lookup"><span data-stu-id="ab87a-133">4096</span></span>  
<span data-ttu-id="ab87a-134">指定的套件名稱（/PACKAGENAME）無效。</span><span class="sxs-lookup"><span data-stu-id="ab87a-134">The specified package name (/PACKAGENAME) is not valid.</span></span>

<a href="" id="8192"></a><span data-ttu-id="ab87a-135">8192</span><span class="sxs-lookup"><span data-stu-id="ab87a-135">8192</span></span>  
<span data-ttu-id="ab87a-136">指定的區塊大小（/BLOCKSIZE <em> ） </em> 無效。</span><span class="sxs-lookup"><span data-stu-id="ab87a-136">The specified block size (/BLOCKSIZE<em>)</em> is not valid.</span></span>

<a href="" id="16384"></a><span data-ttu-id="ab87a-137">16384</span><span class="sxs-lookup"><span data-stu-id="ab87a-137">16384</span></span>  
<span data-ttu-id="ab87a-138">指定的壓縮類型（/COMPRESSION）無效。</span><span class="sxs-lookup"><span data-stu-id="ab87a-138">The specified compression type (/COMPRESSION) is not valid.</span></span>

<a href="" id="32768"></a><span data-ttu-id="ab87a-139">32768</span><span class="sxs-lookup"><span data-stu-id="ab87a-139">32768</span></span>  
<span data-ttu-id="ab87a-140">指定的專案路徑無效。</span><span class="sxs-lookup"><span data-stu-id="ab87a-140">The specified project path is not valid.</span></span>

<a href="" id="65536"></a><span data-ttu-id="ab87a-141">65536</span><span class="sxs-lookup"><span data-stu-id="ab87a-141">65536</span></span>  
<span data-ttu-id="ab87a-142">指定的升級參數無效。</span><span class="sxs-lookup"><span data-stu-id="ab87a-142">The specified upgrade parameter is not valid.</span></span>

<a href="" id="131072"></a><span data-ttu-id="ab87a-143">131072</span><span class="sxs-lookup"><span data-stu-id="ab87a-143">131072</span></span>  
<span data-ttu-id="ab87a-144">指定的升級專案參數無效。</span><span class="sxs-lookup"><span data-stu-id="ab87a-144">The specified upgrade project parameter is not valid.</span></span>

<a href="" id="262144"></a><span data-ttu-id="ab87a-145">262144</span><span class="sxs-lookup"><span data-stu-id="ab87a-145">262144</span></span>  
<span data-ttu-id="ab87a-146">指定的 [解碼路徑] 參數無效。</span><span class="sxs-lookup"><span data-stu-id="ab87a-146">The specified decode path parameter is not valid.</span></span>

<a href="" id="525288"></a><span data-ttu-id="ab87a-147">525288</span><span class="sxs-lookup"><span data-stu-id="ab87a-147">525288</span></span>  
<span data-ttu-id="ab87a-148">未指定套件名稱。</span><span class="sxs-lookup"><span data-stu-id="ab87a-148">The package name was not specified.</span></span>

## <span data-ttu-id="ab87a-149">相關主題</span><span class="sxs-lookup"><span data-stu-id="ab87a-149">Related topics</span></span>


[<span data-ttu-id="ab87a-150">關於使用排序器命令列</span><span class="sxs-lookup"><span data-stu-id="ab87a-150">About Using the Sequencer Command Line</span></span>](about-using-the-sequencer-command-line.md)

[<span data-ttu-id="ab87a-151">命令列參數</span><span class="sxs-lookup"><span data-stu-id="ab87a-151">Command-Line Parameters</span></span>](command-line-parameters.md)

 

 





