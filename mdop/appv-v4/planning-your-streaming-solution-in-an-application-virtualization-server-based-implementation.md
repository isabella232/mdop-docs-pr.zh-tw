---
title: 在以 Application Virtualization 伺服器為基礎的實作中規劃您的串流解決方案
description: 在以 Application Virtualization 伺服器為基礎的實作中規劃您的串流解決方案
author: dansimp
ms.assetid: 3a57306e-5c54-4fde-8593-fe3b788f18d3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0d315f554eb99fc5c05c231630eaa41d4f505535
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800905"
---
# <span data-ttu-id="8b01e-103">在以 Application Virtualization 伺服器為基礎的實作中規劃您的串流解決方案</span><span class="sxs-lookup"><span data-stu-id="8b01e-103">Planning Your Streaming Solution in an Application Virtualization Server-Based Implementation</span></span>


<span data-ttu-id="8b01e-104">如果您想要將應用程式虛擬化資料流程伺服器與應用程式虛擬化管理伺服器的部署搭配使用，您可以選擇幾個替代方案，充分利用任何基礎結構已就緒。</span><span class="sxs-lookup"><span data-stu-id="8b01e-104">If you want to use Application Virtualization Streaming Servers in conjunction with your Application Virtualization Management Server-based implementation, you can choose from several alternatives, taking advantage of whatever infrastructure is already in place.</span></span> <span data-ttu-id="8b01e-105">例如，如果您已在欄位分支辦公室中擁有伺服器，您可以將應用程式虛擬化 \\CONTENT 共用放在這些伺服器上，然後將用戶端設定為使用該內容共用作為其應用程式內容來源。</span><span class="sxs-lookup"><span data-stu-id="8b01e-105">For example, if you already have servers in your field branch offices, you can place the Application Virtualization \\CONTENT share on those servers and then configure the clients to use that content share as their application content source.</span></span> <span data-ttu-id="8b01e-106">如果您選擇只使用應用程式虛擬化管理伺服器（例如，因為您只有單一 office），則用戶端可以對流進行資料流程內容。</span><span class="sxs-lookup"><span data-stu-id="8b01e-106">If you choose to use only Application Virtualization Management Servers—for example, because you have only a single office—the clients can stream content from that server.</span></span>

<span data-ttu-id="8b01e-107">支援的選項包括使用檔案伺服器、IIS 伺服器或應用程式虛擬化資料流程伺服器。</span><span class="sxs-lookup"><span data-stu-id="8b01e-107">The supported options include using a file server, an IIS server, or an Application Virtualization Streaming Server.</span></span> <span data-ttu-id="8b01e-108">您也可以在現有的檔案伺服器或 IIS 伺服器上安裝應用程式虛擬化資料流程伺服器。</span><span class="sxs-lookup"><span data-stu-id="8b01e-108">You could also install the Application Virtualization Streaming Server on an existing file server or IIS server.</span></span> <span data-ttu-id="8b01e-109">下表摘要列出這些不同選項的特性。</span><span class="sxs-lookup"><span data-stu-id="8b01e-109">The characteristics of these different options are summarized in the following table.</span></span>

