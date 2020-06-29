---
title: 排序器命令列參數
description: 排序器命令列參數
author: dansimp
ms.assetid: 28fb875a-c302-4d95-b2e0-8dc0c5dbb0f8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ecfa269de04cf3dcba30cbb4a40f9176f03f6571
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800842"
---
# <span data-ttu-id="b3481-103">排序器命令列參數</span><span class="sxs-lookup"><span data-stu-id="b3481-103">Sequencer Command-Line Parameters</span></span>


<span data-ttu-id="b3481-104">您可以使用下列應用程式虛擬化（App-v） Sequencer 參數來排序應用程式，並使用命令列來升級現有的虛擬應用程式。</span><span class="sxs-lookup"><span data-stu-id="b3481-104">You can use the following Application Virtualization (App-V) Sequencer parameters to sequence an application and to upgrade an existing virtual application by using a command line.</span></span> <span data-ttu-id="b3481-105">如需使用命令列來排序應用程式的詳細資訊，請參閱[如何使用命令列來排序新的應用程式](how-to-sequence-a-new-application-by-using-the-command-line.md)。</span><span class="sxs-lookup"><span data-stu-id="b3481-105">For more information about sequencing an application by using a command line, see [How to Sequence a New Application by Using the Command Line](how-to-sequence-a-new-application-by-using-the-command-line.md).</span></span>

## <span data-ttu-id="b3481-106">排序器命令列參數</span><span class="sxs-lookup"><span data-stu-id="b3481-106">Sequencer Command-Line Parameters</span></span>


<a href="" id="-help-or---"></a>**<span data-ttu-id="b3481-107">/HELP 或/？</span><span class="sxs-lookup"><span data-stu-id="b3481-107">/HELP or /?</span></span>**  
<span data-ttu-id="b3481-108">顯示可使用命令列來排序應用程式之參數的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="b3481-108">Displays information about parameters that are available for using a command line to sequence applications.</span></span>

<a href="" id="-installpackage-or--i"></a>**<span data-ttu-id="b3481-109">/INSTALLPACKAGE 或/I</span><span class="sxs-lookup"><span data-stu-id="b3481-109">/INSTALLPACKAGE or /I</span></span>**  
<span data-ttu-id="b3481-110">指定要用來安裝應用程式的 Windows Installer 或批次處理檔案，以便進行排序。</span><span class="sxs-lookup"><span data-stu-id="b3481-110">Specifies the Windows Installer or a batch file that will be used to install an application so that it can be sequenced.</span></span>

<a href="" id="-installpath-or--p"></a>**<span data-ttu-id="b3481-111">/INSTALLPATH 或/P</span><span class="sxs-lookup"><span data-stu-id="b3481-111">/INSTALLPATH or /P</span></span>**  
<span data-ttu-id="b3481-112">指定應用程式的套件根目錄。</span><span class="sxs-lookup"><span data-stu-id="b3481-112">Specifies the package root directory for an application.</span></span>

<a href="" id="-outputfile-or--o"></a>**<span data-ttu-id="b3481-113">/OUTPUTFILE 或/O</span><span class="sxs-lookup"><span data-stu-id="b3481-113">/OUTPUTFILE or /O</span></span>**  
<span data-ttu-id="b3481-114">指定將產生的 SPRJ 檔案的路徑和檔案名。</span><span class="sxs-lookup"><span data-stu-id="b3481-114">Specifies the path and file name of the SPRJ file that will be generated.</span></span>

<a href="" id="-fullload-or--f"></a>**<span data-ttu-id="b3481-115">/FULLLOAD 或/F</span><span class="sxs-lookup"><span data-stu-id="b3481-115">/FULLLOAD or /F</span></span>**  
<span data-ttu-id="b3481-116">指定是否將所有檔案包含在主要功能區塊中。</span><span class="sxs-lookup"><span data-stu-id="b3481-116">Specifies whether all files will be contained in the primary feature block.</span></span> <span data-ttu-id="b3481-117">如果 **/FULLLOAD**參數是在命令列上指定，則所有相關聯的應用程式資料都會新增到主要功能區塊。</span><span class="sxs-lookup"><span data-stu-id="b3481-117">If the **/FULLLOAD** parameter is specified on the command line, all of the associated application data is added to primary feature block.</span></span> <span data-ttu-id="b3481-118">如果未在命令列上指定 **/FULLLOAD**參數，則不會在主要功能區塊中新增任何相關聯的應用程式資料。</span><span class="sxs-lookup"><span data-stu-id="b3481-118">If the **/FULLLOAD** parameter is not specified on the command line, then none of the associated application data is added to the primary feature block.</span></span>

<a href="" id="-packagename-or--k"></a>**<span data-ttu-id="b3481-119">/PACKAGENAME 或/K</span><span class="sxs-lookup"><span data-stu-id="b3481-119">/PACKAGENAME or /K</span></span>**  
<span data-ttu-id="b3481-120">指定將指派給序列化應用程式的套件名稱。</span><span class="sxs-lookup"><span data-stu-id="b3481-120">Specifies the package name that will be assigned to the sequenced application.</span></span>

<a href="" id="-blocksize"></a>**<span data-ttu-id="b3481-121">/BLOCKSIZE</span><span class="sxs-lookup"><span data-stu-id="b3481-121">/BLOCKSIZE</span></span>**  
<span data-ttu-id="b3481-122">指定將用來將套件資料流程封裝至用戶端電腦的 SFT 檔案區塊大小。</span><span class="sxs-lookup"><span data-stu-id="b3481-122">Specifies the SFT file block size that will be used to stream the package to client computers.</span></span> <span data-ttu-id="b3481-123">您可以選取下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="b3481-123">You can select one of the following values:</span></span>

