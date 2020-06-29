---
title: 檢閱 GPO 設定
description: 檢閱 GPO 設定
author: dansimp
ms.assetid: e82570b2-d8ce-4bf0-8ad7-8910409f3041
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 681492f423266ce3722bb1a657ee93527c6bdd7b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801774"
---
# <span data-ttu-id="ebdf6-103">檢閱 GPO 設定</span><span class="sxs-lookup"><span data-stu-id="ebdf6-103">Review GPO Settings</span></span>


<span data-ttu-id="ebdf6-104">您可以在任何版本的群群組原則物件（GPO）中產生以 HTML 與 XML 為基礎的報告來檢查設定。</span><span class="sxs-lookup"><span data-stu-id="ebdf6-104">You can generate HTML-based and XML-based reports for reviewing settings within any version of a Group Policy object (GPO).</span></span>

<span data-ttu-id="ebdf6-105">具有 [檢閱者]、[編輯]、[核准者] 或 [AGPM 管理員（完全控制）] 角色的使用者帳戶，或 [高級群組原則管理] 中的必要許可權必須完成此程式。</span><span class="sxs-lookup"><span data-stu-id="ebdf6-105">A user account with the Reviewer, Editor, Approver, or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management is required to complete this procedure.</span></span> <span data-ttu-id="ebdf6-106">請參閱本主題中的「其他注意事項」中的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="ebdf6-106">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="ebdf6-107">若要查看任何版本的 GPO 中的設定</span><span class="sxs-lookup"><span data-stu-id="ebdf6-107">To review settings in any version of a GPO</span></span>**

1.  <span data-ttu-id="ebdf6-108">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="ebdf6-108">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="ebdf6-109">在 [詳細資料] 窗格的 [**內容**] 索引標籤上，按一下索引標籤以顯示 [gpo]。</span><span class="sxs-lookup"><span data-stu-id="ebdf6-109">On the **Contents** tab in the details pane, click a tab to display GPOs.</span></span>

3.  <span data-ttu-id="ebdf6-110">按兩下該 GPO 以顯示其歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="ebdf6-110">Double-click the GPO to display its history.</span></span>

4.  <span data-ttu-id="ebdf6-111">以滑鼠右鍵按一下要查看其設定的 GPO 版本，按一下 [**設定**]，然後按一下 [ **HTML 報表**] 或 [ **XML 報表**]，以顯示 GPO 設定的摘要。</span><span class="sxs-lookup"><span data-stu-id="ebdf6-111">Right-click the GPO version for which to review the settings, click **Settings**, and then click **HTML Report** or **XML Report** to display a summary of the GPO's settings.</span></span>

### <span data-ttu-id="ebdf6-112">其他考量</span><span class="sxs-lookup"><span data-stu-id="ebdf6-112">Additional considerations</span></span>

-   <span data-ttu-id="ebdf6-113">根據預設，您必須是檢閱者、編輯者或 AGPM 管理員（完全控制），才能執行此程式。</span><span class="sxs-lookup"><span data-stu-id="ebdf6-113">By default, you must be a Reviewer, an Editor, an Approver, or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="ebdf6-114">具體來說，您必須擁有 [**清單內容**] 和 [**讀取設定**] 許可權給 GPO。</span><span class="sxs-lookup"><span data-stu-id="ebdf6-114">Specifically, you must have **List Contents** and **Read Settings** permissions for the GPO.</span></span> <span data-ttu-id="ebdf6-115">此外，若要顯示 Gpo 清單，您必須擁有該網域的 [**清單內容**] 許可權。</span><span class="sxs-lookup"><span data-stu-id="ebdf6-115">Also, to display the list of GPOs, you must have **List Contents** permission for the domain.</span></span>

### <span data-ttu-id="ebdf6-116">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="ebdf6-116">Additional references</span></span>

-   [<span data-ttu-id="ebdf6-117">執行檢閱者工作</span><span class="sxs-lookup"><span data-stu-id="ebdf6-117">Performing Reviewer Tasks</span></span>](performing-reviewer-tasks.md)

 

 





