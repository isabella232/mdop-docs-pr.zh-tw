---
title: App-V 5.0 伺服器部署規劃
description: App-V 5.0 伺服器部署規劃
author: dansimp
ms.assetid: fd89b324-3961-471a-ad90-c8f9ae7a8155
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 06c7c17fd081b89337bbecd31f20f6796338f697
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800348"
---
# <span data-ttu-id="a67a8-103">App-V 5.0 伺服器部署規劃</span><span class="sxs-lookup"><span data-stu-id="a67a8-103">Planning for the App-V 5.0 Server Deployment</span></span>


<span data-ttu-id="a67a8-104">Microsoft Application Virtualization （App-v） 5.0 server 基礎結構包含一組專用功能，可根據企業的需求，在一或多台伺服器電腦上安裝。</span><span class="sxs-lookup"><span data-stu-id="a67a8-104">The Microsoft Application Virtualization (App-V) 5.0 server infrastructure consists of a set of specialized features that can be installed on one or more server computers, based on the requirements of the enterprise.</span></span>

## <span data-ttu-id="a67a8-105">規劃 app-v 5.0 Server 部署</span><span class="sxs-lookup"><span data-stu-id="a67a8-105">Planning for App-V 5.0 Server Deployment</span></span>


<span data-ttu-id="a67a8-106">App-V 5.0 伺服器包含下列功能：</span><span class="sxs-lookup"><span data-stu-id="a67a8-106">The App-V 5.0 server consists of the following features:</span></span>

-   <span data-ttu-id="a67a8-107">管理伺服器-提供 App-V 5.0 基礎結構的整體管理功能。</span><span class="sxs-lookup"><span data-stu-id="a67a8-107">Management Server – provides overall management functionality for the App-V 5.0 infrastructure.</span></span>

-   <span data-ttu-id="a67a8-108">管理資料庫–可協助 App-v 5.0 管理的資料庫 predeployments。</span><span class="sxs-lookup"><span data-stu-id="a67a8-108">Management Database – facilitates database predeployments for App-V 5.0 management.</span></span>

-   <span data-ttu-id="a67a8-109">發佈伺服器-提供虛擬應用程式的託管與流式處理功能。</span><span class="sxs-lookup"><span data-stu-id="a67a8-109">Publishing Server – provides hosting and streaming functionality for virtual applications.</span></span>

-   <span data-ttu-id="a67a8-110">報表伺服器–提供 App-v 5.0 reporting services。</span><span class="sxs-lookup"><span data-stu-id="a67a8-110">Reporting Server – provides App-V 5.0 reporting services.</span></span>

-   <span data-ttu-id="a67a8-111">報告資料庫–協助 App-v 5.0 報告的資料庫 predeployments。</span><span class="sxs-lookup"><span data-stu-id="a67a8-111">Reporting Database – facilitates database predeployments for App-V 5.0 reporting.</span></span>

<span data-ttu-id="a67a8-112">下列清單顯示安裝 App-V 5.0 伺服器基礎結構的建議方法：</span><span class="sxs-lookup"><span data-stu-id="a67a8-112">The following list displays the recommended methods for installing the App-V 5.0 server infrastructure:</span></span>

-   <span data-ttu-id="a67a8-113">安裝 App-V 5.0 伺服器。</span><span class="sxs-lookup"><span data-stu-id="a67a8-113">Install the App-V 5.0 server.</span></span> <span data-ttu-id="a67a8-114">如需詳細資訊，請參閱[如何部署 app-v 5.0 伺服器](how-to-deploy-the-app-v-50-server-50sp3.md)。</span><span class="sxs-lookup"><span data-stu-id="a67a8-114">For more information, see [How to Deploy the App-V 5.0 Server](how-to-deploy-the-app-v-50-server-50sp3.md).</span></span>

-   <span data-ttu-id="a67a8-115">在不同的電腦上安裝資料庫、報告和管理功能。</span><span class="sxs-lookup"><span data-stu-id="a67a8-115">Install the database, reporting, and management features on separate computers.</span></span> <span data-ttu-id="a67a8-116">如需詳細資訊，請參閱[如何從管理和報表服務在不同的電腦上安裝管理和報告資料庫](how-to-install-the-management-and-reporting-databases-on-separate-computers-from-the-management-and-reporting-services.md)。</span><span class="sxs-lookup"><span data-stu-id="a67a8-116">For more information, see [How to Install the Management and Reporting Databases on Separate Computers from the Management and Reporting Services](how-to-install-the-management-and-reporting-databases-on-separate-computers-from-the-management-and-reporting-services.md).</span></span>

