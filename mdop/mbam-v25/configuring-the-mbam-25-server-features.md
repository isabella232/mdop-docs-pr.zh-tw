---
title: 設定 MBAM 2.5 伺服器功能
description: 設定 MBAM 2.5 伺服器功能
author: dansimp
ms.assetid: 894d1080-5f13-48f7-8fde-82f8d440a4ed
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e6ba2fc49086acf698f61b9997505c8fa884c0eb
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809728"
---
# <span data-ttu-id="43ca9-103">設定 MBAM 2.5 伺服器功能</span><span class="sxs-lookup"><span data-stu-id="43ca9-103">Configuring the MBAM 2.5 Server Features</span></span>


<span data-ttu-id="43ca9-104">在[安裝 MBAM 2.5 伺服器軟體](installing-the-mbam-25-server-software.md)之後，請使用此資訊做為設定 Microsoft BitLocker 管理和監控（MBAM）2.5 伺服器功能的開始位置。</span><span class="sxs-lookup"><span data-stu-id="43ca9-104">Use this information as a starting place for configuring Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 Server features after [Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md).</span></span> <span data-ttu-id="43ca9-105">您可以使用兩種方法來設定 MBAM：</span><span class="sxs-lookup"><span data-stu-id="43ca9-105">There are two methods you can use to configure MBAM:</span></span>

-   <span data-ttu-id="43ca9-106">MBAM Server 設定精靈</span><span class="sxs-lookup"><span data-stu-id="43ca9-106">MBAM Server Configuration wizard</span></span>

-   <span data-ttu-id="43ca9-107">Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="43ca9-107">Windows PowerShell cmdlets</span></span>

## <span data-ttu-id="43ca9-108">開始設定 MBAM 伺服器功能之前</span><span class="sxs-lookup"><span data-stu-id="43ca9-108">Before you start configuring MBAM Server features</span></span>


<span data-ttu-id="43ca9-109">開始設定 MBAM 伺服器功能之前，請先複習並完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="43ca9-109">Review and complete the following steps before you start configuring the MBAM Server features:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="43ca9-110">步驟</span><span class="sxs-lookup"><span data-stu-id="43ca9-110">Step</span></span></th>
<th align="left"><span data-ttu-id="43ca9-111">取得指示的位置</span><span class="sxs-lookup"><span data-stu-id="43ca9-111">Where to get instructions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="43ca9-112">針對 MBAM 查看建議的架構。</span><span class="sxs-lookup"><span data-stu-id="43ca9-112">Review the recommended architecture for MBAM.</span></span></p></td>
<td align="left"><p><a href="high-level-architecture-for-mbam-25.md" data-raw-source="[High-Level Architecture for MBAM 2.5](high-level-architecture-for-mbam-25.md)"><span data-ttu-id="43ca9-113">MBAM 2.5 的概要架構</span><span class="sxs-lookup"><span data-stu-id="43ca9-113">High-Level Architecture for MBAM 2.5</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="43ca9-114">查看 MBAM 支援的設定。</span><span class="sxs-lookup"><span data-stu-id="43ca9-114">Review the supported configurations for MBAM.</span></span></p></td>
<td align="left"><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)"><span data-ttu-id="43ca9-115">MBAM 2.5 支援的組態</span><span class="sxs-lookup"><span data-stu-id="43ca9-115">MBAM 2.5 Supported Configurations</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="43ca9-116">在每個伺服器上完成必要的先決條件。</span><span class="sxs-lookup"><span data-stu-id="43ca9-116">Complete the required prerequisites on each server.</span></span></p></td>
<td align="left"><ul>
<li><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)"><span data-ttu-id="43ca9-117">獨立拓撲與 Configuration Manager 整合拓撲的 MBAM 2.5 伺服器必要條件</span><span class="sxs-lookup"><span data-stu-id="43ca9-117">MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies</span></span></a></p></li>
<li><p><a href="mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md" data-raw-source="[MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)"><span data-ttu-id="43ca9-118">僅適用於 Configuration Manager 整合拓撲的 MBAM 2.5 伺服器必要條件</span><span class="sxs-lookup"><span data-stu-id="43ca9-118">MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology</span></span></a></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="43ca9-119">在您要設定 MBAM 伺服器功能的每個伺服器上安裝 MBAM Server 軟體。</span><span class="sxs-lookup"><span data-stu-id="43ca9-119">Install the MBAM Server software on each server where you will configure an MBAM Server feature.</span></span></p></td>
<td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)"><span data-ttu-id="43ca9-120">安裝 MBAM 2.5 伺服器軟體</span><span class="sxs-lookup"><span data-stu-id="43ca9-120">Installing the MBAM 2.5 Server Software</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="43ca9-121">查看使用 Windows PowerShell 來設定 MBAM 伺服器功能的先決條件（如果您使用此方法來設定 MBAM 伺服器功能）。</span><span class="sxs-lookup"><span data-stu-id="43ca9-121">Review the prerequisites for using Windows PowerShell to configure MBAM Server features (if you are using this method to configure MBAM Server features).</span></span></p></td>
<td align="left"><p><a href="configuring-mbam-25-server-features-by-using-windows-powershell.md" data-raw-source="[Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md)"><span data-ttu-id="43ca9-122">使用 Windows PowerShell 設定 MBAM 2.5 伺服器功能</span><span class="sxs-lookup"><span data-stu-id="43ca9-122">Configuring MBAM 2.5 Server Features by Using Windows PowerShell</span></span></a></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="43ca9-123">配置 MBAM Server 功能的步驟</span><span class="sxs-lookup"><span data-stu-id="43ca9-123">Steps for configuring MBAM Server features</span></span>