-   <span data-ttu-id="b3481-124">4 KB</span><span class="sxs-lookup"><span data-stu-id="b3481-124">4 KB</span></span>

-   <span data-ttu-id="b3481-125">16 KB</span><span class="sxs-lookup"><span data-stu-id="b3481-125">16 KB</span></span>

-   <span data-ttu-id="b3481-126">32 KB</span><span class="sxs-lookup"><span data-stu-id="b3481-126">32 KB</span></span>

-   <span data-ttu-id="b3481-127">64 KB</span><span class="sxs-lookup"><span data-stu-id="b3481-127">64 KB</span></span>

<span data-ttu-id="b3481-128">當您指定區塊大小時，您應該考慮 SFT 檔案的大小。</span><span class="sxs-lookup"><span data-stu-id="b3481-128">You should consider the size of the SFT file when you specify the block size.</span></span> <span data-ttu-id="b3481-129">區塊大小較小的檔案需要較長的時間，才能在網路上傳輸，但較少佔用頻寬。</span><span class="sxs-lookup"><span data-stu-id="b3481-129">A file with a smaller block size takes longer to stream over the network but is less bandwidth-intensive.</span></span> <span data-ttu-id="b3481-130">區塊大小較大的檔案會使用更多的網路頻寬。</span><span class="sxs-lookup"><span data-stu-id="b3481-130">Files with larger block sizes use more network bandwidth.</span></span>

<a href="" id="-compression"></a>**<span data-ttu-id="b3481-131">/COMPRESSION</span><span class="sxs-lookup"><span data-stu-id="b3481-131">/COMPRESSION</span></span>**  
<span data-ttu-id="b3481-132">指定壓縮要傳送到用戶端的 SFT 檔案的方法。</span><span class="sxs-lookup"><span data-stu-id="b3481-132">Specifies the method for compressing the SFT file that will be streamed to the client.</span></span>

<a href="" id="-msi-or--m"></a>**<span data-ttu-id="b3481-133">/MSI 或/M</span><span class="sxs-lookup"><span data-stu-id="b3481-133">/MSI or /M</span></span>**  
<span data-ttu-id="b3481-134">指定是否應建立已排序之應用程式的 Windows 安裝程式。</span><span class="sxs-lookup"><span data-stu-id="b3481-134">Specifies whether a Windows Installer for the sequenced application should be created.</span></span>

<a href="" id="-default"></a>**<span data-ttu-id="b3481-135">/DEFAULT</span><span class="sxs-lookup"><span data-stu-id="b3481-135">/DEFAULT</span></span>**  
<span data-ttu-id="b3481-136">指定建立虛擬應用程式套件時將使用的預設 SPRJ 檔案。</span><span class="sxs-lookup"><span data-stu-id="b3481-136">Specifies the default SPRJ file that will be used when creating a virtual application package.</span></span> <span data-ttu-id="b3481-137">當應用程式第一次排序時，此檔案會當作 sprj 範本使用。</span><span class="sxs-lookup"><span data-stu-id="b3481-137">This file is used as the .sprj template when the application is sequenced for the first time.</span></span>

<a href="" id="-upgrade"></a>**<span data-ttu-id="b3481-138">/UPGRADE</span><span class="sxs-lookup"><span data-stu-id="b3481-138">/UPGRADE</span></span>**  
<span data-ttu-id="b3481-139">指定將升級之 SPRJ 檔案的路徑和檔案名。</span><span class="sxs-lookup"><span data-stu-id="b3481-139">Specifies the path and file name of the SPRJ file that will be upgraded.</span></span>

<a href="" id="-decodepath"></a>**<span data-ttu-id="b3481-140">/DECODEPATH</span><span class="sxs-lookup"><span data-stu-id="b3481-140">/DECODEPATH</span></span>**  
<span data-ttu-id="b3481-141">指定排序電腦上已安裝與序列化應用程式套件相關聯之檔案的目錄。</span><span class="sxs-lookup"><span data-stu-id="b3481-141">Specifies the directory on the sequencing computer where the files associated with the sequenced application package are installed.</span></span> <span data-ttu-id="b3481-142">指定目錄時，請使用下列其中一種格式：</span><span class="sxs-lookup"><span data-stu-id="b3481-142">Use one of the following formats when specifying the directory:</span></span>

-   <span data-ttu-id="b3481-143">/decodepath：問：</span><span class="sxs-lookup"><span data-stu-id="b3481-143">/decodepath:Q:</span></span>

-   <span data-ttu-id="b3481-144">/decodepath:Q:.</span><span class="sxs-lookup"><span data-stu-id="b3481-144">/decodepath:Q:.</span></span>

-   <span data-ttu-id="b3481-145">/decodepath:"Q:."</span><span class="sxs-lookup"><span data-stu-id="b3481-145">/decodepath:”Q:.”</span></span>

-   <span data-ttu-id="b3481-146">/decodepath： "Q："</span><span class="sxs-lookup"><span data-stu-id="b3481-146">/decodepath:”Q:”</span></span>

## <span data-ttu-id="b3481-147">相關主題</span><span class="sxs-lookup"><span data-stu-id="b3481-147">Related topics</span></span>


[<span data-ttu-id="b3481-148">Application Virtualization Sequencer</span><span class="sxs-lookup"><span data-stu-id="b3481-148">Application Virtualization Sequencer</span></span>](application-virtualization-sequencer.md)

[<span data-ttu-id="b3481-149">排序器命令列錯誤碼</span><span class="sxs-lookup"><span data-stu-id="b3481-149">Sequencer Command-Line Error Codes</span></span>](sequencer-command-line-error-codes.md)

 

 





