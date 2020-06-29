---
title: 如何使用 Administration and Monitoring Website
description: 如何使用 Administration and Monitoring Website
author: dansimp
ms.assetid: bb96a4e8-d4f4-4e6f-b7db-82d96998bfa6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9b9597e29a5a7a6236cb351d8d6d1f682edce3cf
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800245"
---
# <span data-ttu-id="9cb77-103">如何使用 Administration and Monitoring Website</span><span class="sxs-lookup"><span data-stu-id="9cb77-103">How to Use the Administration and Monitoring Website</span></span>


<span data-ttu-id="9cb77-104">管理和監控網站（也稱為說明服務台）是 BitLocker 磁碟機加密的管理介面。</span><span class="sxs-lookup"><span data-stu-id="9cb77-104">The Administration and Monitoring Website, also referred to as the Help Desk, is an administrative interface for BitLocker Drive Encryption.</span></span> <span data-ttu-id="9cb77-105">您可以使用網站來查看報告、復原使用者的磁片磁碟機，以及管理使用者的 TPMs，如下列各節所述。</span><span class="sxs-lookup"><span data-stu-id="9cb77-105">Use the website to review reports, recover end users’ drives, and manage end users’ TPMs, as described in the following sections.</span></span>

<span data-ttu-id="9cb77-106">**記事** 如果您是在獨立拓撲中使用 MBAM，您可以從 [管理] 和 [監視] 網站上查看所有報表。</span><span class="sxs-lookup"><span data-stu-id="9cb77-106">**Note** If you are using MBAM in the Stand-alone topology, you view all reports from the Administration and Monitoring Website.</span></span> <span data-ttu-id="9cb77-107">如果您使用的是 Configuration Manager 整合拓朴，您可以在 Configuration Manager 中查看所有報表，除了復原審核報告之外，您還會從管理和監控網站繼續進行查看。</span><span class="sxs-lookup"><span data-stu-id="9cb77-107">If you are using the Configuration Manager Integration topology, you view all reports in Configuration Manager, except the Recovery Audit report, which you continue to view from the Administration and Monitoring Website.</span></span> <span data-ttu-id="9cb77-108">如需有關報告的詳細資訊，請參閱[使用 MBAM 2.5 監視及報告 BitLocker 合規性](monitoring-and-reporting-bitlocker-compliance-with-mbam-25.md)。</span><span class="sxs-lookup"><span data-stu-id="9cb77-108">For more information about reports, see [Monitoring and Reporting BitLocker Compliance with MBAM 2.5](monitoring-and-reporting-bitlocker-compliance-with-mbam-25.md).</span></span>

 

## <span data-ttu-id="9cb77-109">使用管理和監控網站所需的角色</span><span class="sxs-lookup"><span data-stu-id="9cb77-109">Required roles for using the Administration and Monitoring Website</span></span>


<span data-ttu-id="9cb77-110">若要存取 [管理] 和 [監視] 網站的特定區域，您必須具備下列其中一項角色，即您在 Active Directory 中建立的群組。</span><span class="sxs-lookup"><span data-stu-id="9cb77-110">To access specific areas of the Administration and Monitoring Website, you must have one of the following roles, which are groups that you create in Active Directory.</span></span> <span data-ttu-id="9cb77-111">您可以為這些群組使用任何名稱。</span><span class="sxs-lookup"><span data-stu-id="9cb77-111">You can use any name for these groups.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9cb77-112">帳戶</span><span class="sxs-lookup"><span data-stu-id="9cb77-112">Account</span></span></th>
<th align="left"><span data-ttu-id="9cb77-113">描述</span><span class="sxs-lookup"><span data-stu-id="9cb77-113">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9cb77-114">MBAM 高級支援人員的使用者</span><span class="sxs-lookup"><span data-stu-id="9cb77-114">MBAM Advanced Helpdesk Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="9cb77-115">提供管理和監控網站所有區域的存取權。</span><span class="sxs-lookup"><span data-stu-id="9cb77-115">Provides access to all areas of the Administration and Monitoring Website.</span></span> <span data-ttu-id="9cb77-116">擁有此角色的使用者在協助使用者復原其磁碟機時，只會輸入復原金鑰，而不是使用者的網域和使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="9cb77-116">Users who have this role enter only the recovery key, and not the end user’s domain and user name, when helping end users recover their drives.</span></span> <span data-ttu-id="9cb77-117">如果使用者是 MBAM [支援人員] 群組和 MBAM [高級服務台使用者] 群組的成員，MBAM [高級支援人員] 群組許可權會覆寫 MBAM 的 [支援人員] 群組許可權。</span><span class="sxs-lookup"><span data-stu-id="9cb77-117">If a user is a member of both the MBAM Helpdesk Users group and the MBAM Advanced Helpdesk Users group, the MBAM Advanced Helpdesk Users group permissions override the MBAM Helpdesk Users Group permissions.</span></span></p>
<p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9cb77-118">MBAM 支援人員的使用者</span><span class="sxs-lookup"><span data-stu-id="9cb77-118">MBAM Helpdesk Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="9cb77-119">提供存取管理和監控網站的 [管理 TPM] 和 [磁碟機恢復] 區域。</span><span class="sxs-lookup"><span data-stu-id="9cb77-119">Provides access to the Manage TPM and Drive Recovery areas of the Administration and Monitoring Website.</span></span> <span data-ttu-id="9cb77-120">擁有此角色的人員在使用任一區域時，都必須填入所有欄位，包括使用者的網域和帳戶名稱。</span><span class="sxs-lookup"><span data-stu-id="9cb77-120">Individuals who have this role must fill in all fields, including the end-user’s domain and account name, when they use either area.</span></span></p>
<p><span data-ttu-id="9cb77-121">如果使用者是 MBAM [支援人員] 群組和 MBAM [高級服務台使用者] 群組的成員，MBAM [高級支援人員] 群組許可權會覆寫 MBAM 的 [支援人員] 群組許可權。</span><span class="sxs-lookup"><span data-stu-id="9cb77-121">If a user is a member of both the MBAM Helpdesk Users group and the MBAM Advanced Helpdesk Users group, the MBAM Advanced Helpdesk Users group permissions override the MBAM Helpdesk Users Group permissions.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9cb77-122">MBAM 報表使用者</span><span class="sxs-lookup"><span data-stu-id="9cb77-122">MBAM Report Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="9cb77-123">提供 <strong> </strong> 管理和監控網站 [報告] 區域中報告的存取權。</span><span class="sxs-lookup"><span data-stu-id="9cb77-123">Provides access to the reports in the <strong>Reports</strong> area of the Administration and Monitoring Website.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="9cb77-124">您可以在 [管理及監視] 網站上執行的工作</span><span class="sxs-lookup"><span data-stu-id="9cb77-124">Tasks you can perform on the Administration and Monitoring Website</span></span>


