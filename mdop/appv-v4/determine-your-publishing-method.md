---
title: 決定您的發佈方法
description: 決定您的發佈方法
author: dansimp
ms.assetid: 1f2d0d39-5d65-457a-b826-4f45b00c8c85
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9a6b19b12c28ab67e3250909cb32ddb8419f399a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10808900"
---
# <span data-ttu-id="0a660-103">決定您的發佈方法</span><span class="sxs-lookup"><span data-stu-id="0a660-103">Determine Your Publishing Method</span></span>


<span data-ttu-id="0a660-104">使用應用程式虛擬化排序器將應用程式排序之後，您必須將該應用程式*發佈*給您的使用者。</span><span class="sxs-lookup"><span data-stu-id="0a660-104">After you sequence an application by using the Application Virtualization Sequencer, you need to *publish* that application to your users.</span></span> <span data-ttu-id="0a660-105">發佈應用程式的方式，包括將圖示、套件定義資訊和內容源位置傳送給安裝應用程式虛擬化用戶端的每個電腦。</span><span class="sxs-lookup"><span data-stu-id="0a660-105">Publishing the application consists of delivering the icons, package definition information, and content source location to each computer where the Application Virtualization Client has been installed.</span></span> <span data-ttu-id="0a660-106">下表說明當您使用電子軟體發佈（ESD）系統部署應用程式虛擬化時支援的發佈方法。</span><span class="sxs-lookup"><span data-stu-id="0a660-106">The following table describes publishing methods that are supported when you deploy Application Virtualization by using an electronic software distribution (ESD) system.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="0a660-107">方法</span><span class="sxs-lookup"><span data-stu-id="0a660-107">Method</span></span></th>
<th align="left"><span data-ttu-id="0a660-108">優點</span><span class="sxs-lookup"><span data-stu-id="0a660-108">Advantages</span></span></th>
<th align="left"><span data-ttu-id="0a660-109">缺點</span><span class="sxs-lookup"><span data-stu-id="0a660-109">Disadvantages</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0a660-110">在排序期間產生 Windows 安裝程式檔案，做為獨立的方案。</span><span class="sxs-lookup"><span data-stu-id="0a660-110">Generate a Windows Installer file during sequencing, as a stand-alone solution.</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="0a660-111">輕鬆使用。</span><span class="sxs-lookup"><span data-stu-id="0a660-111">Very simple to use.</span></span></p></li>
<li><p><span data-ttu-id="0a660-112">套件會載入到每個電腦上本機的快取中。</span><span class="sxs-lookup"><span data-stu-id="0a660-112">Package loaded into cache locally on each computer.</span></span></p></li>
<li><p><span data-ttu-id="0a660-113">顯示給使用者的圖示。</span><span class="sxs-lookup"><span data-stu-id="0a660-113">Icons displayed to user.</span></span></p></li>
<li><p><span data-ttu-id="0a660-114">類似傳統的軟體部署。</span><span class="sxs-lookup"><span data-stu-id="0a660-114">Similar to traditional software deployment.</span></span></p></li>
<li><p><span data-ttu-id="0a660-115">不需要流式伺服器。</span><span class="sxs-lookup"><span data-stu-id="0a660-115">No need for streaming servers.</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="0a660-116">在電腦上的套件內容位置，不具靈活性-所有電腦上的位置都相同。</span><span class="sxs-lookup"><span data-stu-id="0a660-116">No flexibility in location of package contents on computers—same location on all computers.</span></span></p></li>
<li><p><span data-ttu-id="0a660-117">必須只使用 [新增/移除程式] 或 msiexec 來移除應用程式。</span><span class="sxs-lookup"><span data-stu-id="0a660-117">Must use only Add/Remove Programs or msiexec to remove applications.</span></span></p></li>
<li><p><span data-ttu-id="0a660-118">移除和取代套件更新所需的新版本。</span><span class="sxs-lookup"><span data-stu-id="0a660-118">Removal and replacement with new version required for package updating.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0a660-119">在排序期間產生 Windows 安裝程式檔案，搭配使用 MODE、LOAD 及 OVERRIDEURL 命令列屬性和套件資訊清單。</span><span class="sxs-lookup"><span data-stu-id="0a660-119">Generate a Windows Installer file during sequencing, used with MODE, LOAD, and OVERRIDEURL command-line properties and the package manifest.</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="0a660-120">簡單易用，但增加了靈活性。</span><span class="sxs-lookup"><span data-stu-id="0a660-120">Simple to use but with added flexibility.</span></span></p></li>
<li><p><span data-ttu-id="0a660-121">顯示給使用者的圖示。</span><span class="sxs-lookup"><span data-stu-id="0a660-121">Icons displayed to user.</span></span></p></li>
<li><p><span data-ttu-id="0a660-122">包含應用程式的 SFT 檔案可以放在流式來源位置，並將用戶端設定為使用該位置。</span><span class="sxs-lookup"><span data-stu-id="0a660-122">SFT file containing the applications can be placed on a streaming source location, with clients configured to use that location.</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="0a660-123">靈活性有限-只有套件內容的位置可以在執行時間加以控制。</span><span class="sxs-lookup"><span data-stu-id="0a660-123">Limited flexibility—only the location of the package content can be controlled at run time.</span></span></p></li>
<li><p><span data-ttu-id="0a660-124">必須只使用 [新增/移除程式] 或 msiexec 來移除應用程式。</span><span class="sxs-lookup"><span data-stu-id="0a660-124">Must use only Add/Remove Programs or msiexec to remove the application.</span></span></p></li>
<li><p><span data-ttu-id="0a660-125">移除和取代套件更新所需的新版本，除非使用流式伺服器。</span><span class="sxs-lookup"><span data-stu-id="0a660-125">Removal and replacement with new version required for package updating, unless using streaming server.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0a660-126">執行 SFTMIME 命令。</span><span class="sxs-lookup"><span data-stu-id="0a660-126">Run SFTMIME commands.</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="0a660-127">全面的靈活性：完全控制所有套件管理功能。</span><span class="sxs-lookup"><span data-stu-id="0a660-127">Complete flexibility—full control of all package management functions.</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="0a660-128">命令必須經過腳本才能搭配 ESD 系統使用。</span><span class="sxs-lookup"><span data-stu-id="0a660-128">Commands must be scripted for use with the ESD system.</span></span></p></li>
<li><p><span data-ttu-id="0a660-129">命令必須以正確順序在每個電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="0a660-129">Commands must be run on each computer in correct sequence.</span></span></p></li>
<li><p><span data-ttu-id="0a660-130">深入瞭解命令語言及需要小心規劃。</span><span class="sxs-lookup"><span data-stu-id="0a660-130">Detailed understanding of command language and careful planning required.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="0a660-131">如需使用這些發佈方法的詳細資訊，請參閱[如何在用戶端發佈虛擬應用程式](how-to-publish-a-virtual-application-on-the-client.md)。</span><span class="sxs-lookup"><span data-stu-id="0a660-131">For more information about using these publishing methods, see [How to Publish a Virtual Application on the Client](how-to-publish-a-virtual-application-on-the-client.md).</span></span>

