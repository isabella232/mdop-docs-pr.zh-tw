---
title: 從檔案匯入 GPO
description: 從檔案匯入 GPO
author: dansimp
ms.assetid: 2cbcda72-4de3-47ad-aaf8-4fc7341d5a00
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 04819dacac8df73f0a61cace0dab8b9fa79b7307
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802742"
---
# <span data-ttu-id="95d9f-103">從檔案匯入 GPO</span><span class="sxs-lookup"><span data-stu-id="95d9f-103">Import a GPO from a File</span></span>


<span data-ttu-id="95d9f-104">在高級群組原則管理（AGPM）中，如果您是 AGPM 系統管理員（完全控制），而您已將群組原則物件（GPO）匯出到 CAB 檔案，您可以將該 GPO 的原則設定匯入到新的 GPO，或另一個目錄林中網域中的現有 GPO。</span><span class="sxs-lookup"><span data-stu-id="95d9f-104">In Advanced Group Policy Management (AGPM), if you are an AGPM Administrator (Full Control) and you have exported a Group Policy Object (GPO) to a CAB file, you can import the policy settings from that GPO into a new GPO or an existing GPO in a domain in another forest.</span></span> <span data-ttu-id="95d9f-105">如需將 GPO 設定匯出到 CAB 檔案的相關資訊，請參閱[將 Gpo 匯出至](export-a-gpo-to-a-file.md)檔案。</span><span class="sxs-lookup"><span data-stu-id="95d9f-105">For information about exporting GPO settings to a CAB file, see [Export a GPO to a File](export-a-gpo-to-a-file.md).</span></span>

<span data-ttu-id="95d9f-106">需要使用 AGPM 系統管理員角色的使用者帳戶，或在 AGPM 中所需的許可權，才能將原則設定匯入新的受控 GPO。</span><span class="sxs-lookup"><span data-stu-id="95d9f-106">A user account with the AGPM Administrator role or the necessary permissions in AGPM is required to import policy settings into a new controlled GPO.</span></span> <span data-ttu-id="95d9f-107">需要在 AGPM 中使用 [編輯者] 或 [AGPM 管理員角色] 或 [必要] 許可權的使用者帳戶，才能將原則設定匯入現有的 GPO。</span><span class="sxs-lookup"><span data-stu-id="95d9f-107">A user account with the Editor or AGPM Administrator role or necessary permissions in AGPM is required to import policy settings into an existing GPO.</span></span> <span data-ttu-id="95d9f-108">請參閱本主題中的「其他注意事項」中的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="95d9f-108">Review the details in "Additional considerations" in this topic.</span></span>

## <span data-ttu-id="95d9f-109">從檔案匯入原則設定</span><span class="sxs-lookup"><span data-stu-id="95d9f-109">Importing policy settings from a file</span></span>


<span data-ttu-id="95d9f-110">從檔案匯入原則設定時，您可以將它們匯入到新的 GPO 或現有的 GPO 中。</span><span class="sxs-lookup"><span data-stu-id="95d9f-110">When you import policy settings from a file, you can import them into a new GPO or an existing GPO.</span></span> <span data-ttu-id="95d9f-111">不過，如果您將原則設定匯入到現有的 GPO 中，則會取代其中的所有原則設定。</span><span class="sxs-lookup"><span data-stu-id="95d9f-111">However, if you import policy settings into an existing GPO, all policy settings within it are replaced.</span></span>

