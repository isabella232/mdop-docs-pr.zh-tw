---
title: 在不同的組織單位測試 GPO
description: 在不同的組織單位測試 GPO
author: dansimp
ms.assetid: 9a9e6d22-74e6-41d8-ac2f-12a1b76ad5a0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 509721fdd775c8669399549f6dcc29cb9ebaea2f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801745"
---
# <span data-ttu-id="758fc-103">在不同的組織單位測試 GPO</span><span class="sxs-lookup"><span data-stu-id="758fc-103">Test a GPO in a Separate Organizational Unit</span></span>


<span data-ttu-id="758fc-104">如果您在部署到生產環境之前，使用測試組織單位（OU）來測試同一個網域中的群組原則物件（Gpo），您必須具備存取測試 OU 所需的許可權。</span><span class="sxs-lookup"><span data-stu-id="758fc-104">If you use a testing organizational unit (OU) to test Group Policy Objects (GPOs) within the same domain before deployment to the production environment, you must have the necessary permissions to access the test OU.</span></span> <span data-ttu-id="758fc-105">使用測試 OU 是選用的。</span><span class="sxs-lookup"><span data-stu-id="758fc-105">Using a test OU is optional.</span></span>

**<span data-ttu-id="758fc-106">使用測試 OU</span><span class="sxs-lookup"><span data-stu-id="758fc-106">To use a test OU</span></span>**

1.  <span data-ttu-id="758fc-107">雖然您已取出 GPO 進行編輯，但在**群群組原則管理主控台**中，按一下您要管理 gpo 的林和網域中的 [**群組原則物件**]。</span><span class="sxs-lookup"><span data-stu-id="758fc-107">Although you have the GPO checked out for editing, in the **Group Policy Management Console**, click **Group Policy Objects** in the forest and domain in which you are managing GPOs.</span></span>

2.  <span data-ttu-id="758fc-108">按一下要測試之 GPO 的取出複本。</span><span class="sxs-lookup"><span data-stu-id="758fc-108">Click the checked out copy of the GPO to be tested.</span></span> <span data-ttu-id="758fc-109">名稱前面會加上**\ [AGPM \]**。</span><span class="sxs-lookup"><span data-stu-id="758fc-109">The name will be preceded by **\[AGPM\]**.</span></span> <span data-ttu-id="758fc-110">（如果沒有列出，請按一下 [**動作**]，然後按一下 **[重新整理**]。</span><span class="sxs-lookup"><span data-stu-id="758fc-110">(If it is not listed, click **Action**, then **Refresh**.</span></span> <span data-ttu-id="758fc-111">依字母順序排序名稱， **\ [AGPM \]** gpo 通常會出現在清單頂端。</span><span class="sxs-lookup"><span data-stu-id="758fc-111">Sort the names alphabetically, and **\[AGPM\]** GPOs will typically appear at the top of the list.)</span></span>

3.  <span data-ttu-id="758fc-112">將 GPO 拖曳到測試 OU。</span><span class="sxs-lookup"><span data-stu-id="758fc-112">Drag the GPO to the test OU.</span></span>

4.  <span data-ttu-id="758fc-113">在詢問是否要在測試 OU 中建立 GPO 連結的對話方塊中，按一下 **[確定**]。</span><span class="sxs-lookup"><span data-stu-id="758fc-113">Click **OK** in the dialog box that asks whether to create a link to the GPO in the test OU.</span></span>

### <span data-ttu-id="758fc-114">其他考量</span><span class="sxs-lookup"><span data-stu-id="758fc-114">Additional considerations</span></span>

-   <span data-ttu-id="758fc-115">測試完成時，在 GPO 中檢入會自動刪除 GPO 的取出複本連結。</span><span class="sxs-lookup"><span data-stu-id="758fc-115">When testing is complete, checking in the GPO automatically deletes the link to the checked-out copy of the GPO.</span></span>

### <span data-ttu-id="758fc-116">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="758fc-116">Additional references</span></span>

-   [<span data-ttu-id="758fc-117">使用測試環境</span><span class="sxs-lookup"><span data-stu-id="758fc-117">Using a Test Environment</span></span>](using-a-test-environment.md)

 

 





