---
title: 設定 MED-V 工作區原則
description: 設定 MED-V 工作區原則
author: dansimp
ms.assetid: 0eaed981-cbf3-4b16-a4b7-4705c5705dc7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 84bdae38b1c801e2c2be2a3dd1d12dd2ca7d932d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810808"
---
# <span data-ttu-id="ccac5-103">設定 MED-V 工作區原則</span><span class="sxs-lookup"><span data-stu-id="ccac5-103">Configuring MED-V Workspace Policies</span></span>


<span data-ttu-id="ccac5-104">MED-V 工作區原則是一組可設定的設定，可定義虛擬化環境和應用程式在主機電腦上的執行方式。</span><span class="sxs-lookup"><span data-stu-id="ccac5-104">A MED-V workspace policy is a group of configurable settings that define how the virtualized environment and applications perform on the host machine.</span></span> <span data-ttu-id="ccac5-105">本節中的主題描述 MED-V 工作區原則中所有可設定的設定，以及這些設定如何影響 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="ccac5-105">The topics in this section describe all the configurable settings in the MED-V workspace policy as well as how these settings influence the MED-V workspace.</span></span>

<span data-ttu-id="ccac5-106">提供下列 MED-V 工作區類型：</span><span class="sxs-lookup"><span data-stu-id="ccac5-106">The following MED-V workspace types are available:</span></span>

-   <span data-ttu-id="ccac5-107">**Persistent**：在持久的 med-v 工作區中，使用者對 med-v 工作區所做的所有變更和新增，都儲存在 [會話] 之間的 med-v 工作區中。</span><span class="sxs-lookup"><span data-stu-id="ccac5-107">**Persistent**—In a persistent MED-V workspace, all changes and additions the user makes to the MED-V workspace are saved in the MED-V workspace between sessions.</span></span> <span data-ttu-id="ccac5-108">此外，在網域環境中通常會使用持久的 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="ccac5-108">Additionally, a persistent MED-V workspace is generally used in a domain environment.</span></span>

-   <span data-ttu-id="ccac5-109">**Revertible**-在 REVERTIBLE 的 med-v 工作區中，在每個會話完成時（亦即，當 Med-v-v 工作區停止時），med-v 工作區會在部署期間還原為原始狀態。</span><span class="sxs-lookup"><span data-stu-id="ccac5-109">**Revertible**—In a revertible MED-V workspace, at the completion of each session (that is, when the MED-V workspace is stopped), the MED-V workspace reverts to its original state during deployment.</span></span> <span data-ttu-id="ccac5-110">使用者所做的任何變更或附加都不會儲存在 [會話] 之間的 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="ccac5-110">No changes or additions that the user made are saved on the MED-V workspace between sessions.</span></span> <span data-ttu-id="ccac5-111">在網域環境中不能使用 revertible MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="ccac5-111">A revertible MED-V workspace cannot be used in a domain environment.</span></span>

<span data-ttu-id="ccac5-112">在部署 MED-V 工作區之前，請務必決定您要建立的 MED-V 工作區類型，因為建議您在策略部署給使用者之後，再重新設定 MED-V 工作區類型。</span><span class="sxs-lookup"><span data-stu-id="ccac5-112">It is important to decide on the type of MED-V workspace you are creating before deploying the MED-V workspace, because it is not recommended to reconfigure the type of MED-V workspace after a policy has been deployed to users.</span></span>

<span data-ttu-id="ccac5-113">**記事** 設定原則時，[強制] 欄位旁會出現一個警告符號，且未填入。</span><span class="sxs-lookup"><span data-stu-id="ccac5-113">**Note** When configuring a policy, a warning symbol appears next to mandatory fields that are not filled in.</span></span> <span data-ttu-id="ccac5-114">如果未填入強制性欄位，該符號也會出現在索引標籤上。</span><span class="sxs-lookup"><span data-stu-id="ccac5-114">If a mandatory field is not filled in, the symbol appears on the tab as well.</span></span>

 

## <span data-ttu-id="ccac5-115">本節內容</span><span class="sxs-lookup"><span data-stu-id="ccac5-115">In This Section</span></span>


<a href="" id="how-to-apply-general-settings-to-a-med-v-workspace"></a>[<span data-ttu-id="ccac5-116">如何套用一般設定到 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="ccac5-116">How to Apply General Settings to a MED-V Workspace</span></span>](how-to-apply-general-settings-to-a-med-v-workspace.md)  
<span data-ttu-id="ccac5-117">描述 MED-V 工作區的一般設定，以及如何將其套用至原則。</span><span class="sxs-lookup"><span data-stu-id="ccac5-117">Describes the general settings of a MED-V workspace, and how to apply them to a policy.</span></span>

