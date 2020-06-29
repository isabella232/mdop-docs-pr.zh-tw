---
title: 如何使用 PowerShell 在 App-V 5.1 用戶端上啟用報表
description: 如何使用 PowerShell 在 App-V 5.1 用戶端上啟用報表
author: dansimp
ms.assetid: c4c58be6-cc50-44f6-bf4f-8346fc5d0c0e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1d8c0d5e1930020ed1ce354f806f8917a9644e02
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800502"
---
# <span data-ttu-id="a4d95-103">如何使用 PowerShell 在 App-V 5.1 用戶端上啟用報表</span><span class="sxs-lookup"><span data-stu-id="a4d95-103">How to Enable Reporting on the App-V 5.1 Client by Using PowerShell</span></span>


<span data-ttu-id="a4d95-104">使用下列程式來設定用於報告的 App-v 5.1。</span><span class="sxs-lookup"><span data-stu-id="a4d95-104">Use the following procedure to configure the App-V 5.1 for reporting.</span></span>

**<span data-ttu-id="a4d95-105">設定執行 App-V 5.1 用戶端以進行報告的電腦</span><span class="sxs-lookup"><span data-stu-id="a4d95-105">To configure the computer running the App-V 5.1 client for reporting</span></span>**

1. <span data-ttu-id="a4d95-106">安裝 App-V 5.1 用戶端。</span><span class="sxs-lookup"><span data-stu-id="a4d95-106">Install the App-V 5.1 client.</span></span> <span data-ttu-id="a4d95-107">如需有關安裝用戶端的詳細資訊，請參閱[如何部署 App-v 用戶端](how-to-deploy-the-app-v-client-51gb18030.md)。</span><span class="sxs-lookup"><span data-stu-id="a4d95-107">For more information about installing the client see [How to Deploy the App-V Client](how-to-deploy-the-app-v-client-51gb18030.md).</span></span>

