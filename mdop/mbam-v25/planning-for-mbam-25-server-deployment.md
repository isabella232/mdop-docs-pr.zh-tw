---
title: MBAM 2.5 伺服器部署規劃
description: MBAM 2.5 伺服器部署規劃
author: dansimp
ms.assetid: 88774c89-31c8-4eb8-a845-a00bbec8c870
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d2ecb510fab821118ce210577f9ffb83c39be050
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811619"
---
# <span data-ttu-id="cb3f6-103">MBAM 2.5 伺服器部署規劃</span><span class="sxs-lookup"><span data-stu-id="cb3f6-103">Planning for MBAM 2.5 Server Deployment</span></span>


<span data-ttu-id="cb3f6-104">本主題列出您針對 MBAM 獨立版與 Configuration Manager 拓撲所部署的功能，並列出您需要的部署順序。</span><span class="sxs-lookup"><span data-stu-id="cb3f6-104">This topic lists the features that you deploy for the MBAM Stand-alone and Configuration Manager topologies and lists the order in which you need to deploy them.</span></span> <span data-ttu-id="cb3f6-105">每個拓朴都有建議的配置。</span><span class="sxs-lookup"><span data-stu-id="cb3f6-105">There is a recommended configuration for each topology.</span></span> <span data-ttu-id="cb3f6-106">不過，您可以根據您的可伸縮性需求，在不同的配置和多個伺服器上設定 MBAM 伺服器資料庫和功能。</span><span class="sxs-lookup"><span data-stu-id="cb3f6-106">However, you can configure MBAM server databases and features in different configurations and across multiple servers, depending on your scalability requirements.</span></span>

## <span data-ttu-id="cb3f6-107">兩種拓撲的重要規劃考慮</span><span class="sxs-lookup"><span data-stu-id="cb3f6-107">Important planning considerations for both topologies</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="cb3f6-108">考量</span><span class="sxs-lookup"><span data-stu-id="cb3f6-108">Considerations</span></span></th>
<th align="left"><span data-ttu-id="cb3f6-109">詳細資料或用途</span><span class="sxs-lookup"><span data-stu-id="cb3f6-109">Details or purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="cb3f6-110">開始進行部署之前，請先檢查下列專案：</span><span class="sxs-lookup"><span data-stu-id="cb3f6-110">Review the following before you start the deployment:</span></span></p>
<ul>
<li><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)"><span data-ttu-id="cb3f6-111">獨立拓撲與 Configuration Manager 整合拓撲的 MBAM 2.5 伺服器必要條件</span><span class="sxs-lookup"><span data-stu-id="cb3f6-111">MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies</span></span></a></p></li>
<li><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)"><span data-ttu-id="cb3f6-112">MBAM 2.5 支援的組態</span><span class="sxs-lookup"><span data-stu-id="cb3f6-112">MBAM 2.5 Supported Configurations</span></span></a></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="cb3f6-113">每個 MBAM 功能都有特定的先決條件，您必須先滿足這些先決條件，才能開始 MBAM 安裝。</span><span class="sxs-lookup"><span data-stu-id="cb3f6-113">Each MBAM feature has specific prerequisites that must be met before you start the MBAM installation.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="cb3f6-114">MBAM 中的 BitLocker 復原金鑰會在單一使用後到期。</span><span class="sxs-lookup"><span data-stu-id="cb3f6-114">BitLocker recovery keys in MBAM expire after a single use.</span></span></p></td>
<td align="left"><p><span data-ttu-id="cb3f6-115">單一用途代表已透過管理和監控網站（又稱為說明服務台）、自助入口網站或使用 <strong> MbamBitLockerRecoveryKey Windows PowerShell Cmdlet 來檢索復原金鑰 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="cb3f6-115">A single use means that the recovery key has been retrieved through the Administration and Monitoring Website (also known as Help Desk), Self-Service Portal, or by using the Get-<strong>MbamBitLockerRecoveryKey</strong> Windows PowerShell cmdlet.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="cb3f6-116">追蹤設定每個功能的電腦名稱稱。</span><span class="sxs-lookup"><span data-stu-id="cb3f6-116">Keep track of the names of the computers on which you configure each feature.</span></span> <span data-ttu-id="cb3f6-117">您將會在整個配置程式中使用此資訊。</span><span class="sxs-lookup"><span data-stu-id="cb3f6-117">You will use this information throughout the configuration process.</span></span></p></td>
<td align="left"><p><span data-ttu-id="cb3f6-118">您可能會想要使用 <a href="mbam-25-deployment-checklist.md" data-raw-source="[MBAM 2.5 Deployment Checklist](mbam-25-deployment-checklist.md)"> MBAM 2.5 部署檢查清單 </a> 來達到此目的。</span><span class="sxs-lookup"><span data-stu-id="cb3f6-118">You may want to use the <a href="mbam-25-deployment-checklist.md" data-raw-source="[MBAM 2.5 Deployment Checklist](mbam-25-deployment-checklist.md)">MBAM 2.5 Deployment Checklist</a> for this purpose.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="cb3f6-119">只設定 MDOP MBAM （BitLocker 管理）節點中的 [群組原則] 設定。</span><span class="sxs-lookup"><span data-stu-id="cb3f6-119">Configure only the Group Policy settings in the MDOP MBAM (BitLocker Management) node.</span></span> <span data-ttu-id="cb3f6-120">請勿變更 BitLocker 磁片磁碟機加密節點中的群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="cb3f6-120">Do not change the Group Policy settings in the BitLocker Drive Encryption node.</span></span></p></td>
<td align="left"><p><span data-ttu-id="cb3f6-121">如果您在 BitLocker 磁片磁碟機加密節點中變更群組原則設定，MBAM 將無法運作。</span><span class="sxs-lookup"><span data-stu-id="cb3f6-121">If you change the Group Policy settings in the BitLocker Drive Encryption node, MBAM will not work.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="planning-for-mbam-server-deployment---stand-alone-topology"></a><span data-ttu-id="cb3f6-122">規劃 MBAM Server 部署-獨立拓朴</span><span class="sxs-lookup"><span data-stu-id="cb3f6-122">Planning for MBAM Server deployment – Stand-alone topology</span></span>


