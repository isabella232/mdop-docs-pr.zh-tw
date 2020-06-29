---
title: 評估 MBAM 2.0
description: 評估 MBAM 2.0
author: dansimp
ms.assetid: bfc77eec-0fd7-4fec-9c78-6870afa87152
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b7be883f44f5f09a904f619972ae3e7c35261d26
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810736"
---
# <span data-ttu-id="c778f-103">評估 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="c778f-103">Evaluating MBAM 2.0</span></span>


<span data-ttu-id="c778f-104">在將 Microsoft BitLocker 管理和監控（MBAM）部署到生產環境之前，您應該先在測試環境中評估它。</span><span class="sxs-lookup"><span data-stu-id="c778f-104">Before deploying Microsoft BitLocker Administration and Monitoring (MBAM) into a production environment, you should evaluate it in a test environment.</span></span> <span data-ttu-id="c778f-105">本主題中的資訊可以用來在單一伺服器測試環境中設定 Microsoft BitLocker 管理和監控，僅供評估之用。</span><span class="sxs-lookup"><span data-stu-id="c778f-105">The information in this topic can be used to set up Microsoft BitLocker Administration and Monitoring with a Stand-alone topology in a single-server test environment for evaluation purposes only.</span></span> <span data-ttu-id="c778f-106">不建議在生產環境中使用單一伺服器拓撲。</span><span class="sxs-lookup"><span data-stu-id="c778f-106">A single-server topology is not recommended for production environments.</span></span>

