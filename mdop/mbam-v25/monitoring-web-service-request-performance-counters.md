---
title: 監視 Web 服務要求效能計數器
description: 監視 Web 服務要求效能計數器
author: dansimp
ms.assetid: bdb812a1-465a-4098-b4c0-cb99890d1b0d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 2db96e3375562b48d289ea5a21dc7e89b800d1ad
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810220"
---
# <span data-ttu-id="2789e-103">監視 Web 服務要求效能計數器</span><span class="sxs-lookup"><span data-stu-id="2789e-103">Monitoring Web Service Request Performance Counters</span></span>


<span data-ttu-id="2789e-104">Microsoft BitLocker 管理與監控（MBAM）提供的效能計數器會記錄傳送至下列 web 服務的要求效能：</span><span class="sxs-lookup"><span data-stu-id="2789e-104">Microsoft BitLocker Administration and Monitoring (MBAM) provides performance counters that record the performance of requests that are sent to the following web services:</span></span>

-   <span data-ttu-id="2789e-105">**StatusReportingService** –接收合規性狀態要求的服務</span><span class="sxs-lookup"><span data-stu-id="2789e-105">**StatusReportingService.svc** – service that receives requests for compliance status</span></span>

-   <span data-ttu-id="2789e-106">**CoreService** -接收到金鑰復原嘗試要求的服務</span><span class="sxs-lookup"><span data-stu-id="2789e-106">**CoreService.svc** – service that receives requests for key recovery attempts</span></span>

## <span data-ttu-id="2789e-107">MBAM 提供的效能計數器</span><span class="sxs-lookup"><span data-stu-id="2789e-107">Performance counters that MBAM provides</span></span>


<span data-ttu-id="2789e-108">MBAM 會針對每個由其 StatusReportingService 和 CoreService web 服務所實現的公用方法，提供下列效能計數器：</span><span class="sxs-lookup"><span data-stu-id="2789e-108">MBAM provides the following performance counters for each of the public methods that is implemented by its StatusReportingService and CoreService web services:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2789e-109">效能計數器類型</span><span class="sxs-lookup"><span data-stu-id="2789e-109">Type of performance counter</span></span></th>
<th align="left"><span data-ttu-id="2789e-110">描述</span><span class="sxs-lookup"><span data-stu-id="2789e-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2789e-111">要求總次數</span><span class="sxs-lookup"><span data-stu-id="2789e-111">Total number of requests</span></span></p></td>
<td align="left"><p><span data-ttu-id="2789e-112">提供伺服器啟動或重新開機時從零開始的遞增計數。</span><span class="sxs-lookup"><span data-stu-id="2789e-112">Provides an incrementing count that starts from zero when the server is started or restarted.</span></span></p>
<p><span data-ttu-id="2789e-113">提供系統活動的整體視圖。</span><span class="sxs-lookup"><span data-stu-id="2789e-113">Provides an overall view of system activity.</span></span> <span data-ttu-id="2789e-114">可透過自動化工具加以監視，以確保伺服器的健康情況，並確認計數器在指定的一段時間內持續增加。</span><span class="sxs-lookup"><span data-stu-id="2789e-114">Can be monitored by automated tools to ensure the health of the server and to validate that the counter continually increments over a specified period of time.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2789e-115">每秒的要求數</span><span class="sxs-lookup"><span data-stu-id="2789e-115">Requests per second</span></span></p></td>
<td align="left"><p><span data-ttu-id="2789e-116">指示 MBAM 伺服器的目前輸送量，因為它支援 MBAM 用戶端基礎。</span><span class="sxs-lookup"><span data-stu-id="2789e-116">Indicates the current throughput of the MBAM Server as it supports the MBAM client base.</span></span></p>
<p><span data-ttu-id="2789e-117">可讓網站系統管理員：</span><span class="sxs-lookup"><span data-stu-id="2789e-117">Enables site administrators to:</span></span></p>
<ul>
<li><p><span data-ttu-id="2789e-118">根據 MBAM 用戶端數及其報告頻率，計算每秒的平均請求數。</span><span class="sxs-lookup"><span data-stu-id="2789e-118">Calculate the average number of requests per second, based on the number of MBAM Clients and their reporting frequency.</span></span></p></li>
<li><p><span data-ttu-id="2789e-119">驗證每秒的要求數已廣泛與計算每秒的平均請求數。</span><span class="sxs-lookup"><span data-stu-id="2789e-119">Validate that the number of requests per second broadly correlates with the calculated average number of requests per second.</span></span> <span data-ttu-id="2789e-120">明顯的變化可能表示 MBAM 用戶端未安裝在用戶端基礎的某個部分，或是 MBAM 群組原則物件尚未順利部署。</span><span class="sxs-lookup"><span data-stu-id="2789e-120">A significant variance can indicate that the MBAM Client isn't installed on a percentage of the client base or that an MBAM Group Policy Object hasn't been successfully deployed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2789e-121">要求持續時間</span><span class="sxs-lookup"><span data-stu-id="2789e-121">Request duration</span></span></p></td>
<td align="left"><p><span data-ttu-id="2789e-122">記錄要求的持續時間（以毫秒為單位）。</span><span class="sxs-lookup"><span data-stu-id="2789e-122">Records the duration of requests in milliseconds.</span></span></p>
<p><span data-ttu-id="2789e-123">雖然這個計數器會在每個要求的持續時間內更新，但是 Windows 效能監視器會定期（通常是每秒一個）進行範例，因此您可能會在值中看到一些可變性。</span><span class="sxs-lookup"><span data-stu-id="2789e-123">Although this counter is updated with the duration of each request, Windows Performance Monitor samples it only periodically (typically every second), so you might see some variability in the value.</span></span> <span data-ttu-id="2789e-124">基於這個原因，請考慮使用 [效能監視器] 所顯示的 [平均值] 值。</span><span class="sxs-lookup"><span data-stu-id="2789e-124">For this reason, consider using the average value displayed by Performance Monitor.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="2789e-125">效能計數器結果與建議</span><span class="sxs-lookup"><span data-stu-id="2789e-125">Performance counter results and recommendations</span></span>


