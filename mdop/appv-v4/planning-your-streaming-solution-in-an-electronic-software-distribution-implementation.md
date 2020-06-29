---
title: 在電子軟體發佈實作中規劃您的串流解決方案
description: 在電子軟體發佈實作中規劃您的串流解決方案
author: dansimp
ms.assetid: bc18772a-f169-486f-adb1-7af1a31845aa
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c49d6fc0b5f8f5dee347ead3bb899ce9b0387024
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800903"
---
# <span data-ttu-id="335c6-103">在電子軟體發佈實作中規劃您的串流解決方案</span><span class="sxs-lookup"><span data-stu-id="335c6-103">Planning Your Streaming Solution in an Electronic Software Distribution Implementation</span></span>


<span data-ttu-id="335c6-104">如果您決定將流式處理伺服器與 ESD 系統搭配使用，以讓應用程式內容可供您的最終使用者電腦使用，您可以選擇幾個替代方案，充分利用任何基礎結構。</span><span class="sxs-lookup"><span data-stu-id="335c6-104">If you decide to use streaming servers in conjunction with your ESD system to make application content available to your end user computers, you can choose from several alternatives, taking advantage of whatever infrastructure is already in place.</span></span> <span data-ttu-id="335c6-105">例如，如果您的 ESD 系統在欄位分支辦公室中的伺服器上有軟體發佈共用，您可以將應用程式虛擬化 \\CONTENT 共用放在這些伺服器上，然後將用戶端設定為使用該內容共用作為其應用程式內容來源。</span><span class="sxs-lookup"><span data-stu-id="335c6-105">For example, if your ESD system has software distribution shares on servers in your field branch offices, you can place the Application Virtualization \\CONTENT share on those servers and then configure the clients to use that content share as their application content source.</span></span> <span data-ttu-id="335c6-106">支援的選項包括使用檔案伺服器或 IIS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="335c6-106">The supported options include using a file server or an IIS server.</span></span> <span data-ttu-id="335c6-107">您也可以在現有的檔案伺服器或 IIS 伺服器上安裝應用程式虛擬化資料流程伺服器。</span><span class="sxs-lookup"><span data-stu-id="335c6-107">You could also install the Application Virtualization Streaming Server on an existing file server or IIS server.</span></span>

<span data-ttu-id="335c6-108">應用程式虛擬化資料流程伺服器提供應用程式虛擬化中的作用中升級功能支援。</span><span class="sxs-lookup"><span data-stu-id="335c6-108">The Application Virtualization Streaming Server provides support for the active upgrade feature in Application Virtualization.</span></span> <span data-ttu-id="335c6-109">[作用中升級] 功能可將新版本的應用程式新增至 App-v 管理伺服器或流式處理伺服器，而不會影響目前執行該應用程式的使用者。</span><span class="sxs-lookup"><span data-stu-id="335c6-109">The active upgrade feature enables a new version of an application to be added to an App-V Management Server or Streaming Server without affecting users currently running the application.</span></span> <span data-ttu-id="335c6-110">App-V 用戶端會在使用者下次啟動應用程式時，從 App-v 管理伺服器或資料流程伺服器自動接收最新版本的應用程式。</span><span class="sxs-lookup"><span data-stu-id="335c6-110">The App-V clients will automatically receive the latest version of the application from the App-V Management Server or Streaming Server the next time the user starts the application.</span></span> <span data-ttu-id="335c6-111">此功能需要使用 RTSP （S）協定。</span><span class="sxs-lookup"><span data-stu-id="335c6-111">Use of the RTSP(S) protocol is required for this feature.</span></span> <span data-ttu-id="335c6-112">如果您選擇不使用應用程式虛擬化資料流程伺服器，您將需要使用 ESD 系統來明確管理應用程式套件升級。</span><span class="sxs-lookup"><span data-stu-id="335c6-112">If you choose not to use the Application Virtualization Streaming Server, you will need to explicitly manage application package upgrades by using the ESD system.</span></span>