<a href="" id="how-to-apply-virtual-machine-settings-to-a-med-v-workspace"></a>[<span data-ttu-id="ccac5-118">如何套用虛擬機器設定到 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="ccac5-118">How to Apply Virtual Machine Settings to a MED-V Workspace</span></span>](how-to-apply-virtual-machine-settings-to-a-med-v-workspace.md)  
<span data-ttu-id="ccac5-119">描述 MED-V 工作區的虛擬機器設定，以及如何將其套用至原則。</span><span class="sxs-lookup"><span data-stu-id="ccac5-119">Describes the virtual machine settings for a MED-V workspace, and how to apply them to a policy.</span></span>

<a href="" id="how-to-configure-a-domain-user-or-group"></a>[<span data-ttu-id="ccac5-120">如何設定網域使用者或群組</span><span class="sxs-lookup"><span data-stu-id="ccac5-120">How to Configure a Domain User or Group</span></span>](how-to-configure-a-domain-user-or-groupmedvv2.md)  
<span data-ttu-id="ccac5-121">說明如何設定網域使用者和群組。</span><span class="sxs-lookup"><span data-stu-id="ccac5-121">Describes how to configure domain users and groups.</span></span>

<a href="" id="how-to-configure-published-applications"></a>[<span data-ttu-id="ccac5-122">如何設定已發佈的應用程式</span><span class="sxs-lookup"><span data-stu-id="ccac5-122">How to Configure Published Applications</span></span>](how-to-configure-published-applicationsmedvv2.md)  
<span data-ttu-id="ccac5-123">說明已發佈的應用程式和功能表，以及如何將它們套用至原則。</span><span class="sxs-lookup"><span data-stu-id="ccac5-123">Describes published applications and menus, and how to apply them to a policy.</span></span>

<a href="" id="how-to-configure-web-settings-for-a-med-v-workspace"></a>[<span data-ttu-id="ccac5-124">如何設定 MED-V 工作區的網頁設定</span><span class="sxs-lookup"><span data-stu-id="ccac5-124">How to Configure Web Settings for a MED-V Workspace</span></span>](how-to-configure-web-settings-for-a-med-v-workspace.md)  
<span data-ttu-id="ccac5-125">說明 MED-V 工作區可用的網路設定，以及如何將其套用至原則。</span><span class="sxs-lookup"><span data-stu-id="ccac5-125">Describes the Web settings available for a MED-V workspace, and how to apply them to a policy.</span></span>

<a href="" id="how-to-configure-the-virtual-machine-setup-for-a-med-v-workspace"></a>[<span data-ttu-id="ccac5-126">如何設定 MED-V 工作區的虛擬機器設定</span><span class="sxs-lookup"><span data-stu-id="ccac5-126">How to Configure the Virtual Machine Setup for a MED-V Workspace</span></span>](how-to-configure-the-virtual-machine-setup-for-a-med-v-workspace.md)  
<span data-ttu-id="ccac5-127">說明 MED-V 工作區的虛擬機器設定，以及如何將其套用至原則。</span><span class="sxs-lookup"><span data-stu-id="ccac5-127">Describes the virtual machine setup for a MED-V workspace, and how to apply it to a policy.</span></span>

<a href="" id="how-to-apply-network-settings-to-a-med-v-workspace"></a>[<span data-ttu-id="ccac5-128">如何套用網路設定到 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="ccac5-128">How to Apply Network Settings to a MED-V Workspace</span></span>](how-to-apply-network-settings-to-a-med-v-workspace.md)  
<span data-ttu-id="ccac5-129">描述 MED-V 工作區的網路設定，以及如何將其套用至原則。</span><span class="sxs-lookup"><span data-stu-id="ccac5-129">Describes the network settings of a MED-V workspace, and how to apply them to a policy.</span></span>

<a href="" id="how-to-apply-performance-settings-to-a-med-v-workspace"></a>[<span data-ttu-id="ccac5-130">如何套用效能設定到 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="ccac5-130">How to Apply Performance Settings to a MED-V Workspace</span></span>](how-to-apply-performance-settings-to-a-med-v-workspace.md)  
<span data-ttu-id="ccac5-131">描述 MED-V 工作區的效能設定，以及如何將其套用至原則。</span><span class="sxs-lookup"><span data-stu-id="ccac5-131">Describes the performance settings of a MED-V workspace, and how to apply them to a policy.</span></span>

<a href="" id="how-to-import-and-export-a-policy"></a>[<span data-ttu-id="ccac5-132">如何匯入和匯出原則</span><span class="sxs-lookup"><span data-stu-id="ccac5-132">How to Import and Export a Policy</span></span>](how-to-import-and-export-a-policy.md)  
<span data-ttu-id="ccac5-133">說明如何匯入及匯出原則。</span><span class="sxs-lookup"><span data-stu-id="ccac5-133">Describes how to import and export a policy.</span></span>

 

 