<span data-ttu-id="c778f-107">如需在測試環境中部署 MBAM 的相關指示，請參閱[如何在單一伺服器上安裝和設定 MBAM](how-to-install-and-configure-mbam-on-a-single-server-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="c778f-107">For instructions on deploying MBAM in a test environment, see [How to Install and Configure MBAM on a Single Server](how-to-install-and-configure-mbam-on-a-single-server-mbam-2.md).</span></span>

## <span data-ttu-id="c778f-108">設定測試環境</span><span class="sxs-lookup"><span data-stu-id="c778f-108">Setting up the Test Environment</span></span>


<span data-ttu-id="c778f-109">即使您要在測試環境中設定要評估的非生產 MBAM 實例，您仍然應該確認您已滿足系統必備與硬體及軟體需求。</span><span class="sxs-lookup"><span data-stu-id="c778f-109">Even though you are setting up a non-production instance of MBAM to evaluate in a test environment, you should still verify that you have met the prerequisites and hardware and software requirements.</span></span> <span data-ttu-id="c778f-110">開始安裝之前，請參閱[MBAM 2.0 部署先決條件](mbam-20-deployment-prerequisites-mbam-2.md)、 [MBAM 2.0 支援](mbam-20-supported-configurations-mbam-2.md)的設定，以及[為 MBAM 2.0 準備您的環境](preparing-your-environment-for-mbam-20-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="c778f-110">Before you start the installation, see [MBAM 2.0 Deployment Prerequisites](mbam-20-deployment-prerequisites-mbam-2.md), [MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md), and [Preparing your Environment for MBAM 2.0](preparing-your-environment-for-mbam-20-mbam-2.md).</span></span>

### <span data-ttu-id="c778f-111">規劃 MBAM 評估部署</span><span class="sxs-lookup"><span data-stu-id="c778f-111">Plan for an MBAM Evaluation Deployment</span></span>

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
<th align="left"><span data-ttu-id="c778f-112">工作</span><span class="sxs-lookup"><span data-stu-id="c778f-112">Task</span></span></th>
<th align="left"><span data-ttu-id="c778f-113">參考資料</span><span class="sxs-lookup"><span data-stu-id="c778f-113">References</span></span></th>
<th align="left"><span data-ttu-id="c778f-114">附註</span><span class="sxs-lookup"><span data-stu-id="c778f-114">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="c778f-115">查看 MBAM 的快速入門資訊，以深入瞭解開始部署規劃之前的產品。</span><span class="sxs-lookup"><span data-stu-id="c778f-115">Review the Getting Started information about MBAM to gain a basic understanding of the product before beginning deployment planning.</span></span></p></td>
<td align="left"><p><a href="getting-started-with-mbam-20-mbam-2.md" data-raw-source="[Getting Started with MBAM 2.0](getting-started-with-mbam-20-mbam-2.md)"><span data-ttu-id="c778f-116">開始使用 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="c778f-116">Getting Started with MBAM 2.0</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="c778f-117">規劃 MBAM 2.0 部署必備元件並準備您的計算環境。</span><span class="sxs-lookup"><span data-stu-id="c778f-117">Plan for MBAM 2.0 Deployment Prerequisites and prepare your computing environment.</span></span></p></td>
<td align="left"><p><a href="mbam-20-deployment-prerequisites-mbam-2.md" data-raw-source="[MBAM 2.0 Deployment Prerequisites](mbam-20-deployment-prerequisites-mbam-2.md)"><span data-ttu-id="c778f-118">MBAM 2.0 部署必要條件</span><span class="sxs-lookup"><span data-stu-id="c778f-118">MBAM 2.0 Deployment Prerequisites</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="c778f-119">規劃及設定 MBAM 群組原則需求。</span><span class="sxs-lookup"><span data-stu-id="c778f-119">Plan for and configure MBAM Group Policy requirements.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-20-group-policy-requirements-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Group Policy Requirements](planning-for-mbam-20-group-policy-requirements-mbam-2.md)"><span data-ttu-id="c778f-120">MBAM 2.0 群組原則需求規劃</span><span class="sxs-lookup"><span data-stu-id="c778f-120">Planning for MBAM 2.0 Group Policy Requirements</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="c778f-121">規劃及建立必要的 ActiveDirectoryDomainServices 安全性群組，並規劃 MBAM 的本機安全性群組成員資格需求。</span><span class="sxs-lookup"><span data-stu-id="c778f-121">Plan for and create necessary ActiveDirectoryDomainServices security groups, and plan for MBAM local security group membership requirements.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-20-administrator-roles-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Administrator Roles](planning-for-mbam-20-administrator-roles-mbam-2.md)"><span data-ttu-id="c778f-122">MBAM 2.0 系統管理員角色規劃</span><span class="sxs-lookup"><span data-stu-id="c778f-122">Planning for MBAM 2.0 Administrator Roles</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="c778f-123">規劃部署 MBAM Server 功能部署。</span><span class="sxs-lookup"><span data-stu-id="c778f-123">Plan for deploying MBAM Server feature deployment.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-20-server-deployment-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Server Deployment](planning-for-mbam-20-server-deployment-mbam-2.md)"><span data-ttu-id="c778f-124">MBAM 2.0 伺服器部署規劃</span><span class="sxs-lookup"><span data-stu-id="c778f-124">Planning for MBAM 2.0 Server Deployment</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="c778f-125">規劃部署 MBAM 用戶端部署。</span><span class="sxs-lookup"><span data-stu-id="c778f-125">Plan for deploying MBAM Client deployment.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-20-client-deployment-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Client Deployment](planning-for-mbam-20-client-deployment-mbam-2.md)"><span data-ttu-id="c778f-126">MBAM 2.0 用戶端部署規劃</span><span class="sxs-lookup"><span data-stu-id="c778f-126">Planning for MBAM 2.0 Client Deployment</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="c778f-127">執行 MBAM 評估部署</span><span class="sxs-lookup"><span data-stu-id="c778f-127">Perform an MBAM Evaluation Deployment</span></span>

