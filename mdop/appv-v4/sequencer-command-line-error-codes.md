---
title: 排序器命令列錯誤碼
description: 排序器命令列錯誤碼
author: dansimp
ms.assetid: 3d491314-4923-45fd-9839-c541c5e620bd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 74f5bd0c1b66656ac6891dcc1c019254fa36fdac
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800843"
---
# <span data-ttu-id="abe48-103">排序器命令列錯誤碼</span><span class="sxs-lookup"><span data-stu-id="abe48-103">Sequencer Command-Line Error Codes</span></span>


<span data-ttu-id="abe48-104">使用下列清單，協助您使用命令列來識別與順序應用程式相關的錯誤。</span><span class="sxs-lookup"><span data-stu-id="abe48-104">Use the following list to help identify errors that are related to sequencing applications by using the command line.</span></span> <span data-ttu-id="abe48-105">您也可以透過查看關聯的 App-v 排序器記錄檔來查看此資訊。</span><span class="sxs-lookup"><span data-stu-id="abe48-105">You can also see this information by viewing the associated App-V Sequencer log file.</span></span>

<span data-ttu-id="abe48-106">**記事** 在排序期間，可能會發生多個錯誤，如果發生這種情況，則顯示的錯誤碼可能是兩個錯誤碼的總和。</span><span class="sxs-lookup"><span data-stu-id="abe48-106">**Note** Multiple errors can occur during sequencing, and if this happens, the error code that is displayed might be the sum of two error codes.</span></span> <span data-ttu-id="abe48-107">例如，如果 */InstallPath*和 */outputfile*參數遺失，app-v 會傳回**96**，即兩個錯誤碼的總和。</span><span class="sxs-lookup"><span data-stu-id="abe48-107">For example, if the */InstallPath* and */OutputFile* parameters are missing, the App-V Sequencer will return **96**—the sum of the two error codes.</span></span>

 

<a href="" id="01"></a><span data-ttu-id="abe48-108">01</span><span class="sxs-lookup"><span data-stu-id="abe48-108">01</span></span>  
<span data-ttu-id="abe48-109">出現未指定的錯誤。</span><span class="sxs-lookup"><span data-stu-id="abe48-109">There is an unspecified error.</span></span>

<a href="" id="02"></a><span data-ttu-id="abe48-110">2002</span><span class="sxs-lookup"><span data-stu-id="abe48-110">02</span></span>  
<span data-ttu-id="abe48-111">指定的安裝目錄（/INSTALLPACKAGE）無效。</span><span class="sxs-lookup"><span data-stu-id="abe48-111">The specified installation directory (/INSTALLPACKAGE) is not valid.</span></span>

<a href="" id="04"></a><span data-ttu-id="abe48-112">年</span><span class="sxs-lookup"><span data-stu-id="abe48-112">04</span></span>  
<span data-ttu-id="abe48-113">指定的套件根目錄（/INSTALLPATH）無效。</span><span class="sxs-lookup"><span data-stu-id="abe48-113">The specified package root directory (/INSTALLPATH) is not valid.</span></span>

<a href="" id="08"></a><span data-ttu-id="abe48-114">下半年</span><span class="sxs-lookup"><span data-stu-id="abe48-114">08</span></span>  
<span data-ttu-id="abe48-115">指定的 */outputfile*參數無效。</span><span class="sxs-lookup"><span data-stu-id="abe48-115">The specified */OutputFile* parameter is not valid.</span></span>

<a href="" id="16"></a><span data-ttu-id="abe48-116">位</span><span class="sxs-lookup"><span data-stu-id="abe48-116">16</span></span>  
<span data-ttu-id="abe48-117">未指定安裝目錄（/INSTALLPACKAGE）。</span><span class="sxs-lookup"><span data-stu-id="abe48-117">The installation directory (/INSTALLPACKAGE) is not specified.</span></span>

<a href="" id="32"></a><span data-ttu-id="abe48-118">32</span><span class="sxs-lookup"><span data-stu-id="abe48-118">32</span></span>  
<span data-ttu-id="abe48-119">未指定套件根目錄（/INSTALLPATH）。</span><span class="sxs-lookup"><span data-stu-id="abe48-119">The package root directory (/INSTALLPATH) is not specified.</span></span>

<a href="" id="64"></a><span data-ttu-id="abe48-120">64</span><span class="sxs-lookup"><span data-stu-id="abe48-120">64</span></span>  
<span data-ttu-id="abe48-121">未指定 */outputfile*參數。</span><span class="sxs-lookup"><span data-stu-id="abe48-121">The */OutputFile* parameter is not specified.</span></span>

<a href="" id="128"></a><span data-ttu-id="abe48-122">128</span><span class="sxs-lookup"><span data-stu-id="abe48-122">128</span></span>  
<span data-ttu-id="abe48-123">指定的應用程式虛擬化磁片磁碟機無效。</span><span class="sxs-lookup"><span data-stu-id="abe48-123">The specified application virtualization drive is not valid.</span></span>

