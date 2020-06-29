---
title: 適用於周邊網路的網際網路對向伺服器案例
description: 適用於周邊網路的網際網路對向伺服器案例
author: dansimp
ms.assetid: 8a4da6e6-82c7-49e5-b9b1-1666cba02f65
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: fcb04e651341fa107c358eaabbd7992d7ea155ec
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800988"
---
# <span data-ttu-id="203d3-103">適用於周邊網路的網際網路對向伺服器案例</span><span class="sxs-lookup"><span data-stu-id="203d3-103">Internet-Facing Server Scenarios for Perimeter Networks</span></span>


<span data-ttu-id="203d3-104">App-v 4.5 支援網際網路伺服器案例，在這種情況下，未連接至公司網路的使用者或從網路中斷連線的使用者仍然可以使用 App-v。</span><span class="sxs-lookup"><span data-stu-id="203d3-104">App-V4.5 supports Internet-facing server scenarios, in which users who are not connected to the corporate network or who disconnect from the network can still use App-V.</span></span> <span data-ttu-id="203d3-105">如下圖所示，只支援在網際網路（RTSPS 及 HTTPS）上使用安全通訊協定。</span><span class="sxs-lookup"><span data-stu-id="203d3-105">As shown in the following illustration, only the use of secure protocols on the Internet (RTSPS and HTTPS) is supported.</span></span>

![app-v 防火牆定點陣圖表](images/appvfirewalls.gif)

<span data-ttu-id="203d3-107">您可以使用 ISA 伺服器（在內部網路上有下列幾種方式）來設定網際網路程式解決方案：</span><span class="sxs-lookup"><span data-stu-id="203d3-107">You can set up an Internet-facing solution, using an ISA Server, where the App-V infrastructure is on the internal network in the following ways:</span></span>

-   <span data-ttu-id="203d3-108">為裝載 .ICO 和 OSD 檔案的 IIS 伺服器建立 Web 發佈規則，也可以選擇在內部網路上的 [資料流程套件]。</span><span class="sxs-lookup"><span data-stu-id="203d3-108">Create a Web Publishing rule for the IIS server that is hosting the ICO and OSD files—and optionally, the packages for streaming—located on the internal network.</span></span> <span data-ttu-id="203d3-109">這裡提供詳細步驟 <https://go.microsoft.com/fwlink/?LinkId=151982> 。</span><span class="sxs-lookup"><span data-stu-id="203d3-109">Detailed steps are provided at <https://go.microsoft.com/fwlink/?LinkId=151982>.</span></span>

