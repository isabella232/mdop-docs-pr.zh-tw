---
title: 匯出 GPO 到檔案
description: 匯出 GPO 到檔案
author: dansimp
ms.assetid: 0d01b1f7-a6a4-4d0d-9aa7-2d6f1ae93d9d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4622930cb0e5b439649cc0445ae2b3d02d7d3224
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802782"
---
# <span data-ttu-id="3b5ba-103">匯出 GPO 到檔案</span><span class="sxs-lookup"><span data-stu-id="3b5ba-103">Export a GPO to a File</span></span>


<span data-ttu-id="3b5ba-104">您可以將受控的群組原則物件（GPO）匯出到 CAB 檔案，以便將它複製到另一個樹林中的網域，然後將該 GPO 匯入該網域中的 [高級組原則管理] （AGPM）。</span><span class="sxs-lookup"><span data-stu-id="3b5ba-104">You can export a controlled Group Policy Object (GPO) to a CAB file so that you can copy it to a domain in another forest and import the GPO into Advanced Group Policy Management (AGPM) in that domain.</span></span> <span data-ttu-id="3b5ba-105">如需如何將 GPO 設定匯入新的或現有的 GPO 的相關資訊，請參閱從檔案匯[入 gpo](import-a-gpo-from-a-file-ed.md)。</span><span class="sxs-lookup"><span data-stu-id="3b5ba-105">For information about how to import GPO settings into a new or existing GPO, see [Import a GPO from a File](import-a-gpo-from-a-file-ed.md).</span></span>

<span data-ttu-id="3b5ba-106">具有 [編輯者] 或 [AGPM 管理員] （完全控制）角色的使用者帳戶，或 [高級群組原則管理] （AGPM）中的必要許可權，才能完成此程式。</span><span class="sxs-lookup"><span data-stu-id="3b5ba-106">A user account with the Editor or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span><span data-ttu-id="3b5ba-107">請參閱本主題中的「其他注意事項」中的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="3b5ba-107">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="3b5ba-108">將 GPO 匯出至檔案</span><span class="sxs-lookup"><span data-stu-id="3b5ba-108">To export a GPO to a file</span></span>**

1.  <span data-ttu-id="3b5ba-109">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="3b5ba-109">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="3b5ba-110">在 [**內容**] 索引標籤上，按一下 [**受控**] 索引標籤以顯示受控制的 gpo。</span><span class="sxs-lookup"><span data-stu-id="3b5ba-110">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

3.  <span data-ttu-id="3b5ba-111">以滑鼠右鍵按一下該 GPO，然後按一下 [**匯出到**]。</span><span class="sxs-lookup"><span data-stu-id="3b5ba-111">Right-click the GPO, and then click **Export to**.</span></span>

4.  <span data-ttu-id="3b5ba-112">輸入您要匯出 GPO 之檔案的檔案名，然後按一下 [**匯出**]。</span><span class="sxs-lookup"><span data-stu-id="3b5ba-112">Enter a file name for the file to which you want to export the GPO, and then click **Export**.</span></span> <span data-ttu-id="3b5ba-113">如果檔案不存在，就會建立檔案。</span><span class="sxs-lookup"><span data-stu-id="3b5ba-113">If the file does not exist, it is created.</span></span> <span data-ttu-id="3b5ba-114">如果它已存在，則會被取代。</span><span class="sxs-lookup"><span data-stu-id="3b5ba-114">If it already exists, it is replaced.</span></span>

### <span data-ttu-id="3b5ba-115">其他考量</span><span class="sxs-lookup"><span data-stu-id="3b5ba-115">Additional considerations</span></span>

-   <span data-ttu-id="3b5ba-116">根據預設，您必須是編輯者或 AGPM 系統管理員（完全控制）才能執行此程式。</span><span class="sxs-lookup"><span data-stu-id="3b5ba-116">By default, you must be an Editor or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="3b5ba-117">具體說來，您必須擁有**清單內容**、**閱讀設定**及 gpo 的**匯出 gpo**許可權。</span><span class="sxs-lookup"><span data-stu-id="3b5ba-117">Specifically, you must have **List Contents**, **Read Settings**, and **Export GPO** permissions for the GPO.</span></span>

### <span data-ttu-id="3b5ba-118">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="3b5ba-118">Additional references</span></span>

-   [<span data-ttu-id="3b5ba-119">使用測試環境</span><span class="sxs-lookup"><span data-stu-id="3b5ba-119">Using a Test Environment</span></span>](using-a-test-environment.md)

 

 





