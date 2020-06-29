---
title: 回復到舊版的 GPO
description: 回復到舊版的 GPO
author: dansimp
ms.assetid: 06ce9251-95e0-46d0-99c2-b9a0690e5891
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1146a8ecaf25796b9ac105ba46ea7f27b06fc8aa
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802550"
---
# <span data-ttu-id="4217c-103">回復到舊版的 GPO</span><span class="sxs-lookup"><span data-stu-id="4217c-103">Roll Back to an Earlier Version of a GPO</span></span>


<span data-ttu-id="4217c-104">核准者可以透過從其歷程記錄中重新部署舊版的 GPO，來回滾對群組原則物件（GPO）的變更。</span><span class="sxs-lookup"><span data-stu-id="4217c-104">An Approver can roll back changes to a Group Policy Object (GPO) by redeploying an earlier version of the GPO from its history.</span></span> <span data-ttu-id="4217c-105">部署舊版的 GPO 會覆寫目前在生產中的 GPO 版本。</span><span class="sxs-lookup"><span data-stu-id="4217c-105">Deploying an earlier version of a GPO overwrites the version of the GPO currently in production.</span></span>

<span data-ttu-id="4217c-106">使用者帳戶必須有核准者或 AGPM 管理員（完全控制）角色或高級群組原則管理（AGPM）中的必要許可權，才能完成此程式。</span><span class="sxs-lookup"><span data-stu-id="4217c-106">A user account with the Approver or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span> <span data-ttu-id="4217c-107">請參閱本主題中的「其他注意事項」中的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="4217c-107">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="4217c-108">將舊版的 GPO 部署到網域的生產環境</span><span class="sxs-lookup"><span data-stu-id="4217c-108">To deploy an earlier version of a GPO to the production environment of the domain</span></span>**

1.  <span data-ttu-id="4217c-109">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="4217c-109">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="4217c-110">在 [**內容**] 索引標籤上，按一下 [**受控**] 索引標籤以顯示受控制的 gpo。</span><span class="sxs-lookup"><span data-stu-id="4217c-110">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

3.  <span data-ttu-id="4217c-111">按兩下要部署的 GPO，以顯示其歷程**記錄**。</span><span class="sxs-lookup"><span data-stu-id="4217c-111">Double-click the GPO to be deployed to display its **History**.</span></span>

4.  <span data-ttu-id="4217c-112">以滑鼠右鍵按一下要部署的版本，按一下 [**部署**]，然後按一下 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="4217c-112">Right-click the version to be deployed, click **Deploy**, and then click **Yes**.</span></span>

5.  <span data-ttu-id="4217c-113">當**進度**視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="4217c-113">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="4217c-114">在 [歷程**記錄**] 視窗中，按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="4217c-114">In the **History** window, click **Close**.</span></span>

<span data-ttu-id="4217c-115">**記事** 若要確認重新部署的版本符合預期的版本，請檢查兩個版本的差異報告。</span><span class="sxs-lookup"><span data-stu-id="4217c-115">**Note** To verify that the version that has been redeployed matches the version intended, examine a difference report for the two versions.</span></span> <span data-ttu-id="4217c-116">在 GPO 的 [歷程**記錄**] 視窗中，醒目提示兩個版本，然後按一下滑鼠右鍵，然後選取 [**差異**] 和 [ **HTML 報表**] 或 [ **XML 報表**]。</span><span class="sxs-lookup"><span data-stu-id="4217c-116">In the **History** window for the GPO, highlight the two versions, and then right-click and select **Difference** and either **HTML Report** or **XML Report**.</span></span>

 

### <span data-ttu-id="4217c-117">其他考量</span><span class="sxs-lookup"><span data-stu-id="4217c-117">Additional considerations</span></span>

-   <span data-ttu-id="4217c-118">根據預設，您必須是 [核准者] 或 [AGPM 管理員（完全控制）]，才能執行此程式。</span><span class="sxs-lookup"><span data-stu-id="4217c-118">By default, you must be an Approver or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="4217c-119">具體說來，您必須擁有**清單內容**並**部署**gpo 的 gpo 許可權。</span><span class="sxs-lookup"><span data-stu-id="4217c-119">Specifically, you must have **List Contents** and **Deploy GPO** permissions for the GPO.</span></span>

### <span data-ttu-id="4217c-120">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="4217c-120">Additional references</span></span>

-   [<span data-ttu-id="4217c-121">執行核准者工作</span><span class="sxs-lookup"><span data-stu-id="4217c-121">Performing Approver Tasks</span></span>](performing-approver-tasks-agpm40.md)

 

 





