---
title: 從生產匯入 GPO
description: 從生產匯入 GPO
author: dansimp
ms.assetid: ad90f13e-e73c-400f-b86f-c12f2e75d19d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c78cba0f69bf282fb720051fc1c074b41ec0a6c4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802714"
---
# <span data-ttu-id="0a92c-103">從生產匯入 GPO</span><span class="sxs-lookup"><span data-stu-id="0a92c-103">Import a GPO from Production</span></span>


<span data-ttu-id="0a92c-104">如果您在 [高級群組原則管理] （AGPM）外，在受管理的群群組原則物件（GPO）中進行變更，您可以從生產環境中匯入 GPO 複本，並將其儲存到封存，以使封存和生產環境保持一致的狀態。</span><span class="sxs-lookup"><span data-stu-id="0a92c-104">If changes are made to a controlled Group Policy Object (GPO) outside of Advanced Group Policy Management (AGPM), you can import a copy of the GPO from the production environment and save it to the archive to bring the archive and the production environment to a consistent state.</span></span> <span data-ttu-id="0a92c-105">（若要匯入不受管理的 GPO，請控制該 GPO。</span><span class="sxs-lookup"><span data-stu-id="0a92c-105">(To import an uncontrolled GPO, control the GPO.</span></span> <span data-ttu-id="0a92c-106">請參閱[控制不受管理的 GPO](control-an-uncontrolled-gpo-agpm30ops.md)。）</span><span class="sxs-lookup"><span data-stu-id="0a92c-106">See [Control an Uncontrolled GPO](control-an-uncontrolled-gpo-agpm30ops.md).)</span></span>

<span data-ttu-id="0a92c-107">擁有 [編輯者]、[核准者] 或 [AGPM 管理員（完全控制）] 角色或必要許可權 inAGPM 的使用者帳戶需要完成此程式。</span><span class="sxs-lookup"><span data-stu-id="0a92c-107">A user account with the Editor, Approver, or AGPM Administrator (Full Control) role or necessary permissions inAGPM is required to complete this procedure.</span></span> <span data-ttu-id="0a92c-108">請參閱本主題中的「其他注意事項」中的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="0a92c-108">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="0a92c-109">從生產環境匯入 GPO</span><span class="sxs-lookup"><span data-stu-id="0a92c-109">To import a GPO from the production environment</span></span>**

1.  <span data-ttu-id="0a92c-110">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="0a92c-110">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="0a92c-111">在 [**內容**] 索引標籤上，按一下 [**受控**] 索引標籤以顯示受控制的 gpo。</span><span class="sxs-lookup"><span data-stu-id="0a92c-111">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

3.  <span data-ttu-id="0a92c-112">以滑鼠右鍵按一下該 GPO，然後按一下 [**從生產匯入**]。</span><span class="sxs-lookup"><span data-stu-id="0a92c-112">Right-click the GPO, and then click **Import from Production**.</span></span>

4.  <span data-ttu-id="0a92c-113">輸入 GPO 之審核追蹤的批註，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="0a92c-113">Type a comment for the audit trail of the GPO, and then click **OK**.</span></span>

### <span data-ttu-id="0a92c-114">其他考量</span><span class="sxs-lookup"><span data-stu-id="0a92c-114">Additional considerations</span></span>

-   <span data-ttu-id="0a92c-115">根據預設，您必須是編輯者、核准者或 AGPM 系統管理員（完全控制），才能執行此程式。</span><span class="sxs-lookup"><span data-stu-id="0a92c-115">By default, you must be an Editor, Approver, or AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="0a92c-116">具體說來，您必須擁有**清單內容**，並**編輯設定**、**部署 GPO**或刪除 gpo 的**gpo**許可權。</span><span class="sxs-lookup"><span data-stu-id="0a92c-116">Specifically, you must have **List Contents** and either **Edit Settings**, **Deploy GPO**, or **Delete GPO** permissions for the GPO.</span></span>

### <span data-ttu-id="0a92c-117">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="0a92c-117">Additional references</span></span>

-   [<span data-ttu-id="0a92c-118">建立、控制或匯入 GPO</span><span class="sxs-lookup"><span data-stu-id="0a92c-118">Creating, Controlling, or Importing a GPO</span></span>](creating-controlling-or-importing-a-gpo-editor-agpm30ops.md)

 

 