<span data-ttu-id="335c6-113">**記事** 應用程式的存取權是由 Active Directory 網域服務中的安全性群組所控制，因此您必須規劃一個處理每個虛擬應用程式的安全性群組，以及管理要新增至每個群組的使用者。</span><span class="sxs-lookup"><span data-stu-id="335c6-113">**Note** Access to the applications is controlled by means of Security Groups in Active Directory Domain Services, so you will need to plan a process for setting up a security group for each virtual application and for managing which users are added to each group.</span></span> <span data-ttu-id="335c6-114">應用程式虛擬化系統管理員會將 Acl 設定為使用這些 Active Directory 群組，方法是將 Acl 套用至內容共用底下的應用程式目錄，控制對套件的存取權（根據 Active Directory 群組成員資格）。</span><span class="sxs-lookup"><span data-stu-id="335c6-114">The Application Virtualization system administrator configures each streaming server to use these Active Directory groups by applying ACLs to the application directories under the CONTENT share, which controls access to the packages based on Active Directory group membership.</span></span>

 

<span data-ttu-id="335c6-115">下表摘要列出可用的 [資料流程] 選項的特性。</span><span class="sxs-lookup"><span data-stu-id="335c6-115">The characteristics of the available streaming options are summarized in the following table.</span></span>

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
<th align="left"><span data-ttu-id="335c6-116">伺服器類型</span><span class="sxs-lookup"><span data-stu-id="335c6-116">Server Type</span></span></th>
<th align="left"><span data-ttu-id="335c6-117">通訊協定</span><span class="sxs-lookup"><span data-stu-id="335c6-117">Protocol</span></span></th>
<th align="left"><span data-ttu-id="335c6-118">優點</span><span class="sxs-lookup"><span data-stu-id="335c6-118">Advantages</span></span></th>
<th align="left"><span data-ttu-id="335c6-119">缺點</span><span class="sxs-lookup"><span data-stu-id="335c6-119">Disadvantages</span></span></th>
<th align="left"><span data-ttu-id="335c6-120">連結</span><span class="sxs-lookup"><span data-stu-id="335c6-120">Links</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="335c6-121">檔案伺服器</span><span class="sxs-lookup"><span data-stu-id="335c6-121">File server</span></span></p></td>
<td align="left"><p><span data-ttu-id="335c6-122">SMB</span><span class="sxs-lookup"><span data-stu-id="335c6-122">SMB</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="335c6-123">簡單的低成本解決方案，可使用 \CONTENT 共用來設定現有的檔案伺服器</span><span class="sxs-lookup"><span data-stu-id="335c6-123">Simple low-cost solution to configure existing file server with \CONTENT share</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="335c6-124">沒有作用中升級</span><span class="sxs-lookup"><span data-stu-id="335c6-124">No active upgrade</span></span></p></li>
</ul></td>
<td align="left"><p><a href="how-to-configure-the-file-server.md" data-raw-source="[How to Configure the File Server](how-to-configure-the-file-server.md)"><span data-ttu-id="335c6-125">如何設定檔案伺服器</span><span class="sxs-lookup"><span data-stu-id="335c6-125">How to Configure the File Server</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="335c6-126">IIS 伺服器</span><span class="sxs-lookup"><span data-stu-id="335c6-126">IIS server</span></span></p></td>
<td align="left"><p><span data-ttu-id="335c6-127">HTTP/HTTPS</span><span class="sxs-lookup"><span data-stu-id="335c6-127">HTTP/ HTTPS</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="335c6-128">使用 HTTPS 通訊協定支援增強的安全性</span><span class="sxs-lookup"><span data-stu-id="335c6-128">Supports enhanced security using HTTPS protocol</span></span></p></li>
<li><p><span data-ttu-id="335c6-129">支援透過網際網路在遠端電腦上傳送資料流程</span><span class="sxs-lookup"><span data-stu-id="335c6-129">Supports streaming to remote computers across the Internet</span></span></p></li>
<li><p><span data-ttu-id="335c6-130">在防火牆中只開啟一個埠</span><span class="sxs-lookup"><span data-stu-id="335c6-130">Only one port in firewall to open</span></span></p></li>
<li><p><span data-ttu-id="335c6-131">可</span><span class="sxs-lookup"><span data-stu-id="335c6-131">Scalable</span></span></p></li>
<li><p><span data-ttu-id="335c6-132">熟悉的通訊協定</span><span class="sxs-lookup"><span data-stu-id="335c6-132">Familiar protocol</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="335c6-133">需要管理 IIS</span><span class="sxs-lookup"><span data-stu-id="335c6-133">Need to manage IIS</span></span></p></li>
<li><p><span data-ttu-id="335c6-134">沒有作用中升級</span><span class="sxs-lookup"><span data-stu-id="335c6-134">No active upgrade</span></span></p></li>
</ul></td>
<td align="left"><p><a href="how-to-configure-the-server-for-iis.md" data-raw-source="[How to Configure the Server for IIS](how-to-configure-the-server-for-iis.md)"><span data-ttu-id="335c6-135">如何設定伺服器使用 IIS</span><span class="sxs-lookup"><span data-stu-id="335c6-135">How to Configure the Server for IIS</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="335c6-136">應用程式虛擬化資料流程伺服器</span><span class="sxs-lookup"><span data-stu-id="335c6-136">Application Virtualization Streaming Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="335c6-137">RTSP/RTSPS</span><span class="sxs-lookup"><span data-stu-id="335c6-137">RTSP/ RTSPS</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="335c6-138">活動升級</span><span class="sxs-lookup"><span data-stu-id="335c6-138">Active upgrade</span></span></p></li>
<li><p><span data-ttu-id="335c6-139">使用 RTSPS 通訊協定支援增強的安全性</span><span class="sxs-lookup"><span data-stu-id="335c6-139">Supports enhanced security using RTSPS protocol</span></span></p></li>
<li><p><span data-ttu-id="335c6-140">在防火牆中只開啟一個埠</span><span class="sxs-lookup"><span data-stu-id="335c6-140">Only one port in firewall to open</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="335c6-141">雙基礎結構</span><span class="sxs-lookup"><span data-stu-id="335c6-141">Dual infrastructure</span></span></p></li>
<li><p><span data-ttu-id="335c6-142">伺服器管理需求</span><span class="sxs-lookup"><span data-stu-id="335c6-142">Server administration requirement</span></span></p></li>
</ul></td>
<td align="left"><p><a href="how-to-configure-the-application-virtualization-management-servers.md" data-raw-source="[How to Configure the Application Virtualization Management Servers](how-to-configure-the-application-virtualization-management-servers.md)"><span data-ttu-id="335c6-143">如何設定 Application Virtualization Management Server</span><span class="sxs-lookup"><span data-stu-id="335c6-143">How to Configure the Application Virtualization Management Servers</span></span></a></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="335c6-144">相關主題</span><span class="sxs-lookup"><span data-stu-id="335c6-144">Related topics</span></span>


[<span data-ttu-id="335c6-145">如何針對以 ESD 為基礎的部署設定伺服器</span><span class="sxs-lookup"><span data-stu-id="335c6-145">How to Configure Servers for ESD-Based Deployment</span></span>](how-to-configure-servers-for-esd-based-deployment.md)

[<span data-ttu-id="335c6-146">安全性與保護概觀</span><span class="sxs-lookup"><span data-stu-id="335c6-146">Security and Protection Overview</span></span>](security-and-protection-overview.md)

[<span data-ttu-id="335c6-147">使用電子軟體發佈來發佈虛擬應用程式</span><span class="sxs-lookup"><span data-stu-id="335c6-147">Publishing Virtual Applications Using Electronic Software Distribution</span></span>](publishing-virtual-applications-using-electronic-software-distribution.md)

 

 





