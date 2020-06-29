---
title: 設定預設範本
description: 設定預設範本
author: dansimp
ms.assetid: 84edbd69-451b-4c10-a898-781d4b75d09c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dec198126e98e1267589fdf252e158a0b1181b05
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802545"
---
# <span data-ttu-id="92952-103">設定預設範本</span><span class="sxs-lookup"><span data-stu-id="92952-103">Set a Default Template</span></span>


<span data-ttu-id="92952-104">就像編輯者一樣，您可以指定哪些可用範本將是為所有群組原則管理員建立新的群組原則物件（Gpo）所建議的預設範本。</span><span class="sxs-lookup"><span data-stu-id="92952-104">As an Editor, you can specify which of the available templates will be the default template suggested for all Group Policy administrators creating new Group Policy Objects (GPOs).</span></span>

<span data-ttu-id="92952-105">**記事** 範本是一個無法編輯且靜態的 GPO 版本，以做為建立新的可編輯 Gpo 的起點。</span><span class="sxs-lookup"><span data-stu-id="92952-105">**Note** A template is an uneditable, static version of a GPO for use as a starting point for creating new, editable GPOs.</span></span>

 

<span data-ttu-id="92952-106">具有 [編輯者] 或 [AGPM 管理員] （完全控制）角色的使用者帳戶，或 [高級群組原則管理] （AGPM）中的必要許可權，才能完成此程式。</span><span class="sxs-lookup"><span data-stu-id="92952-106">A user account with the Editor or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span> <span data-ttu-id="92952-107">請參閱本主題中的「其他注意事項」中的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="92952-107">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="92952-108">若要設定建立新 Gpo 時使用的預設範本</span><span class="sxs-lookup"><span data-stu-id="92952-108">To set the default template for use when creating new GPOs</span></span>**

1.  <span data-ttu-id="92952-109">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="92952-109">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="92952-110">在 [詳細資料] 窗格的 [**內容**] 索引標籤上，按一下 [**範本**] 索引標籤以顯示可用範本。</span><span class="sxs-lookup"><span data-stu-id="92952-110">On the **Contents** tab in the details pane, click the **Templates** tab to display available templates.</span></span>

3.  <span data-ttu-id="92952-111">以滑鼠右鍵按一下您要設定為預設值的範本，然後按一下 [**設成預設值**]。</span><span class="sxs-lookup"><span data-stu-id="92952-111">Right-click the template that you want to set as the default, and then click **Set as Default**.</span></span>

4.  <span data-ttu-id="92952-112">按一下 **[是]** 以進行確認。</span><span class="sxs-lookup"><span data-stu-id="92952-112">Click **Yes** to confirm.</span></span>

5.  <span data-ttu-id="92952-113">當**進度**視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="92952-113">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="92952-114">預設範本具有藍色圖示，且狀態在 [**範本**] 索引標籤上會標示為 **[範本（預設）** ]。</span><span class="sxs-lookup"><span data-stu-id="92952-114">The default template has a blue icon and the state is identified as **Template (default)** on the **Templates** tab.</span></span>

### <span data-ttu-id="92952-115">其他考量</span><span class="sxs-lookup"><span data-stu-id="92952-115">Additional considerations</span></span>

-   <span data-ttu-id="92952-116">根據預設，您必須是編輯者或 AGPM 系統管理員（完全控制）才能執行此程式。</span><span class="sxs-lookup"><span data-stu-id="92952-116">By default, you must be an Editor or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="92952-117">具體說來，您必須擁有**清單內容**，並為該網域**建立範本**許可權。</span><span class="sxs-lookup"><span data-stu-id="92952-117">Specifically, you must have **List Contents** and **Create Template** permissions for the domain.</span></span>

-   <span data-ttu-id="92952-118">將範本設定為預設值後，該範本就會是初始在新的 [**受管理的 gpo** ] 對話方塊中選取的範本（當群組原則系統管理員建立新的 gpo 時）。</span><span class="sxs-lookup"><span data-stu-id="92952-118">After you set a template as the default, that template will be the one initially selected in the **New Controlled GPO** dialog box when Group Policy administrators create new GPOs.</span></span> <span data-ttu-id="92952-119">不過，它們會有選取任何其他 GPO 範本的選項，包括\*\* &lt; 空白 gpo &gt; \*\*，不包含任何設定。</span><span class="sxs-lookup"><span data-stu-id="92952-119">However, they will have the option to select any other GPO template, including **&lt;Empty GPO&gt;**, which does not include any settings.</span></span>

-   <span data-ttu-id="92952-120">重新命名或刪除範本不會影響從該範本建立的 Gpo。</span><span class="sxs-lookup"><span data-stu-id="92952-120">Renaming or deleting a template does not impact GPOs created from that template.</span></span>

-   <span data-ttu-id="92952-121">因為範本不能變更，所以範本沒有歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="92952-121">Because it cannot be altered, a template does not have a history.</span></span>

### <span data-ttu-id="92952-122">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="92952-122">Additional references</span></span>

-   [<span data-ttu-id="92952-123">建立範本和設定預設範本</span><span class="sxs-lookup"><span data-stu-id="92952-123">Creating a Template and Setting a Default Template</span></span>](creating-a-template-and-setting-a-default-template-agpm30ops.md)

-   [<span data-ttu-id="92952-124">要求建立新的受控制 GPO</span><span class="sxs-lookup"><span data-stu-id="92952-124">Request the Creation of a New Controlled GPO</span></span>](request-the-creation-of-a-new-controlled-gpo-agpm30ops.md)

 

 





