---
title: 功能可見性設定
description: 功能可見性設定
author: dansimp
ms.assetid: 9db2ba03-fb75-4f95-9138-ec89b9fc8d01
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 26f19895d0a9163885779688ba7d89f6d16f2a17
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802765"
---
# <span data-ttu-id="8f88b-103">功能可見性設定</span><span class="sxs-lookup"><span data-stu-id="8f88b-103">Feature Visibility Settings</span></span>


<span data-ttu-id="8f88b-104">[高級群組原則管理（AGPM）] 的 [管理範本] 設定可讓您集中設定套用這些設定之群組原則物件（GPO）之 [**變更控制**] 節點與 [歷程**記錄**] 索引標籤的可見度。</span><span class="sxs-lookup"><span data-stu-id="8f88b-104">The Administrative template settings for Advanced Group Policy Management (AGPM) enable you to centrally configure the visibility of the **Change Control** node and **History** tab for Group Policy administrators to whom a Group Policy object (GPO) with these settings is applied.</span></span>

<span data-ttu-id="8f88b-105">在群群組原則管理主控台（GPMC）中編輯**GPO 時，在 [使用者**Configuration\\Administrative Templates\\Windows Components\\Microsoft 管理主控台 \ \ 受限制/允許的 Snap-ins\\Extension] 增益集中提供下列設定。</span><span class="sxs-lookup"><span data-stu-id="8f88b-105">The following settings are available under User Configuration\\Administrative Templates\\Windows Components\\Microsoft Management Console\\Restricted/Permitted Snap-ins\\Extension Snap-ins in the **Group Policy Object Editor** when editing a GPO in the Group Policy Management Console (GPMC).</span></span> <span data-ttu-id="8f88b-106">如果看不到此路徑，請以滑鼠右鍵按一下 [**管理範本**]，然後新增 [agpm. admx] 或 [agpm .adm] 範本。</span><span class="sxs-lookup"><span data-stu-id="8f88b-106">If this path is not visible, right-click **Administrative Templates**, and add the agpm.admx or agpm.adm template.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8f88b-107">設定</span><span class="sxs-lookup"><span data-stu-id="8f88b-107">Setting</span></span></th>
<th align="left"><span data-ttu-id="8f88b-108">效果</span><span class="sxs-lookup"><span data-stu-id="8f88b-108">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="8f88b-109">AGPM 變更控制</span><span class="sxs-lookup"><span data-stu-id="8f88b-109">AGPM Change Control</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="8f88b-110">如果已啟用或未設定，則 <strong> 會在 GPMC 中看到 [變更控制] </strong> 節點。</span><span class="sxs-lookup"><span data-stu-id="8f88b-110">If enabled or not configured, the <strong>Change Control</strong> node is visible in the GPMC.</span></span></p>
<p><span data-ttu-id="8f88b-111">如果停用，則 <strong> </strong> 會在 GPMC 中看不到 [變更控制] 節點。</span><span class="sxs-lookup"><span data-stu-id="8f88b-111">If disabled, the <strong>Change Control</strong> node is not visible in the GPMC.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="8f88b-112">AGPM 連結延伸</span><span class="sxs-lookup"><span data-stu-id="8f88b-112">AGPM Link Extension</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="8f88b-113">如果已啟用或未設定， <strong> 則 </strong> 會在 GPMC 中顯示每個連結 GPO 的 [歷程記錄] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="8f88b-113">If enabled or not configured, a <strong>History</strong> tab appears in the GPMC for each linked GPO.</span></span></p>
<p><span data-ttu-id="8f88b-114">如果停用， <strong> 則 </strong> 連結的 gpo 看不到 [歷程記錄] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="8f88b-114">If disabled, the <strong>History</strong> tab is not visible for linked GPOs.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="8f88b-115">AGPM GPO 延伸</span><span class="sxs-lookup"><span data-stu-id="8f88b-115">AGPM GPO Extension</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="8f88b-116">如果已啟用或未設定， <strong> 則 </strong> 會在 GPMC 中顯示每個 GPO 的 [歷程記錄] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="8f88b-116">If enabled or not configured, a <strong>History</strong> tab appears in the GPMC for each GPO.</span></span></p>
<p><span data-ttu-id="8f88b-117">如果停用，則 [History] 索引標籤 <strong> </strong> 不會顯示在 [gpo] 中。</span><span class="sxs-lookup"><span data-stu-id="8f88b-117">If disabled, the <strong>History</strong> tab is not visible for GPOs.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="8f88b-118">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="8f88b-118">Additional references</span></span>

-   [<span data-ttu-id="8f88b-119">系統管理範本設定</span><span class="sxs-lookup"><span data-stu-id="8f88b-119">Administrative Template Settings</span></span>](administrative-template-settings.md)

 

 





