---
title: 從檔案匯入 GPO
description: 從檔案匯入 GPO
author: dansimp
ms.assetid: 6e901a52-1101-4fed-9f90-3819b573b378
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e15704806f089bb0d8530cd84df64b0889413426
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802730"
---
# <span data-ttu-id="7e560-103">從檔案匯入 GPO</span><span class="sxs-lookup"><span data-stu-id="7e560-103">Import a GPO from a File</span></span>


<span data-ttu-id="7e560-104">在 [高級群組原則管理（AGPM）] 中，如果您已將群組原則物件（GPO）匯出到 CAB 檔案，您可以將該 GPO 的原則設定匯入另一個目錄林中網域中的現有 GPO。</span><span class="sxs-lookup"><span data-stu-id="7e560-104">In Advanced Group Policy Management (AGPM), if you have exported a Group Policy Object (GPO) to a CAB file, you can import the policy settings from that GPO into an existing GPO in a domain in another forest.</span></span> <span data-ttu-id="7e560-105">將原則設定匯入現有的 GPO 會取代該 GPO 中的所有原則設定。</span><span class="sxs-lookup"><span data-stu-id="7e560-105">Importing policy settings into an existing GPO replaces all policy settings within that GPO.</span></span> <span data-ttu-id="7e560-106">如需將 GPO 設定匯出到 CAB 檔案的相關資訊，請參閱[將 Gpo 匯出至](export-a-gpo-to-a-file.md)檔案。</span><span class="sxs-lookup"><span data-stu-id="7e560-106">For information about exporting GPO settings to a CAB file, see [Export a GPO to a File](export-a-gpo-to-a-file.md).</span></span>

<span data-ttu-id="7e560-107">具有 [編輯者] 或 [AGPM 管理員] （完全控制）角色的使用者帳戶，或 [高級群組原則管理] （AGPM）中的必要許可權，才能完成此程式。</span><span class="sxs-lookup"><span data-stu-id="7e560-107">A user account with the Editor or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span><span data-ttu-id="7e560-108">請參閱本主題中的「其他注意事項」中的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="7e560-108">Review the details in "Additional considerations" in this topic.</span></span>

## <a href="" id="bkmk-existing"></a>


**<span data-ttu-id="7e560-109">將原則設定匯入現有的 GPO</span><span class="sxs-lookup"><span data-stu-id="7e560-109">To import policy settings into an existing GPO</span></span>**

1.  <span data-ttu-id="7e560-110">在 [**群組原則管理] 主控台**樹狀結構中，按一下您要匯入原則設定的網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="7e560-110">In the **Group Policy Management Console** tree, click **Change Control** in the domain to which you want to import policy settings.</span></span>

2.  <span data-ttu-id="7e560-111">在 [**內容**] 索引標籤上，按一下 [**受控**] 索引標籤以顯示受控制的 gpo。</span><span class="sxs-lookup"><span data-stu-id="7e560-111">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

3.  <span data-ttu-id="7e560-112">取出您要匯入原則設定的目的地 GPO。</span><span class="sxs-lookup"><span data-stu-id="7e560-112">Check out the destination GPO to which you want to import policy settings.</span></span>

4.  <span data-ttu-id="7e560-113">以滑鼠右鍵按一下目的地 GPO，指向 [匯**入來源**]，然後**按一下 [** 檔案]。</span><span class="sxs-lookup"><span data-stu-id="7e560-113">Right-click the destination GPO, point to **Import from**, and then click **File**.</span></span>

5.  <span data-ttu-id="7e560-114">依照 [匯**入設定] 嚮導**中的指示來選取 GPO 備份、匯入其原則設定以取代目的地 gpo 中的那些，然後輸入目標 gpo 之審核追蹤的批註。</span><span class="sxs-lookup"><span data-stu-id="7e560-114">Follow the instructions in the **Import Settings Wizard** to select a GPO backup, import its policy settings to replace those in the destination GPO, and enter a comment for the audit trail of the destination GPO.</span></span> <span data-ttu-id="7e560-115">根據預設，當嚮導完成時，會檢入目的地 GPO。</span><span class="sxs-lookup"><span data-stu-id="7e560-115">By default, the destination GPO is checked in when the wizard is finished.</span></span>

### <span data-ttu-id="7e560-116">其他考量</span><span class="sxs-lookup"><span data-stu-id="7e560-116">Additional considerations</span></span>

-   <span data-ttu-id="7e560-117">根據預設，您必須是編輯者或 AGPM 系統管理員（完全控制）才能執行此程式。</span><span class="sxs-lookup"><span data-stu-id="7e560-117">By default, you must be an Editor or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="7e560-118">具體來說，您必須擁有**清單內容**、**編輯設定**及網域的匯**入 GPO**許可權，而且 GPO 必須由您取出。</span><span class="sxs-lookup"><span data-stu-id="7e560-118">Specifically, you must have **List Contents**, **Edit Settings**, and **Import GPO** permissions for the domain, and the GPO must be checked out by you.</span></span>

-   <span data-ttu-id="7e560-119">雖然編輯程式無法在建立時將原則設定匯入到新的 GPO 中，但是編輯者可以要求建立新的 GPO，然後在建立之後將原則設定匯入到新的 gpo 中。</span><span class="sxs-lookup"><span data-stu-id="7e560-119">Although an Editor cannot import policy settings into a new GPO during its creation, an Editor can request the creation of a new GPO and then import policy settings into it after it is created.</span></span>

### <span data-ttu-id="7e560-120">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="7e560-120">Additional references</span></span>

-   [<span data-ttu-id="7e560-121">使用測試環境</span><span class="sxs-lookup"><span data-stu-id="7e560-121">Using a Test Environment</span></span>](using-a-test-environment.md)

 

 





