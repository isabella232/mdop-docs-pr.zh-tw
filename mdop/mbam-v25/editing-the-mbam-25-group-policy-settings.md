---
title: 編輯 MBAM 2.5 群組原則設定
description: 編輯 MBAM 2.5 群組原則設定
author: dansimp
ms.assetid: a50b6b0c-6818-4419-8447-d0520a533dba
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0f6d180cba6dc721ff7de1607d57f90184303d88
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800133"
---
# <span data-ttu-id="0e876-103">編輯 MBAM 2.5 群組原則設定</span><span class="sxs-lookup"><span data-stu-id="0e876-103">Editing the MBAM 2.5 Group Policy Settings</span></span>


<span data-ttu-id="0e876-104">若要成功部署 Microsoft BitLocker 管理和監控（MBAM），您必須：</span><span class="sxs-lookup"><span data-stu-id="0e876-104">To successfully deploy Microsoft BitLocker Administration and Monitoring (MBAM), you have to:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="0e876-105">工作</span><span class="sxs-lookup"><span data-stu-id="0e876-105">Task</span></span></th>
<th align="left"><span data-ttu-id="0e876-106">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="0e876-106">More information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0e876-107">複製 MBAM 2.5 群組原則範本。</span><span class="sxs-lookup"><span data-stu-id="0e876-107">Copy the MBAM 2.5 Group Policy Templates.</span></span></p></td>
<td align="left"><p><a href="copying-the-mbam-25-group-policy-templates.md" data-raw-source="[Copying the MBAM 2.5 Group Policy Templates](copying-the-mbam-25-group-policy-templates.md)"><span data-ttu-id="0e876-108">複製 MBAM 2.5 群組原則範本</span><span class="sxs-lookup"><span data-stu-id="0e876-108">Copying the MBAM 2.5 Group Policy Templates</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0e876-109">決定您想要在 MBAM 實施中使用哪一個群組原則物件（Gpo）。</span><span class="sxs-lookup"><span data-stu-id="0e876-109">Determine which Group Policy Objects (GPOs) you want to use in your MBAM implementation.</span></span> <span data-ttu-id="0e876-110">根據貴組織的需求，您可能必須設定其他群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="0e876-110">Based on the needs of your organization, you might have to configure additional Group Policy settings.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-25-group-policy-requirements.md" data-raw-source="[Planning for MBAM 2.5 Group Policy Requirements](planning-for-mbam-25-group-policy-requirements.md)"><span data-ttu-id="0e876-111">規劃 MBAM 2.5 群組原則需求 </a> -包含 gpo 的描述</span><span class="sxs-lookup"><span data-stu-id="0e876-111">Planning for MBAM 2.5 Group Policy Requirements</a> – contains descriptions of the GPOs</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0e876-112">為您的組織設定群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="0e876-112">Set the Group Policy settings for your organization.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="0e876-113">**重要** 請勿變更**BitLocker 磁片磁碟機加密**節點中的群組原則設定，否則 MBAM 將無法正常運作。</span><span class="sxs-lookup"><span data-stu-id="0e876-113">**Important** Do not change the Group Policy settings in the **BitLocker Drive Encryption** node, or MBAM will not work correctly.</span></span> <span data-ttu-id="0e876-114">當您在**MDOP MBAM （BitLocker 管理）** 節點中設定群組原則設定時，MBAM 會自動為您設定**BitLocker 磁片磁碟機加密**設定。</span><span class="sxs-lookup"><span data-stu-id="0e876-114">When you configure the Group Policy settings in the **MDOP MBAM (BitLocker Management)** node, MBAM automatically configures the **BitLocker Drive Encryption** settings for you.</span></span>

 

**<span data-ttu-id="0e876-115">編輯 MBAM 用戶端群組原則設定</span><span class="sxs-lookup"><span data-stu-id="0e876-115">To edit MBAM Client Group Policy settings</span></span>**

1.  <span data-ttu-id="0e876-116">在已安裝 MBAM 群組原則範本的電腦上，請確定已啟用 MBAM 服務。</span><span class="sxs-lookup"><span data-stu-id="0e876-116">On a computer that has the MBAM Group Policy Templates installed, make sure that MBAM Services are enabled.</span></span>

