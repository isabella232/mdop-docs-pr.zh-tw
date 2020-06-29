---
title: Configuration Manager 整合功能的必要條件
description: Configuration Manager 整合功能的必要條件
author: dansimp
ms.assetid: b318cbd3-b009-44b8-991b-f7364c1cae88
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: af7abd50f6218810dd6718f091512b48fee32652
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810899"
---
# <span data-ttu-id="7dd36-103">Configuration Manager 整合功能的必要條件</span><span class="sxs-lookup"><span data-stu-id="7dd36-103">Prerequisites for the Configuration Manager Integration Feature</span></span>


<span data-ttu-id="7dd36-104">如果您使用 System Center Configuration Manager 整合拓朴部署 MBAM，我們建議使用三個伺服器架構，如[MBAM 2.5 的高層架構與 Configuration Manager 整合拓撲](high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="7dd36-104">If you deploy MBAM with the System Center Configuration Manager Integration topology, we recommend a three-server architecture, as described in [High-Level Architecture of MBAM 2.5 with Configuration Manager Integration Topology](high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology.md).</span></span> <span data-ttu-id="7dd36-105">這個架構可以支援500000用戶端電腦。</span><span class="sxs-lookup"><span data-stu-id="7dd36-105">This architecture can support 500,000 client computers.</span></span>

**<span data-ttu-id="7dd36-106">重要</span><span class="sxs-lookup"><span data-stu-id="7dd36-106">Important</span></span>**  
<span data-ttu-id="7dd36-107">當您使用 Configuration Manager 2007 時，Configuration Manager 整合拓撲安裝不支援 Windows To Go。</span><span class="sxs-lookup"><span data-stu-id="7dd36-107">Windows To Go is not supported for the Configuration Manager Integration topology installation when you are using Configuration Manager 2007.</span></span>



## <span data-ttu-id="7dd36-108">Configuration Manager 整合功能的一般先決條件</span><span class="sxs-lookup"><span data-stu-id="7dd36-108">General prerequisites for the Configuration Manager Integration feature</span></span>


<span data-ttu-id="7dd36-109">當您使用 Configuration Manager 安裝 MBAM 時，除了獨立拓朴的先決條件之外，還需要下列額外的先決條件。</span><span class="sxs-lookup"><span data-stu-id="7dd36-109">When you install MBAM with Configuration Manager, the following additional prerequisites are required in addition to the prerequisites for the Stand-alone topology.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="7dd36-110">必備</span><span class="sxs-lookup"><span data-stu-id="7dd36-110">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="7dd36-111">其他資訊</span><span class="sxs-lookup"><span data-stu-id="7dd36-111">Additional information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7dd36-112">Configuration Manager 伺服器是 Configuration Manager 系統中的主要網站。</span><span class="sxs-lookup"><span data-stu-id="7dd36-112">The Configuration Manager Server is a primary site in the Configuration Manager system.</span></span></p></td>
<td align="left"><p><span data-ttu-id="7dd36-113">無</span><span class="sxs-lookup"><span data-stu-id="7dd36-113">N/A</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="7dd36-114">硬體清查用戶端代理程式位於 Configuration Manager 伺服器上。</span><span class="sxs-lookup"><span data-stu-id="7dd36-114">The Hardware Inventory Client Agent is on the Configuration Manager Server.</span></span></p></td>
<td align="left"><p><span data-ttu-id="7dd36-115">針對 System Center 2012 Configuration Manager，請參閱 <a href="https://go.microsoft.com/fwlink/?LinkId=301685" data-raw-source="[How to Configure Hardware Inventory in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301685)"> 如何在 Configuration Manager 中設定硬體清查 </a> 。</span><span class="sxs-lookup"><span data-stu-id="7dd36-115">For System Center 2012 Configuration Manager, see <a href="https://go.microsoft.com/fwlink/?LinkId=301685" data-raw-source="[How to Configure Hardware Inventory in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301685)">How to Configure Hardware Inventory in Configuration Manager</a>.</span></span></p>
<p><span data-ttu-id="7dd36-116">如需 Configuration Manager 2007 的詳細說明，請參閱 <a href="https://go.microsoft.com/fwlink/?LinkId=301656" data-raw-source="[How to Configure Hardware Inventory for a Site](https://go.microsoft.com/fwlink/?LinkId=301656)"> 如何設定網站的硬體清點 </a> 。</span><span class="sxs-lookup"><span data-stu-id="7dd36-116">For Configuration Manager 2007, see <a href="https://go.microsoft.com/fwlink/?LinkId=301656" data-raw-source="[How to Configure Hardware Inventory for a Site](https://go.microsoft.com/fwlink/?LinkId=301656)">How to Configure Hardware Inventory for a Site</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7dd36-117">根據您所使用的 Configuration Manager 版本，會啟用下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="7dd36-117">One of the following is enabled, depending on the version of Configuration Manager that you are using:</span></span></p>
<ul>
<li><p><span data-ttu-id="7dd36-118">合規性設定-（系統中心 2012 Configuration Manager）</span><span class="sxs-lookup"><span data-stu-id="7dd36-118">Compliance Settings - (System Center 2012 Configuration Manager)</span></span></p></li>
<li><p><span data-ttu-id="7dd36-119">所需的建構管理（DCM）用戶端代理程式–（Configuration Manager 2007）</span><span class="sxs-lookup"><span data-stu-id="7dd36-119">Desired Configuration Management (DCM) Client Agent – (Configuration Manager 2007)</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="7dd36-120">針對 System Center 2012 Configuration Manager，請參閱 <a href="https://go.microsoft.com/fwlink/?LinkId=301687" data-raw-source="[Configuring Compliance Settings in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301687)"> 在 Configuration Manager 中設定合規性設定 </a> 。</span><span class="sxs-lookup"><span data-stu-id="7dd36-120">For System Center 2012 Configuration Manager, see <a href="https://go.microsoft.com/fwlink/?LinkId=301687" data-raw-source="[Configuring Compliance Settings in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301687)">Configuring Compliance Settings in Configuration Manager</a>.</span></span></p>
<p><span data-ttu-id="7dd36-121">針對 Configuration Manager 2007，請參閱 <a href="https://go.microsoft.com/fwlink/?LinkId=301686" data-raw-source="[Desired Configuration Management Client Agent Properties](https://go.microsoft.com/fwlink/?LinkId=301686)"> 所需的設定管理用戶端代理程式屬性 </a> 。</span><span class="sxs-lookup"><span data-stu-id="7dd36-121">For Configuration Manager 2007, see <a href="https://go.microsoft.com/fwlink/?LinkId=301686" data-raw-source="[Desired Configuration Management Client Agent Properties](https://go.microsoft.com/fwlink/?LinkId=301686)">Desired Configuration Management Client Agent Properties</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="7dd36-122">[Configuration Manager] 中定義了 [報表服務點]。</span><span class="sxs-lookup"><span data-stu-id="7dd36-122">A reporting services point is defined in Configuration Manager.</span></span> <span data-ttu-id="7dd36-123">SQL Server Reporting Services （SSRS）所需。</span><span class="sxs-lookup"><span data-stu-id="7dd36-123">Required for SQL Server Reporting Services (SSRS).</span></span></p></td>
<td align="left"><p><span data-ttu-id="7dd36-124">針對 System Center 2012 Configuration Manager，請參閱 <a href="https://go.microsoft.com/fwlink/?LinkId=301689" data-raw-source="[Prerequisites for Reporting in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301689)"> Configuration manager 中的報告先決條件 </a> 。</span><span class="sxs-lookup"><span data-stu-id="7dd36-124">For System Center 2012 Configuration Manager, see <a href="https://go.microsoft.com/fwlink/?LinkId=301689" data-raw-source="[Prerequisites for Reporting in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301689)">Prerequisites for Reporting in Configuration Manager</a>.</span></span></p>
<p><span data-ttu-id="7dd36-125">如需 Configuration Manager 2007 的詳細說明，請參閱 <a href="https://go.microsoft.com/fwlink/?LinkId=301688" data-raw-source="[How to Create a Reporting Services Point for SQL Reporting Services](https://go.microsoft.com/fwlink/?LinkId=301688)"> 如何為 SQL Reporting Services 建立 Reporting Services 點 </a> 。</span><span class="sxs-lookup"><span data-stu-id="7dd36-125">For Configuration Manager 2007, see <a href="https://go.microsoft.com/fwlink/?LinkId=301688" data-raw-source="[How to Create a Reporting Services Point for SQL Reporting Services](https://go.microsoft.com/fwlink/?LinkId=301688)">How to Create a Reporting Services Point for SQL Reporting Services</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7dd36-126">Configuration Manager 2007 需要 Microsoft .NET Framework 2。0</span><span class="sxs-lookup"><span data-stu-id="7dd36-126">Configuration Manager 2007 requires Microsoft .NET Framework 2.0</span></span></p></td>
<td align="left"><p><span data-ttu-id="7dd36-127">Configuration Manager 2007 中所需的建構管理（DCM）用戶端代理程式需要 .NET Framework 2.0 來報告合規性。</span><span class="sxs-lookup"><span data-stu-id="7dd36-127">The Desired Configuration Management (DCM) Client Agent in Configuration Manager 2007 requires .NET Framework 2.0 to report compliance.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="7dd36-128">注意</span><span class="sxs-lookup"><span data-stu-id="7dd36-128">Note</span></span></strong><br/><p><span data-ttu-id="7dd36-129">安裝 .NET Framework 3.5 時會自動安裝 .NET Framework 2.0。</span><span class="sxs-lookup"><span data-stu-id="7dd36-129">Installing .NET Framework 3.5 automatically installs .NET Framework 2.0.</span></span></p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="7dd36-130">使用 Configuration Manager 安裝 MBAM 所需的許可權</span><span class="sxs-lookup"><span data-stu-id="7dd36-130">Required permissions to install MBAM with Configuration Manager</span></span>


<span data-ttu-id="7dd36-131">若要使用 Configuration Manager 安裝 MBAM，您必須在 Configuration Manager 中擁有具有下表所列許可權的安全性角色的系統管理使用者。</span><span class="sxs-lookup"><span data-stu-id="7dd36-131">To install MBAM with Configuration Manager, you must have an administrative user in Configuration Manager who has a security role with the minimum permissions listed in the following table.</span></span> <span data-ttu-id="7dd36-132">該表也會顯示您必須擁有的許可權（除了基本的電腦系統管理員許可權之外），才能安裝 MBAM 伺服器。</span><span class="sxs-lookup"><span data-stu-id="7dd36-132">The table also shows the rights that you must have, beyond basic computer administrator rights, to install the MBAM Server.</span></span>

**<span data-ttu-id="7dd36-133">下表中的許可權適用于這兩個版本的 Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="7dd36-133">The permissions in the following table apply to both versions of Configuration Manager.</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="7dd36-134">權限</span><span class="sxs-lookup"><span data-stu-id="7dd36-134">Permissions</span></span></th>
<th align="left"><span data-ttu-id="7dd36-135">MBAM Server 功能</span><span class="sxs-lookup"><span data-stu-id="7dd36-135">MBAM Server feature</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7dd36-136">SQL Server 實例登入伺服器角色：-dbcreator-processadmin</span><span class="sxs-lookup"><span data-stu-id="7dd36-136">SQL Server instance login server roles: - dbcreator- processadmin</span></span></p></td>
<td align="left"><p>- <span data-ttu-id="7dd36-137">復原資料庫-審核資料庫</span><span class="sxs-lookup"><span data-stu-id="7dd36-137">Recovery Database- Audit Database</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="7dd36-138">SSRS 實例許可權：-建立資料夾-發佈報表</span><span class="sxs-lookup"><span data-stu-id="7dd36-138">SSRS instance rights: - Create Folders- Publish Reports</span></span></p></td>
<td align="left"><p>- <span data-ttu-id="7dd36-139">System Center Configuration Manager 整合</span><span class="sxs-lookup"><span data-stu-id="7dd36-139">System Center Configuration Manager Integration</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="7dd36-140">System Center 2012 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="7dd36-140">System Center 2012 Configuration Manager</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="7dd36-141">權限</span><span class="sxs-lookup"><span data-stu-id="7dd36-141">Permissions</span></span></th>
<th align="left"><span data-ttu-id="7dd36-142">Configuration Manager 伺服器功能</span><span class="sxs-lookup"><span data-stu-id="7dd36-142">Configuration Manager Server feature</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7dd36-143">Configuration Manager 網站許可權：-讀取</span><span class="sxs-lookup"><span data-stu-id="7dd36-143">Configuration Manager site rights:- Read</span></span></p></td>
<td align="left"><p><span data-ttu-id="7dd36-144">System Center Configuration Manager 整合</span><span class="sxs-lookup"><span data-stu-id="7dd36-144">System Center Configuration Manager Integration</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="7dd36-145">Configuration Manager 集合許可權：-建立-刪除-已讀-修改-部署設定項目</span><span class="sxs-lookup"><span data-stu-id="7dd36-145">Configuration Manager collection rights: - Create- Delete- Read- Modify- Deploy Configuration Items</span></span></p></td>
<td align="left"><p><span data-ttu-id="7dd36-146">System Center Configuration Manager 整合</span><span class="sxs-lookup"><span data-stu-id="7dd36-146">System Center Configuration Manager Integration</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7dd36-147">Configuration Manager 設定專案許可權：-建立-刪除-已讀取</span><span class="sxs-lookup"><span data-stu-id="7dd36-147">Configuration Manager configuration item rights: - Create- Delete- Read</span></span></p></td>
<td align="left"><p><span data-ttu-id="7dd36-148">System Center Configuration Manager 整合</span><span class="sxs-lookup"><span data-stu-id="7dd36-148">System Center Configuration Manager Integration</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="7dd36-149">Configuration Manager 2007</span><span class="sxs-lookup"><span data-stu-id="7dd36-149">Configuration Manager 2007</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="7dd36-150">權限</span><span class="sxs-lookup"><span data-stu-id="7dd36-150">Permissions</span></span></th>
<th align="left"><span data-ttu-id="7dd36-151">Configuration Manager 伺服器功能</span><span class="sxs-lookup"><span data-stu-id="7dd36-151">Configuration Manager Server feature</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7dd36-152">Configuration Manager 網站許可權：-讀取</span><span class="sxs-lookup"><span data-stu-id="7dd36-152">Configuration Manager site rights:- Read</span></span></p></td>
<td align="left"><p><span data-ttu-id="7dd36-153">System Center Configuration Manager 整合</span><span class="sxs-lookup"><span data-stu-id="7dd36-153">System Center Configuration Manager Integration</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="7dd36-154">Configuration Manager 集合許可權：-建立-Delete-ReadResource</span><span class="sxs-lookup"><span data-stu-id="7dd36-154">Configuration Manager collection rights: - Create- Delete- Read- ReadResource</span></span></p></td>
<td align="left"><p><span data-ttu-id="7dd36-155">System Center Configuration Manager 整合</span><span class="sxs-lookup"><span data-stu-id="7dd36-155">System Center Configuration Manager Integration</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7dd36-156">Configuration Manager 設定項目許可權：-建立-刪除-已讀取-發佈</span><span class="sxs-lookup"><span data-stu-id="7dd36-156">Configuration Manager configuration item rights: - Create- Delete- Read- Distribute</span></span></p></td>
<td align="left"><p><span data-ttu-id="7dd36-157">System Center Configuration Manager 整合</span><span class="sxs-lookup"><span data-stu-id="7dd36-157">System Center Configuration Manager Integration</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="7dd36-158">對 mof 檔案所需的變更</span><span class="sxs-lookup"><span data-stu-id="7dd36-158">Required changes for the .mof files</span></span>


<span data-ttu-id="7dd36-159">若要讓用戶端電腦透過 MBAM Configuration Manager 報告來報告 BitLocker 合規性詳細資料，您必須編輯 System Center 2012 Configuration Manager 和 Microsoft System Center Configuration Manager 2007 的 Configuration mof 檔案和 Sms \ [_def 的 mof 檔。</span><span class="sxs-lookup"><span data-stu-id="7dd36-159">To enable the client computers to report BitLocker compliance details through the MBAM Configuration Manager reports, you have to edit the Configuration.mof file and Sms\_def.mof file for System Center 2012 Configuration Manager and Microsoft System Center Configuration Manager 2007.</span></span> <span data-ttu-id="7dd36-160">如需相關指示，請參閱[僅適用于 Configuration Manager 整合拓朴的 MBAM 2.5 Server 先決條件](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="7dd36-160">For instructions, see [MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md).</span></span>



## <span data-ttu-id="7dd36-161">相關主題</span><span class="sxs-lookup"><span data-stu-id="7dd36-161">Related topics</span></span>


[<span data-ttu-id="7dd36-162">獨立拓撲與 Configuration Manager 整合拓撲的 MBAM 2.5 伺服器必要條件</span><span class="sxs-lookup"><span data-stu-id="7dd36-162">MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies</span></span>](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)

[<span data-ttu-id="7dd36-163">僅適用於 Configuration Manager 整合拓撲的 MBAM 2.5 伺服器必要條件</span><span class="sxs-lookup"><span data-stu-id="7dd36-163">MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology</span></span>](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)



## <span data-ttu-id="7dd36-164">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="7dd36-164">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="7dd36-165">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="7dd36-165">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="7dd36-166">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="7dd36-166">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





