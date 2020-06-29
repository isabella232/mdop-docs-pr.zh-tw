---
title: 使用測試環境
description: 使用測試環境
author: dansimp
ms.assetid: 86295084-b39e-4040-bb3f-15c3c1e99b1a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1264d9fe6f922a7e61bcd069581c7bd5e39b7787
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801737"
---
# <span data-ttu-id="da2c4-103">使用測試環境</span><span class="sxs-lookup"><span data-stu-id="da2c4-103">Use a Test Environment</span></span>


<span data-ttu-id="da2c4-104">如果您在部署到生產環境之前，使用測試組織單位（OU）來測試群組原則物件（Gpo），您必須具備存取測試 OU 所需的許可權。</span><span class="sxs-lookup"><span data-stu-id="da2c4-104">If you use a testing organizational unit (OU) to test Group Policy Objects (GPOs) before deployment to the production environment, you must have the necessary permissions to access the test OU.</span></span> <span data-ttu-id="da2c4-105">使用測試 OU 是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="da2c4-105">The use of a test OU is optional.</span></span>

**<span data-ttu-id="da2c4-106">使用測試 OU</span><span class="sxs-lookup"><span data-stu-id="da2c4-106">To use a test OU</span></span>**

1.  <span data-ttu-id="da2c4-107">當您已取出 GPO 進行編輯時，請在 [**群組原則管理主控台**] 中，按一下您管理 gpo 的林和網域中的 [**群組原則物件**]。</span><span class="sxs-lookup"><span data-stu-id="da2c4-107">While you have the GPO checked out for editing, in the **Group Policy Management Console**, click **Group Policy Objects** in the forest and domain in which you are managing GPOs.</span></span>

2.  <span data-ttu-id="da2c4-108">按一下要測試之 GPO 的取出複本。</span><span class="sxs-lookup"><span data-stu-id="da2c4-108">Click the checked out copy of the GPO to be tested.</span></span> <span data-ttu-id="da2c4-109">名稱前面會有**\ [已取出 \]**。</span><span class="sxs-lookup"><span data-stu-id="da2c4-109">The name will be preceded with **\[Checked Out\]**.</span></span> <span data-ttu-id="da2c4-110">（如果沒有列出，請按一下 [**動作**]，然後按一下 **[重新整理**]。</span><span class="sxs-lookup"><span data-stu-id="da2c4-110">(If it is not listed, click **Action**, then **Refresh**.</span></span> <span data-ttu-id="da2c4-111">依字母順序排序名稱， **\ [已取出的 \]** gpo 通常會顯示在清單頂端。</span><span class="sxs-lookup"><span data-stu-id="da2c4-111">Sort the names alphabetically, and **\[Checked Out\]** GPOs will typically appear at the top of the list.)</span></span>

3.  <span data-ttu-id="da2c4-112">將 GPO 拖放到測試 OU 中。</span><span class="sxs-lookup"><span data-stu-id="da2c4-112">Drag and drop the GPO to the test OU.</span></span>

4.  <span data-ttu-id="da2c4-113">按一下對話方塊中的 **[確定**]，詢問是否要在測試 OU 中建立 GPO 的連結。</span><span class="sxs-lookup"><span data-stu-id="da2c4-113">Click **OK** in the dialog box asking whether to create a link to the GPO in the test OU.</span></span>

### <span data-ttu-id="da2c4-114">其他考量</span><span class="sxs-lookup"><span data-stu-id="da2c4-114">Additional considerations</span></span>

-   <span data-ttu-id="da2c4-115">測試完成時，在 GPO 中檢入會自動刪除 GPO 的取出複本連結。</span><span class="sxs-lookup"><span data-stu-id="da2c4-115">When testing is complete, checking in the GPO automatically deletes the link to the checked-out copy of the GPO.</span></span>

### <span data-ttu-id="da2c4-116">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="da2c4-116">Additional references</span></span>

-   [<span data-ttu-id="da2c4-117">編輯 GPO</span><span class="sxs-lookup"><span data-stu-id="da2c4-117">Editing a GPO</span></span>](editing-a-gpo-agpm30ops.md)

 

 





