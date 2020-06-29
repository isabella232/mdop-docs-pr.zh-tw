---
title: 使用 App-V 5.1 Client Management Console
description: 使用 App-V 5.1 Client Management Console
author: dansimp
ms.assetid: be6d4e35-5701-4f9a-ba8a-bede12662cf1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 63dd75395cdfef1aebae30b364f77465ba8a9882
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800298"
---
# <span data-ttu-id="aa6bb-103">使用 App-V 5.1 Client Management Console</span><span class="sxs-lookup"><span data-stu-id="aa6bb-103">Using the App-V 5.1 Client Management Console</span></span>


<span data-ttu-id="aa6bb-104">本主題提供如何設定及管理 Microsoft Application Virtualization （App-v）5.1 用戶端的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="aa6bb-104">This topic provides information about how you can configure and manage the Microsoft Application Virtualization (App-V) 5.1 client.</span></span>

## <span data-ttu-id="aa6bb-105">修改 App-V 5.1 用戶端設定</span><span class="sxs-lookup"><span data-stu-id="aa6bb-105">Modify App-V 5.1 client configuration</span></span>


<span data-ttu-id="aa6bb-106">App-V 5.1 用戶端具有相關設定，可設定為決定用戶端在您的環境中執行的方式。</span><span class="sxs-lookup"><span data-stu-id="aa6bb-106">The App-V 5.1 client has associated settings that can be configured to determine how the client will run in your environment.</span></span> <span data-ttu-id="aa6bb-107">您可以在執行用戶端或使用 PowerShell 或群組原則的電腦上管理這些設定。</span><span class="sxs-lookup"><span data-stu-id="aa6bb-107">You can manage these settings on the computer that runs the client or by using PowerShell or Group Policy.</span></span> <span data-ttu-id="aa6bb-108">如需有關如何使用 PowerShell 或群組原則設定修改用戶端的詳細資訊，請參閱[如何使用 Powershell 修改用戶端](how-to-modify-client-configuration-by-using-powershell51.md)設定。</span><span class="sxs-lookup"><span data-stu-id="aa6bb-108">For more information about how to modify the client using PowerShell or Group Policy configuration see, [How to Modify Client Configuration by Using PowerShell](how-to-modify-client-configuration-by-using-powershell51.md).</span></span>

## <a href="" id="the-app-v-5-1-client-management-console-"></a><span data-ttu-id="aa6bb-109">App-V 5.1 用戶端管理主控台</span><span class="sxs-lookup"><span data-stu-id="aa6bb-109">The App-V 5.1 client management console</span></span>