<span data-ttu-id="9cb77-125">下表摘要列出您可以在 [管理] 和 [監視] 網站上執行的工作，並提供每個任務詳細資訊的連結。</span><span class="sxs-lookup"><span data-stu-id="9cb77-125">The following table summarizes the tasks you can perform on the Administration and Monitoring Website and provides links to more information about each task.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9cb77-126">工作</span><span class="sxs-lookup"><span data-stu-id="9cb77-126">Task</span></span></th>
<th align="left"><span data-ttu-id="9cb77-127">您可在其中存取任務的網站區域</span><span class="sxs-lookup"><span data-stu-id="9cb77-127">Area of the Website where you access the task</span></span></th>
<th align="left"><span data-ttu-id="9cb77-128">描述</span><span class="sxs-lookup"><span data-stu-id="9cb77-128">Description</span></span></th>
<th align="left"><span data-ttu-id="9cb77-129">其他資訊</span><span class="sxs-lookup"><span data-stu-id="9cb77-129">For more information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9cb77-130">檢視報告</span><span class="sxs-lookup"><span data-stu-id="9cb77-130">View reports</span></span></p></td>
<td align="left"><p><span data-ttu-id="9cb77-131">報告</span><span class="sxs-lookup"><span data-stu-id="9cb77-131">Reports</span></span></p></td>
<td align="left"><p><span data-ttu-id="9cb77-132">可讓您執行報告，以監控 BitLocker 使用量、合規性及金鑰復原活動。</span><span class="sxs-lookup"><span data-stu-id="9cb77-132">Enables you to run reports to monitor BitLocker usage, compliance, and key recovery activity.</span></span> <span data-ttu-id="9cb77-133">報告提供有關企業合規性、個別電腦，以及特定電腦要求復原金鑰或 TPM OwnerAuth 套件的相關資料。</span><span class="sxs-lookup"><span data-stu-id="9cb77-133">Reports provide data about enterprise compliance, individual computers, and who requested recovery keys or the TPM OwnerAuth package for a specific computer.</span></span></p></td>
<td align="left"><p><a href="viewing-mbam-25-reports-for-the-stand-alone-topology.md" data-raw-source="[Viewing MBAM 2.5 Reports for the Stand-alone Topology](viewing-mbam-25-reports-for-the-stand-alone-topology.md)"><span data-ttu-id="9cb77-134">檢視獨立拓撲的 MBAM 2.5 報告</span><span class="sxs-lookup"><span data-stu-id="9cb77-134">Viewing MBAM 2.5 Reports for the Stand-alone Topology</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9cb77-135">判斷遺失或被盜電腦的 BitLocker 加密狀態</span><span class="sxs-lookup"><span data-stu-id="9cb77-135">Determine the BitLocker encryption status of lost or stolen computers</span></span></p></td>
<td align="left"><p><span data-ttu-id="9cb77-136">報告</span><span class="sxs-lookup"><span data-stu-id="9cb77-136">Reports</span></span></p></td>
<td align="left"><p><span data-ttu-id="9cb77-137">判斷電腦遺失或被盜時，是否已加密卷。</span><span class="sxs-lookup"><span data-stu-id="9cb77-137">Determine if a volume was encrypted if the computer is lost or stolen.</span></span></p></td>
<td align="left"><p><a href="how-to-determine-bitlocker-encryption-state-of-lost-computers-mbam-25.md" data-raw-source="[How to Determine BitLocker Encryption State of Lost Computers](how-to-determine-bitlocker-encryption-state-of-lost-computers-mbam-25.md)"><span data-ttu-id="9cb77-138">如何判斷遺失的電腦之 BitLocker 加密狀態</span><span class="sxs-lookup"><span data-stu-id="9cb77-138">How to Determine BitLocker Encryption State of Lost Computers</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9cb77-139">復原遺失的磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="9cb77-139">Recover lost drives</span></span></p></td>
<td align="left"><p><span data-ttu-id="9cb77-140">磁片磁碟機恢復</span><span class="sxs-lookup"><span data-stu-id="9cb77-140">Drive Recovery</span></span></p></td>
<td align="left"><p><span data-ttu-id="9cb77-141">復原下列磁片磁碟機：</span><span class="sxs-lookup"><span data-stu-id="9cb77-141">Recover drives that are:</span></span></p>
<ul>
<li><p><span data-ttu-id="9cb77-142">在復原模式中</span><span class="sxs-lookup"><span data-stu-id="9cb77-142">In recovery mode</span></span></p></li>
<li><p><span data-ttu-id="9cb77-143">已移動</span><span class="sxs-lookup"><span data-stu-id="9cb77-143">Have been moved</span></span></p></li>
<li><p><span data-ttu-id="9cb77-144">已損毀</span><span class="sxs-lookup"><span data-stu-id="9cb77-144">Are corrupted</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><a href="how-to-recover-a-drive-in-recovery-mode-mbam-25.md" data-raw-source="[How to Recover a Drive in Recovery Mode](how-to-recover-a-drive-in-recovery-mode-mbam-25.md)"><span data-ttu-id="9cb77-145">如何修復處於修復模式的磁碟機</span><span class="sxs-lookup"><span data-stu-id="9cb77-145">How to Recover a Drive in Recovery Mode</span></span></a></p></li>
<li><p><a href="how-to-recover-a-moved-drive-mbam-25.md" data-raw-source="[How to Recover a Moved Drive](how-to-recover-a-moved-drive-mbam-25.md)"><span data-ttu-id="9cb77-146">如何修復已移動的磁碟機</span><span class="sxs-lookup"><span data-stu-id="9cb77-146">How to Recover a Moved Drive</span></span></a></p></li>
<li><p><a href="how-to-recover-a-corrupted-drive-mbam-25.md" data-raw-source="[How to Recover a Corrupted Drive](how-to-recover-a-corrupted-drive-mbam-25.md)"><span data-ttu-id="9cb77-147">如何修復損毀的磁碟機</span><span class="sxs-lookup"><span data-stu-id="9cb77-147">How to Recover a Corrupted Drive</span></span></a></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9cb77-148">重設 TPM 封鎖</span><span class="sxs-lookup"><span data-stu-id="9cb77-148">Reset a TPM lockout</span></span></p></td>
<td align="left"><p><span data-ttu-id="9cb77-149">管理 TPM</span><span class="sxs-lookup"><span data-stu-id="9cb77-149">Manage TPM</span></span></p></td>
<td align="left"><p><span data-ttu-id="9cb77-150">提供存取 MBAM 用戶端所收集的 TPM 資料的許可權。</span><span class="sxs-lookup"><span data-stu-id="9cb77-150">Provides access to TPM data that has been collected by the MBAM Client.</span></span> <span data-ttu-id="9cb77-151">在 TPM 封鎖中，請使用 [管理] 和 [監視] 網站來取得解鎖 TPM 所需的密碼檔。</span><span class="sxs-lookup"><span data-stu-id="9cb77-151">In a TPM lockout, use the Administration and Monitoring Website to retrieve the necessary password file to unlock the TPM.</span></span></p></td>
<td align="left"><p><a href="how-to-reset-a-tpm-lockout-mbam-25.md" data-raw-source="[How to Reset a TPM Lockout](how-to-reset-a-tpm-lockout-mbam-25.md)"><span data-ttu-id="9cb77-152">如何重設 TPM 鎖定</span><span class="sxs-lookup"><span data-stu-id="9cb77-152">How to Reset a TPM Lockout</span></span></a></p></td>
</tr>
</tbody>
</table>

 


## <span data-ttu-id="9cb77-153">相關主題</span><span class="sxs-lookup"><span data-stu-id="9cb77-153">Related topics</span></span>


[<span data-ttu-id="9cb77-154">使用 MBAM 2.5 執行 BitLocker 管理</span><span class="sxs-lookup"><span data-stu-id="9cb77-154">Performing BitLocker Management with MBAM 2.5</span></span>](performing-bitlocker-management-with-mbam-25.md)

 

## <span data-ttu-id="9cb77-155">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="9cb77-155">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="9cb77-156">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="9cb77-156">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="9cb77-157">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="9cb77-157">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