-   <span data-ttu-id="203d3-110">為 App-V Web 管理伺服器（RTSPS）建立伺服器發佈規則。</span><span class="sxs-lookup"><span data-stu-id="203d3-110">Create a Server Publishing rule for the App-V Web Management Server (RTSPS).</span></span> <span data-ttu-id="203d3-111">這裡提供詳細步驟 [https://go.microsoft.com/fwlink/?LinkId=151983&](https://go.microsoft.com/fwlink/?LinkId=151983) 。</span><span class="sxs-lookup"><span data-stu-id="203d3-111">Detailed steps are provided at [https://go.microsoft.com/fwlink/?LinkId=151983&](https://go.microsoft.com/fwlink/?LinkId=151983).</span></span>

<span data-ttu-id="203d3-112">如下圖所示，如果基礎結構在用戶端與 ISA 伺服器之間或 ISA 伺服器與內部網路之間已實施其他防火牆，則必須建立 RTSPS （TCP 322）與 HTTPS （TCP 443）防火牆規則，才能支援流量流程。</span><span class="sxs-lookup"><span data-stu-id="203d3-112">As shown in the following illustration, if the infrastructure has implemented other firewalls between the client and the ISA Server or between the ISA Server and the internal network, both RTSPS (TCP 322) and HTTPS (TCP 443) firewall rules must be created to support the flow of traffic.</span></span> <span data-ttu-id="203d3-113">此外，如果在 ISA 伺服器與內部網路之間已實施防火牆，則必須允許網域成員所需的預設流量透過防火牆（DNS、LDAP、Kerberos、SMB/CIFS）進行隧道。</span><span class="sxs-lookup"><span data-stu-id="203d3-113">Also, if firewalls have been implemented between the ISA Server and the internal network, the default traffic required for domain members must be permitted to tunnel through the firewall (DNS, LDAP, Kerberos, SMB/CIFS).</span></span>

![app-v 周邊網路防火牆圖表](images/appvperimeternetworkfirewall.gif)

<span data-ttu-id="203d3-115">由於防火牆解決方案與環境有所不同，本主題中所提供的指導方針說明在周邊網路中設定面向網際網路的 App-v 環境所需的流量。</span><span class="sxs-lookup"><span data-stu-id="203d3-115">Because the firewall solutions vary from environment to environment, the guidance provided in this topic describes the traffic that would be required to configure an Internet-facing App-V environment in the perimeter network.</span></span> <span data-ttu-id="203d3-116">此資訊也包括建議的內部網路伺服器。</span><span class="sxs-lookup"><span data-stu-id="203d3-116">This information also includes the recommended internal network servers.</span></span>

<span data-ttu-id="203d3-117">將下列伺服器放在周邊網路：</span><span class="sxs-lookup"><span data-stu-id="203d3-117">Place the following servers in the perimeter network:</span></span>

-   <span data-ttu-id="203d3-118">App-v 管理伺服器</span><span class="sxs-lookup"><span data-stu-id="203d3-118">App-V Management Server</span></span>

-   <span data-ttu-id="203d3-119">用於發佈及流式處理的 IIS 伺服器</span><span class="sxs-lookup"><span data-stu-id="203d3-119">IIS server for publishing and streaming</span></span>

<span data-ttu-id="203d3-120">**記事** 最佳做法是將管理伺服器與 IIS 伺服器放在不同的電腦上。</span><span class="sxs-lookup"><span data-stu-id="203d3-120">**Note** It is a best practice to place the Management Server and IIS server on separate computers.</span></span>

 

<span data-ttu-id="203d3-121">將下列伺服器放在內部網路：</span><span class="sxs-lookup"><span data-stu-id="203d3-121">Place the following servers in the internal network:</span></span>

-   <span data-ttu-id="203d3-122">內容伺服器</span><span class="sxs-lookup"><span data-stu-id="203d3-122">Content server</span></span>

-   <span data-ttu-id="203d3-123">資料存放區（SQL Server）</span><span class="sxs-lookup"><span data-stu-id="203d3-123">Data store (SQL Server)</span></span>

-   <span data-ttu-id="203d3-124">Active Directory 網網域控制站</span><span class="sxs-lookup"><span data-stu-id="203d3-124">Active Directory Domain Controller</span></span>

## <span data-ttu-id="203d3-125">流量需求</span><span class="sxs-lookup"><span data-stu-id="203d3-125">Traffic Requirements</span></span>


<span data-ttu-id="203d3-126">下表列出從網際網路與周邊網路，以及從周邊網路到內部網路的通訊需求。</span><span class="sxs-lookup"><span data-stu-id="203d3-126">The following tables list the traffic requirements for communication from the Internet and the perimeter network and from the perimeter network to the internal network.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="203d3-127">從網際網路到周邊網路的流量需求</span><span class="sxs-lookup"><span data-stu-id="203d3-127">Traffic Requirements from Internet to Perimeter Network</span></span></th>
<th align="left"><span data-ttu-id="203d3-128">詳細資料</span><span class="sxs-lookup"><span data-stu-id="203d3-128">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="203d3-129">RTSPS （發佈更新及流式處理套件）</span><span class="sxs-lookup"><span data-stu-id="203d3-129">RTSPS (publishing refresh and streaming packages)</span></span></p></td>
<td align="left"><p><span data-ttu-id="203d3-130">預設為 TCP 322;此功能可以在 App-v Management Server 中變更。</span><span class="sxs-lookup"><span data-stu-id="203d3-130">TCP 322 by default; this can be changed in App-V Management Server.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="203d3-131">HTTPS （發佈 .ICO 和 OSD 檔案及流式套件）</span><span class="sxs-lookup"><span data-stu-id="203d3-131">HTTPS (publishing ICO and OSD files and streaming packages)</span></span></p></td>
<td align="left"><p><span data-ttu-id="203d3-132">預設為 TCP 443;這可以在 IIS 設定中變更。</span><span class="sxs-lookup"><span data-stu-id="203d3-132">TCP 443 by default; this can be changed in the IIS configuration.</span></span></p></td>
</tr>
</tbody>
</table>

 

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="203d3-133">從周邊網路到內部網路的流量需求</span><span class="sxs-lookup"><span data-stu-id="203d3-133">Traffic Requirements from Perimeter Network to Internal Network</span></span></th>
<th align="left"><span data-ttu-id="203d3-134">詳細資料</span><span class="sxs-lookup"><span data-stu-id="203d3-134">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="203d3-135">SQL Server</span><span class="sxs-lookup"><span data-stu-id="203d3-135">SQL Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="203d3-136">TCP 1433 是預設值，但可以在 SQL Server 中設定。</span><span class="sxs-lookup"><span data-stu-id="203d3-136">TCP 1433 is the default but can be configured in SQL Server.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="203d3-137">SMB/CIFS</span><span class="sxs-lookup"><span data-stu-id="203d3-137">SMB/CIFS</span></span></p></td>
<td align="left"><p><span data-ttu-id="203d3-138">如果內容目錄是從管理伺服器或 IIS 伺服器的遠端位置（建議使用）。</span><span class="sxs-lookup"><span data-stu-id="203d3-138">If the content directory is located remotely from the Management Server(s) or IIS server (recommended).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="203d3-139">Kerberos</span><span class="sxs-lookup"><span data-stu-id="203d3-139">Kerberos</span></span></p></td>
<td align="left"><p><span data-ttu-id="203d3-140">TCP 和 UDP 88</span><span class="sxs-lookup"><span data-stu-id="203d3-140">TCP and UDP 88</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="203d3-141">適用</span><span class="sxs-lookup"><span data-stu-id="203d3-141">LDAP</span></span></p></td>
<td align="left"><p><span data-ttu-id="203d3-142">TCP 和 UDP 389</span><span class="sxs-lookup"><span data-stu-id="203d3-142">TCP and UDP 389</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="203d3-143">DNS</span><span class="sxs-lookup"><span data-stu-id="203d3-143">DNS</span></span></p></td>
<td align="left"><p><span data-ttu-id="203d3-144">內部資源的名稱解析（在週邊網路伺服器上使用主機的檔案可以消除）</span><span class="sxs-lookup"><span data-stu-id="203d3-144">For name resolution of internal resources (can be eliminated with the use of host’s file on perimeter network servers)</span></span></p></td>
</tr>
</tbody>
</table>

 

 

 





