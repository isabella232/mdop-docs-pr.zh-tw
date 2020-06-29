---
title: App-V 5.1 容量規劃
description: App-V 5.1 容量規劃
author: dansimp
ms.assetid: 7a98062f-5a60-49d6-ab40-dc6057e1dd5a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b152536b3c61e47f3fda84489b1e102c285e01c6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800680"
---
# <span data-ttu-id="bfa65-103">App-V 5.1 容量規劃</span><span class="sxs-lookup"><span data-stu-id="bfa65-103">App-V 5.1 Capacity Planning</span></span>


<span data-ttu-id="bfa65-104">下列建議可以用來做為比較基準，以協助判斷適合您組織的 app-v 5.1 基礎結構的容量規劃資訊。</span><span class="sxs-lookup"><span data-stu-id="bfa65-104">The following recommendations can be used as a baseline to help determine capacity planning information that is appropriate to your organization’s App-V 5.1 infrastructure.</span></span>

<span data-ttu-id="bfa65-105">**重要** 此區段中的資訊只能做為規劃 App-v 5.1 部署的一般指南。</span><span class="sxs-lookup"><span data-stu-id="bfa65-105">**Important** Use the information in this section only as a general guide for planning your App-V 5.1 deployment.</span></span> <span data-ttu-id="bfa65-106">您的系統容量需求將取決於您的硬體和應用程式環境的特定詳細資料。</span><span class="sxs-lookup"><span data-stu-id="bfa65-106">Your system capacity requirements will depend on the specific details of your hardware and application environment.</span></span> <span data-ttu-id="bfa65-107">此外，此檔中顯示的績效數位是範例，而您的結果可能會有所不同。</span><span class="sxs-lookup"><span data-stu-id="bfa65-107">Additionally, the performance numbers displayed in this document are examples and your results may vary.</span></span>

 

## <span data-ttu-id="bfa65-108">判斷專案範圍</span><span class="sxs-lookup"><span data-stu-id="bfa65-108">Determine the Project Scope</span></span>


<span data-ttu-id="bfa65-109">設計 App-v 5.1 基礎結構之前，您必須判斷專案的範圍。</span><span class="sxs-lookup"><span data-stu-id="bfa65-109">Before you design the App-V 5.1 infrastructure, you must determine the project’s scope.</span></span> <span data-ttu-id="bfa65-110">範圍包括判斷哪些應用程式將會真正可用，以及識別目標使用者及其位置。</span><span class="sxs-lookup"><span data-stu-id="bfa65-110">The scope consists of determining which applications will be available virtually and to also identify the target users, and their locations.</span></span> <span data-ttu-id="bfa65-111">這項資訊將協助您判斷應該要實施哪種類型的 App-v 5.1 基礎結構。</span><span class="sxs-lookup"><span data-stu-id="bfa65-111">This information will help determine what type of App-V 5.1 infrastructure should be implemented.</span></span> <span data-ttu-id="bfa65-112">專案範圍的相關決策必須以貴組織的特定需求為基礎。</span><span class="sxs-lookup"><span data-stu-id="bfa65-112">Decisions about the scope of the project must be based on the specific needs of your organization.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bfa65-113">工作</span><span class="sxs-lookup"><span data-stu-id="bfa65-113">Task</span></span></th>
<th align="left"><span data-ttu-id="bfa65-114">其他資訊</span><span class="sxs-lookup"><span data-stu-id="bfa65-114">More Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bfa65-115">決定應用程式範圍</span><span class="sxs-lookup"><span data-stu-id="bfa65-115">Determine Application Scope</span></span></p></td>
<td align="left"><p><span data-ttu-id="bfa65-116">根據要虛擬化的應用程式而定，App-v 5.1 基礎結構可以以不同的方式加以設定。</span><span class="sxs-lookup"><span data-stu-id="bfa65-116">Depending on the applications to be virtualized, the App-V 5.1 infrastructure can be set up in different ways.</span></span> <span data-ttu-id="bfa65-117">第一個工作是定義您想要虛擬化的應用程式。</span><span class="sxs-lookup"><span data-stu-id="bfa65-117">The first task is to define what applications you want to virtualize.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bfa65-118">判斷位置範圍</span><span class="sxs-lookup"><span data-stu-id="bfa65-118">Determine Location Scope</span></span></p></td>
<td align="left"><p><span data-ttu-id="bfa65-119">[位置範圍] 是指您計畫執行虛擬化應用程式的物理位置（例如，企業範圍或特定地理位置）。</span><span class="sxs-lookup"><span data-stu-id="bfa65-119">Location scope refers to the physical locations (for example, enterprise-wide or a specific geographic location) where you plan to run the virtualized applications.</span></span> <span data-ttu-id="bfa65-120">它也可以參照使用者群體（例如，單一部門），他們將會執行虛擬應用程式。</span><span class="sxs-lookup"><span data-stu-id="bfa65-120">It can also refer to the user population (for example, a single department) who will run the virtual applications.</span></span> <span data-ttu-id="bfa65-121">您應該會取得包含連接路徑以及使用虛擬化應用程式及 WAN 連結速度的使用者數目的網狀圖。</span><span class="sxs-lookup"><span data-stu-id="bfa65-121">You should obtain a network map that includes the connection paths as well as available bandwidth to each location and the number of users using virtualized applications and the WAN link speed.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="bfa65-122">判斷需要 App-v 5.1 基礎結構</span><span class="sxs-lookup"><span data-stu-id="bfa65-122">Determine Which App-V 5.1 Infrastructure is Required</span></span>


<span data-ttu-id="bfa65-123">**重要** 下列兩種模型都需要在您計畫執行虛擬應用程式的電腦上安裝 App-v 5.1 用戶端。</span><span class="sxs-lookup"><span data-stu-id="bfa65-123">**Important** Both of the following models require the App-V 5.1 client to be installed on the computer where you plan to run virtual applications.</span></span>

<span data-ttu-id="bfa65-124">您也可以使用電子軟體發佈（ESD）方案（例如 Microsoft 系統中心設定管理員），管理您的 App-v 5.1 環境。</span><span class="sxs-lookup"><span data-stu-id="bfa65-124">You can also manage your App-V 5.1 environment using an Electronic Software Distribution (ESD) solution such as Microsoft Systems Center Configuration Manager.</span></span> <span data-ttu-id="bfa65-125">如需詳細資訊，請參閱[如何使用電子軟體發佈部署 app-v 5.1 套件](how-to-deploy-app-v-51-packages-using-electronic-software-distribution.md)。</span><span class="sxs-lookup"><span data-stu-id="bfa65-125">For more information see [How to deploy App-V 5.1 Packages Using Electronic Software Distribution](how-to-deploy-app-v-51-packages-using-electronic-software-distribution.md).</span></span>

 