<span data-ttu-id="43ca9-124">下表中的每個資料列描述您將根據[針對 MBAM 2.5 建議的高層次架構](high-level-architecture-for-mbam-25.md)，在個別伺服器上設定的功能。</span><span class="sxs-lookup"><span data-stu-id="43ca9-124">Each row in the following table describes the features that you will configure on a separate server, according to the recommended [High-Level Architecture for MBAM 2.5](high-level-architecture-for-mbam-25.md).</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="43ca9-125">要安裝的功能</span><span class="sxs-lookup"><span data-stu-id="43ca9-125">Features to install</span></span></th>
<th align="left"><span data-ttu-id="43ca9-126">取得指示的位置</span><span class="sxs-lookup"><span data-stu-id="43ca9-126">Where to get instructions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="43ca9-127">設定資料庫。</span><span class="sxs-lookup"><span data-stu-id="43ca9-127">Configure the databases.</span></span></p></td>
<td align="left"><p><a href="how-to-configure-the-mbam-25-databases.md" data-raw-source="[How to Configure the MBAM 2.5 Databases](how-to-configure-the-mbam-25-databases.md)"><span data-ttu-id="43ca9-128">如何設定 MBAM 2.5 資料庫</span><span class="sxs-lookup"><span data-stu-id="43ca9-128">How to Configure the MBAM 2.5 Databases</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="43ca9-129">設定報告。</span><span class="sxs-lookup"><span data-stu-id="43ca9-129">Configure the reports.</span></span></p></td>
<td align="left"><p><a href="how-to-configure-the-mbam-25-reports.md" data-raw-source="[How to Configure the MBAM 2.5 Reports](how-to-configure-the-mbam-25-reports.md)"><span data-ttu-id="43ca9-130">如何設定 MBAM 2.5 報告</span><span class="sxs-lookup"><span data-stu-id="43ca9-130">How to Configure the MBAM 2.5 Reports</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="43ca9-131">設定 web 應用程式。</span><span class="sxs-lookup"><span data-stu-id="43ca9-131">Configure the web applications.</span></span></p></td>
<td align="left"><p><a href="how-to-configure-the-mbam-25-web-applications.md" data-raw-source="[How to Configure the MBAM 2.5 Web Applications](how-to-configure-the-mbam-25-web-applications.md)"><span data-ttu-id="43ca9-132">如何設定 MBAM 2.5 Web 應用程式</span><span class="sxs-lookup"><span data-stu-id="43ca9-132">How to Configure the MBAM 2.5 Web Applications</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="43ca9-133">設定 System Center Configuration Manager 整合（如果適用的話）。</span><span class="sxs-lookup"><span data-stu-id="43ca9-133">Configure the System Center Configuration Manager Integration (if applicable).</span></span></p></td>
<td align="left"><p><a href="how-to-configure-the-mbam-25-system-center-configuration-manager-integration.md" data-raw-source="[How to Configure the MBAM 2.5 System Center Configuration Manager Integration](how-to-configure-the-mbam-25-system-center-configuration-manager-integration.md)"><span data-ttu-id="43ca9-134">如何設定 MBAM 2.5 System Center Configuration Manager 整合</span><span class="sxs-lookup"><span data-stu-id="43ca9-134">How to Configure the MBAM 2.5 System Center Configuration Manager Integration</span></span></a></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="43ca9-135">如需 MBAM Server 功能設定的事件清單，請參閱[伺服器事件記錄](server-event-logs.md)。</span><span class="sxs-lookup"><span data-stu-id="43ca9-135">For a list of events about MBAM Server feature configuration, see [Server Event Logs](server-event-logs.md).</span></span>



## <span data-ttu-id="43ca9-136">相關主題</span><span class="sxs-lookup"><span data-stu-id="43ca9-136">Related topics</span></span>


<span data-ttu-id="43ca9-137">設定 MBAM 2.5 伺服器功能</span><span class="sxs-lookup"><span data-stu-id="43ca9-137">Configuring the MBAM 2.5 Server Features</span></span>
 

 
## <span data-ttu-id="43ca9-138">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="43ca9-138">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="43ca9-139">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="43ca9-139">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="43ca9-140">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="43ca9-140">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>




