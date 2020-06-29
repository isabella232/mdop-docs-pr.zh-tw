---
title: MBAM 2.0 部署檢查清單
description: MBAM 2.0 部署檢查清單
author: dansimp
ms.assetid: 7905d31d-f21c-4683-b9c4-95b815e08fab
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5d8d0ce1a3ff48d4bf2f84e61b4a578b170264a0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811756"
---
# <span data-ttu-id="39cdf-103">MBAM 2.0 部署檢查清單</span><span class="sxs-lookup"><span data-stu-id="39cdf-103">MBAM 2.0 Deployment Checklist</span></span>


<span data-ttu-id="39cdf-104">此檢查清單可用來協助您在 Microsoft BitLocker 管理和監控（MBAM）部署中使用獨立拓撲。</span><span class="sxs-lookup"><span data-stu-id="39cdf-104">This checklist can be used to help you during Microsoft BitLocker Administration and Monitoring (MBAM) deployment with a Stand-alone topology.</span></span>

**<span data-ttu-id="39cdf-105">注意</span><span class="sxs-lookup"><span data-stu-id="39cdf-105">Note</span></span>**  
<span data-ttu-id="39cdf-106">此檢查清單概述在部署 Microsoft BitLocker 管理和監視功能時，建議的步驟和要考慮的高層次專案清單。</span><span class="sxs-lookup"><span data-stu-id="39cdf-106">This checklist outlines the recommended steps and a high-level list of items to consider when deploying Microsoft BitLocker Administration and Monitoring features.</span></span> <span data-ttu-id="39cdf-107">建議您將此檢查清單複製到試算表程式中，然後將它自訂為供您使用。</span><span class="sxs-lookup"><span data-stu-id="39cdf-107">It is recommended that you copy this checklist into a spreadsheet program and customize it for your use.</span></span>



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
<th align="left"><span data-ttu-id="39cdf-108">工作</span><span class="sxs-lookup"><span data-stu-id="39cdf-108">Task</span></span></th>
<th align="left"><span data-ttu-id="39cdf-109">參考資料</span><span class="sxs-lookup"><span data-stu-id="39cdf-109">References</span></span></th>
<th align="left"><span data-ttu-id="39cdf-110">附註</span><span class="sxs-lookup"><span data-stu-id="39cdf-110">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="39cdf-111">完成規劃階段以準備 MBAM 部署的計算環境。</span><span class="sxs-lookup"><span data-stu-id="39cdf-111">Complete the planning phase to prepare the computing environment for MBAM deployment.</span></span></p></td>
<td align="left"><p><a href="mbam-20-planning-checklist-mbam-2.md" data-raw-source="[MBAM 2.0 Planning Checklist](mbam-20-planning-checklist-mbam-2.md)"><span data-ttu-id="39cdf-112">MBAM 2.0 規劃檢查清單</span><span class="sxs-lookup"><span data-stu-id="39cdf-112">MBAM 2.0 Planning Checklist</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="39cdf-113">查看 MBAM 支援的設定資訊，確認已選取的用戶端和伺服器電腦支援 MBAM 功能安裝。</span><span class="sxs-lookup"><span data-stu-id="39cdf-113">Review the MBAM supported configurations information to make sure selected client and server computers are supported for MBAM feature installation.</span></span></p></td>
<td align="left"><p><a href="mbam-20-supported-configurations-mbam-2.md" data-raw-source="[MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md)"><span data-ttu-id="39cdf-114">MBAM 2.0 支援的組態</span><span class="sxs-lookup"><span data-stu-id="39cdf-114">MBAM 2.0 Supported Configurations</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="39cdf-115">執行 MBAM 安裝程式，以下列順序部署 MBAM 伺服器功能：</span><span class="sxs-lookup"><span data-stu-id="39cdf-115">Run MBAM Setup to deploy MBAM Server features in the following order:</span></span></p>
<ol>
<li><p><span data-ttu-id="39cdf-116">復原資料庫</span><span class="sxs-lookup"><span data-stu-id="39cdf-116">Recovery Database</span></span></p></li>
<li><p><span data-ttu-id="39cdf-117">合規性和審核資料庫</span><span class="sxs-lookup"><span data-stu-id="39cdf-117">Compliance and Audit Database</span></span></p></li>
<li><p><span data-ttu-id="39cdf-118">合規性審核與報告</span><span class="sxs-lookup"><span data-stu-id="39cdf-118">Compliance Audit and Reports</span></span></p></li>
<li><p><span data-ttu-id="39cdf-119">自助服務伺服器</span><span class="sxs-lookup"><span data-stu-id="39cdf-119">Self-Service Server</span></span></p></li>
<li><p><span data-ttu-id="39cdf-120">管理和監控伺服器</span><span class="sxs-lookup"><span data-stu-id="39cdf-120">Administration and Monitoring Server</span></span></p></li>
<li><p><span data-ttu-id="39cdf-121">MBAM 群組原則範本</span><span class="sxs-lookup"><span data-stu-id="39cdf-121">MBAM Group Policy template</span></span></p></li>
</ol>
<div class="alert">
<strong><span data-ttu-id="39cdf-122">注意</span><span class="sxs-lookup"><span data-stu-id="39cdf-122">Note</span></span></strong><br/><p><span data-ttu-id="39cdf-123">追蹤每個安裝功能的伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="39cdf-123">Keep track of the names of the servers each feature is installed on.</span></span> <span data-ttu-id="39cdf-124">此資訊將會在整個安裝過程中使用。</span><span class="sxs-lookup"><span data-stu-id="39cdf-124">This information will be used throughout the installation process.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><a href="deploying-the-mbam-20-server-infrastructure-mbam-2.md" data-raw-source="[Deploying the MBAM 2.0 Server Infrastructure](deploying-the-mbam-20-server-infrastructure-mbam-2.md)"><span data-ttu-id="39cdf-125">部署 MBAM 2.0 伺服器基礎結構</span><span class="sxs-lookup"><span data-stu-id="39cdf-125">Deploying the MBAM 2.0 Server Infrastructure</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="39cdf-126">將在規劃階段建立的 Active Directory 網域服務安全性群組新增至適當的本機 MBAM 伺服器功能系統管理員群組（適用于適當的伺服器）。</span><span class="sxs-lookup"><span data-stu-id="39cdf-126">Add Active Directory Domain Services security groups created during the planning phase to the appropriate local MBAM Server feature administrators groups on appropriate servers.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-20-administrator-roles-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Administrator Roles](planning-for-mbam-20-administrator-roles-mbam-2.md)"><span data-ttu-id="39cdf-127">規劃 MBAM 2.0 系統管理員角色 </a> ，以及 <a href="how-to-manage-mbam-administrator-roles-mbam-2.md" data-raw-source="[How to Manage MBAM Administrator Roles](how-to-manage-mbam-administrator-roles-mbam-2.md)"> 如何管理 MBAM 系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="39cdf-127">Planning for MBAM 2.0 Administrator Roles</a> and <a href="how-to-manage-mbam-administrator-roles-mbam-2.md" data-raw-source="[How to Manage MBAM Administrator Roles](how-to-manage-mbam-administrator-roles-mbam-2.md)">How to Manage MBAM Administrator Roles</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="39cdf-128">建立及部署所需的 MBAM 群組原則物件。</span><span class="sxs-lookup"><span data-stu-id="39cdf-128">Create and deploy required MBAM Group Policy Objects.</span></span></p></td>
<td align="left"><p><a href="deploying-mbam-20-group-policy-objects-mbam-2.md" data-raw-source="[Deploying MBAM 2.0 Group Policy Objects](deploying-mbam-20-group-policy-objects-mbam-2.md)"><span data-ttu-id="39cdf-129">部署 MBAM 2.0 群組原則物件</span><span class="sxs-lookup"><span data-stu-id="39cdf-129">Deploying MBAM 2.0 Group Policy Objects</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="39cdf-130">部署 MBAM 用戶端軟體。</span><span class="sxs-lookup"><span data-stu-id="39cdf-130">Deploy the MBAM Client software.</span></span></p></td>
<td align="left"><p><a href="deploying-the-mbam-20-client-mbam-2.md" data-raw-source="[Deploying the MBAM 2.0 Client](deploying-the-mbam-20-client-mbam-2.md)"><span data-ttu-id="39cdf-131">部署 MBAM 2.0 用戶端</span><span class="sxs-lookup"><span data-stu-id="39cdf-131">Deploying the MBAM 2.0 Client</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="39cdf-132">相關主題</span><span class="sxs-lookup"><span data-stu-id="39cdf-132">Related topics</span></span>


[<span data-ttu-id="39cdf-133">部署 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="39cdf-133">Deploying MBAM 2.0</span></span>](deploying-mbam-20-mbam-2.md)