2.  <span data-ttu-id="0e876-117">在已安裝 MBAM 群組原則範本的電腦上使用 [群組原則管理主控台（GPMC）] 或 [Microsoft 高級群組原則管理 MDOP] 產品，選取 [**電腦**設定 &gt; **原則**] &gt; **管理範本** &gt; **Windows 元件** &gt; **MDOP MBAM （BitLocker 管理）**。</span><span class="sxs-lookup"><span data-stu-id="0e876-117">Using the Group Policy Management Console (GPMC.msc) or the Microsoft Advanced Group Policy Management MDOP product on a computer with the MBAM Group Policy Templates installed, select **Computer configuration** &gt; **Policies** &gt; **Administrative Templates** &gt; **Windows Components** &gt; **MDOP MBAM (BitLocker Management)**.</span></span>

3.  <span data-ttu-id="0e876-118">編輯在用戶端電腦上啟用 MBAM 用戶端服務所需的群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="0e876-118">Edit the Group Policy settings that are required to enable MBAM Client services on client computers.</span></span> <span data-ttu-id="0e876-119">針對下表中的每個原則，選取 [**原則群組**]，按一下您想要的**原則**，然後設定設定。</span><span class="sxs-lookup"><span data-stu-id="0e876-119">For each policy in the following table, select **Policy Group**, click the **Policy** you want, and then configure the settings.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="0e876-120">原則群組</span><span class="sxs-lookup"><span data-stu-id="0e876-120">Policy Group</span></span></th>
    <th align="left"><span data-ttu-id="0e876-121">原則</span><span class="sxs-lookup"><span data-stu-id="0e876-121">Policy</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="0e876-122">用戶端管理</span><span class="sxs-lookup"><span data-stu-id="0e876-122">Client Management</span></span></p></td>
    <td align="left"><p><span data-ttu-id="0e876-123">設定 MBAM 服務</span><span class="sxs-lookup"><span data-stu-id="0e876-123">Configure MBAM Services</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="0e876-124">作業系統磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="0e876-124">Operating System Drive</span></span></p></td>
    <td align="left"><p><span data-ttu-id="0e876-125">作業系統磁片磁碟機加密設定</span><span class="sxs-lookup"><span data-stu-id="0e876-125">Operating system drive encryption settings</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="0e876-126">抽取式磁碟磁碟機</span><span class="sxs-lookup"><span data-stu-id="0e876-126">Removable Drive</span></span></p></td>
    <td align="left"><p><span data-ttu-id="0e876-127">在抽取式磁碟磁碟機上控制 BitLocker 的使用</span><span class="sxs-lookup"><span data-stu-id="0e876-127">Control use of BitLocker on removable drives</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="0e876-128">固定磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="0e876-128">Fixed Drive</span></span></p></td>
    <td align="left"><p><span data-ttu-id="0e876-129">在固定磁片磁碟機上控制 BitLocker 的使用</span><span class="sxs-lookup"><span data-stu-id="0e876-129">Control use of BitLocker on fixed drives</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

## <span data-ttu-id="0e876-130">相關主題</span><span class="sxs-lookup"><span data-stu-id="0e876-130">Related topics</span></span>


[<span data-ttu-id="0e876-131">MBAM 2.5 群組原則需求規劃</span><span class="sxs-lookup"><span data-stu-id="0e876-131">Planning for MBAM 2.5 Group Policy Requirements</span></span>](planning-for-mbam-25-group-policy-requirements.md)

[<span data-ttu-id="0e876-132">複製 MBAM 2.5 群組原則範本</span><span class="sxs-lookup"><span data-stu-id="0e876-132">Copying the MBAM 2.5 Group Policy Templates</span></span>](copying-the-mbam-25-group-policy-templates.md)

 
## <span data-ttu-id="0e876-133">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="0e876-133">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="0e876-134">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="0e876-134">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="0e876-135">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="0e876-135">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>
 





