---
title: MBAM 2.5 規劃檢查清單
description: MBAM 2.5 規劃檢查清單
author: dansimp
ms.assetid: ffe11eb8-44db-4886-8300-6dffec8bcfa4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 505f2890d67f36056ab5bb87df2a894473cd3306
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811817"
---
# <span data-ttu-id="8d58b-103">MBAM 2.5 規劃檢查清單</span><span class="sxs-lookup"><span data-stu-id="8d58b-103">MBAM 2.5 Planning Checklist</span></span>


<span data-ttu-id="8d58b-104">您可以使用下列檢查清單，協助您為 Microsoft BitLocker 管理和監控（MBAM）部署準備您的計算環境。</span><span class="sxs-lookup"><span data-stu-id="8d58b-104">You can use the following checklists to help you prepare your computing environment for the Microsoft BitLocker Administration and Monitoring (MBAM) deployment.</span></span> <span data-ttu-id="8d58b-105">在規劃部署時，檢查清單會提供一個要考慮的高層次專案清單。</span><span class="sxs-lookup"><span data-stu-id="8d58b-105">The checklists provide a high-level list of items to consider when planning the deployment.</span></span> <span data-ttu-id="8d58b-106">獨立拓朴與 Configuration Manager 整合拓朴有個別的檢查清單。</span><span class="sxs-lookup"><span data-stu-id="8d58b-106">There are separate checklists for the Stand-alone topology and the Configuration Manager Integration topology.</span></span> <span data-ttu-id="8d58b-107">您可能會想要將所需的檢查清單複製到試算表中，並自訂它供您使用。</span><span class="sxs-lookup"><span data-stu-id="8d58b-107">You might want to copy the desired checklist into a spreadsheet and customize it for your use.</span></span>

