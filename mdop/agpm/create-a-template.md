---
title: 建立範本
description: 建立範本
author: dansimp
ms.assetid: 6992bd55-4a4f-401f-9815-c468bac598ef
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9ad57204170fc3f49b01b571d82b00e1faf62de0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802869"
---
# <span data-ttu-id="ac100-103">建立範本</span><span class="sxs-lookup"><span data-stu-id="ac100-103">Create a Template</span></span>


<span data-ttu-id="ac100-104">建立範本可讓您儲存特定版本的群組原則物件（GPO）的所有設定，以做為建立新 Gpo 的起點。</span><span class="sxs-lookup"><span data-stu-id="ac100-104">Creating a template enables you to save all of the settings of a particular version of a Group Policy object (GPO) to use as a starting point for creating new GPOs.</span></span>

<span data-ttu-id="ac100-105">**記事** 範本是一個無法編輯且靜態的 GPO 版本，以做為建立新的可編輯 Gpo 的起點。</span><span class="sxs-lookup"><span data-stu-id="ac100-105">**Note** A template is an uneditable, static version of a GPO for use as a starting point for creating new, editable GPOs.</span></span>

 

<span data-ttu-id="ac100-106">具有 [編輯者] 或 [AGPM 管理員] （完全控制）角色或 [高級群組原則管理] 中的必要許可權的使用者帳戶必須完成此程式。</span><span class="sxs-lookup"><span data-stu-id="ac100-106">A user account with the Editor or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management is required to complete this procedure.</span></span> <span data-ttu-id="ac100-107">請參閱本主題中的「其他注意事項」中的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="ac100-107">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="ac100-108">根據現有的 GPO 建立範本</span><span class="sxs-lookup"><span data-stu-id="ac100-108">To create a template based on an existing GPO</span></span>**

1.  <span data-ttu-id="ac100-109">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="ac100-109">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="ac100-110">在 [詳細資料] 窗格的 [**內容**] 索引標籤上，按一下 [**受控**] 或 [未**控制**] 索引標籤以顯示</span><span class="sxs-lookup"><span data-stu-id="ac100-110">On the **Contents** tab in the details pane, click the **Controlled** or **Uncontrolled** tab to display available GPOs.</span></span>

3.  <span data-ttu-id="ac100-111">以滑鼠右鍵按一下您要建立範本的 GPO，然後按一下 [**另存為範本**]。</span><span class="sxs-lookup"><span data-stu-id="ac100-111">Right-click the GPO from which you want to create a template, then click **Save as Template**.</span></span>

4.  <span data-ttu-id="ac100-112">輸入範本的名稱和批註，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="ac100-112">Type a name for the template and a comment, then click **OK**.</span></span>

5.  <span data-ttu-id="ac100-113">當**進度**視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="ac100-113">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="ac100-114">新範本隨即出現在 [**範本**] 索引標籤上。</span><span class="sxs-lookup"><span data-stu-id="ac100-114">The new template appears on the **Templates** tab.</span></span>

### <span data-ttu-id="ac100-115">其他考量</span><span class="sxs-lookup"><span data-stu-id="ac100-115">Additional considerations</span></span>

-   <span data-ttu-id="ac100-116">根據預設，您必須是編輯者或 AGPM 系統管理員（完全控制）才能執行此程式。</span><span class="sxs-lookup"><span data-stu-id="ac100-116">By default, you must be an Editor or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="ac100-117">具體說來，您必須擁有**清單內容**，並為該網域**建立範本**許可權。</span><span class="sxs-lookup"><span data-stu-id="ac100-117">Specifically, you must have **List Contents** and **Create Template** permissions for the domain.</span></span>

-   <span data-ttu-id="ac100-118">重新命名或刪除範本不會影響從該範本建立的 Gpo。</span><span class="sxs-lookup"><span data-stu-id="ac100-118">Renaming or deleting a template does not impact GPOs created from that template.</span></span>

-   <span data-ttu-id="ac100-119">因為範本不能變更，所以範本沒有歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="ac100-119">Because it cannot be altered, a template does not have a history.</span></span>

### <span data-ttu-id="ac100-120">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="ac100-120">Additional references</span></span>

-   [<span data-ttu-id="ac100-121">建立範本和設定預設範本</span><span class="sxs-lookup"><span data-stu-id="ac100-121">Creating a Template and Setting a Default Template</span></span>](creating-a-template-and-setting-a-default-template.md)

-   [<span data-ttu-id="ac100-122">要求建立新的受控制 GPO</span><span class="sxs-lookup"><span data-stu-id="ac100-122">Request the Creation of a New Controlled GPO</span></span>](request-the-creation-of-a-new-controlled-gpo.md)

 

 





