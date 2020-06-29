---
title: 控制不受控制的 GPO
description: 控制不受控制的 GPO
author: dansimp
ms.assetid: dc81545c-8da5-4b6f-b266-f01a82e27c6b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 418e2a4100e1d824198b7d05034443948ec8a44c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802002"
---
# <span data-ttu-id="f8d8f-103">控制不受控制的 GPO</span><span class="sxs-lookup"><span data-stu-id="f8d8f-103">Control an Uncontrolled GPO</span></span>


<span data-ttu-id="f8d8f-104">若要為群群組原則物件（GPO）提供變更控制，您必須先控制 GPO。</span><span class="sxs-lookup"><span data-stu-id="f8d8f-104">To provide change control for a Group Policy Object (GPO), you must first control the GPO.</span></span>

<span data-ttu-id="f8d8f-105">使用者帳戶必須有核准者或 AGPM 管理員（完全控制）角色或高級群組原則管理（AGPM）中的必要許可權，才能完成此程式。</span><span class="sxs-lookup"><span data-stu-id="f8d8f-105">A user account with the Approver or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span> <span data-ttu-id="f8d8f-106">請參閱本主題中的「其他注意事項」中的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="f8d8f-106">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="f8d8f-107">控制不受管理的 GPO</span><span class="sxs-lookup"><span data-stu-id="f8d8f-107">To control an uncontrolled GPO</span></span>**

1.  <span data-ttu-id="f8d8f-108">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="f8d8f-108">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="f8d8f-109">在 [詳細資料] 窗格的 [**內容**] 索引標籤上，按一下 [**失控**資料] 索引標籤以顯示不受</span><span class="sxs-lookup"><span data-stu-id="f8d8f-109">On the **Contents** tab in the details pane, click the **Uncontrolled** tab to display the uncontrolled GPOs.</span></span>

3.  <span data-ttu-id="f8d8f-110">以滑鼠右鍵按一下要使用 AGPM 進行控制的 GPO，然後按一下 [**控制**]。</span><span class="sxs-lookup"><span data-stu-id="f8d8f-110">Right-click the GPO to be controlled with AGPM, and then click **Control**.</span></span>

4.  <span data-ttu-id="f8d8f-111">輸入要顯示在 GPO 歷程記錄中的批註，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="f8d8f-111">Type a comment to be displayed in the history of the GPO, and then click **OK**.</span></span>

5.  <span data-ttu-id="f8d8f-112">當**進度**視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="f8d8f-112">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="f8d8f-113">GPO 會從 [無法**控制**] 索引標籤上的清單中移除，並新增至 [**受控**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="f8d8f-113">The GPO is removed from the list on the **Uncontrolled** tab and added to the **Controlled** tab.</span></span>

### <span data-ttu-id="f8d8f-114">其他考量</span><span class="sxs-lookup"><span data-stu-id="f8d8f-114">Additional considerations</span></span>

-   <span data-ttu-id="f8d8f-115">根據預設，您必須是 [核准者] 或 [AGPM 管理員（完全控制）]，才能執行此程式。</span><span class="sxs-lookup"><span data-stu-id="f8d8f-115">By default, you must be an Approver or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="f8d8f-116">具體說來，您必須擁有**清單內容**，並為網域**建立 GPO**許可權。</span><span class="sxs-lookup"><span data-stu-id="f8d8f-116">Specifically, you must have **List Contents** and **Create GPO** permissions for the domain.</span></span>

### <span data-ttu-id="f8d8f-117">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="f8d8f-117">Additional references</span></span>

-   [<span data-ttu-id="f8d8f-118">建立或控制 GPO</span><span class="sxs-lookup"><span data-stu-id="f8d8f-118">Creating or Controlling a GPO</span></span>](creating-or-controlling-a-gpo-agpm40-app.md)

 

 





