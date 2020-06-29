---
title: Application Virtualization 系統元件概觀
description: Application Virtualization 系統元件概觀
author: dansimp
ms.assetid: 75d88ef7-44d8-4fa7-b7f5-9153f37e570d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cab0065b9966094da687cce2f5e94069922189fc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800942"
---
# <span data-ttu-id="31065-103">Application Virtualization 系統元件概觀</span><span class="sxs-lookup"><span data-stu-id="31065-103">Overview of the Application Virtualization System Components</span></span>


<span data-ttu-id="31065-104">下表說明 Microsoft Application Virtualization 管理系統的主要元件。</span><span class="sxs-lookup"><span data-stu-id="31065-104">The following table describes the primary components of the Microsoft Application Virtualization Management System.</span></span> <span data-ttu-id="31065-105">如需有關部署這些系統元件的詳細資訊，請參閱[應用程式虛擬化伺服器案例](application-virtualization-server-based-scenario.md)。</span><span class="sxs-lookup"><span data-stu-id="31065-105">For more information about deploying these system components, see [Application Virtualization Server-Based Scenario](application-virtualization-server-based-scenario.md).</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="31065-106">元件</span><span class="sxs-lookup"><span data-stu-id="31065-106">Component</span></span></th>
<th align="left"><span data-ttu-id="31065-107">函式</span><span class="sxs-lookup"><span data-stu-id="31065-107">Function</span></span></th>
<th align="left"><span data-ttu-id="31065-108">其他資訊</span><span class="sxs-lookup"><span data-stu-id="31065-108">Additional Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="31065-109">Microsoft Application Virtualization 管理伺服器</span><span class="sxs-lookup"><span data-stu-id="31065-109">Microsoft Application Virtualization Management Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="31065-110">負責對流內容進行流式處理的元件，以及將快捷方式和檔案類型關聯發佈至應用程式虛擬化用戶端。</span><span class="sxs-lookup"><span data-stu-id="31065-110">The component responsible for streaming the package content and publishing the shortcuts and file type associations to the Application Virtualization Client.</span></span></p></td>
<td align="left"><p><span data-ttu-id="31065-111">應用程式虛擬化管理伺服器支援作用中升級、授權管理，以及可用於報告的資料庫。</span><span class="sxs-lookup"><span data-stu-id="31065-111">The Application Virtualization Management Server supports active upgrade, License Management, and a database that can be used for reporting.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="31065-112">內容 </strong> 資料夾</span><span class="sxs-lookup"><span data-stu-id="31065-112">Content</strong> folder</span></span></p></td>
<td align="left"><p><span data-ttu-id="31065-113">[流式處理] 應用程式虛擬化套件的位置。</span><span class="sxs-lookup"><span data-stu-id="31065-113">The location of the Application Virtualization packages for streaming.</span></span></p></td>
<td align="left"><p><span data-ttu-id="31065-114">這個資料夾可以位於應用程式虛擬化管理伺服器上的共用位置。</span><span class="sxs-lookup"><span data-stu-id="31065-114">This folder can be located on a share on or off the Application Virtualization Management Server.</span></span> <span data-ttu-id="31065-115">資料夾也可位於儲存區域網路（SAN）上。</span><span class="sxs-lookup"><span data-stu-id="31065-115">The folder can also be located on a Storage Area Network (SAN).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="31065-116">Microsoft Application Virtualization 管理主控台</span><span class="sxs-lookup"><span data-stu-id="31065-116">Microsoft Application Virtualization Management Console</span></span></p></td>
<td align="left"><p><span data-ttu-id="31065-117">適用于 Microsoft Application Virtualization Server 管理的 MMC 3.0 管理單元管理公用程式。</span><span class="sxs-lookup"><span data-stu-id="31065-117">An MMC 3.0 snap-in management utility for Microsoft Application Virtualization Server administration.</span></span></p></td>
<td align="left"><p><span data-ttu-id="31065-118">此元件可以安裝在 Microsoft Application Virtualization 伺服器上，或位於裝有 MMC 3.0 和的個別工作站上。已安裝 NET 2.0。</span><span class="sxs-lookup"><span data-stu-id="31065-118">This component can be installed on the Microsoft Application Virtualization server or located on a separate workstation that has MMC3.0 and .NET2.0 installed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="31065-119">Microsoft Application Virtualization 管理 Web 服務</span><span class="sxs-lookup"><span data-stu-id="31065-119">Microsoft Application Virtualization Management Web Service</span></span></p></td>
<td align="left"><p><span data-ttu-id="31065-120">負責將任何讀/寫要求與應用程式虛擬化資料存放區進行通訊的元件。</span><span class="sxs-lookup"><span data-stu-id="31065-120">The component responsible for communicating any read/write requests to the Application Virtualization data store.</span></span></p></td>
<td align="left"><p><span data-ttu-id="31065-121">此元件可以安裝在 Microsoft Application Virtualization 伺服器上，或安裝在裝有 IIS 的個別電腦上。</span><span class="sxs-lookup"><span data-stu-id="31065-121">This component can installed on the Microsoft Application Virtualization Server or on a separate computer with IIS installed.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="31065-122">Microsoft Application Virtualization 資料存放區</span><span class="sxs-lookup"><span data-stu-id="31065-122">Microsoft Application Virtualization Data Store</span></span></p></td>
<td align="left"><p><span data-ttu-id="31065-123">儲存在 SQL 資料庫中的元件，負責儲存與應用程式虛擬化基礎結構相關的所有資訊。</span><span class="sxs-lookup"><span data-stu-id="31065-123">The component stored in the SQL database and responsible for storing all information related to the Application Virtualization infrastructure.</span></span></p></td>
<td align="left"><p><span data-ttu-id="31065-124">此資訊包含所有應用程式記錄、應用程式指派，以及哪些群組負責管理應用程式虛擬化環境。</span><span class="sxs-lookup"><span data-stu-id="31065-124">This information includes all application records, application assignments, and which groups have responsibility for managing the Application Virtualization environment.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="31065-125">Microsoft Application Virtualization 串流伺服器</span><span class="sxs-lookup"><span data-stu-id="31065-125">Microsoft Application Virtualization Streaming Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="31065-126">負責將應用程式虛擬化套件託管至分支辦公室中的用戶端的元件，其中連結回到應用程式虛擬化管理伺服器，並被視為 WAN。</span><span class="sxs-lookup"><span data-stu-id="31065-126">The component responsible for hosting the Application Virtualization packages for streaming to clients in a branch office, where the link back to the Application Virtualization Management Server is considered a WAN.</span></span></p></td>
<td align="left"><p><span data-ttu-id="31065-127">此伺服器只包含流式處理功能，且既不提供應用程式虛擬化管理主控台，也不提供應用程式虛擬化管理 Web 服務。</span><span class="sxs-lookup"><span data-stu-id="31065-127">This server contains streaming functionality only and provides neither the Application Virtualization Management Console nor the Application Virtualization Management Web Service.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="31065-128">Microsoft Application Virtualization 排序器</span><span class="sxs-lookup"><span data-stu-id="31065-128">Microsoft Application Virtualization Sequencer</span></span></p></td>
<td align="left"><p><span data-ttu-id="31065-129">用來監視及捕獲應用程式安裝的元件，以建立虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="31065-129">The component used to monitor and capture the installation of applications to create virtual application packages.</span></span></p></td>
<td align="left"><p><span data-ttu-id="31065-130">輸出包含應用程式的圖示、內含封裝定義資訊的 OSD 檔案、套件資訊清單檔案，以及包含應用程式內容檔案的 SFT 檔案。</span><span class="sxs-lookup"><span data-stu-id="31065-130">Output consists of the application’s icons, an OSD file containing package definition information, a package manifest file, and the SFT file containing the application program’s content files.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="31065-131">Microsoft Application Virtualization 用戶端</span><span class="sxs-lookup"><span data-stu-id="31065-131">Microsoft Application Virtualization Client</span></span></p></td>
<td align="left"><p><span data-ttu-id="31065-132">在應用程式虛擬化桌面用戶端或應用程式虛擬化用戶端上安裝的元件（以前稱為 [終端服務]），並提供虛擬化應用程式的虛擬環境。</span><span class="sxs-lookup"><span data-stu-id="31065-132">The component installed on the Application Virtualization Desktop Client or on the Application Virtualization Client for Remote Desktop Services (formerly Terminal Services) and that provides the virtual environment for the virtualized applications.</span></span></p></td>
<td align="left"><p><span data-ttu-id="31065-133">Microsoft Application Virtualization 用戶端會將套件資料流程管理到快取、發佈重新整理、傳輸，以及與應用程式虛擬化伺服器的所有互動。</span><span class="sxs-lookup"><span data-stu-id="31065-133">The Microsoft Application Virtualization Client manages the package streaming into cache, publishing refresh, transport, and all interaction with the Application Virtualization Servers.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="31065-134">相關主題</span><span class="sxs-lookup"><span data-stu-id="31065-134">Related topics</span></span>


[<span data-ttu-id="31065-135">以 Application Virtualization 伺服器為基礎的案例</span><span class="sxs-lookup"><span data-stu-id="31065-135">Application Virtualization Server-Based Scenario</span></span>](application-virtualization-server-based-scenario.md)

[<span data-ttu-id="31065-136">在以 Application Virtualization 伺服器為基礎的實作中規劃您的串流解決方案</span><span class="sxs-lookup"><span data-stu-id="31065-136">Planning Your Streaming Solution in an Application Virtualization Server-Based Implementation</span></span>](planning-your-streaming-solution-in-an-application-virtualization-server-based-implementation.md)

[<span data-ttu-id="31065-137">使用 Application Virtualization Management Server 發佈虛擬應用程式</span><span class="sxs-lookup"><span data-stu-id="31065-137">Publishing Virtual Applications Using Application Virtualization Management Servers</span></span>](publishing-virtual-applications-using-application-virtualization-management-servers.md)

 

 





