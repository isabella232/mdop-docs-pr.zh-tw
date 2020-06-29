---
title: MBAM 1.0 部署檢查清單
description: MBAM 1.0 部署檢查清單
author: dansimp
ms.assetid: 7e00be23-36a0-4b0f-8663-3c4f2c71546d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 96725183af2cb4e3d86d3f42973452c598497773
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800118"
---
# <span data-ttu-id="f3db9-103">MBAM 1.0 部署檢查清單</span><span class="sxs-lookup"><span data-stu-id="f3db9-103">MBAM 1.0 Deployment Checklist</span></span>


<span data-ttu-id="f3db9-104">此檢查清單旨在協助您部署 Microsoft BitLocker 管理和監控（MBAM）。</span><span class="sxs-lookup"><span data-stu-id="f3db9-104">This checklist is designed to facilitate your deployment of Microsoft BitLocker Administration and Monitoring (MBAM).</span></span>

**<span data-ttu-id="f3db9-105">注意</span><span class="sxs-lookup"><span data-stu-id="f3db9-105">Note</span></span>**  
<span data-ttu-id="f3db9-106">此檢查清單概括了建議的步驟，並提供在您部署 MBAM 功能時要考慮的專案的高層層次清單。</span><span class="sxs-lookup"><span data-stu-id="f3db9-106">This checklist outlines the recommended steps and provides a high-level list of items to consider when you deploy the MBAM features.</span></span> <span data-ttu-id="f3db9-107">我們建議您將此檢查清單複製到試算表程式，並針對您的特定需求來自訂它。</span><span class="sxs-lookup"><span data-stu-id="f3db9-107">We recommend that you copy this checklist into a spreadsheet program and customize it for your specific needs.</span></span>



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
<th align="left"><span data-ttu-id="f3db9-108">工作</span><span class="sxs-lookup"><span data-stu-id="f3db9-108">Task</span></span></th>
<th align="left"><span data-ttu-id="f3db9-109">參考資料</span><span class="sxs-lookup"><span data-stu-id="f3db9-109">References</span></span></th>
<th align="left"><span data-ttu-id="f3db9-110">附註</span><span class="sxs-lookup"><span data-stu-id="f3db9-110">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="f3db9-111">完成規劃階段以準備 MBAM 部署的計算環境。</span><span class="sxs-lookup"><span data-stu-id="f3db9-111">Complete the planning phase to prepare the computing environment for MBAM deployment.</span></span></p></td>
<td align="left"><p><a href="mbam-10-planning-checklist.md" data-raw-source="[MBAM 1.0 Planning Checklist](mbam-10-planning-checklist.md)"><span data-ttu-id="f3db9-112">MBAM 1.0 規劃檢查清單</span><span class="sxs-lookup"><span data-stu-id="f3db9-112">MBAM 1.0 Planning Checklist</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="f3db9-113">請參閱 MBAM 支援的設定中的資訊，以確定您所選取的用戶端和伺服器電腦支援 MBAM 功能安裝。</span><span class="sxs-lookup"><span data-stu-id="f3db9-113">Review the information on MBAM supported configurations to make sure that your selected client and server computers are supported for MBAM feature installation.</span></span></p></td>
<td align="left"><p><a href="mbam-10-supported-configurations.md" data-raw-source="[MBAM 1.0 Supported Configurations](mbam-10-supported-configurations.md)"><span data-ttu-id="f3db9-114">MBAM 1.0 支援的組態</span><span class="sxs-lookup"><span data-stu-id="f3db9-114">MBAM 1.0 Supported Configurations</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="f3db9-115">執行 MBAM 安裝程式，以下列順序部署 MBAM 伺服器功能：</span><span class="sxs-lookup"><span data-stu-id="f3db9-115">Run MBAM Setup to deploy MBAM Server features in the following order:</span></span></p>
<ol>
<li><p><span data-ttu-id="f3db9-116">恢復與硬體資料庫</span><span class="sxs-lookup"><span data-stu-id="f3db9-116">Recovery and Hardware Database</span></span></p></li>
<li><p><span data-ttu-id="f3db9-117">合規性狀態資料庫</span><span class="sxs-lookup"><span data-stu-id="f3db9-117">Compliance Status Database</span></span></p></li>
<li><p><span data-ttu-id="f3db9-118">合規性審核與報告</span><span class="sxs-lookup"><span data-stu-id="f3db9-118">Compliance Audit and Reports</span></span></p></li>
<li><p><span data-ttu-id="f3db9-119">管理和監控伺服器</span><span class="sxs-lookup"><span data-stu-id="f3db9-119">Administration and Monitoring Server</span></span></p></li>
<li><p><span data-ttu-id="f3db9-120">MBAM 群組原則範本</span><span class="sxs-lookup"><span data-stu-id="f3db9-120">MBAM Group Policy Template</span></span></p></li>
</ol>
<div class="alert">
<strong><span data-ttu-id="f3db9-121">注意</span><span class="sxs-lookup"><span data-stu-id="f3db9-121">Note</span></span></strong><br/><p><span data-ttu-id="f3db9-122">追蹤每個安裝功能的伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="f3db9-122">Keep track of the names of the servers each feature is installed on.</span></span> <span data-ttu-id="f3db9-123">您將會在整個安裝過程中使用此資訊。</span><span class="sxs-lookup"><span data-stu-id="f3db9-123">You will use this information throughout the installation process.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><a href="deploying-the-mbam-10-server-infrastructure.md" data-raw-source="[Deploying the MBAM 1.0 Server Infrastructure](deploying-the-mbam-10-server-infrastructure.md)"><span data-ttu-id="f3db9-124">部署 MBAM 1.0 伺服器基礎結構</span><span class="sxs-lookup"><span data-stu-id="f3db9-124">Deploying the MBAM 1.0 Server Infrastructure</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="f3db9-125">將在規劃階段建立的 Active Directory 網域服務安全性群組新增至適當的伺服器上適當的本機 MBAM 伺服器功能系統管理員群組。</span><span class="sxs-lookup"><span data-stu-id="f3db9-125">Add Active Directory Domain Services security groups created during the planning phase to the appropriate local MBAM Server feature administrators groups on the appropriate servers.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-10-administrator-roles.md" data-raw-source="[Planning for MBAM 1.0 Administrator Roles](planning-for-mbam-10-administrator-roles.md)"><span data-ttu-id="f3db9-126">規劃 MBAM 1.0 系統管理員角色 </a> ，以及 <a href="how-to-manage-mbam-administrator-roles-mbam-1.md" data-raw-source="[How to Manage MBAM Administrator Roles](how-to-manage-mbam-administrator-roles-mbam-1.md)"> 如何管理 MBAM 系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="f3db9-126">Planning for MBAM 1.0 Administrator Roles</a> and <a href="how-to-manage-mbam-administrator-roles-mbam-1.md" data-raw-source="[How to Manage MBAM Administrator Roles](how-to-manage-mbam-administrator-roles-mbam-1.md)">How to Manage MBAM Administrator Roles</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="f3db9-127">建立及部署所需的 MBAM 群組原則物件。</span><span class="sxs-lookup"><span data-stu-id="f3db9-127">Create and deploy the required MBAM Group Policy Objects.</span></span></p></td>
<td align="left"><p><a href="deploying-mbam-10-group-policy-objects.md" data-raw-source="[Deploying MBAM 1.0 Group Policy Objects](deploying-mbam-10-group-policy-objects.md)"><span data-ttu-id="f3db9-128">部署 MBAM 1.0 群組原則物件</span><span class="sxs-lookup"><span data-stu-id="f3db9-128">Deploying MBAM 1.0 Group Policy Objects</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="f3db9-129">部署 MBAM 用戶端軟體。</span><span class="sxs-lookup"><span data-stu-id="f3db9-129">Deploy the MBAM Client software.</span></span></p></td>
<td align="left"><p><a href="deploying-the-mbam-10-client.md" data-raw-source="[Deploying the MBAM 1.0 Client](deploying-the-mbam-10-client.md)"><span data-ttu-id="f3db9-130">部署 MBAM 1.0 用戶端</span><span class="sxs-lookup"><span data-stu-id="f3db9-130">Deploying the MBAM 1.0 Client</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="f3db9-131">相關主題</span><span class="sxs-lookup"><span data-stu-id="f3db9-131">Related topics</span></span>


[<span data-ttu-id="f3db9-132">部署 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="f3db9-132">Deploying MBAM 1.0</span></span>](deploying-mbam-10.md)