-   [<span data-ttu-id="95d9f-112">將原則設定匯入到新的受控 GPO</span><span class="sxs-lookup"><span data-stu-id="95d9f-112">Import policy settings into a new controlled GPO</span></span>](#bkmk-new)

-   [<span data-ttu-id="95d9f-113">將原則設定匯入現有的 GPO</span><span class="sxs-lookup"><span data-stu-id="95d9f-113">Import policy settings into an existing GPO</span></span>](#bkmk-existing)

### <a href="" id="bkmk-new"></a>

**<span data-ttu-id="95d9f-114">將原則設定匯入新的受控 GPO</span><span class="sxs-lookup"><span data-stu-id="95d9f-114">To import policy settings into a new controlled GPO</span></span>**

1.  <span data-ttu-id="95d9f-115">在 [**群組原則管理] 主控台**樹狀結構中，按一下您要匯入原則設定的網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="95d9f-115">In the **Group Policy Management Console** tree, click **Change Control** in the domain to which you want to import policy settings.</span></span>

2.  <span data-ttu-id="95d9f-116">在 [**內容**] 索引標籤上，按一下 [**受控**] 索引標籤以顯示受控制的 gpo。</span><span class="sxs-lookup"><span data-stu-id="95d9f-116">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

3.  <span data-ttu-id="95d9f-117">建立新的受控 GPO。</span><span class="sxs-lookup"><span data-stu-id="95d9f-117">Create a new controlled GPO.</span></span> <span data-ttu-id="95d9f-118">在 [**新的受控 GPO** ] 對話方塊中，按一下 [匯**入**]，然後按一下 [**啟動嚮導]**。</span><span class="sxs-lookup"><span data-stu-id="95d9f-118">In the **New Controlled GPO** dialog box, click **Import** and then click **Launch Wizard**.</span></span> <span data-ttu-id="95d9f-119">如需如何建立 GPO 的詳細資訊，請參閱[建立新的受控 GPO](create-a-new-controlled-gpo-agpm40.md)。</span><span class="sxs-lookup"><span data-stu-id="95d9f-119">For more information about how to create a GPO, see [Create a New Controlled GPO](create-a-new-controlled-gpo-agpm40.md).</span></span>

4.  <span data-ttu-id="95d9f-120">依照 [匯**入設定] 嚮導**中的指示來選取 GPO 備份，然後針對新的 gpo 匯入策略設定，然後輸入新 gpo 之審核追蹤的意見。</span><span class="sxs-lookup"><span data-stu-id="95d9f-120">Follow the instructions in the **Import Settings Wizard** to select a GPO backup, import policy settings from it for the new GPO, and enter a comment for the audit trail of the new GPO.</span></span>

### <a href="" id="bkmk-existing"></a>

**<span data-ttu-id="95d9f-121">將原則設定匯入現有的 GPO</span><span class="sxs-lookup"><span data-stu-id="95d9f-121">To import policy settings into an existing GPO</span></span>**

1.  <span data-ttu-id="95d9f-122">在 [**群組原則管理] 主控台**樹狀結構中，按一下您要匯入原則設定的網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="95d9f-122">In the **Group Policy Management Console** tree, click **Change Control** in the domain to which you want to import policy settings.</span></span>

2.  <span data-ttu-id="95d9f-123">在 [**內容**] 索引標籤上，按一下 [**受控**] 索引標籤以顯示受控制的 gpo。</span><span class="sxs-lookup"><span data-stu-id="95d9f-123">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

3.  <span data-ttu-id="95d9f-124">取出您要匯入原則設定的目的地 GPO。</span><span class="sxs-lookup"><span data-stu-id="95d9f-124">Check out the destination GPO to which you want to import policy settings.</span></span>

4.  <span data-ttu-id="95d9f-125">以滑鼠右鍵按一下目的地 GPO，指向 [匯**入來源**]，然後**按一下 [** 檔案]。</span><span class="sxs-lookup"><span data-stu-id="95d9f-125">Right-click the destination GPO, point to **Import from**, and then click **File**.</span></span>

5.  <span data-ttu-id="95d9f-126">依照 [匯**入設定] 嚮導**中的指示來選取 GPO 備份、匯入其原則設定以取代目的地 gpo 中的那些，然後輸入目標 gpo 之審核追蹤的批註。</span><span class="sxs-lookup"><span data-stu-id="95d9f-126">Follow the instructions in the **Import Settings Wizard** to select a GPO backup, import its policy settings to replace those in the destination GPO, and enter a comment for the audit trail of the destination GPO.</span></span> <span data-ttu-id="95d9f-127">根據預設，當嚮導完成時，會檢入目的地 GPO。</span><span class="sxs-lookup"><span data-stu-id="95d9f-127">By default, the destination GPO is checked in when the wizard is finished.</span></span>

### <span data-ttu-id="95d9f-128">其他考量</span><span class="sxs-lookup"><span data-stu-id="95d9f-128">Additional considerations</span></span>

-   <span data-ttu-id="95d9f-129">若要將原則設定匯入到新的受控 GPO，您必須擁有**清單內容**、匯**入 GPO**，以及為網域**建立 GPO**許可權。</span><span class="sxs-lookup"><span data-stu-id="95d9f-129">To import policy settings to a new controlled GPO, you must have **List Contents**, **Import GPO**, and **Create GPO** permissions for the domain.</span></span> <span data-ttu-id="95d9f-130">根據預設，您必須是 AGPM 系統管理員才能執行此程式。</span><span class="sxs-lookup"><span data-stu-id="95d9f-130">By default, you must be an AGPM Administrator to perform this procedure.</span></span>

-   <span data-ttu-id="95d9f-131">若要將原則設定匯入至現有的 GPO，您必須擁有**清單內容**、**編輯設定**及針對網域的匯**入 gpo**許可權，而且 GPO 必須由您取出。</span><span class="sxs-lookup"><span data-stu-id="95d9f-131">To import policy settings to an existing GPO, you must have **List Contents**, **Edit Settings**, and **Import GPO** permissions for the domain, and the GPO must be checked out by you.</span></span> <span data-ttu-id="95d9f-132">根據預設，您必須是編輯者或 AGPM 系統管理員（完全控制）才能執行此程式。</span><span class="sxs-lookup"><span data-stu-id="95d9f-132">By default, you must be an Editor or an AGPM Administrator (Full Control) to perform this procedure.</span></span>

### <span data-ttu-id="95d9f-133">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="95d9f-133">Additional references</span></span>

-   [<span data-ttu-id="95d9f-134">管理封存</span><span class="sxs-lookup"><span data-stu-id="95d9f-134">Managing the Archive</span></span>](managing-the-archive-agpm40.md)

 

 





