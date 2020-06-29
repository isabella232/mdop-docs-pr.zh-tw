---
title: 要求部署 GPO
description: 要求部署 GPO
author: dansimp
ms.assetid: f44ae0fb-bcf7-477b-b99e-9dd6a55ee597
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7c8d1ac1ab157f744a6d5f2ede9bb281b553f718
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801817"
---
# <span data-ttu-id="cb6c9-103">要求部署 GPO</span><span class="sxs-lookup"><span data-stu-id="cb6c9-103">Request Deployment of a GPO</span></span>


<span data-ttu-id="cb6c9-104">在您修改並檢查群組原則物件（GPO）之後，請部署該 GPO，如此會在生產環境中生效。</span><span class="sxs-lookup"><span data-stu-id="cb6c9-104">After you have modified and checked in a Group Policy Object (GPO), deploy the GPO, so it will take effect in the production environment.</span></span>

<span data-ttu-id="cb6c9-105">必須具備高級群組原則管理（AGPM）中具有編輯者角色或必要許可權的使用者帳戶，才能完成此程式。</span><span class="sxs-lookup"><span data-stu-id="cb6c9-105">A user account with the Editor role or necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span> <span data-ttu-id="cb6c9-106">請參閱本主題中的「其他注意事項」中的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="cb6c9-106">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="cb6c9-107">向生產環境要求 GPO 部署</span><span class="sxs-lookup"><span data-stu-id="cb6c9-107">To request the deployment of a GPO to the production environment</span></span>**

1.  <span data-ttu-id="cb6c9-108">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="cb6c9-108">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="cb6c9-109">在 [**內容**] 索引標籤上，按一下 [**受控**] 索引標籤以顯示受控制的 gpo。</span><span class="sxs-lookup"><span data-stu-id="cb6c9-109">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

3.  <span data-ttu-id="cb6c9-110">以滑鼠右鍵按一下要部署的 GPO，然後按一下 [**部署**]。</span><span class="sxs-lookup"><span data-stu-id="cb6c9-110">Right-click the GPO to be deployed, and then click **Deploy**.</span></span>

4.  <span data-ttu-id="cb6c9-111">除非您是核准者或 AGPM 管理員，或是擁有部署 Gpo 的特殊許可權，否則您必須提交部署的要求。</span><span class="sxs-lookup"><span data-stu-id="cb6c9-111">Unless you are an Approver or AGPM Administrator or have special permission to deploy GPOs, you must submit a request for deployment.</span></span> <span data-ttu-id="cb6c9-112">若要接收申請的複本，請在 [**抄送**] 欄位中輸入您的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="cb6c9-112">To receive a copy of the request, type your e-mail address in the **Cc** field.</span></span> <span data-ttu-id="cb6c9-113">輸入要顯示在該 GPO 之歷程**記錄**中的批註，然後按一下 [**提交**]。</span><span class="sxs-lookup"><span data-stu-id="cb6c9-113">Type a comment to be displayed in the **History** for the GPO, and then click **Submit**.</span></span>

5.  <span data-ttu-id="cb6c9-114">當**進度**視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="cb6c9-114">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="cb6c9-115">GPO 會顯示在 [**擱置**] 索引標籤上的 [gpo] 清單中。當核准者核准您的要求之後，該 GPO 就會從 [**擱置**] 索引標籤移至 [**受控**] 索引標籤，並進行部署。</span><span class="sxs-lookup"><span data-stu-id="cb6c9-115">The GPO is displayed on the list of GPOs on the **Pending** tab. When an Approver has approved your request, the GPO will be moved from the **Pending** tab to the **Controlled** tab and be deployed.</span></span>

### <span data-ttu-id="cb6c9-116">其他考量</span><span class="sxs-lookup"><span data-stu-id="cb6c9-116">Additional considerations</span></span>

-   <span data-ttu-id="cb6c9-117">根據預設，您必須是編輯器才能執行此程式。</span><span class="sxs-lookup"><span data-stu-id="cb6c9-117">By default, you must be an Editor to perform this procedure.</span></span> <span data-ttu-id="cb6c9-118">具體說來，您必須擁有 [**清單內容**] 和 [**編輯設定**] GPO 的 [設定] 許可權。</span><span class="sxs-lookup"><span data-stu-id="cb6c9-118">Specifically, you must have **List Contents** and **Edit Settings** permissions for the GPO.</span></span>

-   <span data-ttu-id="cb6c9-119">若要在獲核准前收回您的要求，請按一下 [**待定**] 索引標籤。以滑鼠右鍵按一下該 GPO，然後按一下 [**收回**]。</span><span class="sxs-lookup"><span data-stu-id="cb6c9-119">To withdraw your request before it has been approved, click the **Pending** tab. Right-click the GPO, and then click **Withdraw**.</span></span> <span data-ttu-id="cb6c9-120">GPO 將會傳回 [**受控**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="cb6c9-120">The GPO will be returned to the **Controlled** tab.</span></span>

### <span data-ttu-id="cb6c9-121">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="cb6c9-121">Additional references</span></span>

-   [<span data-ttu-id="cb6c9-122">編輯 GPO</span><span class="sxs-lookup"><span data-stu-id="cb6c9-122">Editing a GPO</span></span>](editing-a-gpo-agpm30ops.md)

 

 