## <span data-ttu-id="0a660-132">相關主題</span><span class="sxs-lookup"><span data-stu-id="0a660-132">Related topics</span></span>


[<span data-ttu-id="0a660-133">決定您的串流方法</span><span class="sxs-lookup"><span data-stu-id="0a660-133">Determine Your Streaming Method</span></span>](determine-your-streaming-method.md)

[<span data-ttu-id="0a660-134">以電子軟體發佈為基礎的案例</span><span class="sxs-lookup"><span data-stu-id="0a660-134">Electronic Software Distribution-Based Scenario</span></span>](electronic-software-distribution-based-scenario.md)

[<span data-ttu-id="0a660-135">以電子軟體發佈為基礎的案例概觀</span><span class="sxs-lookup"><span data-stu-id="0a660-135">Electronic Software Distribution-Based Scenario Overview</span></span>](electronic-software-distribution-based-scenario-overview.md)

[<span data-ttu-id="0a660-136">如何在用戶端上發佈虛擬應用程式</span><span class="sxs-lookup"><span data-stu-id="0a660-136">How to Publish a Virtual Application on the Client</span></span>](how-to-publish-a-virtual-application-on-the-client.md)

[<span data-ttu-id="0a660-137">SFTMIME 命令參考</span><span class="sxs-lookup"><span data-stu-id="0a660-137">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