-   <span data-ttu-id="a67a8-117">使用電子軟體發佈（ESD）。</span><span class="sxs-lookup"><span data-stu-id="a67a8-117">Use Electronic Software Distribution (ESD).</span></span> <span data-ttu-id="a67a8-118">如需詳細資訊，請參閱[如何使用電子軟體發佈部署 app-v 5.0 套件](how-to-deploy-app-v-50-packages-using-electronic-software-distribution.md)。</span><span class="sxs-lookup"><span data-stu-id="a67a8-118">For more information, see [How to deploy App-V 5.0 Packages Using Electronic Software Distribution](how-to-deploy-app-v-50-packages-using-electronic-software-distribution.md).</span></span>

-   <span data-ttu-id="a67a8-119">在一部電腦上安裝所有伺服器功能。</span><span class="sxs-lookup"><span data-stu-id="a67a8-119">Install all server features on a single computer.</span></span>

## <a href="" id="---------app-v-5-0-server-interaction"></a> <span data-ttu-id="a67a8-120">App-v 5.0 Server 互動</span><span class="sxs-lookup"><span data-stu-id="a67a8-120">App-V 5.0 Server Interaction</span></span>


<span data-ttu-id="a67a8-121">本節包含各個 App-v 5.0 伺服器角色彼此互動的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="a67a8-121">This section contains information about how the various App-V 5.0 server roles interact with each other.</span></span>

<span data-ttu-id="a67a8-122">App-v 5.0 管理伺服器包含套件的儲存庫及其指派的設定。</span><span class="sxs-lookup"><span data-stu-id="a67a8-122">The App-V 5.0 Management Server contains the repository of packages and their assigned configurations.</span></span> <span data-ttu-id="a67a8-123">針對已在管理伺服器註冊的發佈伺服器，在執行 App-v 5.0 用戶端的電腦收到發佈重新整理要求時，就會提供與發佈伺服器搭配使用的相關中繼資料。</span><span class="sxs-lookup"><span data-stu-id="a67a8-123">For Publishing Servers that are registered with the Management Server, the associated metadata is provided to the Publishing servers for use when publishing refresh requests are received from computers running the App-V 5.0 Client.</span></span> <span data-ttu-id="a67a8-124">由單一管理伺服器所管理的 app-v 5.0 發佈伺服器可提供不同的用戶端，而且可以有不同的網站名稱和埠系結。</span><span class="sxs-lookup"><span data-stu-id="a67a8-124">App-V 5.0 publishing servers managed by a single management server can be serving different clients and can have different website names and port bindings.</span></span> <span data-ttu-id="a67a8-125">此外，同一個管理伺服器所管理的所有發佈伺服器都是彼此的複本。</span><span class="sxs-lookup"><span data-stu-id="a67a8-125">Additionally, all Publishing Servers managed by the same Management Server are replicas of each other.</span></span>

<span data-ttu-id="a67a8-126">**記事** 管理伺服器不會執行任何負載平衡。</span><span class="sxs-lookup"><span data-stu-id="a67a8-126">**Note** The Management Server does not perform any load balancing.</span></span> <span data-ttu-id="a67a8-127">關聯的中繼資料只會傳遞到發佈伺服器，以供處理用戶端要求時使用。</span><span class="sxs-lookup"><span data-stu-id="a67a8-127">The associated metadata is simply passed to the publishing server for use when processing client requests.</span></span>

 

## <span data-ttu-id="a67a8-128">伺服器相關通訊協定與外部功能</span><span class="sxs-lookup"><span data-stu-id="a67a8-128">Server-Related Protocols and External Features</span></span>


