---
title: 決定您的串流方法
description: 決定您的串流方法
author: dansimp
ms.assetid: 50d5e0ec-7f48-4cea-8711-5882bd89153b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0acfd345ac55f11476cffe94b3a95b13c5d8f303
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10808894"
---
# <span data-ttu-id="c1f7e-103">決定您的串流方法</span><span class="sxs-lookup"><span data-stu-id="c1f7e-103">Determine Your Streaming Method</span></span>


<span data-ttu-id="c1f7e-104">當使用者第一次按兩下已透過發佈程式在電腦上放置的圖示時，應用程式虛擬化用戶端會從流式來源位置取得虛擬應用程式套件內容。</span><span class="sxs-lookup"><span data-stu-id="c1f7e-104">The first time that a user double-clicks the icon that has been placed on a computer through the publishing process, the Application Virtualization client will obtain the virtual application package content from a streaming source location.</span></span>

<span data-ttu-id="c1f7e-105">**記事** 
*串流*是用來描述取得順序式應用程式套件內容的程式，從主要功能區塊開始，然後視需要取得其他區塊。</span><span class="sxs-lookup"><span data-stu-id="c1f7e-105">**Note**
*Streaming* is the term used to describe the process of obtaining content from a sequenced application package, starting with the primary feature block and then obtaining additional blocks as needed.</span></span>

 

<span data-ttu-id="c1f7e-106">流式來源位置通常是使用者電腦可存取的伺服器;不過，某些電子發佈系統（例如 Microsoft 端點設定管理員）可以將 SFT 檔案散佈到使用者的電腦，然後從該電腦的快取本機對流進行虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="c1f7e-106">The streaming source location is usually a server that is accessible by the user’s computer; however, some electronic distribution systems, such as Microsoft Endpoint Configuration Manager, can distribute the SFT file to the user’s computer and then stream the virtual application package locally from that computer’s cache.</span></span>

<span data-ttu-id="c1f7e-107">**記事** 虛擬套件的流式來源位置可以在不是伺服器的電腦上設定。</span><span class="sxs-lookup"><span data-stu-id="c1f7e-107">**Note** A streaming source location for virtual packages can be set up on a computer that is not a server.</span></span> <span data-ttu-id="c1f7e-108">這在沒有伺服器的小型分支機搆中特別有用。</span><span class="sxs-lookup"><span data-stu-id="c1f7e-108">This is especially useful in a small branch office that has no server.</span></span>

 