-   <span data-ttu-id="bfa65-126">**獨立模型**-獨立模型可讓虛擬應用程式在 Windows 安裝程式啟用，以便在沒有資料流程的情況下發布。</span><span class="sxs-lookup"><span data-stu-id="bfa65-126">**Standalone Model** - The standalone model allows virtual applications to be Windows Installer-enabled for distribution without streaming.</span></span> <span data-ttu-id="bfa65-127">在獨立模式中，app-v 5.1 是由排序器和用戶端所組成;不需要額外的元件。</span><span class="sxs-lookup"><span data-stu-id="bfa65-127">App-V 5.1 in Standalone Mode consists of the sequencer and the client; no additional components are required.</span></span> <span data-ttu-id="bfa65-128">應用程式準備好使用稱為 [排序] 的程式來進行虛擬化。</span><span class="sxs-lookup"><span data-stu-id="bfa65-128">Applications are prepared for virtualization using a process called sequencing.</span></span> <span data-ttu-id="bfa65-129">如需詳細資訊，請參閱[應用程式-V 5.1 排序器與用戶端部署的規劃](planning-for-the-app-v-51-sequencer-and-client-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="bfa65-129">For more information see, [Planning for the App-V 5.1 Sequencer and Client Deployment](planning-for-the-app-v-51-sequencer-and-client-deployment.md).</span></span> <span data-ttu-id="bfa65-130">針對下列案例，建議使用獨立模型：</span><span class="sxs-lookup"><span data-stu-id="bfa65-130">The stand-alone model is recommended for the following scenarios:</span></span>

    -   <span data-ttu-id="bfa65-131">無法連線到 app-v 5.1 基礎結構的中斷遠端使用者使用。</span><span class="sxs-lookup"><span data-stu-id="bfa65-131">With disconnected remote users who cannot connect to the App-V 5.1 infrastructure.</span></span>

    -   <span data-ttu-id="bfa65-132">當您執行的是軟體管理系統（例如 Configuration Manager 2012）時。</span><span class="sxs-lookup"><span data-stu-id="bfa65-132">When you are running a software management system, such as Configuration Manager 2012.</span></span>

    -   <span data-ttu-id="bfa65-133">當網路頻寬限制抑制電子軟體發佈時。</span><span class="sxs-lookup"><span data-stu-id="bfa65-133">When network bandwidth limitations inhibit electronic software distribution.</span></span>

-   <span data-ttu-id="bfa65-134">**完整的基礎結構模型**-完整的基礎結構模型可提供軟體發佈、管理和報告功能;它也包含跨網路的應用程式資料流程。</span><span class="sxs-lookup"><span data-stu-id="bfa65-134">**Full Infrastructure Model** - The full infrastructure model provides for software distribution, management, and reporting capabilities; it also includes the streaming of applications across the network.</span></span> <span data-ttu-id="bfa65-135">App-v 5.1 完整基礎結構模型是由一或多個 App-v 5.1 管理伺服器所組成。</span><span class="sxs-lookup"><span data-stu-id="bfa65-135">The App-V 5.1 Full Infrastructure Model consists of one or more App-V 5.1 management servers.</span></span> <span data-ttu-id="bfa65-136">管理伺服器可以用來將應用程式發佈到所有用戶端。</span><span class="sxs-lookup"><span data-stu-id="bfa65-136">The Management Server can be used to publish applications to all clients.</span></span> <span data-ttu-id="bfa65-137">發佈程式會將虛擬應用程式圖示和快速鍵放在目的電腦上。</span><span class="sxs-lookup"><span data-stu-id="bfa65-137">The publishing process places the virtual application icons and shortcuts on the target computer.</span></span> <span data-ttu-id="bfa65-138">它也可以將應用程式流式資料流程給本機使用者。</span><span class="sxs-lookup"><span data-stu-id="bfa65-138">It can also stream applications to local users.</span></span> <span data-ttu-id="bfa65-139">如需安裝管理伺服器的詳細資訊，請參閱[規劃 app-v 5.1 Server 部署](planning-for-the-app-v-51-server-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="bfa65-139">For more information about installing the management server see, [Planning for the App-V 5.1 Server Deployment](planning-for-the-app-v-51-server-deployment.md).</span></span> <span data-ttu-id="bfa65-140">針對下列案例，建議使用完整的基礎結構模型：</span><span class="sxs-lookup"><span data-stu-id="bfa65-140">The full infrastructure model is recommended for the following scenarios:</span></span>

    <span data-ttu-id="bfa65-141">**重要** App-v 5.1 完整基礎結構模型需要 Microsoft SQL Server 來儲存配置資料。</span><span class="sxs-lookup"><span data-stu-id="bfa65-141">**Important** The App-V 5.1 full infrastructure model requires Microsoft SQL Server to store configuration data.</span></span> <span data-ttu-id="bfa65-142">如需詳細資訊，請參閱[app-v 5.1 支援的](app-v-51-supported-configurations.md)設定。</span><span class="sxs-lookup"><span data-stu-id="bfa65-142">For more information see [App-V 5.1 Supported Configurations](app-v-51-supported-configurations.md).</span></span>

     

    -   <span data-ttu-id="bfa65-143">當您想要使用管理伺服器將應用程式發佈至目的電腦時。</span><span class="sxs-lookup"><span data-stu-id="bfa65-143">When you want to use the Management Server to publish the application to target computers.</span></span>

    -   <span data-ttu-id="bfa65-144">可快速提供目的電腦的應用程式。</span><span class="sxs-lookup"><span data-stu-id="bfa65-144">For rapid provisioning of applications to target computers.</span></span>

    -   <span data-ttu-id="bfa65-145">當您想要使用 App-v 5.1 報表時。</span><span class="sxs-lookup"><span data-stu-id="bfa65-145">When you want to use App-V 5.1 reporting.</span></span>

## <span data-ttu-id="bfa65-146">端對端伺服器規模調整指南</span><span class="sxs-lookup"><span data-stu-id="bfa65-146">End-to-end Server Sizing Guidance</span></span>


<span data-ttu-id="bfa65-147">下列章節提供有關端對端 App-V 5.1 大小及規劃的資訊。</span><span class="sxs-lookup"><span data-stu-id="bfa65-147">The following section provides information about end-to-end App-V 5.1 sizing and planning.</span></span> <span data-ttu-id="bfa65-148">如需詳細資訊，請參閱後續章節。</span><span class="sxs-lookup"><span data-stu-id="bfa65-148">For more specific information, refer to the subsequent sections.</span></span>

<span data-ttu-id="bfa65-149">**記事** 用戶端上的往返行程回應時間是執行 App-V 5.1 用戶端以接收發布伺服器成功通知的時間。</span><span class="sxs-lookup"><span data-stu-id="bfa65-149">**Note** Round trip response time on the client is the time taken by the computer running the App-V 5.1 client to receive a successful notification from the publishing server.</span></span> <span data-ttu-id="bfa65-150">發佈伺服器上的往返行程回應時間是電腦執行發佈伺服器時所花費的時間，可從管理伺服器接收成功的套件中繼資料更新。</span><span class="sxs-lookup"><span data-stu-id="bfa65-150">Round trip response time on the publishing server is the time taken by the computer running the publishing server to receive a successful package metadata update from the management server.</span></span>

 

-   <span data-ttu-id="bfa65-151">20000用戶端可以以單一發布伺服器為目標，以在可接受的往返行程時間內取得套件更新。</span><span class="sxs-lookup"><span data-stu-id="bfa65-151">20,000 clients can target a single publishing server to obtain the package refreshes in an acceptable round trip time.</span></span> <span data-ttu-id="bfa65-152">（ &lt; 3 秒）</span><span class="sxs-lookup"><span data-stu-id="bfa65-152">(&lt;3 seconds)</span></span>

-   <span data-ttu-id="bfa65-153">單一管理伺服器最多可支援50發佈伺服器，以便在可接受的往返行程期間更新套件中繼資料。</span><span class="sxs-lookup"><span data-stu-id="bfa65-153">A single management server can support up to 50 publishing servers for package metadata refreshes in an acceptable round trip time.</span></span> <span data-ttu-id="bfa65-154">（ &lt; 5 秒）</span><span class="sxs-lookup"><span data-stu-id="bfa65-154">(&lt;5 seconds)</span></span>

## <a href="" id="---------app-v-5-1-management-server-capacity-planning-recommendations"></a> <span data-ttu-id="bfa65-155">App-V 5.1 管理伺服器容量規劃建議</span><span class="sxs-lookup"><span data-stu-id="bfa65-155">App-V 5.1 Management Server Capacity Planning Recommendations</span></span>


<span data-ttu-id="bfa65-156">App-v 5.1 發佈伺服器需要管理伺服器來更新套件重新整理要求和套件重新整理回應。</span><span class="sxs-lookup"><span data-stu-id="bfa65-156">The App-V 5.1 publishing servers require the management server for package refresh requests and package refresh responses.</span></span> <span data-ttu-id="bfa65-157">然後，管理伺服器會將資訊傳送給管理資料庫以取得資訊。</span><span class="sxs-lookup"><span data-stu-id="bfa65-157">The management server then sends the information to the management database to retrieve information.</span></span> <span data-ttu-id="bfa65-158">如需 App-V 5.1 管理伺服器支援的設定的詳細資訊，請參閱[app-v 5.1 支援](app-v-51-supported-configurations.md)的設定。</span><span class="sxs-lookup"><span data-stu-id="bfa65-158">For more information about App-V 5.1 management server supported configurations see [App-V 5.1 Supported Configurations](app-v-51-supported-configurations.md).</span></span>

<span data-ttu-id="bfa65-159">**記事** App-v 5.1 發佈伺服器上的預設重新整理時間為10分鐘。</span><span class="sxs-lookup"><span data-stu-id="bfa65-159">**Note** The default refresh time on the App-V 5.1 publishing server is ten minutes.</span></span>

 

<span data-ttu-id="bfa65-160">當多個同時發佈伺服器與單一管理伺服器連線以進行套件中繼資料更新時，下列三個因素會影響發佈伺服器上的往返行程回應時間：</span><span class="sxs-lookup"><span data-stu-id="bfa65-160">When multiple simultaneous publishing servers contact a single management server for package metadata refreshes, the following three factors influence the round trip response time on the publishing server:</span></span>

1.  <span data-ttu-id="bfa65-161">同時要求進行的發佈伺服器數量。</span><span class="sxs-lookup"><span data-stu-id="bfa65-161">Number of publishing servers making simultaneous requests.</span></span>

2.  <span data-ttu-id="bfa65-162">管理伺服器上設定的連線群組數目。</span><span class="sxs-lookup"><span data-stu-id="bfa65-162">Number of connection groups configured on the management server.</span></span>

3.  <span data-ttu-id="bfa65-163">管理伺服器上設定的存取組數目。</span><span class="sxs-lookup"><span data-stu-id="bfa65-163">Number of access groups configured on the management server.</span></span>

<span data-ttu-id="bfa65-164">下表顯示影響往返行程時間之每個因素的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="bfa65-164">The following table displays more information about each factor that impacts round trip time.</span></span>

<span data-ttu-id="bfa65-165">**記事** 往返行程回應時間是電腦執行 App-v 5.1 發佈伺服器以從管理伺服器接收成功的套件中繼資料更新所花費的時間。</span><span class="sxs-lookup"><span data-stu-id="bfa65-165">**Note** Round trip response time is the time taken by the computer running the App-V 5.1 publishing server to receive a successful package metadata update from the management server.</span></span>

 

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bfa65-166">影響往返行程回應時間的因素</span><span class="sxs-lookup"><span data-stu-id="bfa65-166">Factors impacting round trip response time</span></span></th>
<th align="left"><span data-ttu-id="bfa65-167">其他資訊</span><span class="sxs-lookup"><span data-stu-id="bfa65-167">More Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bfa65-168">同時要求封裝中繼資料重新整理的發佈伺服器數目。</span><span class="sxs-lookup"><span data-stu-id="bfa65-168">The number of publishing servers simultaneously requesting package metadata refreshes.</span></span></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-169">單一管理伺服器可以同時回應多達320發佈的發佈伺服器（要求同時發佈中繼資料）。</span><span class="sxs-lookup"><span data-stu-id="bfa65-169">A single management server can respond to up to 320 publishing servers requesting publishing metadata simultaneously.</span></span></p></li>
<li><p><span data-ttu-id="bfa65-170">320 pub 伺服器的往返行程回應時間是大約40秒。</span><span class="sxs-lookup"><span data-stu-id="bfa65-170">Round trip response time for 320 pub servers is ~40 seconds.</span></span></p></li>
<li><p><span data-ttu-id="bfa65-171">針對 &lt; 50 同時要求中繼資料的發佈伺服器，往返行程回應時間為 &lt; 5 秒。</span><span class="sxs-lookup"><span data-stu-id="bfa65-171">For &lt;50 publishing servers requesting metadata simultaneously, the round trip response time is &lt;5 seconds.</span></span></p></li>
<li><p><span data-ttu-id="bfa65-172">從50到320發佈伺服器，回應時間會線性增加（約2x）。</span><span class="sxs-lookup"><span data-stu-id="bfa65-172">From 50 to 320 publishing servers, the response time increases linearly (approximately 2x).</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bfa65-173">管理伺服器上設定的連線群組數目。</span><span class="sxs-lookup"><span data-stu-id="bfa65-173">The number of connection groups configured on the management server.</span></span></p>
<p></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-174">最多100個連線群組，發佈伺服器的往返行程回應時間不會有顯著的變更。</span><span class="sxs-lookup"><span data-stu-id="bfa65-174">For up to 100 connection groups, there is no significant change in the round trip response time on the publishing server.</span></span></p></li>
<li><p><span data-ttu-id="bfa65-175">針對 100-400 連線群組，往返行程回應時間有輕微的線性增加。</span><span class="sxs-lookup"><span data-stu-id="bfa65-175">For 100 - 400 connection groups, there is a minor linear increase in the round trip response time.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bfa65-176">管理伺服器上設定的存取組數目。</span><span class="sxs-lookup"><span data-stu-id="bfa65-176">The number of access groups configured on the management server.</span></span></p>
<p></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-177">在最多40存取群組中，發佈伺服器的往返行程回應時間有一個線性（大約3倍）的增加。</span><span class="sxs-lookup"><span data-stu-id="bfa65-177">For up to 40 access groups, there is a linear (approximately 3x) increase in the round trip response time on the publishing server.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="bfa65-178">下表顯示上述每個因素的範例值。</span><span class="sxs-lookup"><span data-stu-id="bfa65-178">The following table displays sample values for each of the previous factors.</span></span> <span data-ttu-id="bfa65-179">在每個變化中，120套件都會從 App-v 5.1 管理伺服器進行重新整理。</span><span class="sxs-lookup"><span data-stu-id="bfa65-179">In each variation, 120 packages are refreshed from the App-V 5.1management server.</span></span>

<table>
<colgroup>
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bfa65-180">案例</span><span class="sxs-lookup"><span data-stu-id="bfa65-180">Scenario</span></span></th>
<th align="left"><span data-ttu-id="bfa65-181">變化</span><span class="sxs-lookup"><span data-stu-id="bfa65-181">Variation</span></span></th>
<th align="left"><span data-ttu-id="bfa65-182">連線群組數目</span><span class="sxs-lookup"><span data-stu-id="bfa65-182">Number of connection groups</span></span></th>
<th align="left"><span data-ttu-id="bfa65-183">存取群組的數目</span><span class="sxs-lookup"><span data-stu-id="bfa65-183">Number of access groups</span></span></th>
<th align="left"><span data-ttu-id="bfa65-184">發佈伺服器數</span><span class="sxs-lookup"><span data-stu-id="bfa65-184">Number of publishing servers</span></span></th>
<th align="left"><span data-ttu-id="bfa65-185">網路連線類型發佈伺服器/管理伺服器</span><span class="sxs-lookup"><span data-stu-id="bfa65-185">Network connection type publishing server / management server</span></span></th>
<th align="left"><span data-ttu-id="bfa65-186">發佈伺服器上的往返行程回應時間（以秒為單位）</span><span class="sxs-lookup"><span data-stu-id="bfa65-186">Round trip response time on the publishing server (in seconds)</span></span></th>
<th align="left"><span data-ttu-id="bfa65-187">管理伺服器上的 CPU 利用率</span><span class="sxs-lookup"><span data-stu-id="bfa65-187">CPU utilization on management server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bfa65-188">同時發佈伺服器與管理伺服器一起發佈中繼資料。</span><span class="sxs-lookup"><span data-stu-id="bfa65-188">Publishing servers simultaneously contacting management server for publishing metadata.</span></span></p></td>
<td align="left"><p><span data-ttu-id="bfa65-189">發佈伺服器數</span><span class="sxs-lookup"><span data-stu-id="bfa65-189">Number of publishing servers</span></span></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-190">0</span><span class="sxs-lookup"><span data-stu-id="bfa65-190">0</span></span></p></li>
<li><p><span data-ttu-id="bfa65-191">0</span><span class="sxs-lookup"><span data-stu-id="bfa65-191">0</span></span></p></li>
<li><p><span data-ttu-id="bfa65-192">0</span><span class="sxs-lookup"><span data-stu-id="bfa65-192">0</span></span></p></li>
<li><p><span data-ttu-id="bfa65-193">0</span><span class="sxs-lookup"><span data-stu-id="bfa65-193">0</span></span></p></li>
<li><p><span data-ttu-id="bfa65-194">0</span><span class="sxs-lookup"><span data-stu-id="bfa65-194">0</span></span></p></li>
<li><p><span data-ttu-id="bfa65-195">0</span><span class="sxs-lookup"><span data-stu-id="bfa65-195">0</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-196">sr-1</span><span class="sxs-lookup"><span data-stu-id="bfa65-196">1</span></span></p></li>
<li><p><span data-ttu-id="bfa65-197">sr-1</span><span class="sxs-lookup"><span data-stu-id="bfa65-197">1</span></span></p></li>
<li><p><span data-ttu-id="bfa65-198">sr-1</span><span class="sxs-lookup"><span data-stu-id="bfa65-198">1</span></span></p></li>
<li><p><span data-ttu-id="bfa65-199">sr-1</span><span class="sxs-lookup"><span data-stu-id="bfa65-199">1</span></span></p></li>
<li><p><span data-ttu-id="bfa65-200">sr-1</span><span class="sxs-lookup"><span data-stu-id="bfa65-200">1</span></span></p></li>
<li><p><span data-ttu-id="bfa65-201">sr-1</span><span class="sxs-lookup"><span data-stu-id="bfa65-201">1</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-202">50</span><span class="sxs-lookup"><span data-stu-id="bfa65-202">50</span></span></p></li>
<li><p><span data-ttu-id="bfa65-203">100</span><span class="sxs-lookup"><span data-stu-id="bfa65-203">100</span></span></p></li>
<li><p><span data-ttu-id="bfa65-204">200</span><span class="sxs-lookup"><span data-stu-id="bfa65-204">200</span></span></p></li>
<li><p><span data-ttu-id="bfa65-205">300</span><span class="sxs-lookup"><span data-stu-id="bfa65-205">300</span></span></p></li>
<li><p><span data-ttu-id="bfa65-206">315</span><span class="sxs-lookup"><span data-stu-id="bfa65-206">315</span></span></p></li>
<li><p><span data-ttu-id="bfa65-207">320</span><span class="sxs-lookup"><span data-stu-id="bfa65-207">320</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-208">LAN</span><span class="sxs-lookup"><span data-stu-id="bfa65-208">LAN</span></span></p></li>
<li><p><span data-ttu-id="bfa65-209">LAN</span><span class="sxs-lookup"><span data-stu-id="bfa65-209">LAN</span></span></p></li>
<li><p><span data-ttu-id="bfa65-210">LAN</span><span class="sxs-lookup"><span data-stu-id="bfa65-210">LAN</span></span></p></li>
<li><p><span data-ttu-id="bfa65-211">LAN</span><span class="sxs-lookup"><span data-stu-id="bfa65-211">LAN</span></span></p></li>
<li><p><span data-ttu-id="bfa65-212">LAN</span><span class="sxs-lookup"><span data-stu-id="bfa65-212">LAN</span></span></p></li>
<li><p><span data-ttu-id="bfa65-213">LAN</span><span class="sxs-lookup"><span data-stu-id="bfa65-213">LAN</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-214">500</span><span class="sxs-lookup"><span data-stu-id="bfa65-214">5</span></span></p></li>
<li><p><span data-ttu-id="bfa65-215">第</span><span class="sxs-lookup"><span data-stu-id="bfa65-215">10</span></span></p></li>
<li><p><span data-ttu-id="bfa65-216">合</span><span class="sxs-lookup"><span data-stu-id="bfa65-216">19</span></span></p></li>
<li><p><span data-ttu-id="bfa65-217">32</span><span class="sxs-lookup"><span data-stu-id="bfa65-217">32</span></span></p></li>
<li><p><span data-ttu-id="bfa65-218">為期</span><span class="sxs-lookup"><span data-stu-id="bfa65-218">30</span></span></p></li>
<li><p><span data-ttu-id="bfa65-219">37</span><span class="sxs-lookup"><span data-stu-id="bfa65-219">37</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-220">11x17</span><span class="sxs-lookup"><span data-stu-id="bfa65-220">17</span></span></p></li>
<li><p><span data-ttu-id="bfa65-221">11x17</span><span class="sxs-lookup"><span data-stu-id="bfa65-221">17</span></span></p></li>
<li><p><span data-ttu-id="bfa65-222">11x17</span><span class="sxs-lookup"><span data-stu-id="bfa65-222">17</span></span></p></li>
<li><p><span data-ttu-id="bfa65-223">工資</span><span class="sxs-lookup"><span data-stu-id="bfa65-223">15</span></span></p></li>
<li><p><span data-ttu-id="bfa65-224">11x17</span><span class="sxs-lookup"><span data-stu-id="bfa65-224">17</span></span></p></li>
<li><p><span data-ttu-id="bfa65-225">工資</span><span class="sxs-lookup"><span data-stu-id="bfa65-225">15</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bfa65-226">發佈中繼資料包含連接群組</span><span class="sxs-lookup"><span data-stu-id="bfa65-226">Publishing metadata contains connection groups</span></span></p></td>
<td align="left"><p><span data-ttu-id="bfa65-227">連線群組數目</span><span class="sxs-lookup"><span data-stu-id="bfa65-227">Number of connection groups</span></span></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-228">第</span><span class="sxs-lookup"><span data-stu-id="bfa65-228">10</span></span></p></li>
<li><p><span data-ttu-id="bfa65-229">50</span><span class="sxs-lookup"><span data-stu-id="bfa65-229">50</span></span></p></li>
<li><p><span data-ttu-id="bfa65-230">100</span><span class="sxs-lookup"><span data-stu-id="bfa65-230">100</span></span></p></li>
<li><p><span data-ttu-id="bfa65-231">150</span><span class="sxs-lookup"><span data-stu-id="bfa65-231">150</span></span></p></li>
<li><p><span data-ttu-id="bfa65-232">300</span><span class="sxs-lookup"><span data-stu-id="bfa65-232">300</span></span></p></li>
<li><p><span data-ttu-id="bfa65-233">400</span><span class="sxs-lookup"><span data-stu-id="bfa65-233">400</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-234">sr-1</span><span class="sxs-lookup"><span data-stu-id="bfa65-234">1</span></span></p></li>
<li><p><span data-ttu-id="bfa65-235">sr-1</span><span class="sxs-lookup"><span data-stu-id="bfa65-235">1</span></span></p></li>
<li><p><span data-ttu-id="bfa65-236">sr-1</span><span class="sxs-lookup"><span data-stu-id="bfa65-236">1</span></span></p></li>
<li><p><span data-ttu-id="bfa65-237">sr-1</span><span class="sxs-lookup"><span data-stu-id="bfa65-237">1</span></span></p></li>
<li><p><span data-ttu-id="bfa65-238">sr-1</span><span class="sxs-lookup"><span data-stu-id="bfa65-238">1</span></span></p></li>
<li><p><span data-ttu-id="bfa65-239">sr-1</span><span class="sxs-lookup"><span data-stu-id="bfa65-239">1</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-240">100</span><span class="sxs-lookup"><span data-stu-id="bfa65-240">100</span></span></p></li>
<li><p><span data-ttu-id="bfa65-241">100</span><span class="sxs-lookup"><span data-stu-id="bfa65-241">100</span></span></p></li>
<li><p><span data-ttu-id="bfa65-242">100</span><span class="sxs-lookup"><span data-stu-id="bfa65-242">100</span></span></p></li>
<li><p><span data-ttu-id="bfa65-243">100</span><span class="sxs-lookup"><span data-stu-id="bfa65-243">100</span></span></p></li>
<li><p><span data-ttu-id="bfa65-244">100</span><span class="sxs-lookup"><span data-stu-id="bfa65-244">100</span></span></p></li>
<li><p><span data-ttu-id="bfa65-245">100</span><span class="sxs-lookup"><span data-stu-id="bfa65-245">100</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-246">LAN</span><span class="sxs-lookup"><span data-stu-id="bfa65-246">LAN</span></span></p></li>
<li><p><span data-ttu-id="bfa65-247">LAN</span><span class="sxs-lookup"><span data-stu-id="bfa65-247">LAN</span></span></p></li>
<li><p><span data-ttu-id="bfa65-248">LAN</span><span class="sxs-lookup"><span data-stu-id="bfa65-248">LAN</span></span></p></li>
<li><p><span data-ttu-id="bfa65-249">LAN</span><span class="sxs-lookup"><span data-stu-id="bfa65-249">LAN</span></span></p></li>
<li><p><span data-ttu-id="bfa65-250">LAN</span><span class="sxs-lookup"><span data-stu-id="bfa65-250">LAN</span></span></p></li>
<li><p><span data-ttu-id="bfa65-251">LAN</span><span class="sxs-lookup"><span data-stu-id="bfa65-251">LAN</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-252">第</span><span class="sxs-lookup"><span data-stu-id="bfa65-252">10</span></span></p></li>
<li><p><span data-ttu-id="bfa65-253">11</span><span class="sxs-lookup"><span data-stu-id="bfa65-253">11</span></span></p></li>
<li><p><span data-ttu-id="bfa65-254">11</span><span class="sxs-lookup"><span data-stu-id="bfa65-254">11</span></span></p></li>
<li><p><span data-ttu-id="bfa65-255">位</span><span class="sxs-lookup"><span data-stu-id="bfa65-255">16</span></span></p></li>
<li><p><span data-ttu-id="bfa65-256">22</span><span class="sxs-lookup"><span data-stu-id="bfa65-256">22</span></span></p></li>
<li><p><span data-ttu-id="bfa65-257">位</span><span class="sxs-lookup"><span data-stu-id="bfa65-257">25</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-258">11x17</span><span class="sxs-lookup"><span data-stu-id="bfa65-258">17</span></span></p></li>
<li><p><span data-ttu-id="bfa65-259">合</span><span class="sxs-lookup"><span data-stu-id="bfa65-259">19</span></span></p></li>
<li><p><span data-ttu-id="bfa65-260">22</span><span class="sxs-lookup"><span data-stu-id="bfa65-260">22</span></span></p></li>
<li><p><span data-ttu-id="bfa65-261">合</span><span class="sxs-lookup"><span data-stu-id="bfa65-261">19</span></span></p></li>
<li><p><span data-ttu-id="bfa65-262">20</span><span class="sxs-lookup"><span data-stu-id="bfa65-262">20</span></span></p></li>
<li><p><span data-ttu-id="bfa65-263">20</span><span class="sxs-lookup"><span data-stu-id="bfa65-263">20</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bfa65-264">發佈中繼資料包含存取群組</span><span class="sxs-lookup"><span data-stu-id="bfa65-264">Publishing metadata contains access groups</span></span></p></td>
<td align="left"><p><span data-ttu-id="bfa65-265">存取群組的數目</span><span class="sxs-lookup"><span data-stu-id="bfa65-265">Number of access groups</span></span></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-266">0</span><span class="sxs-lookup"><span data-stu-id="bfa65-266">0</span></span></p></li>
<li><p><span data-ttu-id="bfa65-267">0</span><span class="sxs-lookup"><span data-stu-id="bfa65-267">0</span></span></p></li>
<li><p><span data-ttu-id="bfa65-268">0</span><span class="sxs-lookup"><span data-stu-id="bfa65-268">0</span></span></p></li>
<li><p><span data-ttu-id="bfa65-269">0</span><span class="sxs-lookup"><span data-stu-id="bfa65-269">0</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-270">sr-1</span><span class="sxs-lookup"><span data-stu-id="bfa65-270">1</span></span></p></li>
<li><p><span data-ttu-id="bfa65-271">第</span><span class="sxs-lookup"><span data-stu-id="bfa65-271">10</span></span></p></li>
<li><p><span data-ttu-id="bfa65-272">20</span><span class="sxs-lookup"><span data-stu-id="bfa65-272">20</span></span></p></li>
<li><p><span data-ttu-id="bfa65-273">40</span><span class="sxs-lookup"><span data-stu-id="bfa65-273">40</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-274">100</span><span class="sxs-lookup"><span data-stu-id="bfa65-274">100</span></span></p></li>
<li><p><span data-ttu-id="bfa65-275">100</span><span class="sxs-lookup"><span data-stu-id="bfa65-275">100</span></span></p></li>
<li><p><span data-ttu-id="bfa65-276">100</span><span class="sxs-lookup"><span data-stu-id="bfa65-276">100</span></span></p></li>
<li><p><span data-ttu-id="bfa65-277">100</span><span class="sxs-lookup"><span data-stu-id="bfa65-277">100</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-278">LAN</span><span class="sxs-lookup"><span data-stu-id="bfa65-278">LAN</span></span></p></li>
<li><p><span data-ttu-id="bfa65-279">LAN</span><span class="sxs-lookup"><span data-stu-id="bfa65-279">LAN</span></span></p></li>
<li><p><span data-ttu-id="bfa65-280">LAN</span><span class="sxs-lookup"><span data-stu-id="bfa65-280">LAN</span></span></p></li>
<li><p><span data-ttu-id="bfa65-281">LAN</span><span class="sxs-lookup"><span data-stu-id="bfa65-281">LAN</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-282">第</span><span class="sxs-lookup"><span data-stu-id="bfa65-282">10</span></span></p></li>
<li><p><span data-ttu-id="bfa65-283">43</span><span class="sxs-lookup"><span data-stu-id="bfa65-283">43</span></span></p></li>
<li><p><span data-ttu-id="bfa65-284">153</span><span class="sxs-lookup"><span data-stu-id="bfa65-284">153</span></span></p></li>
<li><p><span data-ttu-id="bfa65-285">535</span><span class="sxs-lookup"><span data-stu-id="bfa65-285">535</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-286">11x17</span><span class="sxs-lookup"><span data-stu-id="bfa65-286">17</span></span></p></li>
<li><p><span data-ttu-id="bfa65-287">26</span><span class="sxs-lookup"><span data-stu-id="bfa65-287">26</span></span></p></li>
<li><p><span data-ttu-id="bfa65-288">24</span><span class="sxs-lookup"><span data-stu-id="bfa65-288">24</span></span></p></li>
<li><p><span data-ttu-id="bfa65-289">24</span><span class="sxs-lookup"><span data-stu-id="bfa65-289">24</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="bfa65-290">執行管理伺服器之電腦的 CPU 利用率會接近25%，而不考慮以目標為目標的發佈伺服器數量而定。</span><span class="sxs-lookup"><span data-stu-id="bfa65-290">The CPU utilization of the computer running the management server is around 25% irrespective of the number of publishing servers targeting it.</span></span> <span data-ttu-id="bfa65-291">Microsoft SQL Server 資料庫事務/秒、批次要求/秒和使用者連線，與發佈伺服器數量無關。</span><span class="sxs-lookup"><span data-stu-id="bfa65-291">The Microsoft SQL Server database transactions/sec, batch requests/sec and user connections are identical irrespective of the number of publishing servers.</span></span> <span data-ttu-id="bfa65-292">例如：交易/秒是 ~ 30，批次要求 ~ 200，而使用者則會連接 ~ 6。</span><span class="sxs-lookup"><span data-stu-id="bfa65-292">For example: Transactions/sec is ~30, batch requests ~200, and user connects ~6.</span></span>

<span data-ttu-id="bfa65-293">使用地理位置分散的部署（管理伺服器 & 發佈伺服器）使用低速連結網路時，發佈伺服器的往返行程回應時間是在可接受的時間限制內（ &lt; 5 秒），即使是在單一管理伺服器上同時進行100的要求也是如此。</span><span class="sxs-lookup"><span data-stu-id="bfa65-293">Using a geographically distributed deployment, where the management server & publishing servers utilize a slow link network between them, the round trip response time on the publishing servers is within acceptable time limits (&lt;5 seconds), even for 100 simultaneous requests on a single management server.</span></span>

<table>
<colgroup>
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bfa65-294">案例</span><span class="sxs-lookup"><span data-stu-id="bfa65-294">Scenario</span></span></th>
<th align="left"><span data-ttu-id="bfa65-295">變化</span><span class="sxs-lookup"><span data-stu-id="bfa65-295">Variation</span></span></th>
<th align="left"><span data-ttu-id="bfa65-296">連線群組數目</span><span class="sxs-lookup"><span data-stu-id="bfa65-296">Number of connection groups</span></span></th>
<th align="left"><span data-ttu-id="bfa65-297">存取群組的數目</span><span class="sxs-lookup"><span data-stu-id="bfa65-297">Number of access groups</span></span></th>
<th align="left"><span data-ttu-id="bfa65-298">發佈伺服器數</span><span class="sxs-lookup"><span data-stu-id="bfa65-298">Number of publishing servers</span></span></th>
<th align="left"><span data-ttu-id="bfa65-299">網路連線類型發佈伺服器/管理伺服器</span><span class="sxs-lookup"><span data-stu-id="bfa65-299">Network connection type publishing server / management server</span></span></th>
<th align="left"><span data-ttu-id="bfa65-300">發佈伺服器上的往返行程回應時間（以秒為單位）</span><span class="sxs-lookup"><span data-stu-id="bfa65-300">Round trip response time on the publishing server (in seconds)</span></span></th>
<th align="left"><span data-ttu-id="bfa65-301">管理伺服器上的 CPU 利用率</span><span class="sxs-lookup"><span data-stu-id="bfa65-301">CPU utilization on management server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bfa65-302">發佈伺服器與管理伺服器之間的網路連線</span><span class="sxs-lookup"><span data-stu-id="bfa65-302">Network connection between the publishing server and management server</span></span></p></td>
<td align="left"><p><span data-ttu-id="bfa65-303">1.5 Mbps 低速連結網路</span><span class="sxs-lookup"><span data-stu-id="bfa65-303">1.5 Mbps Slow link Network</span></span></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-304">0</span><span class="sxs-lookup"><span data-stu-id="bfa65-304">0</span></span></p></li>
<li><p><span data-ttu-id="bfa65-305">0</span><span class="sxs-lookup"><span data-stu-id="bfa65-305">0</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-306">sr-1</span><span class="sxs-lookup"><span data-stu-id="bfa65-306">1</span></span></p></li>
<li><p><span data-ttu-id="bfa65-307">sr-1</span><span class="sxs-lookup"><span data-stu-id="bfa65-307">1</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-308">50</span><span class="sxs-lookup"><span data-stu-id="bfa65-308">50</span></span></p></li>
<li><p><span data-ttu-id="bfa65-309">100</span><span class="sxs-lookup"><span data-stu-id="bfa65-309">100</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-310">1.5 mbps 纜線 DSL</span><span class="sxs-lookup"><span data-stu-id="bfa65-310">1.5Mbps Cable DSL</span></span></p></li>
<li><p><span data-ttu-id="bfa65-311">1.5 mbps 纜線 DSL</span><span class="sxs-lookup"><span data-stu-id="bfa65-311">1.5Mbps Cable DSL</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-312">4</span><span class="sxs-lookup"><span data-stu-id="bfa65-312">4</span></span></p></li>
<li><p><span data-ttu-id="bfa65-313">500</span><span class="sxs-lookup"><span data-stu-id="bfa65-313">5</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-314">sr-1</span><span class="sxs-lookup"><span data-stu-id="bfa65-314">1</span></span></p></li>
<li><p><span data-ttu-id="bfa65-315">pplx-2</span><span class="sxs-lookup"><span data-stu-id="bfa65-315">2</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bfa65-316">發佈伺服器與管理伺服器之間的網路連線</span><span class="sxs-lookup"><span data-stu-id="bfa65-316">Network connection between the publishing server and management server</span></span></p></td>
<td align="left"><p><span data-ttu-id="bfa65-317">局域網/WIFI 網路</span><span class="sxs-lookup"><span data-stu-id="bfa65-317">LAN / WIFI Network</span></span></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-318">0</span><span class="sxs-lookup"><span data-stu-id="bfa65-318">0</span></span></p></li>
<li><p><span data-ttu-id="bfa65-319">0</span><span class="sxs-lookup"><span data-stu-id="bfa65-319">0</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-320">sr-1</span><span class="sxs-lookup"><span data-stu-id="bfa65-320">1</span></span></p></li>
<li><p><span data-ttu-id="bfa65-321">sr-1</span><span class="sxs-lookup"><span data-stu-id="bfa65-321">1</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-322">100</span><span class="sxs-lookup"><span data-stu-id="bfa65-322">100</span></span></p></li>
<li><p><span data-ttu-id="bfa65-323">200</span><span class="sxs-lookup"><span data-stu-id="bfa65-323">200</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-324">Wifi</span><span class="sxs-lookup"><span data-stu-id="bfa65-324">Wifi</span></span></p></li>
<li><p><span data-ttu-id="bfa65-325">Wifi</span><span class="sxs-lookup"><span data-stu-id="bfa65-325">Wifi</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-326">11</span><span class="sxs-lookup"><span data-stu-id="bfa65-326">11</span></span></p></li>
<li><p><span data-ttu-id="bfa65-327">20</span><span class="sxs-lookup"><span data-stu-id="bfa65-327">20</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-328">工資</span><span class="sxs-lookup"><span data-stu-id="bfa65-328">15</span></span></p></li>
<li><p><span data-ttu-id="bfa65-329">11x17</span><span class="sxs-lookup"><span data-stu-id="bfa65-329">17</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="bfa65-330">無論管理伺服器和發佈伺服器是以低速連結網路或高速網路連線，管理伺服器都可以在30分鐘內處理大約15000套件重新整理要求。</span><span class="sxs-lookup"><span data-stu-id="bfa65-330">Whether the management server and publishing servers are connected over a slow link network, or a high speed network, the management server can handle approximately 15,000 package refresh requests in 30 minutes.</span></span>

## <a href="" id="---------app-v-5-1-reporting-server-capacity-planning-recommendations"></a> <span data-ttu-id="bfa65-331">App-V 5.1 報表伺服器容量規劃建議</span><span class="sxs-lookup"><span data-stu-id="bfa65-331">App-V 5.1 Reporting Server Capacity Planning Recommendations</span></span>


<span data-ttu-id="bfa65-332">App-v 5.1 用戶端會將報告資料傳送到報表伺服器。</span><span class="sxs-lookup"><span data-stu-id="bfa65-332">App-V 5.1 clients send reporting data to the reporting server.</span></span> <span data-ttu-id="bfa65-333">然後，報表伺服器會在 Microsoft SQL Server 資料庫中記錄資訊，並將成功的通知傳回執行 App-v 5.1 用戶端的電腦上。</span><span class="sxs-lookup"><span data-stu-id="bfa65-333">The reporting server then records the information in the Microsoft SQL Server database and returns a successful notification back to the computer running App-V 5.1 client.</span></span> <span data-ttu-id="bfa65-334">如需 App-V 5.1 報表服務器支援之設定的詳細資訊，請參閱[app-v 5.1 支援](app-v-51-supported-configurations.md)的設定。</span><span class="sxs-lookup"><span data-stu-id="bfa65-334">For more information about App-V 5.1 Reporting Server supported configurations see [App-V 5.1 Supported Configurations](app-v-51-supported-configurations.md).</span></span>

<span data-ttu-id="bfa65-335">**記事** 往返行程回應時間是執行 App-v 5.1 用戶端的電腦用來傳送報告資訊至報表伺服器並接收來自報表伺服器的成功通知的時間。</span><span class="sxs-lookup"><span data-stu-id="bfa65-335">**Note** Round trip response time is the time taken by the computer running the App-V 5.1 client to send the reporting information to the reporting server and receive a successful notification from the reporting server.</span></span>

 

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bfa65-336">案例</span><span class="sxs-lookup"><span data-stu-id="bfa65-336">Scenario</span></span></th>
<th align="left"><span data-ttu-id="bfa65-337">摘要</span><span class="sxs-lookup"><span data-stu-id="bfa65-337">Summary</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bfa65-338">多個 App-V 5.1 用戶端會同時將報告資訊傳送到報表伺服器。</span><span class="sxs-lookup"><span data-stu-id="bfa65-338">Multiple App-V 5.1 clients send reporting information to the reporting server simultaneously.</span></span></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-339">來自報表服務器的往返行程回應時間是500用戶端的2.6 秒。</span><span class="sxs-lookup"><span data-stu-id="bfa65-339">Round trip response time from the reporting server is 2.6 seconds for 500 clients.</span></span></p></li>
<li><p><span data-ttu-id="bfa65-340">來自報表服務器的往返行程回應時間是1000用戶端的5.65 秒。</span><span class="sxs-lookup"><span data-stu-id="bfa65-340">Round trip response time from the reporting server is 5.65 seconds for 1000 clients.</span></span></p></li>
<li><p><span data-ttu-id="bfa65-341">隨著用戶端數量而定，往返行程回應時間會線性增加。</span><span class="sxs-lookup"><span data-stu-id="bfa65-341">Round trip response time increases linearly depending on number of clients.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bfa65-342">報表服務器每秒處理的要求。</span><span class="sxs-lookup"><span data-stu-id="bfa65-342">Requests per second processed by the reporting server.</span></span></p>
<p></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-343">單一報表伺服器與單一資料庫，最多可處理每秒139個要求。</span><span class="sxs-lookup"><span data-stu-id="bfa65-343">A single reporting server and a single database, can process a maximum of 139 requests per second.</span></span> <span data-ttu-id="bfa65-344">平均值為121個要求/秒。</span><span class="sxs-lookup"><span data-stu-id="bfa65-344">The average is 121 requests/second.</span></span></p></li>
<li><p><span data-ttu-id="bfa65-345">使用兩個報表伺服器來報告相同的 Microsoft SQL Server 資料庫，平均要求/秒數與單一報表服務器 = ~ 127，最多可有278個要求/秒。</span><span class="sxs-lookup"><span data-stu-id="bfa65-345">Using two reporting servers reporting to the same Microsoft SQL Server database, the average requests/second is similar to a single reporting server = ~127, with a max of 278 requests/second.</span></span></p></li>
<li><p><span data-ttu-id="bfa65-346">單一報表服務器可以處理500併發/活動連線。</span><span class="sxs-lookup"><span data-stu-id="bfa65-346">A single reporting server can process 500 concurrent/active connections.</span></span></p></li>
<li><p><span data-ttu-id="bfa65-347">單一報表服務器可以處理最大1500併發連接。</span><span class="sxs-lookup"><span data-stu-id="bfa65-347">A single reporting server can process a maximum 1500 concurrent connections.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bfa65-348">報告資料庫。</span><span class="sxs-lookup"><span data-stu-id="bfa65-348">Reporting Database.</span></span></p>
<p></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-349">執行 Microsoft SQL Server 的電腦上的鎖爭用是要求/秒的限制因素。</span><span class="sxs-lookup"><span data-stu-id="bfa65-349">Lock contention on the computer running Microsoft SQL Server is the limiting factor for requests/second.</span></span></p></li>
<li><p><span data-ttu-id="bfa65-350">輸送量與回應時間是獨立于資料庫大小的。</span><span class="sxs-lookup"><span data-stu-id="bfa65-350">Throughput and response time are independent of database size.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="bfa65-351">**計算隨機延遲**：</span><span class="sxs-lookup"><span data-stu-id="bfa65-351">**Calculating random delay**:</span></span>

<span data-ttu-id="bfa65-352">隨機延遲指定將資料傳送到報表伺服器的最大延遲（以分鐘為單位）。</span><span class="sxs-lookup"><span data-stu-id="bfa65-352">The random delay specifies the maximum delay (in minutes) for data to be sent to the reporting server.</span></span> <span data-ttu-id="bfa65-353">當排程的任務開始時，用戶端會在**0**與**ReportingRandomDelay**之間產生隨機延遲，並在傳送資料之前等待指定的持續時間。</span><span class="sxs-lookup"><span data-stu-id="bfa65-353">When the scheduled task is started, the client generates a random delay between **0** and **ReportingRandomDelay** and will wait the specified duration before sending data.</span></span>

<span data-ttu-id="bfa65-354">隨機延遲 = 4 \ \* 用戶端數目/每秒平均請求數。</span><span class="sxs-lookup"><span data-stu-id="bfa65-354">Random delay = 4 \* number of clients / average requests per second.</span></span>

<span data-ttu-id="bfa65-355">範例：針對500用戶端（每秒含120個要求），隨機延遲是，4 \ \* 500/120 = ~ 17 分鐘。</span><span class="sxs-lookup"><span data-stu-id="bfa65-355">Example: For 500 clients, with 120 requests per second, the Random delay is, 4 \* 500 / 120 = ~17 minutes.</span></span>

## <a href="" id="---------app-v-5-1-publishing-server-capacity-planning-recommendations"></a> <span data-ttu-id="bfa65-356">App-V 5.1 發佈伺服器容量規劃建議</span><span class="sxs-lookup"><span data-stu-id="bfa65-356">App-V 5.1 Publishing Server Capacity Planning Recommendations</span></span>


<span data-ttu-id="bfa65-357">執行 App-V 5.1 用戶端的電腦會連線至 App-v 5.1 發佈伺服器，以傳送發佈重新整理要求並接收回應。</span><span class="sxs-lookup"><span data-stu-id="bfa65-357">Computers running the App-V 5.1 client connect to the App-V 5.1 publishing server to send a publishing refresh request and to receive a response.</span></span> <span data-ttu-id="bfa65-358">在執行 App-v 5.1 用戶端的電腦上測量往返行程回應時間。</span><span class="sxs-lookup"><span data-stu-id="bfa65-358">Round trip response time is measured on the computer running the App-V 5.1 client.</span></span> <span data-ttu-id="bfa65-359">處理器時間是在發佈伺服器上測量。</span><span class="sxs-lookup"><span data-stu-id="bfa65-359">Processor time is measured on the publishing server.</span></span> <span data-ttu-id="bfa65-360">如需 App-V 5.1 發佈伺服器支援之設定的詳細資訊，請參閱[app-v 5.1 支援](app-v-51-supported-configurations.md)的設定。</span><span class="sxs-lookup"><span data-stu-id="bfa65-360">For more information about App-V 5.1 Publishing Server supported configurations see [App-V 5.1 Supported Configurations](app-v-51-supported-configurations.md).</span></span>

<span data-ttu-id="bfa65-361">**重要** 下列清單顯示設定 App-v 5.1 發佈伺服器時要考慮的主要因素：</span><span class="sxs-lookup"><span data-stu-id="bfa65-361">**Important** The following list displays the main factors to consider when setting up the App-V 5.1 publishing server:</span></span>

-   <span data-ttu-id="bfa65-362">同時連接到單一發布伺服器的用戶端數量。</span><span class="sxs-lookup"><span data-stu-id="bfa65-362">The number of clients connecting simultaneously to a single publishing server.</span></span>

-   <span data-ttu-id="bfa65-363">每次重新整理中的套件數目。</span><span class="sxs-lookup"><span data-stu-id="bfa65-363">The number of packages in each refresh.</span></span>

-   <span data-ttu-id="bfa65-364">用戶端與 app-v 5.1 發佈伺服器之間的環境中的可用網路頻寬。</span><span class="sxs-lookup"><span data-stu-id="bfa65-364">The available network bandwidth in your environment between the client and the App-V 5.1 publishing server.</span></span>

 

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bfa65-365">案例</span><span class="sxs-lookup"><span data-stu-id="bfa65-365">Scenario</span></span></th>
<th align="left"><span data-ttu-id="bfa65-366">摘要</span><span class="sxs-lookup"><span data-stu-id="bfa65-366">Summary</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bfa65-367">多個 App-V 5.1 用戶端同時連線到單一發布伺服器。</span><span class="sxs-lookup"><span data-stu-id="bfa65-367">Multiple App-V 5.1 clients connect to a single publishing server simultaneously.</span></span></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-368">執行雙核心處理器的發佈伺服器最多可以在要求同時進行重新整理的5000用戶端上回應。</span><span class="sxs-lookup"><span data-stu-id="bfa65-368">A publishing server running dual core processors can respond to at most 5000 clients requesting a refresh simultaneously.</span></span></p></li>
<li><p><span data-ttu-id="bfa65-369">針對5000-10000 用戶端，發佈伺服器需要最低的四核核心。</span><span class="sxs-lookup"><span data-stu-id="bfa65-369">For 5000-10000 clients, the publishing server requires a minimum quad core.</span></span></p></li>
<li><p><span data-ttu-id="bfa65-370">針對10000-20000 用戶端，發佈伺服器應該有雙四核，以獲得更有效率的回應時間。</span><span class="sxs-lookup"><span data-stu-id="bfa65-370">For 10000-20000 clients, the publishing server should have dual quad cores for more efficient response times.</span></span></p></li>
<li><p><span data-ttu-id="bfa65-371">含四核的發佈伺服器在3秒內可以重新整理至10000套件。</span><span class="sxs-lookup"><span data-stu-id="bfa65-371">A publishing server with a quad core can refresh up to 10000 packages within 3 seconds.</span></span> <span data-ttu-id="bfa65-372">（支援10000併發用戶端）</span><span class="sxs-lookup"><span data-stu-id="bfa65-372">(Supporting 10000 simultaneous clients)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bfa65-373">每次重新整理中的套件數目。</span><span class="sxs-lookup"><span data-stu-id="bfa65-373">Number of packages in each refresh.</span></span></p>
<p></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-374">數量增加的套件會增加大約40% （最多1000個套件）的回應時間。</span><span class="sxs-lookup"><span data-stu-id="bfa65-374">Increasing number of packages will increase response time by ~40% (up to 1000 packages).</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bfa65-375">App-V 5.1 用戶端與發佈伺服器之間的網路。</span><span class="sxs-lookup"><span data-stu-id="bfa65-375">Network between the App-V 5.1 client and the publishing server.</span></span></p>
<p></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-376">在慢速網路（1.5 Mbps 頻寬）中，回應時間會隨著局域網（最高達1000使用者）而增加97%。</span><span class="sxs-lookup"><span data-stu-id="bfa65-376">Across a slow network (1.5 Mbps bandwidth), there is a 97% increase in response time compared to LAN (up to 1000 users).</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="bfa65-377">**記事** 發佈伺服器的 CPU 使用量在必須處理同時要求的時間間隔期間（ &gt; 在大多數情況下，會有90%）。</span><span class="sxs-lookup"><span data-stu-id="bfa65-377">**Note** The publishing server CPU usage is always high during the time interval when it has to process simultaneous requests (&gt;90% in most cases).</span></span> <span data-ttu-id="bfa65-378">發佈伺服器可以在1秒內處理 ~ 1500 用戶端要求。</span><span class="sxs-lookup"><span data-stu-id="bfa65-378">The publishing server can handle ~1500 client requests in 1 second.</span></span>

 

<table>
<colgroup>
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bfa65-379">案例</span><span class="sxs-lookup"><span data-stu-id="bfa65-379">Scenario</span></span></th>
<th align="left"><span data-ttu-id="bfa65-380">變化</span><span class="sxs-lookup"><span data-stu-id="bfa65-380">Variation</span></span></th>
<th align="left"><span data-ttu-id="bfa65-381">App-v 5.1 用戶端的數目</span><span class="sxs-lookup"><span data-stu-id="bfa65-381">Number of App-V 5.1 clients</span></span></th>
<th align="left"><span data-ttu-id="bfa65-382">套件數目</span><span class="sxs-lookup"><span data-stu-id="bfa65-382">Number of packages</span></span></th>
<th align="left"><span data-ttu-id="bfa65-383">發佈伺服器上的處理器配置</span><span class="sxs-lookup"><span data-stu-id="bfa65-383">Processor configuration on the publishing server</span></span></th>
<th align="left"><span data-ttu-id="bfa65-384">網路連線類型發佈 server/App-v 5.1 用戶端</span><span class="sxs-lookup"><span data-stu-id="bfa65-384">Network connection type publishing server / App-V 5.1 client</span></span></th>
<th align="left"><span data-ttu-id="bfa65-385">App-v 5.1 用戶端上的往返時間（以秒為單位）</span><span class="sxs-lookup"><span data-stu-id="bfa65-385">Round trip time on the App-V 5.1 client (in seconds)</span></span></th>
<th align="left"><span data-ttu-id="bfa65-386">發佈伺服器上的 CPU 利用率（以%）</span><span class="sxs-lookup"><span data-stu-id="bfa65-386">CPU utilization on publishing server (in %)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bfa65-387">App-V 5.1 用戶端傳送發佈更新要求 &amp; 接收回應，每個包含120套件的要求</span><span class="sxs-lookup"><span data-stu-id="bfa65-387">App-V 5.1 client sends publishing refresh request &amp; receives response, each request containing 120 packages</span></span></p></td>
<td align="left"><p><span data-ttu-id="bfa65-388">用戶端數目</span><span class="sxs-lookup"><span data-stu-id="bfa65-388">Number of clients</span></span></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-389">100</span><span class="sxs-lookup"><span data-stu-id="bfa65-389">100</span></span></p></li>
<li><p><span data-ttu-id="bfa65-390">1000</span><span class="sxs-lookup"><span data-stu-id="bfa65-390">1000</span></span></p></li>
<li><p><span data-ttu-id="bfa65-391">5000</span><span class="sxs-lookup"><span data-stu-id="bfa65-391">5000</span></span></p></li>
<li><p><span data-ttu-id="bfa65-392">10000</span><span class="sxs-lookup"><span data-stu-id="bfa65-392">10000</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-393">120</span><span class="sxs-lookup"><span data-stu-id="bfa65-393">120</span></span></p></li>
<li><p><span data-ttu-id="bfa65-394">120</span><span class="sxs-lookup"><span data-stu-id="bfa65-394">120</span></span></p></li>
<li><p><span data-ttu-id="bfa65-395">120</span><span class="sxs-lookup"><span data-stu-id="bfa65-395">120</span></span></p></li>
<li><p><span data-ttu-id="bfa65-396">120</span><span class="sxs-lookup"><span data-stu-id="bfa65-396">120</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-397">雙核</span><span class="sxs-lookup"><span data-stu-id="bfa65-397">Dual Core</span></span></p></li>
<li><p><span data-ttu-id="bfa65-398">雙核</span><span class="sxs-lookup"><span data-stu-id="bfa65-398">Dual Core</span></span></p></li>
<li><p><span data-ttu-id="bfa65-399">四核</span><span class="sxs-lookup"><span data-stu-id="bfa65-399">Quad Core</span></span></p></li>
<li><p><span data-ttu-id="bfa65-400">四核</span><span class="sxs-lookup"><span data-stu-id="bfa65-400">Quad Core</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-401">LAN</span><span class="sxs-lookup"><span data-stu-id="bfa65-401">LAN</span></span></p></li>
<li><p><span data-ttu-id="bfa65-402">LAN</span><span class="sxs-lookup"><span data-stu-id="bfa65-402">LAN</span></span></p></li>
<li><p><span data-ttu-id="bfa65-403">LAN</span><span class="sxs-lookup"><span data-stu-id="bfa65-403">LAN</span></span></p></li>
<li><p><span data-ttu-id="bfa65-404">LAN</span><span class="sxs-lookup"><span data-stu-id="bfa65-404">LAN</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-405">sr-1</span><span class="sxs-lookup"><span data-stu-id="bfa65-405">1</span></span></p></li>
<li><p><span data-ttu-id="bfa65-406">pplx-2</span><span class="sxs-lookup"><span data-stu-id="bfa65-406">2</span></span></p></li>
<li><p><span data-ttu-id="bfa65-407">pplx-2</span><span class="sxs-lookup"><span data-stu-id="bfa65-407">2</span></span></p></li>
<li><p><span data-ttu-id="bfa65-408">3</span><span class="sxs-lookup"><span data-stu-id="bfa65-408">3</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-409">100</span><span class="sxs-lookup"><span data-stu-id="bfa65-409">100</span></span></p></li>
<li><p><span data-ttu-id="bfa65-410">99</span><span class="sxs-lookup"><span data-stu-id="bfa65-410">99</span></span></p></li>
<li><p><span data-ttu-id="bfa65-411">89</span><span class="sxs-lookup"><span data-stu-id="bfa65-411">89</span></span></p></li>
<li><p><span data-ttu-id="bfa65-412">77</span><span class="sxs-lookup"><span data-stu-id="bfa65-412">77</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bfa65-413">每次重新整理中有多個套件</span><span class="sxs-lookup"><span data-stu-id="bfa65-413">Multiple packages in each refresh</span></span></p></td>
<td align="left"><p><span data-ttu-id="bfa65-414">套件數目</span><span class="sxs-lookup"><span data-stu-id="bfa65-414">Number of packages</span></span></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-415">1000</span><span class="sxs-lookup"><span data-stu-id="bfa65-415">1000</span></span></p></li>
<li><p><span data-ttu-id="bfa65-416">1000</span><span class="sxs-lookup"><span data-stu-id="bfa65-416">1000</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-417">500</span><span class="sxs-lookup"><span data-stu-id="bfa65-417">500</span></span></p></li>
<li><p><span data-ttu-id="bfa65-418">1000</span><span class="sxs-lookup"><span data-stu-id="bfa65-418">1000</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-419">四核</span><span class="sxs-lookup"><span data-stu-id="bfa65-419">Quad Core</span></span></p></li>
<li><p><span data-ttu-id="bfa65-420">四核</span><span class="sxs-lookup"><span data-stu-id="bfa65-420">Quad Core</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-421">LAN</span><span class="sxs-lookup"><span data-stu-id="bfa65-421">LAN</span></span></p></li>
<li><p><span data-ttu-id="bfa65-422">LAN</span><span class="sxs-lookup"><span data-stu-id="bfa65-422">LAN</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-423">pplx-2</span><span class="sxs-lookup"><span data-stu-id="bfa65-423">2</span></span></p></li>
<li><p><span data-ttu-id="bfa65-424">3</span><span class="sxs-lookup"><span data-stu-id="bfa65-424">3</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-425">92</span><span class="sxs-lookup"><span data-stu-id="bfa65-425">92</span></span></p></li>
<li><p><span data-ttu-id="bfa65-426">91</span><span class="sxs-lookup"><span data-stu-id="bfa65-426">91</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bfa65-427">用戶端與發佈伺服器之間的網路</span><span class="sxs-lookup"><span data-stu-id="bfa65-427">Network between client and publishing server</span></span></p></td>
<td align="left"><p><span data-ttu-id="bfa65-428">1.5 Mbps 低速連結網路</span><span class="sxs-lookup"><span data-stu-id="bfa65-428">1.5 Mbps Slow link network</span></span></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-429">100</span><span class="sxs-lookup"><span data-stu-id="bfa65-429">100</span></span></p></li>
<li><p><span data-ttu-id="bfa65-430">500</span><span class="sxs-lookup"><span data-stu-id="bfa65-430">500</span></span></p></li>
<li><p><span data-ttu-id="bfa65-431">1000</span><span class="sxs-lookup"><span data-stu-id="bfa65-431">1000</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-432">120</span><span class="sxs-lookup"><span data-stu-id="bfa65-432">120</span></span></p></li>
<li><p><span data-ttu-id="bfa65-433">120</span><span class="sxs-lookup"><span data-stu-id="bfa65-433">120</span></span></p></li>
<li><p><span data-ttu-id="bfa65-434">120</span><span class="sxs-lookup"><span data-stu-id="bfa65-434">120</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-435">四核</span><span class="sxs-lookup"><span data-stu-id="bfa65-435">Quad Core</span></span></p></li>
<li><p><span data-ttu-id="bfa65-436">四核</span><span class="sxs-lookup"><span data-stu-id="bfa65-436">Quad Core</span></span></p></li>
<li><p><span data-ttu-id="bfa65-437">四核</span><span class="sxs-lookup"><span data-stu-id="bfa65-437">Quad Core</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-438">1.5 Mbps 的大陸內部網路</span><span class="sxs-lookup"><span data-stu-id="bfa65-438">1.5 Mbps Intra-Continental Network</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-439">3</span><span class="sxs-lookup"><span data-stu-id="bfa65-439">3</span></span></p></li>
<li><p><span data-ttu-id="bfa65-440">10（含0.2% 失敗率）</span><span class="sxs-lookup"><span data-stu-id="bfa65-440">10 (with 0.2% failure rate)</span></span></p></li>
<li><p><span data-ttu-id="bfa65-441">17（1% 失敗率）</span><span class="sxs-lookup"><span data-stu-id="bfa65-441">17 (with 1% failure rate)</span></span></p></li>
</ul></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="---------app-v-5-1-streaming-capacity-planning-recommendations"></a> <span data-ttu-id="bfa65-442">App-v 5.1 流式處理容量規劃建議</span><span class="sxs-lookup"><span data-stu-id="bfa65-442">App-V 5.1 Streaming Capacity Planning Recommendations</span></span>


<span data-ttu-id="bfa65-443">執行 App-V 5.1 用戶端的電腦會從流式處理伺服器對流執行虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="bfa65-443">Computers running the App-V 5.1 client stream the virtual application package from the streaming server.</span></span> <span data-ttu-id="bfa65-444">往返行程回應時間是在執行 App-v 5.1 用戶端的電腦上測量，且是處理整個套件所需的時間。</span><span class="sxs-lookup"><span data-stu-id="bfa65-444">Round trip response time is measured on the computer running the App-V 5.1 client, and is the time taken to stream the entire package.</span></span>

<span data-ttu-id="bfa65-445">**重要** 下列清單說明設定 App-v 5.1 流式處理伺服器時要考慮的主要因素：</span><span class="sxs-lookup"><span data-stu-id="bfa65-445">**Important** The following list identifies the main factors to consider when setting up the App-V 5.1 streaming server:</span></span>

-   <span data-ttu-id="bfa65-446">從單一流式處理伺服器同時流式處理應用程式套件的用戶端數量。</span><span class="sxs-lookup"><span data-stu-id="bfa65-446">The number of clients streaming application packages simultaneously from a single streaming server.</span></span>

-   <span data-ttu-id="bfa65-447">要流入的套件大小。</span><span class="sxs-lookup"><span data-stu-id="bfa65-447">The size of the package being streamed.</span></span>

-   <span data-ttu-id="bfa65-448">用戶端與流式處理伺服器之間的環境中的可用網路頻寬。</span><span class="sxs-lookup"><span data-stu-id="bfa65-448">The available network bandwidth in your environment between the client and the streaming server.</span></span>

 

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bfa65-449">案例</span><span class="sxs-lookup"><span data-stu-id="bfa65-449">Scenario</span></span></th>
<th align="left"><span data-ttu-id="bfa65-450">摘要</span><span class="sxs-lookup"><span data-stu-id="bfa65-450">Summary</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bfa65-451">多個 App-v 5.1 用戶端會同時從單一資料流程伺服器資料流程應用程式。</span><span class="sxs-lookup"><span data-stu-id="bfa65-451">Multiple App-V 5.1 clients stream applications from a single streaming server simultaneously.</span></span></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-452">如果同時從同一個伺服器同時流式處理的用戶端數量增加，就會有與套件下載/資料流程時間相對應的線性關聯。</span><span class="sxs-lookup"><span data-stu-id="bfa65-452">If the number of clients simultaneously streaming from the same server increases, there is a linear relationship with the package download/streaming time.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bfa65-453">要流入的套件大小。</span><span class="sxs-lookup"><span data-stu-id="bfa65-453">Size of the package being streamed.</span></span></p>
<p></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-454">套件大小對於大小約為1GB 的大型套件，只會對資料流程/下載時間產生很大的影響。</span><span class="sxs-lookup"><span data-stu-id="bfa65-454">The package size has a significant impact on the streaming/download time only for larger packages with a size ~ 1GB.</span></span> <span data-ttu-id="bfa65-455">對於從 3 MB 到 100 MB 的封裝大小，資料流程時間的範圍是從20秒到100秒，以及100併發的用戶端。</span><span class="sxs-lookup"><span data-stu-id="bfa65-455">For package sizes ranging from 3 MB to 100 MB, the streaming time ranges from 20 seconds to 100 seconds, with 100 simultaneous clients.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bfa65-456">App-V 5.1 用戶端與流式處理伺服器之間的網路。</span><span class="sxs-lookup"><span data-stu-id="bfa65-456">Network between the App-V 5.1 client and the streaming server.</span></span></p>
<p></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-457">在慢速網路（1.5 Mbps 頻寬）中，回應時間會隨著局域網（最高達100使用者）而增加70-80%。</span><span class="sxs-lookup"><span data-stu-id="bfa65-457">Across a slow network (1.5 Mbps bandwidth), there is a 70-80% increase in response time compared to LAN (up to 100 users).</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="bfa65-458">下表顯示前面清單中每個因素的範例值：</span><span class="sxs-lookup"><span data-stu-id="bfa65-458">The following table displays sample values for each of the factors in the previous list:</span></span>

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bfa65-459">案例</span><span class="sxs-lookup"><span data-stu-id="bfa65-459">Scenario</span></span></th>
<th align="left"><span data-ttu-id="bfa65-460">變化</span><span class="sxs-lookup"><span data-stu-id="bfa65-460">Variation</span></span></th>
<th align="left"><span data-ttu-id="bfa65-461">App-v 5.1 用戶端的數目</span><span class="sxs-lookup"><span data-stu-id="bfa65-461">Number of App-V 5.1 clients</span></span></th>
<th align="left"><span data-ttu-id="bfa65-462">每個套件的大小</span><span class="sxs-lookup"><span data-stu-id="bfa65-462">Size of each package</span></span></th>
<th align="left"><span data-ttu-id="bfa65-463">網路連線類型流式處理伺服器/App-v 5.1 用戶端</span><span class="sxs-lookup"><span data-stu-id="bfa65-463">Network connection type streaming server / App-V 5.1 client</span></span></th>
<th align="left"><span data-ttu-id="bfa65-464">App-v 5.1 用戶端上的往返時間（以秒為單位）</span><span class="sxs-lookup"><span data-stu-id="bfa65-464">Round trip time on the App-V 5.1 client (in seconds)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bfa65-465">多個 App-V 5.1 用戶端從流式處理伺服器流式處理虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="bfa65-465">Multiple App-V 5.1 clients streaming virtual application packages from a streaming server.</span></span></p></td>
<td align="left"><p><span data-ttu-id="bfa65-466">用戶端數量。</span><span class="sxs-lookup"><span data-stu-id="bfa65-466">Number of clients.</span></span></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-467">100</span><span class="sxs-lookup"><span data-stu-id="bfa65-467">100</span></span></p></li>
<li><p><span data-ttu-id="bfa65-468">200</span><span class="sxs-lookup"><span data-stu-id="bfa65-468">200</span></span></p></li>
<li><p><span data-ttu-id="bfa65-469">1000</span><span class="sxs-lookup"><span data-stu-id="bfa65-469">1000</span></span></p></li>
<li><p></p></li>
<li><p><span data-ttu-id="bfa65-470">100</span><span class="sxs-lookup"><span data-stu-id="bfa65-470">100</span></span></p></li>
<li><p><span data-ttu-id="bfa65-471">200</span><span class="sxs-lookup"><span data-stu-id="bfa65-471">200</span></span></p></li>
<li><p><span data-ttu-id="bfa65-472">1000</span><span class="sxs-lookup"><span data-stu-id="bfa65-472">1000</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-473">3.5 MB</span><span class="sxs-lookup"><span data-stu-id="bfa65-473">3.5 MB</span></span></p></li>
<li><p><span data-ttu-id="bfa65-474">3.5 MB</span><span class="sxs-lookup"><span data-stu-id="bfa65-474">3.5 MB</span></span></p></li>
<li><p><span data-ttu-id="bfa65-475">3.5 MB</span><span class="sxs-lookup"><span data-stu-id="bfa65-475">3.5 MB</span></span></p></li>
<li><p></p></li>
<li><p><span data-ttu-id="bfa65-476">5 MB</span><span class="sxs-lookup"><span data-stu-id="bfa65-476">5 MB</span></span></p></li>
<li><p><span data-ttu-id="bfa65-477">5 MB</span><span class="sxs-lookup"><span data-stu-id="bfa65-477">5 MB</span></span></p></li>
<li><p><span data-ttu-id="bfa65-478">5 MB</span><span class="sxs-lookup"><span data-stu-id="bfa65-478">5 MB</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-479">LAN</span><span class="sxs-lookup"><span data-stu-id="bfa65-479">LAN</span></span></p></li>
<li><p><span data-ttu-id="bfa65-480">LAN</span><span class="sxs-lookup"><span data-stu-id="bfa65-480">LAN</span></span></p></li>
<li><p><span data-ttu-id="bfa65-481">LAN</span><span class="sxs-lookup"><span data-stu-id="bfa65-481">LAN</span></span></p></li>
<li><p></p></li>
<li><p><span data-ttu-id="bfa65-482">LAN</span><span class="sxs-lookup"><span data-stu-id="bfa65-482">LAN</span></span></p></li>
<li><p><span data-ttu-id="bfa65-483">LAN</span><span class="sxs-lookup"><span data-stu-id="bfa65-483">LAN</span></span></p></li>
<li><p><span data-ttu-id="bfa65-484">LAN</span><span class="sxs-lookup"><span data-stu-id="bfa65-484">LAN</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-485">5</span><span class="sxs-lookup"><span data-stu-id="bfa65-485">29</span></span></p></li>
<li><p><span data-ttu-id="bfa65-486">39</span><span class="sxs-lookup"><span data-stu-id="bfa65-486">39</span></span></p></li>
<li><p><span data-ttu-id="bfa65-487">391</span><span class="sxs-lookup"><span data-stu-id="bfa65-487">391</span></span></p></li>
<li><p></p></li>
<li><p><span data-ttu-id="bfa65-488">35</span><span class="sxs-lookup"><span data-stu-id="bfa65-488">35</span></span></p></li>
<li><p><span data-ttu-id="bfa65-489">68</span><span class="sxs-lookup"><span data-stu-id="bfa65-489">68</span></span></p></li>
<li><p><span data-ttu-id="bfa65-490">461</span><span class="sxs-lookup"><span data-stu-id="bfa65-490">461</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bfa65-491">正在進行資料流程處理的每個套件大小。</span><span class="sxs-lookup"><span data-stu-id="bfa65-491">Size of each package being streamed.</span></span></p></td>
<td align="left"><p><span data-ttu-id="bfa65-492">每個套件的大小。</span><span class="sxs-lookup"><span data-stu-id="bfa65-492">Size of each package.</span></span></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-493">100</span><span class="sxs-lookup"><span data-stu-id="bfa65-493">100</span></span></p></li>
<li><p><span data-ttu-id="bfa65-494">200</span><span class="sxs-lookup"><span data-stu-id="bfa65-494">200</span></span></p></li>
<li><p></p></li>
<li><p><span data-ttu-id="bfa65-495">100</span><span class="sxs-lookup"><span data-stu-id="bfa65-495">100</span></span></p></li>
<li><p><span data-ttu-id="bfa65-496">200</span><span class="sxs-lookup"><span data-stu-id="bfa65-496">200</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-497">21 MB</span><span class="sxs-lookup"><span data-stu-id="bfa65-497">21 MB</span></span></p></li>
<li><p><span data-ttu-id="bfa65-498">21 MB</span><span class="sxs-lookup"><span data-stu-id="bfa65-498">21 MB</span></span></p></li>
<li><p></p></li>
<li><p><span data-ttu-id="bfa65-499">109</span><span class="sxs-lookup"><span data-stu-id="bfa65-499">109</span></span></p></li>
<li><p><span data-ttu-id="bfa65-500">109</span><span class="sxs-lookup"><span data-stu-id="bfa65-500">109</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-501">LAN</span><span class="sxs-lookup"><span data-stu-id="bfa65-501">LAN</span></span></p></li>
<li><p><span data-ttu-id="bfa65-502">LAN</span><span class="sxs-lookup"><span data-stu-id="bfa65-502">LAN</span></span></p></li>
<li><p></p></li>
<li><p><span data-ttu-id="bfa65-503">LAN</span><span class="sxs-lookup"><span data-stu-id="bfa65-503">LAN</span></span></p></li>
<li><p><span data-ttu-id="bfa65-504">LAN</span><span class="sxs-lookup"><span data-stu-id="bfa65-504">LAN</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<p><span data-ttu-id="bfa65-505">33</span><span class="sxs-lookup"><span data-stu-id="bfa65-505">33</span></span></p>
<p><span data-ttu-id="bfa65-506">83</span><span class="sxs-lookup"><span data-stu-id="bfa65-506">83</span></span></p>
<p></p>
<p><span data-ttu-id="bfa65-507">100</span><span class="sxs-lookup"><span data-stu-id="bfa65-507">100</span></span></p>
<p><span data-ttu-id="bfa65-508">160</span><span class="sxs-lookup"><span data-stu-id="bfa65-508">160</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bfa65-509">用戶端與 App-v 5.1 流式處理伺服器之間的網路連線。</span><span class="sxs-lookup"><span data-stu-id="bfa65-509">Network connection between client and App-V 5.1 streaming server.</span></span></p></td>
<td align="left"><p><span data-ttu-id="bfa65-510">1.5 Mbps 低速連結網路。</span><span class="sxs-lookup"><span data-stu-id="bfa65-510">1.5 Mbps Slow link network.</span></span></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-511">100</span><span class="sxs-lookup"><span data-stu-id="bfa65-511">100</span></span></p></li>
<li><p></p></li>
<li><p><span data-ttu-id="bfa65-512">100</span><span class="sxs-lookup"><span data-stu-id="bfa65-512">100</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-513">3.5 MB</span><span class="sxs-lookup"><span data-stu-id="bfa65-513">3.5 MB</span></span></p></li>
<li><p></p></li>
<li><p><span data-ttu-id="bfa65-514">5 MB</span><span class="sxs-lookup"><span data-stu-id="bfa65-514">5 MB</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="bfa65-515">1.5 Mbps 的大陸內部網路</span><span class="sxs-lookup"><span data-stu-id="bfa65-515">1.5 Mbps Intra-Continental Network</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<p><span data-ttu-id="bfa65-516">102</span><span class="sxs-lookup"><span data-stu-id="bfa65-516">102</span></span></p>
<p></p>
<p><span data-ttu-id="bfa65-517">121</span><span class="sxs-lookup"><span data-stu-id="bfa65-517">121</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="bfa65-518">每個應用程式 V 5.1 流式處理伺服器都應該能夠處理同時流式處理的虛擬化應用程式最少的200個用戶端。</span><span class="sxs-lookup"><span data-stu-id="bfa65-518">Each App-V 5.1 streaming server should be able to handle a minimum of 200 clients concurrently streaming virtualized applications.</span></span>

<span data-ttu-id="bfa65-519">**記事** 資料流程的實際時間是由同時流式處理的用戶端數、套件數目、套件大小、伺服器的網路活動和網路狀況決定。</span><span class="sxs-lookup"><span data-stu-id="bfa65-519">**Note** The actual time to it will take to stream is determined primarily by the number of clients streaming simultaneously, number of packages, package size, the server’s network activity, and network conditions.</span></span>

 

<span data-ttu-id="bfa65-520">例如，當100同步處理的用戶端從伺服器傳送時，一般的使用者可以將 100 MB 套件資料流程傳輸在2分鐘以內。</span><span class="sxs-lookup"><span data-stu-id="bfa65-520">For example, an average user can stream a 100 MB package in less than 2 minutes, when 100 simultaneous clients are streaming from the server.</span></span> <span data-ttu-id="bfa65-521">不過，大小為 1 GB 的套件可能需要長達30分鐘的時間。</span><span class="sxs-lookup"><span data-stu-id="bfa65-521">However, a package of size 1 GB could take up to 30 minutes.</span></span> <span data-ttu-id="bfa65-522">在大部分實際環境中，資料流程需求不會均勻分佈，您必須瞭解環境中所提供的大約峰值流量需求，才能正確地調整所需的流式處理伺服器數目。</span><span class="sxs-lookup"><span data-stu-id="bfa65-522">In most real world environments streaming demand is not uniformly distributed, you will need to understand the approximate peak streaming requirements present in your environment in order to properly size the number of required streaming servers.</span></span>

<span data-ttu-id="bfa65-523">如果您已預先快取您的應用程式，可能會大幅增加流式處理伺服器支援的用戶端數目，並減少峰值流量需求。</span><span class="sxs-lookup"><span data-stu-id="bfa65-523">The number of clients a streaming server can support can be significantly increased and the peak streaming requirements reduced if you pre-cache your applications.</span></span> <span data-ttu-id="bfa65-524">您也可以使用點播流式傳遞和資料流程優化套件，增加流式處理伺服器可支援的用戶端數量。</span><span class="sxs-lookup"><span data-stu-id="bfa65-524">You can also increase the number of clients a streaming server can support by using on-demand streaming delivery and stream optimized packages.</span></span>

## <span data-ttu-id="bfa65-525">結合 app-v 5.1 伺服器角色</span><span class="sxs-lookup"><span data-stu-id="bfa65-525">Combining App-V 5.1 Server Roles</span></span>


<span data-ttu-id="bfa65-526">折扣調整比例與容錯需求，與 Active Directory 連通的位置所需的伺服器數量最少為1。</span><span class="sxs-lookup"><span data-stu-id="bfa65-526">Discounting scaling and fault-tolerance requirements, the minimum number of servers needed for a location with connectivity to Active Directory is one.</span></span> <span data-ttu-id="bfa65-527">此伺服器將託管管理伺服器、管理伺服器服務及 Microsoft SQL Server 角色。</span><span class="sxs-lookup"><span data-stu-id="bfa65-527">This server will host the management server, management server service, and Microsoft SQL Server roles.</span></span> <span data-ttu-id="bfa65-528">因此，伺服器角色可以依任何所需的組合來排列，因為它們不會相互衝突。</span><span class="sxs-lookup"><span data-stu-id="bfa65-528">Server roles, therefore, can be arranged in any desired combination since they do not conflict with one another.</span></span>

<span data-ttu-id="bfa65-529">忽略縮放需求，提供容錯實現所需的伺服器數量最少為4個。</span><span class="sxs-lookup"><span data-stu-id="bfa65-529">Ignoring scaling requirements, the minimum number of servers necessary to provide a fault-tolerant implementation is four.</span></span> <span data-ttu-id="bfa65-530">管理伺服器以及 Microsoft SQL Server 角色支援將其放在容錯設定中。</span><span class="sxs-lookup"><span data-stu-id="bfa65-530">The management server, and Microsoft SQL Server roles support being placed in fault-tolerant configurations.</span></span> <span data-ttu-id="bfa65-531">管理伺服器服務可以與任何角色結合，但仍會保持單一失敗點。</span><span class="sxs-lookup"><span data-stu-id="bfa65-531">The management server service can be combined with any of the roles, but remains a single point of failure.</span></span>

<span data-ttu-id="bfa65-532">雖然有許多容錯策略和技術可供使用，但並非所有都適用于特定的服務。</span><span class="sxs-lookup"><span data-stu-id="bfa65-532">Although there are a number of fault-tolerance strategies and technologies available, not all are applicable to a given service.</span></span> <span data-ttu-id="bfa65-533">此外，如果結合 app-v 5.1 角色，則某些容錯選項可能會因為不相容而不再適用。</span><span class="sxs-lookup"><span data-stu-id="bfa65-533">Additionally, if App-V 5.1 roles are combined, certain fault-tolerance options may no longer apply due to incompatibilities.</span></span>






## <span data-ttu-id="bfa65-534">相關主題</span><span class="sxs-lookup"><span data-stu-id="bfa65-534">Related topics</span></span>


[<span data-ttu-id="bfa65-535">App-V 5.1 支援的組態</span><span class="sxs-lookup"><span data-stu-id="bfa65-535">App-V 5.1 Supported Configurations</span></span>](app-v-51-supported-configurations.md)

[<span data-ttu-id="bfa65-536">App-V 5.1 高可用性規劃</span><span class="sxs-lookup"><span data-stu-id="bfa65-536">Planning for High Availability with App-V 5.1</span></span>](planning-for-high-availability-with-app-v-51.md)

[<span data-ttu-id="bfa65-537">規劃部署 App-V</span><span class="sxs-lookup"><span data-stu-id="bfa65-537">Planning to Deploy App-V</span></span>](planning-to-deploy-app-v51.md)

 

 