<span data-ttu-id="a67a8-129">下列顯示 App-v 5.0 伺服器所使用的伺服器相關通訊協定的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="a67a8-129">The following displays information about server-related protocols used by the App-V 5.0 servers.</span></span> <span data-ttu-id="a67a8-130">此表格也包含每個伺服器類型的報告機制。</span><span class="sxs-lookup"><span data-stu-id="a67a8-130">The table also includes the reporting mechanism for each server type.</span></span>

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
<th align="left"><span data-ttu-id="a67a8-131">伺服器類型</span><span class="sxs-lookup"><span data-stu-id="a67a8-131">Server Type</span></span></th>
<th align="left"><span data-ttu-id="a67a8-132">通訊協定</span><span class="sxs-lookup"><span data-stu-id="a67a8-132">Protocols</span></span></th>
<th align="left"><span data-ttu-id="a67a8-133">需要外部功能</span><span class="sxs-lookup"><span data-stu-id="a67a8-133">External Features Needed</span></span></th>
<th align="left"><span data-ttu-id="a67a8-134">報告</span><span class="sxs-lookup"><span data-stu-id="a67a8-134">Reporting</span></span></th>
<th align="left"></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a67a8-135">IIS 伺服器</span><span class="sxs-lookup"><span data-stu-id="a67a8-135">IIS server</span></span></p></td>
<td align="left"><p><span data-ttu-id="a67a8-136">HTTP</span><span class="sxs-lookup"><span data-stu-id="a67a8-136">HTTP</span></span></p>
<p><span data-ttu-id="a67a8-137">HTTPS</span><span class="sxs-lookup"><span data-stu-id="a67a8-137">HTTPS</span></span></p></td>
<td align="left"><p><span data-ttu-id="a67a8-138">這個伺服器通訊協定組合需要一種機制來同步處理管理伺服器與流式處理伺服器之間的內容。</span><span class="sxs-lookup"><span data-stu-id="a67a8-138">This server-protocol combination requires a mechanism to synchronize the content between the Management Server and the Streaming Server.</span></span> <span data-ttu-id="a67a8-139">使用 HTTP 或 HTTPS 時，請使用 IIS 伺服器和防火牆來保護伺服器，避免暴露在網際網路上。</span><span class="sxs-lookup"><span data-stu-id="a67a8-139">When using HTTP or HTTPS, use an IIS server and a firewall to protect the server from exposure to the Internet.</span></span></p></td>
<td align="left"><p><span data-ttu-id="a67a8-140">內部</span><span class="sxs-lookup"><span data-stu-id="a67a8-140">Internal</span></span></p></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a67a8-141">檔案</span><span class="sxs-lookup"><span data-stu-id="a67a8-141">File</span></span></p></td>
<td align="left"><p><span data-ttu-id="a67a8-142">SMB</span><span class="sxs-lookup"><span data-stu-id="a67a8-142">SMB</span></span></p></td>
<td align="left"><p><span data-ttu-id="a67a8-143">此伺服器通訊協定組合需要支援，才能同步處理管理伺服器與流式處理伺服器之間的內容。</span><span class="sxs-lookup"><span data-stu-id="a67a8-143">This server-protocol combination requires support to synchronize the content between the Management Server and the Streaming Server.</span></span> <span data-ttu-id="a67a8-144">使用用戶端電腦進行檔案共用或流式處理功能。</span><span class="sxs-lookup"><span data-stu-id="a67a8-144">Use a client computer with file sharing or streaming capability.</span></span></p></td>
<td align="left"><p><span data-ttu-id="a67a8-145">內部</span><span class="sxs-lookup"><span data-stu-id="a67a8-145">Internal</span></span></p></td>
<td align="left"></td>
</tr>
</tbody>
</table>

 






## <span data-ttu-id="a67a8-146">相關主題</span><span class="sxs-lookup"><span data-stu-id="a67a8-146">Related topics</span></span>


[<span data-ttu-id="a67a8-147">規劃部署 App-V</span><span class="sxs-lookup"><span data-stu-id="a67a8-147">Planning to Deploy App-V</span></span>](planning-to-deploy-app-v.md)

[<span data-ttu-id="a67a8-148">部署 App-V 5.0 伺服器</span><span class="sxs-lookup"><span data-stu-id="a67a8-148">Deploying the App-V 5.0 Server</span></span>](deploying-the-app-v-50-server.md)

 

 