<span data-ttu-id="c1f7e-109">下表說明可用於儲存順序式應用程式的流式處理來源。</span><span class="sxs-lookup"><span data-stu-id="c1f7e-109">The streaming sources that can be used to store sequenced applications are described in the following table.</span></span>

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="c1f7e-110">伺服器類型</span><span class="sxs-lookup"><span data-stu-id="c1f7e-110">Server Type</span></span></th>
<th align="left"><span data-ttu-id="c1f7e-111">通訊協定</span><span class="sxs-lookup"><span data-stu-id="c1f7e-111">Protocol</span></span></th>
<th align="left"><span data-ttu-id="c1f7e-112">優點</span><span class="sxs-lookup"><span data-stu-id="c1f7e-112">Advantages</span></span></th>
<th align="left"><span data-ttu-id="c1f7e-113">缺點</span><span class="sxs-lookup"><span data-stu-id="c1f7e-113">Disadvantages</span></span></th>
<th align="left"><span data-ttu-id="c1f7e-114">連結</span><span class="sxs-lookup"><span data-stu-id="c1f7e-114">Links</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c1f7e-115">檔案伺服器</span><span class="sxs-lookup"><span data-stu-id="c1f7e-115">File server</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1f7e-116">檔案</span><span class="sxs-lookup"><span data-stu-id="c1f7e-116">File</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="c1f7e-117">簡單的低成本解決方案，可使用 \CONTENT 共用來設定現有的檔案伺服器</span><span class="sxs-lookup"><span data-stu-id="c1f7e-117">Simple low-cost solution to configure existing file server with \CONTENT share</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="c1f7e-118">沒有作用中升級</span><span class="sxs-lookup"><span data-stu-id="c1f7e-118">No active upgrade</span></span></p></li>
</ul></td>
<td align="left"><p><a href="how-to-configure-the-file-server.md" data-raw-source="[How to Configure the File Server](how-to-configure-the-file-server.md)"><span data-ttu-id="c1f7e-119">如何設定檔案伺服器</span><span class="sxs-lookup"><span data-stu-id="c1f7e-119">How to Configure the File Server</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c1f7e-120">IIS 伺服器</span><span class="sxs-lookup"><span data-stu-id="c1f7e-120">IIS server</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1f7e-121">HTTP/HTTPS</span><span class="sxs-lookup"><span data-stu-id="c1f7e-121">HTTP/ HTTPS</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="c1f7e-122">使用 HTTPS 通訊協定支援增強的安全性。</span><span class="sxs-lookup"><span data-stu-id="c1f7e-122">Supports enhanced security using HTTPS protocol.</span></span></p></li>
<li><p><span data-ttu-id="c1f7e-123">支援透過網際網路在遠端電腦上傳送資料流程</span><span class="sxs-lookup"><span data-stu-id="c1f7e-123">Supports streaming to remote computers across the Internet</span></span></p></li>
<li><p><span data-ttu-id="c1f7e-124">在防火牆中只開啟一個埠</span><span class="sxs-lookup"><span data-stu-id="c1f7e-124">Only one port in firewall to open</span></span></p></li>
<li><p><span data-ttu-id="c1f7e-125">高度可伸縮</span><span class="sxs-lookup"><span data-stu-id="c1f7e-125">Highly scalable</span></span></p></li>
<li><p><span data-ttu-id="c1f7e-126">熟悉的通訊協定</span><span class="sxs-lookup"><span data-stu-id="c1f7e-126">Familiar protocol</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="c1f7e-127">需要管理 IIS</span><span class="sxs-lookup"><span data-stu-id="c1f7e-127">Need to manage IIS</span></span></p></li>
<li><p><span data-ttu-id="c1f7e-128">沒有作用中升級</span><span class="sxs-lookup"><span data-stu-id="c1f7e-128">No active upgrade</span></span></p></li>
</ul></td>
<td align="left"><p><a href="how-to-configure-the-server-for-iis.md" data-raw-source="[How to Configure the Server for IIS](how-to-configure-the-server-for-iis.md)"><span data-ttu-id="c1f7e-129">如何設定伺服器使用 IIS</span><span class="sxs-lookup"><span data-stu-id="c1f7e-129">How to Configure the Server for IIS</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c1f7e-130">應用程式虛擬化資料流程伺服器</span><span class="sxs-lookup"><span data-stu-id="c1f7e-130">Application Virtualization Streaming Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1f7e-131">RTSP/RTSPS</span><span class="sxs-lookup"><span data-stu-id="c1f7e-131">RTSP/ RTSPS</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="c1f7e-132">活動升級</span><span class="sxs-lookup"><span data-stu-id="c1f7e-132">Active upgrade</span></span></p></li>
<li><p><span data-ttu-id="c1f7e-133">使用 RTSPS 通訊協定支援增強的安全性</span><span class="sxs-lookup"><span data-stu-id="c1f7e-133">Supports enhanced security using RTSPS protocol</span></span></p></li>
<li><p><span data-ttu-id="c1f7e-134">在防火牆中只開啟一個埠（僅限 RTSPS）</span><span class="sxs-lookup"><span data-stu-id="c1f7e-134">Only one port in firewall to open (RTSPS only)</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="c1f7e-135">雙基礎結構</span><span class="sxs-lookup"><span data-stu-id="c1f7e-135">Dual infrastructure</span></span></p></li>
<li><p><span data-ttu-id="c1f7e-136">伺服器管理需求</span><span class="sxs-lookup"><span data-stu-id="c1f7e-136">Server administration requirement</span></span></p></li>
</ul></td>
<td align="left"><p><a href="how-to-configure-the-application-virtualization-management-servers.md" data-raw-source="[How to Configure the Application Virtualization Management Servers](how-to-configure-the-application-virtualization-management-servers.md)"><span data-ttu-id="c1f7e-137">如何設定 Application Virtualization Management Server</span><span class="sxs-lookup"><span data-stu-id="c1f7e-137">How to Configure the Application Virtualization Management Servers</span></span></a></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="c1f7e-138">相關主題</span><span class="sxs-lookup"><span data-stu-id="c1f7e-138">Related topics</span></span>


[<span data-ttu-id="c1f7e-139">以電子軟體發佈為基礎的案例</span><span class="sxs-lookup"><span data-stu-id="c1f7e-139">Electronic Software Distribution-Based Scenario</span></span>](electronic-software-distribution-based-scenario.md)

[<span data-ttu-id="c1f7e-140">以電子軟體發佈為基礎的案例概觀</span><span class="sxs-lookup"><span data-stu-id="c1f7e-140">Electronic Software Distribution-Based Scenario Overview</span></span>](electronic-software-distribution-based-scenario-overview.md)

[<span data-ttu-id="c1f7e-141">決定您的發佈方法</span><span class="sxs-lookup"><span data-stu-id="c1f7e-141">Determine Your Publishing Method</span></span>](determine-your-publishing-method.md)

 

 