<span data-ttu-id="cb3f6-123">若是獨立拓朴，建議在生產環境中使用雙伺服器設定，雖然您可以使用三至四個伺服器的設定。</span><span class="sxs-lookup"><span data-stu-id="cb3f6-123">For the Stand-alone topology, a two-server configuration is recommended for production environments, although configurations of three to four servers can be used.</span></span>

<span data-ttu-id="cb3f6-124">MBAM 獨立拓朴的伺服器基礎結構包含下列功能，這些功能必須按照所列的順序進行設定：</span><span class="sxs-lookup"><span data-stu-id="cb3f6-124">The Server infrastructure for the MBAM Stand-alone topology contains the following features, which must be configured in the order listed:</span></span>

1.  <span data-ttu-id="cb3f6-125">資料庫（合規性與審核資料庫及復原資料庫）</span><span class="sxs-lookup"><span data-stu-id="cb3f6-125">Databases (Compliance and Audit Database and Recovery Database)</span></span>

2.  <span data-ttu-id="cb3f6-126">報告</span><span class="sxs-lookup"><span data-stu-id="cb3f6-126">Reports</span></span>

3.  <span data-ttu-id="cb3f6-127">Web 應用程式（以及其對應的 web 服務）</span><span class="sxs-lookup"><span data-stu-id="cb3f6-127">Web applications (and their corresponding web services)</span></span>

    -   <span data-ttu-id="cb3f6-128">管理和監控網站</span><span class="sxs-lookup"><span data-stu-id="cb3f6-128">Administration and Monitoring Website</span></span>

    -   <span data-ttu-id="cb3f6-129">自助服務入口網站</span><span class="sxs-lookup"><span data-stu-id="cb3f6-129">Self-Service Portal</span></span>

