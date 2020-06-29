---
title: 命令列參數
description: 命令列參數
author: dansimp
ms.assetid: d90a0591-f1ce-4cb8-b244-85cc70461922
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 31d6ca1215648e2519e9818817ab5cc779a746d0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802202"
---
# <span data-ttu-id="87d4e-103">命令列參數</span><span class="sxs-lookup"><span data-stu-id="87d4e-103">Command-Line Parameters</span></span>


<span data-ttu-id="87d4e-104">使用下列應用程式虛擬化排序器參數來排序應用程式，並在命令提示字元中升級順序化的應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="87d4e-104">Use the following Application Virtualization Sequencer parameters to sequence an application and to upgrade a sequenced application package at the command prompt.</span></span> <span data-ttu-id="87d4e-105">在 Microsoft Application Virtualization Sequencer 目錄中，您可以輸入**SFTSequencer**，後面接著適當的參數。</span><span class="sxs-lookup"><span data-stu-id="87d4e-105">In the Microsoft Application Virtualization Sequencer directory, you would enter **SFTSequencer**, followed by the appropriate parameter.</span></span>

<a href="" id="-help-or---"></a><span data-ttu-id="87d4e-106">*/Help*或 */？*</span><span class="sxs-lookup"><span data-stu-id="87d4e-106">*/HELP* or */?*</span></span>  
<span data-ttu-id="87d4e-107">用來顯示命令列順序的可用參數清單。</span><span class="sxs-lookup"><span data-stu-id="87d4e-107">Use to display the list of parameters available for command-line sequencing.</span></span>

<a href="" id="-installpackage-or--i"></a><span data-ttu-id="87d4e-108">*/INSTALLPACKAGE*或 */i*</span><span class="sxs-lookup"><span data-stu-id="87d4e-108">*/INSTALLPACKAGE* or */I*</span></span>  
<span data-ttu-id="87d4e-109">用來指定要排序之應用程式的安裝程式或批次檔案。</span><span class="sxs-lookup"><span data-stu-id="87d4e-109">Use to specify the installer or a batch file for the application to be sequenced.</span></span>

<a href="" id="-installpath-or--p"></a><span data-ttu-id="87d4e-110">*/INSTALLPATH*或 */p*</span><span class="sxs-lookup"><span data-stu-id="87d4e-110">*/INSTALLPATH* or */P*</span></span>  
<span data-ttu-id="87d4e-111">用來指定套件根目錄。</span><span class="sxs-lookup"><span data-stu-id="87d4e-111">Use to specify the package root directory.</span></span>

<a href="" id="-outputfile-or--o"></a><span data-ttu-id="87d4e-112">*/Outputfile*或 */o*</span><span class="sxs-lookup"><span data-stu-id="87d4e-112">*/OUTPUTFILE* or */O*</span></span>  
<span data-ttu-id="87d4e-113">用來指定將產生的 SPRJ 檔案的路徑和檔案名。</span><span class="sxs-lookup"><span data-stu-id="87d4e-113">Use to specify the path and file name of the SPRJ file that will be generated.</span></span>

<span data-ttu-id="87d4e-114">**重要** 開啟您不想升級的套件時，無法使用 */outputfile*參數。</span><span class="sxs-lookup"><span data-stu-id="87d4e-114">**Important** The */OUTPUTFILE* parameter is not available when opening a package that you do not intend to upgrade.</span></span>

 

<a href="" id="-fullload-or--f"></a><span data-ttu-id="87d4e-115">*/FULLLOAD*或 */f*</span><span class="sxs-lookup"><span data-stu-id="87d4e-115">*/FULLLOAD* or */F*</span></span>  
<span data-ttu-id="87d4e-116">用來指定是否要將所有專案放在主要功能區塊中。</span><span class="sxs-lookup"><span data-stu-id="87d4e-116">Use to specify whether to put everything in the primary feature block.</span></span>

<a href="" id="-packagename-or--k"></a><span data-ttu-id="87d4e-117">*/Packagename*或 */k*</span><span class="sxs-lookup"><span data-stu-id="87d4e-117">*/PACKAGENAME* or */K*</span></span>  
<span data-ttu-id="87d4e-118">用來指定已排序之應用程式的套件名稱。</span><span class="sxs-lookup"><span data-stu-id="87d4e-118">Use to specify the package name of the sequenced application.</span></span>

<a href="" id="-blocksize"></a>*<span data-ttu-id="87d4e-119">/BLOCKSIZE</span><span class="sxs-lookup"><span data-stu-id="87d4e-119">/BLOCKSIZE</span></span>*  
<span data-ttu-id="87d4e-120">指定將用來將套件資料流程封裝至用戶端電腦的 SFT 檔案區塊大小。</span><span class="sxs-lookup"><span data-stu-id="87d4e-120">Specifies the SFT file block size that will be used to stream the package to client computers.</span></span> <span data-ttu-id="87d4e-121">您可以選取下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="87d4e-121">You can select one of the following values:</span></span>

-   <span data-ttu-id="87d4e-122">4 KB</span><span class="sxs-lookup"><span data-stu-id="87d4e-122">4 KB</span></span>

-   <span data-ttu-id="87d4e-123">16 KB</span><span class="sxs-lookup"><span data-stu-id="87d4e-123">16 KB</span></span>

-   <span data-ttu-id="87d4e-124">32 KB</span><span class="sxs-lookup"><span data-stu-id="87d4e-124">32 KB</span></span>

-   <span data-ttu-id="87d4e-125">64 KB</span><span class="sxs-lookup"><span data-stu-id="87d4e-125">64 KB</span></span>