<a href="" id="256"></a><span data-ttu-id="abe48-124">256</span><span class="sxs-lookup"><span data-stu-id="abe48-124">256</span></span>  
<span data-ttu-id="abe48-125">安裝程式失敗。</span><span class="sxs-lookup"><span data-stu-id="abe48-125">The installer failed.</span></span>

<a href="" id="512"></a><span data-ttu-id="abe48-126">512</span><span class="sxs-lookup"><span data-stu-id="abe48-126">512</span></span>  
<span data-ttu-id="abe48-127">排序應用程式失敗。</span><span class="sxs-lookup"><span data-stu-id="abe48-127">Sequencing the application failed.</span></span>

<a href="" id="1024"></a><span data-ttu-id="abe48-128">1024</span><span class="sxs-lookup"><span data-stu-id="abe48-128">1024</span></span>  
<span data-ttu-id="abe48-129">評估已安裝的快速鍵失敗。</span><span class="sxs-lookup"><span data-stu-id="abe48-129">Evaluating installed shortcuts failed.</span></span>

<a href="" id="2048"></a><span data-ttu-id="abe48-130">2048</span><span class="sxs-lookup"><span data-stu-id="abe48-130">2048</span></span>  
<span data-ttu-id="abe48-131">已排序的應用程式套件無法儲存。</span><span class="sxs-lookup"><span data-stu-id="abe48-131">The sequenced application package cannot be saved.</span></span>

<a href="" id="4096"></a><span data-ttu-id="abe48-132">4096</span><span class="sxs-lookup"><span data-stu-id="abe48-132">4096</span></span>  
<span data-ttu-id="abe48-133">指定的套件名稱（/PACKAGENAME）無效。</span><span class="sxs-lookup"><span data-stu-id="abe48-133">The specified package name (/PACKAGENAME) is not valid.</span></span>

<a href="" id="8192"></a><span data-ttu-id="abe48-134">8192</span><span class="sxs-lookup"><span data-stu-id="abe48-134">8192</span></span>  
<span data-ttu-id="abe48-135">指定的區塊大小（/BLOCKSIZE）無效。</span><span class="sxs-lookup"><span data-stu-id="abe48-135">The specified block size (/BLOCKSIZE) is not valid.</span></span>

<a href="" id="16384"></a><span data-ttu-id="abe48-136">16384</span><span class="sxs-lookup"><span data-stu-id="abe48-136">16384</span></span>  
<span data-ttu-id="abe48-137">指定的壓縮類型（/COMPRESSION）無效。</span><span class="sxs-lookup"><span data-stu-id="abe48-137">The specified compression type (/COMPRESSION) is not valid.</span></span>

<a href="" id="32768"></a><span data-ttu-id="abe48-138">32768</span><span class="sxs-lookup"><span data-stu-id="abe48-138">32768</span></span>  
<span data-ttu-id="abe48-139">指定的專案路徑無效。</span><span class="sxs-lookup"><span data-stu-id="abe48-139">The specified project path is not valid.</span></span>

<a href="" id="65536"></a><span data-ttu-id="abe48-140">65536</span><span class="sxs-lookup"><span data-stu-id="abe48-140">65536</span></span>  
<span data-ttu-id="abe48-141">指定的升級參數無效。</span><span class="sxs-lookup"><span data-stu-id="abe48-141">The specified upgrade parameter is not valid.</span></span>

<a href="" id="131072"></a><span data-ttu-id="abe48-142">131072</span><span class="sxs-lookup"><span data-stu-id="abe48-142">131072</span></span>  
<span data-ttu-id="abe48-143">指定的升級專案參數無效。</span><span class="sxs-lookup"><span data-stu-id="abe48-143">The specified upgrade project parameter is not valid.</span></span>

<a href="" id="262144"></a><span data-ttu-id="abe48-144">262144</span><span class="sxs-lookup"><span data-stu-id="abe48-144">262144</span></span>  
<span data-ttu-id="abe48-145">指定的 [解碼路徑] 參數無效。</span><span class="sxs-lookup"><span data-stu-id="abe48-145">The specified decode path parameter is not valid.</span></span>

<a href="" id="525288"></a><span data-ttu-id="abe48-146">525288</span><span class="sxs-lookup"><span data-stu-id="abe48-146">525288</span></span>  
<span data-ttu-id="abe48-147">未指定套件名稱。</span><span class="sxs-lookup"><span data-stu-id="abe48-147">The package name is not specified.</span></span>

## <span data-ttu-id="abe48-148">相關主題</span><span class="sxs-lookup"><span data-stu-id="abe48-148">Related topics</span></span>


[<span data-ttu-id="abe48-149">Application Virtualization Sequencer 參考資料</span><span class="sxs-lookup"><span data-stu-id="abe48-149">Application Virtualization Sequencer Reference</span></span>](application-virtualization-sequencer-reference.md)

[<span data-ttu-id="abe48-150">排序器命令列參數</span><span class="sxs-lookup"><span data-stu-id="abe48-150">Sequencer Command-Line Parameters</span></span>](sequencer-command-line-parameters.md)

 

 