<span data-ttu-id="aa6bb-110">您可以取得 App-V 5.1 用戶端的相關資訊，或使用 App-v 5.1 用戶端管理主控台執行特定工作。</span><span class="sxs-lookup"><span data-stu-id="aa6bb-110">You can obtain information about the App-V 5.1 client or perform specific tasks by using the App-V 5.1 client management console.</span></span> <span data-ttu-id="aa6bb-111">您可以在用戶端管理主控台執行的許多工作，您也可以使用 PowerShell 來執行。</span><span class="sxs-lookup"><span data-stu-id="aa6bb-111">Many of the tasks that you can perform in the client management console you can also perform by using PowerShell.</span></span> <span data-ttu-id="aa6bb-112">每個動作的相關 PowerShell Cmdlet 也會顯示在下表中。</span><span class="sxs-lookup"><span data-stu-id="aa6bb-112">The associated PowerShell cmdlets for each action are also displayed in the following table.</span></span> <span data-ttu-id="aa6bb-113">如需如何使用 PowerShell 的詳細資訊，請參閱[使用 Powershell 管理 app-v 5.1](administering-app-v-51-by-using-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="aa6bb-113">For more information about how to use PowerShell, see [Administering App-V 5.1 by Using PowerShell](administering-app-v-51-by-using-powershell.md).</span></span>

<span data-ttu-id="aa6bb-114">用戶端管理主控台包含下列所述的主要索引標籤。</span><span class="sxs-lookup"><span data-stu-id="aa6bb-114">The client management console contains the following described main tabs.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="aa6bb-115">Tab</span><span class="sxs-lookup"><span data-stu-id="aa6bb-115">Tab</span></span></th>
<th align="left"><span data-ttu-id="aa6bb-116">描述</span><span class="sxs-lookup"><span data-stu-id="aa6bb-116">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="aa6bb-117">概觀</span><span class="sxs-lookup"><span data-stu-id="aa6bb-117">Overview</span></span></p></td>
<td align="left"><p><span data-ttu-id="aa6bb-118">[ <strong> 概覽] 索引標籤 </strong> 包含下列元素：</span><span class="sxs-lookup"><span data-stu-id="aa6bb-118">The <strong>Overview</strong> tab contains the following elements:</span></span></p>
<ul>
<li><p><span data-ttu-id="aa6bb-119">更新–使用 <strong> 更新磚重新整理 </strong> 虛擬化的應用程式，或接收新的虛擬化套件。</span><span class="sxs-lookup"><span data-stu-id="aa6bb-119">Update – Use the <strong>Update</strong> tile to refresh a virtualized application or to receive a new virtualized package.</span></span></p>
<p><span data-ttu-id="aa6bb-120">[ <strong> 上一次重新整理] 會 </strong> 顯示目前的虛擬化套件版本。</span><span class="sxs-lookup"><span data-stu-id="aa6bb-120">The <strong>Last Refresh</strong> displays the current version of the virtualized package.</span></span></p></li>
<li><p><span data-ttu-id="aa6bb-121">下載所有虛擬應用程式–使用 [ <strong> 下載] </strong> 磚下載所有已預配至目前使用者的套件。</span><span class="sxs-lookup"><span data-stu-id="aa6bb-121">Download all virtual applications – Use the <strong>Download</strong> tile to download all of the packages provisioned to the current user.</span></span></p>
<p><span data-ttu-id="aa6bb-122">（相關聯的 PowerShell Cmdlet： <strong>Mount-AppvClientPackage </strong> ）</span><span class="sxs-lookup"><span data-stu-id="aa6bb-122">(Associated PowerShell cmdlet: <strong>Mount-AppvClientPackage</strong>)</span></span></p>
<p></p></li>
<li><p><span data-ttu-id="aa6bb-123">離線工作–使用此磚可禁止所有自動和手動虛擬應用程式更新。</span><span class="sxs-lookup"><span data-stu-id="aa6bb-123">Work Offline – Use this tile to disallow all automatic and manual virtual application updates.</span></span></p>
<p><span data-ttu-id="aa6bb-124">（相關聯的 PowerShell Cmdlet： <strong>Set-AppvPublishServer – UserRefreshEnabled – GlobalRefreshEnabled </strong> ）</span><span class="sxs-lookup"><span data-stu-id="aa6bb-124">(Associated PowerShell cmdlet: <strong>Set-AppvPublishServer –UserRefreshEnabled –GlobalRefreshEnabled</strong>)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="aa6bb-125">虛擬應用程式</span><span class="sxs-lookup"><span data-stu-id="aa6bb-125">Virtual Apps</span></span></p></td>
<td align="left"><p><span data-ttu-id="aa6bb-126">[ <strong> 虛擬 app] 索引標籤 </strong> 會顯示已發佈給使用者的所有套件。</span><span class="sxs-lookup"><span data-stu-id="aa6bb-126">The <strong>VIRTUAL APPS</strong> tab displays all of the packages that have been published to the user.</span></span> <span data-ttu-id="aa6bb-127">您也可以按一下特定套件，並查看屬於該套件的所有應用程式。</span><span class="sxs-lookup"><span data-stu-id="aa6bb-127">You can also click a specific package and see all of the applications that are part of that package.</span></span> <span data-ttu-id="aa6bb-128">這會顯示目前使用中之套件的相關資訊，以及每個套件已下載到電腦的數量。</span><span class="sxs-lookup"><span data-stu-id="aa6bb-128">This displays information about packages that are currently in use and how much of each package has been downloaded to the computer.</span></span> <span data-ttu-id="aa6bb-129">您也可以啟動和停止套件下載。</span><span class="sxs-lookup"><span data-stu-id="aa6bb-129">You can also start and stop package downloads.</span></span> <span data-ttu-id="aa6bb-130">此外，您也可以修復使用者狀態。</span><span class="sxs-lookup"><span data-stu-id="aa6bb-130">Additionally, you can repair the user state.</span></span> <span data-ttu-id="aa6bb-131">修復會刪除與套件相關的所有使用者資料。</span><span class="sxs-lookup"><span data-stu-id="aa6bb-131">A repair will delete all user data that is associated with a package.</span></span></p>
<p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="aa6bb-132">App 連線群組</span><span class="sxs-lookup"><span data-stu-id="aa6bb-132">App Connection Groups</span></span></p></td>
<td align="left"><p><span data-ttu-id="aa6bb-133">[ <strong> 應用程式連線群組] 索引標籤 </strong> 會顯示目前使用者可以使用的所有連線群組。</span><span class="sxs-lookup"><span data-stu-id="aa6bb-133">The <strong>APP CONNECTION GROUPS</strong> tab displays all of the connection groups that are available to the current user.</span></span> <span data-ttu-id="aa6bb-134">按一下特定的連線群組，以查看屬於所選群組的所有套件。</span><span class="sxs-lookup"><span data-stu-id="aa6bb-134">Click a specific connection group to see all of the packages that are part of the selected group.</span></span> <span data-ttu-id="aa6bb-135">這會顯示已在使用中的連線群組資訊，以及將多少連線群組內容下載到電腦。</span><span class="sxs-lookup"><span data-stu-id="aa6bb-135">This displays information about connection groups that are already in use and how much of the connection group contents have been downloaded to the computer.</span></span> <span data-ttu-id="aa6bb-136">此外，您還可以啟動和停止連線群組下載。</span><span class="sxs-lookup"><span data-stu-id="aa6bb-136">Additionally, you can start and stop connection group downloads.</span></span> <span data-ttu-id="aa6bb-137">您可以使用這個區段來啟動修復。</span><span class="sxs-lookup"><span data-stu-id="aa6bb-137">You can use this section to initiate a repair.</span></span> <span data-ttu-id="aa6bb-138">修復會移除所有與連接群組相關聯的使用者狀態。</span><span class="sxs-lookup"><span data-stu-id="aa6bb-138">A repair will remove all of the user state that is associated a connection group.</span></span></p>
<p><span data-ttu-id="aa6bb-139">（關聯的 PowerShell Cmdlet：下載- <strong>Mount-AppvClientConnectionGroup </strong> 。</span><span class="sxs-lookup"><span data-stu-id="aa6bb-139">(Associated PowerShell cmdlets: Download - <strong>Mount-AppvClientConnectionGroup</strong>.</span></span> <span data-ttu-id="aa6bb-140">修復- <strong> AppvClientConnectionGroup </strong> 。）</span><span class="sxs-lookup"><span data-stu-id="aa6bb-140">Repair -<strong>AppvClientConnectionGroup</strong>.)</span></span></p>
<p></p></td>
</tr>
</tbody>
</table>

 

[<span data-ttu-id="aa6bb-141">如何存取 Client Management Console</span><span class="sxs-lookup"><span data-stu-id="aa6bb-141">How to Access the Client Management Console</span></span>](how-to-access-the-client-management-console51.md)

[<span data-ttu-id="aa6bb-142">如何設定用戶端以從發佈伺服器接收套件與連線群組更新</span><span class="sxs-lookup"><span data-stu-id="aa6bb-142">How to Configure the Client to Receive Package and Connection Groups Updates From the Publishing Server</span></span>](how-to-configure-the-client-to-receive-package-and-connection-groups-updates-from-the-publishing-server-51.md)






## <span data-ttu-id="aa6bb-143">相關主題</span><span class="sxs-lookup"><span data-stu-id="aa6bb-143">Related topics</span></span>


[<span data-ttu-id="aa6bb-144">App-V 5.1 作業</span><span class="sxs-lookup"><span data-stu-id="aa6bb-144">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)

 

 