<span data-ttu-id="87d4e-126">當您指定區塊大小時，您應該考慮 SFT 檔案的大小。</span><span class="sxs-lookup"><span data-stu-id="87d4e-126">You should consider the size of the SFT file when you specify the block size.</span></span> <span data-ttu-id="87d4e-127">區塊大小較小的檔案需要較長的時間，才能在網路上傳輸，但較少佔用頻寬。</span><span class="sxs-lookup"><span data-stu-id="87d4e-127">A file with a smaller block size takes longer to stream over the network but is less bandwidth-intensive.</span></span> <span data-ttu-id="87d4e-128">區塊大小較大的檔案會使用更多的網路頻寬。</span><span class="sxs-lookup"><span data-stu-id="87d4e-128">Files with larger block sizes use more network bandwidth.</span></span>

<a href="" id="-compression"></a>*<span data-ttu-id="87d4e-129">/COMPRESSION</span><span class="sxs-lookup"><span data-stu-id="87d4e-129">/COMPRESSION</span></span>*  
<span data-ttu-id="87d4e-130">用來指定在將 SFT 檔案傳送到用戶端時壓縮該檔案的方法。</span><span class="sxs-lookup"><span data-stu-id="87d4e-130">Use to specify the method for compressing the SFT file as it is streamed to the client.</span></span>

<a href="" id="-msi-or--m"></a><span data-ttu-id="87d4e-131">*/MSI*或 */m*</span><span class="sxs-lookup"><span data-stu-id="87d4e-131">*/MSI* or */M*</span></span>  
<span data-ttu-id="87d4e-132">用來指定產生已排序之應用程式的 Microsoft Windows 安裝程式套件。</span><span class="sxs-lookup"><span data-stu-id="87d4e-132">Use to specify generating a Microsoft Windows Installer package for the sequenced application.</span></span>

<a href="" id="-default"></a>*<span data-ttu-id="87d4e-133">/DEFAULT</span><span class="sxs-lookup"><span data-stu-id="87d4e-133">/DEFAULT</span></span>*  
<span data-ttu-id="87d4e-134">指定建立虛擬應用程式套件時將使用的預設 SPRJ 檔案。</span><span class="sxs-lookup"><span data-stu-id="87d4e-134">Specifies the default SPRJ file that will be used when creating a virtual application package.</span></span> <span data-ttu-id="87d4e-135">當應用程式第一次排序時，此檔案會當作 sprj 範本使用。</span><span class="sxs-lookup"><span data-stu-id="87d4e-135">This file is used as the .sprj template when the application is sequenced for the first time.</span></span>

<a href="" id="-upgrade"></a>*<span data-ttu-id="87d4e-136">/UPGRADE</span><span class="sxs-lookup"><span data-stu-id="87d4e-136">/UPGRADE</span></span>*  
<span data-ttu-id="87d4e-137">指定將升級之 SPRJ 檔案的路徑和檔案名。</span><span class="sxs-lookup"><span data-stu-id="87d4e-137">Specifies the path and file name of the SPRJ file that will be upgraded.</span></span>

<a href="" id="-decodepath"></a>*<span data-ttu-id="87d4e-138">/DECODEPATH</span><span class="sxs-lookup"><span data-stu-id="87d4e-138">/DECODEPATH</span></span>*  
<span data-ttu-id="87d4e-139">指定排序電腦上已安裝與序列化應用程式套件相關聯之檔案的目錄。</span><span class="sxs-lookup"><span data-stu-id="87d4e-139">Specifies the directory on the sequencing computer where the files associated with the sequenced application package are installed.</span></span> <span data-ttu-id="87d4e-140">指定目錄時，請使用下列其中一種格式：</span><span class="sxs-lookup"><span data-stu-id="87d4e-140">Use one of the following formats when specifying the directory:</span></span>

-   <span data-ttu-id="87d4e-141">/decodepath：問：</span><span class="sxs-lookup"><span data-stu-id="87d4e-141">/decodepath:Q:</span></span>

-   <span data-ttu-id="87d4e-142">/decodepath:Q:.</span><span class="sxs-lookup"><span data-stu-id="87d4e-142">/decodepath:Q:.</span></span>

-   <span data-ttu-id="87d4e-143">/decodepath:"Q:."</span><span class="sxs-lookup"><span data-stu-id="87d4e-143">/decodepath:”Q:.”</span></span>

-   <span data-ttu-id="87d4e-144">/decodepath： "Q："</span><span class="sxs-lookup"><span data-stu-id="87d4e-144">/decodepath:”Q:”</span></span>

## <span data-ttu-id="87d4e-145">相關主題</span><span class="sxs-lookup"><span data-stu-id="87d4e-145">Related topics</span></span>


[<span data-ttu-id="87d4e-146">關於使用排序器命令列</span><span class="sxs-lookup"><span data-stu-id="87d4e-146">About Using the Sequencer Command Line</span></span>](about-using-the-sequencer-command-line.md)

[<span data-ttu-id="87d4e-147">如何使用命令列來開啟循序應用程式</span><span class="sxs-lookup"><span data-stu-id="87d4e-147">How to Open a Sequenced Application Using the Command Line</span></span>](how-to-open-a-sequenced-application-using-the-command-line.md)

[<span data-ttu-id="87d4e-148">如何使用 [開啟封裝] 命令來升級封裝</span><span class="sxs-lookup"><span data-stu-id="87d4e-148">How to Upgrade a Package Using the Open Package Command</span></span>](how-to-upgrade-a-package-using-the-open-package-command.md)

 

 