2. <span data-ttu-id="a4d95-108">安裝 App-V 5.1 用戶端之後，請使用 AppvClientConfiguration PowerShell 來設定適當**的**報告配置設定：</span><span class="sxs-lookup"><span data-stu-id="a4d95-108">After you have installed the App-V 5.1 client, use the **Set-AppvClientConfiguration** PowerShell to configure appropriate Reporting Configuration settings:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="a4d95-109">設定</span><span class="sxs-lookup"><span data-stu-id="a4d95-109">Setting</span></span></th>
   <th align="left"><span data-ttu-id="a4d95-110">描述</span><span class="sxs-lookup"><span data-stu-id="a4d95-110">Description</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="a4d95-111">ReportingEnabled</span><span class="sxs-lookup"><span data-stu-id="a4d95-111">ReportingEnabled</span></span></p></td>
   <td align="left"><p><span data-ttu-id="a4d95-112">可讓用戶端傳回信息給報表伺服器。</span><span class="sxs-lookup"><span data-stu-id="a4d95-112">Enables the client to return information to a reporting server.</span></span> <span data-ttu-id="a4d95-113">用戶端在用戶端上收集報表資料時，必須有這個設定。</span><span class="sxs-lookup"><span data-stu-id="a4d95-113">This setting is required for the client to collect the reporting data on the client.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="a4d95-114">ReportingServerURL</span><span class="sxs-lookup"><span data-stu-id="a4d95-114">ReportingServerURL</span></span></p></td>
   <td align="left"><p><span data-ttu-id="a4d95-115">指定報表服務器上儲存用戶端資訊的位置。</span><span class="sxs-lookup"><span data-stu-id="a4d95-115">Specifies the location on the reporting server where client information is saved.</span></span> <span data-ttu-id="a4d95-116">例如，HTTP:// &lt; reportingservername &gt; ： &lt; reportingportnumber &gt; 。</span><span class="sxs-lookup"><span data-stu-id="a4d95-116">For example, http://&lt;reportingservername&gt;:&lt;reportingportnumber&gt;.</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="a4d95-117">注意</span><span class="sxs-lookup"><span data-stu-id="a4d95-117">Note</span></span></strong><br/><p><span data-ttu-id="a4d95-118">這是在報表伺服器安裝期間指派的埠號</span><span class="sxs-lookup"><span data-stu-id="a4d95-118">This is the port number that was assigned during the Reporting Server setup</span></span></p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="a4d95-119">報告開始時間</span><span class="sxs-lookup"><span data-stu-id="a4d95-119">Reporting Start Time</span></span></p></td>
   <td align="left"><p><span data-ttu-id="a4d95-120">此設定是為了安排用戶端自動將資料傳送到伺服器。</span><span class="sxs-lookup"><span data-stu-id="a4d95-120">This is set to schedule the client to automatically send the data to the server.</span></span> <span data-ttu-id="a4d95-121">此設定會指出報告資料開始傳送的小時數。</span><span class="sxs-lookup"><span data-stu-id="a4d95-121">This setting will indicate the hour at which the reporting data will start to send.</span></span> <span data-ttu-id="a4d95-122">它是24小時制格式，並會在0-23 之間取得數位。</span><span class="sxs-lookup"><span data-stu-id="a4d95-122">It is in the 24 hour format and will take a number between 0-23.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="a4d95-123">ReportingRandomDelay</span><span class="sxs-lookup"><span data-stu-id="a4d95-123">ReportingRandomDelay</span></span></p></td>
   <td align="left"><p><span data-ttu-id="a4d95-124">指定將資料傳送到報表伺服器的最大延遲（以分鐘為單位）。</span><span class="sxs-lookup"><span data-stu-id="a4d95-124">Specifies the maximum delay (in minutes) for data to be sent to the reporting server.</span></span> <span data-ttu-id="a4d95-125">當排程的任務開始時，用戶端會在0與 ReportingRandomDelay 之間產生隨機延遲，並在傳送資料之前等待指定的持續時間。</span><span class="sxs-lookup"><span data-stu-id="a4d95-125">When the scheduled task is started, the client generates a random delay between 0 and ReportingRandomDelay and will wait the specified duration before sending data.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="a4d95-126">ReportingInterval</span><span class="sxs-lookup"><span data-stu-id="a4d95-126">ReportingInterval</span></span></p></td>
   <td align="left"><p><span data-ttu-id="a4d95-127">指定用戶端將用來重新傳送資料至報表伺服器的重試時間間隔。</span><span class="sxs-lookup"><span data-stu-id="a4d95-127">Specifies the retry interval that the client will use to resend data to the reporting server.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="a4d95-128">ReportingDataCacheLimit</span><span class="sxs-lookup"><span data-stu-id="a4d95-128">ReportingDataCacheLimit</span></span></p></td>
   <td align="left"><p><span data-ttu-id="a4d95-129">指定儲存報告資訊的 XML 快取大小上限（MB）。</span><span class="sxs-lookup"><span data-stu-id="a4d95-129">Specifies the maximum size in megabytes (MB) of the XML cache for storing reporting information.</span></span> <span data-ttu-id="a4d95-130">此大小會套用到記憶體中的快取。</span><span class="sxs-lookup"><span data-stu-id="a4d95-130">The size applies to the cache in memory.</span></span> <span data-ttu-id="a4d95-131">當達到限制時，記錄檔案將會滾過。</span><span class="sxs-lookup"><span data-stu-id="a4d95-131">When the limit is reached, the log file will roll over.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="a4d95-132">ReportingDataBlockSize</span><span class="sxs-lookup"><span data-stu-id="a4d95-132">ReportingDataBlockSize</span></span></p></td>
   <td align="left"><p><span data-ttu-id="a4d95-133">指定儲存報告資訊的 XML 快取大小上限（MB）。</span><span class="sxs-lookup"><span data-stu-id="a4d95-133">Specifies the maximum size in megabytes (MB) of the XML cache for storing reporting information.</span></span> <span data-ttu-id="a4d95-134">此大小會套用到記憶體中的快取。</span><span class="sxs-lookup"><span data-stu-id="a4d95-134">The size applies to the cache in memory.</span></span> <span data-ttu-id="a4d95-135">當達到限制時，記錄檔案將會滾過。</span><span class="sxs-lookup"><span data-stu-id="a4d95-135">When the limit is reached, the log file will roll over.</span></span></p></td>
   </tr>
   </tbody>
   </table>



3. <span data-ttu-id="a4d95-136">設定適當的設定之後，執行 App-v 5.1 用戶端的電腦會自動收集資料，並將資料傳送回報表伺服器。</span><span class="sxs-lookup"><span data-stu-id="a4d95-136">After the appropriate settings have been configured, the computer running the App-V 5.1 client will automatically collect data and will send the data back to the reporting server.</span></span>

   <span data-ttu-id="a4d95-137">此外，系統管理員可以使用**AppvClientReport** PowerShell Cmdlet，手動將資料傳回按需方式。</span><span class="sxs-lookup"><span data-stu-id="a4d95-137">Additionally, administrators can manually send the data back in an on-demand manner using the **Send-AppvClientReport** PowerShell cmdlet.</span></span>

   <span data-ttu-id="a4d95-138">您**有應用程式-V 的建議**嗎？</span><span class="sxs-lookup"><span data-stu-id="a4d95-138">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="a4d95-139">在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="a4d95-139">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="a4d95-140">有應用程式-V 問題嗎？</span><span class="sxs-lookup"><span data-stu-id="a4d95-140">Got an App-V issue?</span></span>** <span data-ttu-id="a4d95-141">使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="a4d95-141">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="a4d95-142">相關主題</span><span class="sxs-lookup"><span data-stu-id="a4d95-142">Related topics</span></span>


[<span data-ttu-id="a4d95-143">使用 PowerShell 管理 App-V 5.1</span><span class="sxs-lookup"><span data-stu-id="a4d95-143">Administering App-V 5.1 by Using PowerShell</span></span>](administering-app-v-51-by-using-powershell.md)