<span data-ttu-id="8b01e-110">**記事** [作用中升級] 功能可將新版本的應用程式新增至 App-v 管理伺服器或流式處理伺服器，而不會影響目前執行該應用程式的使用者。</span><span class="sxs-lookup"><span data-stu-id="8b01e-110">**Note** The active upgrade feature enables a new version of an application to be added to an App-V Management Server or Streaming Server without affecting users currently running the application.</span></span> <span data-ttu-id="8b01e-111">App-V 用戶端會在使用者下次啟動應用程式時，從 App-v 管理伺服器或資料流程伺服器自動接收最新版本的應用程式。</span><span class="sxs-lookup"><span data-stu-id="8b01e-111">The App-V clients will automatically receive the latest version of the application from the App-V Management Server or Streaming Server the next time the user starts the application.</span></span> <span data-ttu-id="8b01e-112">此功能需要使用 RTSP （S）協定。</span><span class="sxs-lookup"><span data-stu-id="8b01e-112">Use of the RTSP(S) protocol is required for this feature.</span></span>

 

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
<th align="left"><span data-ttu-id="8b01e-113">伺服器類型</span><span class="sxs-lookup"><span data-stu-id="8b01e-113">Server Type</span></span></th>
<th align="left"><span data-ttu-id="8b01e-114">通訊協定</span><span class="sxs-lookup"><span data-stu-id="8b01e-114">Protocol</span></span></th>
<th align="left"><span data-ttu-id="8b01e-115">優點</span><span class="sxs-lookup"><span data-stu-id="8b01e-115">Advantages</span></span></th>
<th align="left"><span data-ttu-id="8b01e-116">缺點</span><span class="sxs-lookup"><span data-stu-id="8b01e-116">Disadvantages</span></span></th>
<th align="left"><span data-ttu-id="8b01e-117">連結</span><span class="sxs-lookup"><span data-stu-id="8b01e-117">Links</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b01e-118">檔案伺服器</span><span class="sxs-lookup"><span data-stu-id="8b01e-118">File server</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b01e-119">SMB</span><span class="sxs-lookup"><span data-stu-id="8b01e-119">SMB</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="8b01e-120">簡單的低成本解決方案，可使用 \CONTENT 共用來設定現有的檔案伺服器</span><span class="sxs-lookup"><span data-stu-id="8b01e-120">Simple low-cost solution to configure existing file server with \CONTENT share</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="8b01e-121">沒有作用中升級</span><span class="sxs-lookup"><span data-stu-id="8b01e-121">No active upgrade</span></span></p></li>
</ul></td>
<td align="left"><p><a href="how-to-configure-the-file-server.md" data-raw-source="[How to Configure the File Server](how-to-configure-the-file-server.md)"><span data-ttu-id="8b01e-122">如何設定檔案伺服器</span><span class="sxs-lookup"><span data-stu-id="8b01e-122">How to Configure the File Server</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8b01e-123">IIS 伺服器</span><span class="sxs-lookup"><span data-stu-id="8b01e-123">IIS server</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b01e-124">HTTP/HTTPS</span><span class="sxs-lookup"><span data-stu-id="8b01e-124">HTTP/ HTTPS</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="8b01e-125">使用 HTTPS 通訊協定支援增強的安全性</span><span class="sxs-lookup"><span data-stu-id="8b01e-125">Supports enhanced security using HTTPS protocol</span></span></p></li>
<li><p><span data-ttu-id="8b01e-126">支援透過網際網路在遠端電腦上傳送資料流程</span><span class="sxs-lookup"><span data-stu-id="8b01e-126">Supports streaming to remote computers across the Internet</span></span></p></li>
<li><p><span data-ttu-id="8b01e-127">在防火牆中只開啟一個埠</span><span class="sxs-lookup"><span data-stu-id="8b01e-127">Only one port in firewall to open</span></span></p></li>
<li><p><span data-ttu-id="8b01e-128">可</span><span class="sxs-lookup"><span data-stu-id="8b01e-128">Scalable</span></span></p></li>
<li><p><span data-ttu-id="8b01e-129">熟悉的通訊協定</span><span class="sxs-lookup"><span data-stu-id="8b01e-129">Familiar protocol</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="8b01e-130">需要管理 IIS</span><span class="sxs-lookup"><span data-stu-id="8b01e-130">Need to manage IIS</span></span></p></li>
<li><p><span data-ttu-id="8b01e-131">沒有作用中升級</span><span class="sxs-lookup"><span data-stu-id="8b01e-131">No active upgrade</span></span></p></li>
</ul></td>
<td align="left"><p><a href="how-to-configure-the-server-for-iis.md" data-raw-source="[How to Configure the Server for IIS](how-to-configure-the-server-for-iis.md)"><span data-ttu-id="8b01e-132">如何設定伺服器使用 IIS</span><span class="sxs-lookup"><span data-stu-id="8b01e-132">How to Configure the Server for IIS</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b01e-133">應用程式虛擬化資料流程伺服器</span><span class="sxs-lookup"><span data-stu-id="8b01e-133">Application Virtualization Streaming Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b01e-134">RTSP/RTSPS</span><span class="sxs-lookup"><span data-stu-id="8b01e-134">RTSP/ RTSPS</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="8b01e-135">活動升級</span><span class="sxs-lookup"><span data-stu-id="8b01e-135">Active upgrade</span></span></p></li>
<li><p><span data-ttu-id="8b01e-136">使用 RTSPS 通訊協定支援增強的安全性</span><span class="sxs-lookup"><span data-stu-id="8b01e-136">Supports enhanced security using RTSPS protocol</span></span></p></li>
<li><p><span data-ttu-id="8b01e-137">在防火牆中只開啟一個埠</span><span class="sxs-lookup"><span data-stu-id="8b01e-137">Only one port in firewall to open</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="8b01e-138">雙基礎結構</span><span class="sxs-lookup"><span data-stu-id="8b01e-138">Dual infrastructure</span></span></p></li>
<li><p><span data-ttu-id="8b01e-139">伺服器管理需求</span><span class="sxs-lookup"><span data-stu-id="8b01e-139">Server administration requirement</span></span></p></li>
</ul></td>
<td align="left"><p><a href="how-to-configure-the-application-virtualization-streaming-servers.md" data-raw-source="[How to Configure the Application Virtualization Streaming Servers](how-to-configure-the-application-virtualization-streaming-servers.md)"><span data-ttu-id="8b01e-140">如何設定 Application Virtualization Streaming Server</span><span class="sxs-lookup"><span data-stu-id="8b01e-140">How to Configure the Application Virtualization Streaming Servers</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8b01e-141">應用程式虛擬化管理伺服器</span><span class="sxs-lookup"><span data-stu-id="8b01e-141">Application Virtualization Management Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b01e-142">RTSP/RTSPS</span><span class="sxs-lookup"><span data-stu-id="8b01e-142">RTSP/ RTSPS</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="8b01e-143">活動升級</span><span class="sxs-lookup"><span data-stu-id="8b01e-143">Active upgrade</span></span></p></li>
<li><p><span data-ttu-id="8b01e-144">使用 RTSPS 通訊協定支援增強的安全性</span><span class="sxs-lookup"><span data-stu-id="8b01e-144">Supports enhanced security using RTSPS protocol</span></span></p></li>
<li><p><span data-ttu-id="8b01e-145">在防火牆中只開啟一個埠</span><span class="sxs-lookup"><span data-stu-id="8b01e-145">Only one port in firewall to open</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="8b01e-146">雙基礎結構</span><span class="sxs-lookup"><span data-stu-id="8b01e-146">Dual infrastructure</span></span></p></li>
<li><p><span data-ttu-id="8b01e-147">伺服器管理需求</span><span class="sxs-lookup"><span data-stu-id="8b01e-147">Server administration requirement</span></span></p></li>
</ul></td>
<td align="left"><p><a href="how-to-configure-the-application-virtualization-management-servers.md" data-raw-source="[How to Configure the Application Virtualization Management Servers](how-to-configure-the-application-virtualization-management-servers.md)"><span data-ttu-id="8b01e-148">如何設定 Application Virtualization Management Server</span><span class="sxs-lookup"><span data-stu-id="8b01e-148">How to Configure the Application Virtualization Management Servers</span></span></a></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="8b01e-149">相關主題</span><span class="sxs-lookup"><span data-stu-id="8b01e-149">Related topics</span></span>


[<span data-ttu-id="8b01e-150">以 Application Virtualization 伺服器為基礎的案例</span><span class="sxs-lookup"><span data-stu-id="8b01e-150">Application Virtualization Server-Based Scenario</span></span>](application-virtualization-server-based-scenario.md)

[<span data-ttu-id="8b01e-151">Application Virtualization 系統元件概觀</span><span class="sxs-lookup"><span data-stu-id="8b01e-151">Overview of the Application Virtualization System Components</span></span>](overview-of-the-application-virtualization-system-components.md)

[<span data-ttu-id="8b01e-152">使用 Application Virtualization Management Server 發佈虛擬應用程式</span><span class="sxs-lookup"><span data-stu-id="8b01e-152">Publishing Virtual Applications Using Application Virtualization Management Servers</span></span>](publishing-virtual-applications-using-application-virtualization-management-servers.md)

 

 