<span data-ttu-id="c778f-128">完成所需的規劃和軟體必備元件安裝後，若要為 MBAM 安裝準備您的計算環境，您可以開始進行 MBAM 評估部署。</span><span class="sxs-lookup"><span data-stu-id="c778f-128">After completing the necessary planning and software prerequisite installations to prepare your computing environment for the MBAM installation, you can begin the MBAM evaluation deployment.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="c778f-129">查看 MBAM 支援的設定資訊，確認已選取 [用戶端和伺服器電腦] 支援 MBAM 功能安裝。</span><span class="sxs-lookup"><span data-stu-id="c778f-129">Review the MBAM supported configurations information to make sure that selected client and server computers are supported for MBAM feature installation.</span></span></p></td>
<td align="left"><p><a href="mbam-20-supported-configurations-mbam-2.md" data-raw-source="[MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md)"><span data-ttu-id="c778f-130">MBAM 2.0 支援的組態</span><span class="sxs-lookup"><span data-stu-id="c778f-130">MBAM 2.0 Supported Configurations</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="c778f-131">若要評估，請執行 MBAM 安裝程式，在單一伺服器上部署 MBAM 伺服器功能。</span><span class="sxs-lookup"><span data-stu-id="c778f-131">Run MBAM Setup to deploy MBAM Server features on a single server for evaluation purposes.</span></span></p></td>
<td align="left"><p><a href="how-to-install-and-configure-mbam-on-a-single-server-mbam-2.md" data-raw-source="[How to Install and Configure MBAM on a Single Server](how-to-install-and-configure-mbam-on-a-single-server-mbam-2.md)"><span data-ttu-id="c778f-132">如何在單一伺服器上安裝及設定 MBAM</span><span class="sxs-lookup"><span data-stu-id="c778f-132">How to Install and Configure MBAM on a Single Server</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="c778f-133">將您在規劃階段建立的 ActiveDirectoryDomainServices 安全性群組新增至新 MBAM 伺服器上適當的本機 MBAM 伺服器功能本機群組。</span><span class="sxs-lookup"><span data-stu-id="c778f-133">Add ActiveDirectoryDomainServices security groups, that you created during the planning phase, to the appropriate local MBAM Server feature local groups on the new MBAM Server.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-20-administrator-roles-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Administrator Roles](planning-for-mbam-20-administrator-roles-mbam-2.md)"><span data-ttu-id="c778f-134">規劃 MBAM 2.0 系統管理員角色 </a> ，以及 <a href="how-to-manage-mbam-administrator-roles-mbam-2.md" data-raw-source="[How to Manage MBAM Administrator Roles](how-to-manage-mbam-administrator-roles-mbam-2.md)"> 如何管理 MBAM 系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="c778f-134">Planning for MBAM 2.0 Administrator Roles</a> and <a href="how-to-manage-mbam-administrator-roles-mbam-2.md" data-raw-source="[How to Manage MBAM Administrator Roles](how-to-manage-mbam-administrator-roles-mbam-2.md)">How to Manage MBAM Administrator Roles</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="c778f-135">建立及部署所需的 MBAM 群組原則物件。</span><span class="sxs-lookup"><span data-stu-id="c778f-135">Create and deploy required MBAM Group Policy Objects.</span></span></p></td>
<td align="left"><p><a href="deploying-mbam-20-group-policy-objects-mbam-2.md" data-raw-source="[Deploying MBAM 2.0 Group Policy Objects](deploying-mbam-20-group-policy-objects-mbam-2.md)"><span data-ttu-id="c778f-136">部署 MBAM 2.0 群組原則物件</span><span class="sxs-lookup"><span data-stu-id="c778f-136">Deploying MBAM 2.0 Group Policy Objects</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="c778f-137">部署 MBAM 用戶端軟體。</span><span class="sxs-lookup"><span data-stu-id="c778f-137">Deploy the MBAM Client software.</span></span></p></td>
<td align="left"><p><a href="deploying-the-mbam-20-client-mbam-2.md" data-raw-source="[Deploying the MBAM 2.0 Client](deploying-the-mbam-20-client-mbam-2.md)"><span data-ttu-id="c778f-138">部署 MBAM 2.0 用戶端</span><span class="sxs-lookup"><span data-stu-id="c778f-138">Deploying the MBAM 2.0 Client</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="c778f-139">設定實驗室電腦進行 MBAM 評估</span><span class="sxs-lookup"><span data-stu-id="c778f-139">Configure Lab Computers for MBAM Evaluation</span></span>


<span data-ttu-id="c778f-140">本節包含可用於加速 MBAM 用戶端狀態報表的資訊。</span><span class="sxs-lookup"><span data-stu-id="c778f-140">This section contains information that can be used to speed up the MBAM Client status reporting.</span></span> <span data-ttu-id="c778f-141">不過，這些修改只能用於測試目的。</span><span class="sxs-lookup"><span data-stu-id="c778f-141">However, these modifications should be used for testing purposes only.</span></span>

<span data-ttu-id="c778f-142">**記事** 下列各節中的資訊說明如何修改 Windows registry。</span><span class="sxs-lookup"><span data-stu-id="c778f-142">**Note** The information in following section describes how to modify the Windows registry.</span></span> <span data-ttu-id="c778f-143">無法正確使用登錄編輯程式，可能會導致嚴重問題，可能需要重新安裝 Windows。</span><span class="sxs-lookup"><span data-stu-id="c778f-143">Using Registry Editor incorrectly can cause serious problems that may require you to reinstall Windows.</span></span> <span data-ttu-id="c778f-144">Microsoft 無法保證無法正確使用登錄編輯程式所造成的問題，因此無法解決。</span><span class="sxs-lookup"><span data-stu-id="c778f-144">Microsoft cannot guarantee that problems resulting from the incorrect use of Registry Editor can be solved.</span></span> <span data-ttu-id="c778f-145">使用登錄編輯程式的風險由您自負。</span><span class="sxs-lookup"><span data-stu-id="c778f-145">Use Registry Editor at your own risk.</span></span>

 

