---
title: 重新命名 GPO 或範本
description: 重新命名 GPO 或範本
author: dansimp
ms.assetid: 64a1aaf4-f672-48b5-94c6-473bf1076cf3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 495fc090487ff324bc19c89dcd36ecf0efbcb151
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801838"
---
# <span data-ttu-id="29c46-103">重新命名 GPO 或範本</span><span class="sxs-lookup"><span data-stu-id="29c46-103">Rename a GPO or Template</span></span>


<span data-ttu-id="29c46-104">您可以重新命名受控的群組原則物件（GPO）或範本。</span><span class="sxs-lookup"><span data-stu-id="29c46-104">You can rename a controlled Group Policy object (GPO) or a template.</span></span>

<span data-ttu-id="29c46-105">具有 [編輯者] 或 [AGPM 管理員] （完全控制）角色的使用者帳戶、建立 GPO 之核准者的使用者帳戶，或是必須有高級群組原則管理所需許可權的使用者帳戶才能完成此程式。</span><span class="sxs-lookup"><span data-stu-id="29c46-105">A user account with the Editor or AGPM Administrator (Full Control) role, the user account of the Approver who created the GPO, or a user account with the necessary permissions in Advanced Group Policy Management is required to complete this procedure.</span></span> <span data-ttu-id="29c46-106">請參閱本主題中的「其他注意事項」中的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="29c46-106">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="29c46-107">重新命名 GPO 或範本</span><span class="sxs-lookup"><span data-stu-id="29c46-107">To rename a GPO or template</span></span>**

1.  <span data-ttu-id="29c46-108">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="29c46-108">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="29c46-109">在 [**內容**] 索引標籤上，按一下 [**控制**] 或 [**範本**] 索引標籤，顯示要重新命名的專案</span><span class="sxs-lookup"><span data-stu-id="29c46-109">On the **Contents** tab, click the **Controlled** or **Templates** tab to display the item to rename.</span></span>

3.  <span data-ttu-id="29c46-110">以滑鼠右鍵按一下要重新命名的 GPO 或範本，然後按一下 [**重新命名**]。</span><span class="sxs-lookup"><span data-stu-id="29c46-110">Right-click the GPO or template to rename and click **Rename**.</span></span>

4.  <span data-ttu-id="29c46-111">輸入 GPO 或範本的新名稱和批註，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="29c46-111">Type the new name for the GPO or template and a comment, then click **OK**.</span></span>

5.  <span data-ttu-id="29c46-112">當**進度**視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="29c46-112">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="29c46-113">GPO 或範本會出現在 [**目錄**] 索引標籤上的新名稱底下。</span><span class="sxs-lookup"><span data-stu-id="29c46-113">The GPO or template appears under the new name on the **Contents** tab.</span></span>

### <span data-ttu-id="29c46-114">其他考量</span><span class="sxs-lookup"><span data-stu-id="29c46-114">Additional considerations</span></span>

-   <span data-ttu-id="29c46-115">根據預設，您必須是建立或控制 GPO、編輯器或 AGPM 系統管理員（完全控制）的核准者，才能執行此程式。</span><span class="sxs-lookup"><span data-stu-id="29c46-115">By default, you must be the Approver who created or controlled the GPO, an Editor, or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="29c46-116">具體說來，您必須擁有該 GPO 的 [**清單內容**] 和 [**編輯設定**] 許可權。</span><span class="sxs-lookup"><span data-stu-id="29c46-116">Specifically, you must have **List Contents** and **Edit Settings** permission for the GPO.</span></span>

-   <span data-ttu-id="29c46-117">當您重新命名已部署的 GPO 時，系統會立即在封存中變更該名稱。</span><span class="sxs-lookup"><span data-stu-id="29c46-117">When you rename a GPO that has been deployed, the name is immediately changed in the archive.</span></span> <span data-ttu-id="29c46-118">只有在重新部署 GPO 時，才會在生產環境中變更名稱。</span><span class="sxs-lookup"><span data-stu-id="29c46-118">The name is changed in the production environment only when the GPO is redeployed.</span></span>

    <span data-ttu-id="29c46-119">重新部署 GPO 之後（或刪除生產複本），舊名稱仍會在生產環境中使用，因此無法用於另一個 GPO。</span><span class="sxs-lookup"><span data-stu-id="29c46-119">Until the GPO is redeployed (or the production copy is deleted), the old name is still in use in the production environment and therefore cannot be used for another GPO.</span></span> <span data-ttu-id="29c46-120">同樣地，除非已部署 GPO （變更生產複本的名稱）或已刪除生產複本，否則不能將封存中的 GPO 重新命名回其原始名稱。</span><span class="sxs-lookup"><span data-stu-id="29c46-120">Likewise, the GPO in the archive cannot be renamed back to its original name until the GPO has been deployed (changing the name of the production copy) or the production copy has been deleted.</span></span>

### <span data-ttu-id="29c46-121">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="29c46-121">Additional references</span></span>

-   [<span data-ttu-id="29c46-122">編輯 GPO</span><span class="sxs-lookup"><span data-stu-id="29c46-122">Editing a GPO</span></span>](editing-a-gpo.md)

 

 