<span data-ttu-id="cb3f6-130">如需這些功能的描述，請參閱[含獨立拓朴之 MBAM 2.5 的高層次架構](high-level-architecture-of-mbam-25-with-stand-alone-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="cb3f6-130">For a description of these features, see [High-Level Architecture of MBAM 2.5 with Stand-alone Topology](high-level-architecture-of-mbam-25-with-stand-alone-topology.md).</span></span>

## <a href="" id="planning-for-mbam-server-deployment---configuration-manager-topology"></a><span data-ttu-id="cb3f6-131">規劃 MBAM Server 部署-Configuration Manager 拓撲</span><span class="sxs-lookup"><span data-stu-id="cb3f6-131">Planning for MBAM Server deployment – Configuration Manager topology</span></span>


<span data-ttu-id="cb3f6-132">針對 Configuration Manager 整合拓朴，雖然您可以使用其他伺服器的設定，但針對生產環境建議使用三伺服器配置。</span><span class="sxs-lookup"><span data-stu-id="cb3f6-132">For the Configuration Manager Integration topology, a three-server configuration is recommended for production environments, although configurations of additional servers can be used.</span></span>

<span data-ttu-id="cb3f6-133">MBAM Configuration Manager 拓撲結構的伺服器基礎結構包含下列功能，這些功能必須以所列的順序進行設定或執行：</span><span class="sxs-lookup"><span data-stu-id="cb3f6-133">The Server infrastructure for the MBAM Configuration Manager topology contains the following features, which must be configured or performed in the order listed:</span></span>

1.  <span data-ttu-id="cb3f6-134">資料庫（合規性與審核資料庫及復原資料庫）</span><span class="sxs-lookup"><span data-stu-id="cb3f6-134">Databases (Compliance and Audit Database and Recovery Database)</span></span>

2.  <span data-ttu-id="cb3f6-135">報告</span><span class="sxs-lookup"><span data-stu-id="cb3f6-135">Reports</span></span>

3.  <span data-ttu-id="cb3f6-136">Web 應用程式（以及其對應的 web 服務）</span><span class="sxs-lookup"><span data-stu-id="cb3f6-136">Web applications (and their corresponding web services)</span></span>

    -   <span data-ttu-id="cb3f6-137">管理和監控網站</span><span class="sxs-lookup"><span data-stu-id="cb3f6-137">Administration and Monitoring Website</span></span>

    -   <span data-ttu-id="cb3f6-138">自助服務入口網站</span><span class="sxs-lookup"><span data-stu-id="cb3f6-138">Self-Service Portal</span></span>

4.  <span data-ttu-id="cb3f6-139">System Center Configuration Manager 整合</span><span class="sxs-lookup"><span data-stu-id="cb3f6-139">System Center Configuration Manager Integration</span></span>

<span data-ttu-id="cb3f6-140">如需這些功能的描述，請參閱[含 Configuration Manager 整合拓朴的 MBAM 2.5 高層架構](high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="cb3f6-140">For a description of these features, see [High-Level Architecture of MBAM 2.5 with Configuration Manager Integration Topology](high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology.md).</span></span>



## <span data-ttu-id="cb3f6-141">相關主題</span><span class="sxs-lookup"><span data-stu-id="cb3f6-141">Related topics</span></span>


[<span data-ttu-id="cb3f6-142">規劃部署 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="cb3f6-142">Planning to Deploy MBAM 2.5</span></span>](planning-to-deploy-mbam-25.md)

[<span data-ttu-id="cb3f6-143">部署 MBAM 2.5 伺服器基礎結構</span><span class="sxs-lookup"><span data-stu-id="cb3f6-143">Deploying the MBAM 2.5 Server Infrastructure</span></span>](deploying-the-mbam-25-server-infrastructure.md)

 

## <span data-ttu-id="cb3f6-144">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="cb3f6-144">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="cb3f6-145">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="cb3f6-145">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="cb3f6-146">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="cb3f6-146">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