### <span data-ttu-id="c778f-146">修改 MBAM 用戶端狀態報表頻率設定</span><span class="sxs-lookup"><span data-stu-id="c778f-146">Modify MBAM Client Status Reporting Frequency Settings</span></span>

<span data-ttu-id="c778f-147">使用群組原則設定 MBAM 用戶端喚醒和狀態報表頻率時，其最小值為90分鐘。</span><span class="sxs-lookup"><span data-stu-id="c778f-147">The MBAM Client wakeup and status reporting frequencies have a minimum value of 90 minutes when they are set using Group Policy.</span></span> <span data-ttu-id="c778f-148">您可以在 MBAM 用戶端電腦上使用 Windows 登錄來將這些頻率變更為較低的值，以協助您加速測試。</span><span class="sxs-lookup"><span data-stu-id="c778f-148">You can use the Windows registry to change these frequencies to a lower value on MBAM client computers to help speed up testing.</span></span>

<span data-ttu-id="c778f-149">若要修改 MBAM 用戶端狀態報表頻率設定：</span><span class="sxs-lookup"><span data-stu-id="c778f-149">To modify the MBAM Client status reporting frequency settings:</span></span>

1.  <span data-ttu-id="c778f-150">使用登錄編輯程式流覽至**HKLM\\Software\\Policies\\Microsoft\\FVE\\MDOPBitLockerManagement**。</span><span class="sxs-lookup"><span data-stu-id="c778f-150">Use a registry editor to navigate to **HKLM\\Software\\Policies\\Microsoft\\FVE\\MDOPBitLockerManagement**.</span></span>

2.  <span data-ttu-id="c778f-151">將**ClientWakeupFrequency**和**StatusReportingFrequency**的值變更為**1** ，以支援最小用戶端支援的值。</span><span class="sxs-lookup"><span data-stu-id="c778f-151">Change the values for **ClientWakeupFrequency** and **StatusReportingFrequency** to **1** as the minimum client-supported value.</span></span> <span data-ttu-id="c778f-152">此變更會導致 MBAM 用戶端每分鐘報告一次。</span><span class="sxs-lookup"><span data-stu-id="c778f-152">This change causes the MBAM Client to report every minute.</span></span>

3.  <span data-ttu-id="c778f-153">重新開機**BitLocker 管理用戶端服務**。</span><span class="sxs-lookup"><span data-stu-id="c778f-153">Restart **BitLocker Management Client Service**.</span></span>

<span data-ttu-id="c778f-154">**記事** 若要設定這個低的值，您必須在登錄中手動設定。</span><span class="sxs-lookup"><span data-stu-id="c778f-154">**Note** To set values that are this low, you must set them in the registry manually.</span></span>

 

### <span data-ttu-id="c778f-155">修改 MBAM 用戶端服務啟動延遲</span><span class="sxs-lookup"><span data-stu-id="c778f-155">Modify MBAM Client Service Startup Delay</span></span>

<span data-ttu-id="c778f-156">除了 MBAM 用戶端喚醒和狀態報表頻率之外，在用戶端電腦上啟動 MBAM 用戶端代理服務時，會有最多90分鐘的隨機延遲。</span><span class="sxs-lookup"><span data-stu-id="c778f-156">In addition to the MBAM Client wakeup and status reporting frequencies, there is a random delay of up to 90 minutes when the MBAM Client agent service starts on client computers.</span></span> <span data-ttu-id="c778f-157">如果您不想要隨機延遲，請在 [ **HKLM\\Software\\Microsoft\\MBAM**] 下建立**NoStartupDelay**的**DWORD**值，將它的值設定為**1**，然後重新開機**BitLocker 管理用戶端服務**。</span><span class="sxs-lookup"><span data-stu-id="c778f-157">If you do not want the random delay, create a **DWORD** value of **NoStartupDelay** under **HKLM\\Software\\Microsoft\\MBAM**, set its value to **1**, and then restart **BitLocker Management Client Service**.</span></span>

## <span data-ttu-id="c778f-158">相關主題</span><span class="sxs-lookup"><span data-stu-id="c778f-158">Related topics</span></span>


[<span data-ttu-id="c778f-159">開始使用 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="c778f-159">Getting Started with MBAM 2.0</span></span>](getting-started-with-mbam-20-mbam-2.md)

 

 