<span data-ttu-id="2789e-126">當您將新的 MBAM 用戶端新增到具有備用容量的 MBAM 伺服器時，預期每秒的要求數量都會增加。</span><span class="sxs-lookup"><span data-stu-id="2789e-126">As you add new MBAM Clients to an MBAM Server with spare capacity, expect to see an increase in the number of requests per second.</span></span> <span data-ttu-id="2789e-127">這個增加會與新用戶端電腦的數目成比例。</span><span class="sxs-lookup"><span data-stu-id="2789e-127">This increase will be proportional to the number of new client computers.</span></span> <span data-ttu-id="2789e-128">平均要求期間將保持相對靜態。</span><span class="sxs-lookup"><span data-stu-id="2789e-128">The average request duration will remain relatively static.</span></span> <span data-ttu-id="2789e-129">隨著伺服器接近其最大容量，每秒的要求都會開始到階層，而平均要求期間則會開始較長的時間。</span><span class="sxs-lookup"><span data-stu-id="2789e-129">As the server nears its maximum capacity, the requests per second start to level out, and the average request duration starts to get longer.</span></span>

<span data-ttu-id="2789e-130">如果您擔心 MBAM 伺服器是否可支援您的用戶端基礎，請考慮在不同的用戶端電腦集合的階段中部署 MBAM。</span><span class="sxs-lookup"><span data-stu-id="2789e-130">If you are concerned about whether your MBAM Servers can support your client base, consider deploying MBAM in phases across different collections of client computers.</span></span> <span data-ttu-id="2789e-131">當您將 MBAM 部署到每個用戶端電腦集合時，建議您拍攝效能計數器的快照，以查看部署到每個新用戶端集合的相對效果。</span><span class="sxs-lookup"><span data-stu-id="2789e-131">As you deploy MBAM to each collection of client computers, we recommend that you take snapshots of the performance counters to see the relative impact of deploying to each new client collection.</span></span> <span data-ttu-id="2789e-132">如果每秒的要求數開始為 [停止調配]，而平均要求持續時間增加，請執行下列其中一項操作來加強您的 MBAM 伺服器基礎結構：</span><span class="sxs-lookup"><span data-stu-id="2789e-132">If the number of requests per second starts to level off and the average request duration increases, consider enhancing your MBAM Server infrastructure by doing one of the following:</span></span>

-   <span data-ttu-id="2789e-133">將 MBAM 資料庫移至專用的 Microsoft SQL Server 或 SQL Server 群集</span><span class="sxs-lookup"><span data-stu-id="2789e-133">Moving the MBAM database onto a dedicated Microsoft SQL Server or SQL Server cluster</span></span>

-   <span data-ttu-id="2789e-134">跨多個網際網路資訊服務（IIS） web 伺服器的負載平衡 MBAM</span><span class="sxs-lookup"><span data-stu-id="2789e-134">Load-balancing MBAM across multiple Internet Information Services (IIS) web servers</span></span>

-   <span data-ttu-id="2789e-135">在功能更強大的伺服器硬體上部署 MBAM</span><span class="sxs-lookup"><span data-stu-id="2789e-135">Deploying MBAM on more powerful server hardware</span></span>

## <span data-ttu-id="2789e-136">查看效能計數器</span><span class="sxs-lookup"><span data-stu-id="2789e-136">Viewing performance counters</span></span>


<span data-ttu-id="2789e-137">建議用來查看 MBAM 效能計數器的工具是 windows 效能監視器，它隨附于 Windows。</span><span class="sxs-lookup"><span data-stu-id="2789e-137">The recommended tool for viewing MBAM performance counters is Windows Performance Monitor, which comes with Windows.</span></span> <span data-ttu-id="2789e-138">如果您使用的是 Windows PowerShell，您就不需要在查看計數器之前啟用它們，因為它們是由 Windows PowerShell **enable-webapplication** Cmdlet 自動註冊。</span><span class="sxs-lookup"><span data-stu-id="2789e-138">If you are using Windows PowerShell, you don’t need to enable the counters before viewing them, as they are automatically registered by the Windows PowerShell **Enable-webapplication** cmdlet.</span></span>

<span data-ttu-id="2789e-139">如需如何查看效能計數器的詳細指示，請參閱[如何查看 MBAM 效能計數器](https://go.microsoft.com/fwlink/?LinkId=393457)。</span><span class="sxs-lookup"><span data-stu-id="2789e-139">For detailed instructions on how to view performance counters, see [How to View MBAM Performance Counters](https://go.microsoft.com/fwlink/?LinkId=393457).</span></span>



## <span data-ttu-id="2789e-140">相關主題</span><span class="sxs-lookup"><span data-stu-id="2789e-140">Related topics</span></span>


[<span data-ttu-id="2789e-141">維護 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="2789e-141">Maintaining MBAM 2.5</span></span>](maintaining-mbam-25.md)

 

 


## <span data-ttu-id="2789e-142">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="2789e-142">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="2789e-143">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="2789e-143">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="2789e-144">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="2789e-144">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>