**<span data-ttu-id="8d58b-108">規劃 MBAM 部署的檢查清單</span><span class="sxs-lookup"><span data-stu-id="8d58b-108">Planning checklist for an MBAM deployment</span></span>**

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left"><span data-ttu-id="8d58b-109">工作</span><span class="sxs-lookup"><span data-stu-id="8d58b-109">Task</span></span></th>
<th align="left"><span data-ttu-id="8d58b-110">參考資料</span><span class="sxs-lookup"><span data-stu-id="8d58b-110">References</span></span></th>
<th align="left"><span data-ttu-id="8d58b-111">附註</span><span class="sxs-lookup"><span data-stu-id="8d58b-111">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="8d58b-112">&quot; &quot; 開始進行部署規劃前，請先複習取得入門資訊以瞭解產品。</span><span class="sxs-lookup"><span data-stu-id="8d58b-112">Review the &quot;Getting started&quot; information to understand the product before you start deployment planning.</span></span></p></td>
<td align="left"><p><a href="getting-started-with-mbam-25.md" data-raw-source="[Getting Started with MBAM 2.5](getting-started-with-mbam-25.md)"><span data-ttu-id="8d58b-113">開始使用 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="8d58b-113">Getting Started with MBAM 2.5</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="8d58b-114">針對 MBAM 部署查看建議的高層次架構。</span><span class="sxs-lookup"><span data-stu-id="8d58b-114">Review the recommended high-level architecture for an MBAM deployment.</span></span> <span data-ttu-id="8d58b-115">您可能也想要查看 MBAM 部署的個別元件（資料庫、網站、報表）的圖例和描述。</span><span class="sxs-lookup"><span data-stu-id="8d58b-115">You might also want to review an illustration and description of the individual parts (databases, websites, Reports) of an MBAM deployment.</span></span></p></td>
<td align="left"><p><a href="high-level-architecture-for-mbam-25.md" data-raw-source="[High-Level Architecture for MBAM 2.5](high-level-architecture-for-mbam-25.md)"><span data-ttu-id="8d58b-116">MBAM 2.5 的概要架構</span><span class="sxs-lookup"><span data-stu-id="8d58b-116">High-Level Architecture for MBAM 2.5</span></span></a></p>
<p><a href="illustrated-features-of-an-mbam-25-deployment.md" data-raw-source="[Illustrated Features of an MBAM 2.5 Deployment](illustrated-features-of-an-mbam-25-deployment.md)"><span data-ttu-id="8d58b-117">MBAM 2.5 部署的功能圖例</span><span class="sxs-lookup"><span data-stu-id="8d58b-117">Illustrated Features of an MBAM 2.5 Deployment</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="8d58b-118">複習並完成 MBAM 獨立與 Configuration Manager 整合拓朴的先決條件。</span><span class="sxs-lookup"><span data-stu-id="8d58b-118">Review and complete the prerequisites for the MBAM Stand-alone and Configuration Manager Integration topologies.</span></span></p></td>
<td align="left"><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)"><span data-ttu-id="8d58b-119">獨立拓撲與 Configuration Manager 整合拓撲的 MBAM 2.5 伺服器必要條件</span><span class="sxs-lookup"><span data-stu-id="8d58b-119">MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="8d58b-120">如果您打算使用 Configuration Manager 整合拓撲，請完成隻適用于此拓撲的其他先決條件。</span><span class="sxs-lookup"><span data-stu-id="8d58b-120">If you plan to use the Configuration Manager Integration topology, complete the additional prerequisites that apply only to this topology.</span></span></p></td>
<td align="left"><p><a href="mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md" data-raw-source="[MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)"><span data-ttu-id="8d58b-121">僅適用於 Configuration Manager 整合拓撲的 MBAM 2.5 伺服器必要條件</span><span class="sxs-lookup"><span data-stu-id="8d58b-121">MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="8d58b-122">審查並滿足 MBAM 用戶端的 MBAM 2.5 先決條件。</span><span class="sxs-lookup"><span data-stu-id="8d58b-122">Review and meet the MBAM 2.5 prerequisites for the MBAM Client.</span></span></p></td>
<td align="left"><p><a href="prerequisites-for-mbam-25-clients.md" data-raw-source="[Prerequisites for MBAM 2.5 Clients](prerequisites-for-mbam-25-clients.md)"><span data-ttu-id="8d58b-123">MBAM 2.5 用戶端的必要條件</span><span class="sxs-lookup"><span data-stu-id="8d58b-123">Prerequisites for MBAM 2.5 Clients</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="8d58b-124">規劃及設定 MBAM 群組原則需求。</span><span class="sxs-lookup"><span data-stu-id="8d58b-124">Plan for and configure MBAM Group Policy requirements.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-25-group-policy-requirements.md" data-raw-source="[Planning for MBAM 2.5 Group Policy Requirements](planning-for-mbam-25-group-policy-requirements.md)"><span data-ttu-id="8d58b-125">MBAM 2.5 群組原則需求規劃</span><span class="sxs-lookup"><span data-stu-id="8d58b-125">Planning for MBAM 2.5 Group Policy Requirements</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="8d58b-126">規劃及建立必要的 ActiveDirectoryDomainServices 安全性群組。</span><span class="sxs-lookup"><span data-stu-id="8d58b-126">Plan for and create the necessary ActiveDirectoryDomainServices security groups.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-25-groups-and-accounts.md" data-raw-source="[Planning for MBAM 2.5 Groups and Accounts](planning-for-mbam-25-groups-and-accounts.md)"><span data-ttu-id="8d58b-127">MBAM 2.5 群組與帳戶規劃</span><span class="sxs-lookup"><span data-stu-id="8d58b-127">Planning for MBAM 2.5 Groups and Accounts</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="8d58b-128">規劃如何保護 MBAM 網站的安全。</span><span class="sxs-lookup"><span data-stu-id="8d58b-128">Plan how you will secure the MBAM websites.</span></span></p></td>
<td align="left"><p><a href="planning-how-to-secure-the-mbam-websites.md" data-raw-source="[Planning How to Secure the MBAM Websites](planning-how-to-secure-the-mbam-websites.md)"><span data-ttu-id="8d58b-129">如何保護 MBAM 網站的規劃</span><span class="sxs-lookup"><span data-stu-id="8d58b-129">Planning How to Secure the MBAM Websites</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="8d58b-130">請參閱 MBAM 支援的設定，以確保您的硬體符合安裝系統的需求。</span><span class="sxs-lookup"><span data-stu-id="8d58b-130">Review the MBAM Supported Configurations to ensure that your hardware meets the installation system requirements.</span></span></p></td>
<td align="left"><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)"><span data-ttu-id="8d58b-131">MBAM 2.5 支援的組態</span><span class="sxs-lookup"><span data-stu-id="8d58b-131">MBAM 2.5 Supported Configurations</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="8d58b-132">請參閱部署 MBAM 伺服器功能的考慮。</span><span class="sxs-lookup"><span data-stu-id="8d58b-132">Review the considerations for deploying the MBAM Server features.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-25-server-deployment.md" data-raw-source="[Planning for MBAM 2.5 Server Deployment](planning-for-mbam-25-server-deployment.md)"><span data-ttu-id="8d58b-133">MBAM 2.5 伺服器部署規劃</span><span class="sxs-lookup"><span data-stu-id="8d58b-133">Planning for MBAM 2.5 Server Deployment</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="8d58b-134">請參閱部署 MBAM 用戶端的考慮。</span><span class="sxs-lookup"><span data-stu-id="8d58b-134">Review the considerations for deploying the MBAM Client.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-25-client-deployment.md" data-raw-source="[Planning for MBAM 2.5 Client Deployment](planning-for-mbam-25-client-deployment.md)"><span data-ttu-id="8d58b-135">MBAM 2.5 用戶端部署規劃</span><span class="sxs-lookup"><span data-stu-id="8d58b-135">Planning for MBAM 2.5 Client Deployment</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="8d58b-136">查看在高可用性配置中部署 MBAM 的需求和步驟。</span><span class="sxs-lookup"><span data-stu-id="8d58b-136">Review the requirements and steps to deploy MBAM in a highly available configuration.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-25-high-availability.md" data-raw-source="[Planning for MBAM 2.5 High Availability](planning-for-mbam-25-high-availability.md)"><span data-ttu-id="8d58b-137">MBAM 2.5 高可用性規劃</span><span class="sxs-lookup"><span data-stu-id="8d58b-137">Planning for MBAM 2.5 High Availability</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="8d58b-138">請參閱適用于受信任的平臺模組、記錄檔案和透明資料加密的 MBAM 安全性考慮。</span><span class="sxs-lookup"><span data-stu-id="8d58b-138">Review the MBAM security considerations that pertain to the Trusted Platform Module, log files, and transparent data encryption.</span></span></p></td>
<td align="left"><p><a href="mbam-25-security-considerations.md" data-raw-source="[MBAM 2.5 Security Considerations](mbam-25-security-considerations.md)"><span data-ttu-id="8d58b-139">MBAM 2.5 安全性考量</span><span class="sxs-lookup"><span data-stu-id="8d58b-139">MBAM 2.5 Security Considerations</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="8d58b-140">您也可以在測試環境中，查看評估 MBAM 的步驟。</span><span class="sxs-lookup"><span data-stu-id="8d58b-140">Optionally, review the steps to evaluate MBAM in a test environment.</span></span></p></td>
<td align="left"><p><a href="evaluating-mbam-25-in-a-test-environment.md" data-raw-source="[Evaluating MBAM 2.5 in a Test Environment](evaluating-mbam-25-in-a-test-environment.md)"><span data-ttu-id="8d58b-141">在測試環境中評估 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="8d58b-141">Evaluating MBAM 2.5 in a Test Environment</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>

 


## <span data-ttu-id="8d58b-142">相關主題</span><span class="sxs-lookup"><span data-stu-id="8d58b-142">Related topics</span></span>


[<span data-ttu-id="8d58b-143">MBAM 2.5 規劃</span><span class="sxs-lookup"><span data-stu-id="8d58b-143">Planning for MBAM 2.5</span></span>](planning-for-mbam-25.md)

 

 
## <span data-ttu-id="8d58b-144">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="8d58b-144">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="8d58b-145">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="8d58b-145">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="8d58b-146">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="8d58b-146">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>




