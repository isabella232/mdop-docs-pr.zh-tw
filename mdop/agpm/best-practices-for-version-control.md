---
title: 版本控制最佳做法
description: 版本控制最佳做法
author: dansimp
ms.assetid: 89067f6a-f7ea-4dad-999d-118284cf6c5a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ed91408faeb8968175976382f9dd97d45becddb5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802122"
---
# <span data-ttu-id="edcb5-103">版本控制最佳做法</span><span class="sxs-lookup"><span data-stu-id="edcb5-103">Best Practices for Version Control</span></span>


<span data-ttu-id="edcb5-104">Microsoft 高級群組原則管理（AGPM）提供群組原則物件（Gpo）的版本控制，就像 Microsoft Visual SourceSafe®提供原始程式碼的版本控制。</span><span class="sxs-lookup"><span data-stu-id="edcb5-104">Microsoft Advanced Group Policy Management (AGPM) provides version control for Group Policy Objects (GPOs) much like Microsoft Visual SourceSafe® provides version control for source code.</span></span> <span data-ttu-id="edcb5-105">開發人員可以使用 Visual SourceSafe 來管理每個來源檔案的多個版本。</span><span class="sxs-lookup"><span data-stu-id="edcb5-105">Developers can use Visual SourceSafe to manage multiple versions of each source file.</span></span> <span data-ttu-id="edcb5-106">群組原則系統管理員可以使用 AGPM 來對 Gpo 執行相同的動作。</span><span class="sxs-lookup"><span data-stu-id="edcb5-106">Group Policy administrators can use AGPM to do the same for GPOs.</span></span> <span data-ttu-id="edcb5-107">當您使用 AGPM 時，群組原則管理員應該瞭解適用于任何版本控制系統的最佳做法：</span><span class="sxs-lookup"><span data-stu-id="edcb5-107">When you use AGPM, Group Policy administrators should be aware of best practices that apply to any version control system:</span></span>

-   <span data-ttu-id="edcb5-108">**日期及時間：** AGPM 會將每個版本的 GPO 標記為日期和時間。</span><span class="sxs-lookup"><span data-stu-id="edcb5-108">**Date and time:** AGPM stamps each version of a GPO with the date and time.</span></span> <span data-ttu-id="edcb5-109">若要確保歷程記錄準確無誤，尤其是當您在多部電腦上編輯 Gpo 時，請確定每個電腦都將它的時鐘與一個權威性時間源同步處理。</span><span class="sxs-lookup"><span data-stu-id="edcb5-109">To ensure that history is accurate, especially when you edit GPOs on more than one computer, make sure that each computer synchronizes its clock with one authoritative time source.</span></span>

-   <span data-ttu-id="edcb5-110">**完成編輯 gpo 時，請將其存回：** 常見的情況是，編輯者會取出 Gpo，並忘記將其存回封存。</span><span class="sxs-lookup"><span data-stu-id="edcb5-110">**Check in GPOs when you are finished editing them:** It is common for Editors to check out GPOs and forget to check them back into the archive.</span></span> <span data-ttu-id="edcb5-111">不過，這可以防止其他群組原則管理員變更 GPO。</span><span class="sxs-lookup"><span data-stu-id="edcb5-111">However, this can prevent other Group Policy administrators from changing the GPO.</span></span> <span data-ttu-id="edcb5-112">當您完成編輯時，請務必立即將 Gpo 檢入回 AGPM。</span><span class="sxs-lookup"><span data-stu-id="edcb5-112">Always check GPOs back in to AGPM immediately when you are finished editing.</span></span>

-   <span data-ttu-id="edcb5-113">**經常儲存變更：** 當您編輯 GPO 時，請經常儲存變更。</span><span class="sxs-lookup"><span data-stu-id="edcb5-113">**Save changes frequently:** When you edit a GPO, save changes frequently.</span></span> <span data-ttu-id="edcb5-114">大多數的編輯者會取出一個 GPO，進行許多變更，然後將該 GPO 檢查到封存。</span><span class="sxs-lookup"><span data-stu-id="edcb5-114">Most Editors check out a GPO, make many changes, and then check the GPO into the archive.</span></span> <span data-ttu-id="edcb5-115">請改為將 GPO 定期檢查到封存，然後再次查看該檔案。</span><span class="sxs-lookup"><span data-stu-id="edcb5-115">Instead, check the GPO into the archive regularly, and then check it out again.</span></span> <span data-ttu-id="edcb5-116">在您變更每個設定（不建議）或在進行相關變更群組之後，在 GPO 中進行檢查時，其詳細資料可能相當小，就是在 GPO 中進行檢查。</span><span class="sxs-lookup"><span data-stu-id="edcb5-116">The detail can be as small as checking in the GPO after you change every setting (not recommended) or checking in the GPO after you make groups of related changes.</span></span> <span data-ttu-id="edcb5-117">結果是每個 GPO 的記錄，可協助您解決問題。</span><span class="sxs-lookup"><span data-stu-id="edcb5-117">The result is a better-documented history for each GPO that can help when troubleshooting issues.</span></span>

-   <span data-ttu-id="edcb5-118">**經常部署 gpo：** 請勿讓尚未部署的新與編輯的 Gpo 積累在封存的大量數位中。</span><span class="sxs-lookup"><span data-stu-id="edcb5-118">**Deploy GPOs frequently:** Do not let new and edited GPOs that have not yet been deployed accumulate in large numbers in the archive.</span></span> <span data-ttu-id="edcb5-119">相反地，請儘快部署新的和編輯的 Gpo，讓它們在生產環境上的影響最小。</span><span class="sxs-lookup"><span data-stu-id="edcb5-119">Instead, deploy new and edited GPOs as soon as possible so that they have a minimum effect on the production environment.</span></span> <span data-ttu-id="edcb5-120">一次部署許多新的和已編輯的 Gpo 可能會危害生產環境。</span><span class="sxs-lookup"><span data-stu-id="edcb5-120">Deploying many new and edited GPOs at one time can jeopardize the production environment.</span></span>

-   <span data-ttu-id="edcb5-121">**當您存回 gpo 時，請記錄變更的用途：** 任何檢閱者都可以比較 GPO 的版本，以查看兩者間的特定變更。</span><span class="sxs-lookup"><span data-stu-id="edcb5-121">**Document the purpose of changes when you check in GPOs:** Any Reviewer can compare versions of a GPO to see specific changes between the two.</span></span> <span data-ttu-id="edcb5-122">記錄這些特定變更時，不會加上任何值。</span><span class="sxs-lookup"><span data-stu-id="edcb5-122">Documenting those specific changes adds no value.</span></span> <span data-ttu-id="edcb5-123">相反地，您可以透過查看差異報告，來記錄變更的目的和用途，而不是記錄審查者能看到哪些內容。</span><span class="sxs-lookup"><span data-stu-id="edcb5-123">Instead, document the intent and purpose of a change instead of documenting what Reviewers can see by viewing difference reports.</span></span> <span data-ttu-id="edcb5-124">版本批註應該為比較報告增添價值，並協助審查員瞭解編輯者對 GPO 進行變更的原因。</span><span class="sxs-lookup"><span data-stu-id="edcb5-124">Version comments should add value to the comparison report and help a Reviewer understand why the Editor changed the GPO.</span></span>

-   <span data-ttu-id="edcb5-125">在**部署之前先在實驗室中測試 gpo：** 將 Gpo 部署到生產環境，而不先進行測試，就會有風險。</span><span class="sxs-lookup"><span data-stu-id="edcb5-125">**Test GPOs in a lab before you deploy:** Deploying GPOs to the production environment without first testing them is risky.</span></span> <span data-ttu-id="edcb5-126">您可以在實驗室環境中測試 Gpo，方法是將其連結至包含測試電腦和使用者的組織單位，然後確認它們正常運作。</span><span class="sxs-lookup"><span data-stu-id="edcb5-126">Instead, test GPOs in a lab environment by linking them to an organizational unit that contains test computers and users, and then verifying that they function correctly.</span></span> <span data-ttu-id="edcb5-127">在驗證實驗室中的每個 GPO 之後，將該 GPO 部署到生產環境。</span><span class="sxs-lookup"><span data-stu-id="edcb5-127">After verifying each GPO in the lab, deploy the GPO to the production environment.</span></span>

### <span data-ttu-id="edcb5-128">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="edcb5-128">Additional references</span></span>

-   [<span data-ttu-id="edcb5-129">Microsoft 進階群組原則管理 3.0 操作指南</span><span class="sxs-lookup"><span data-stu-id="edcb5-129">Operations Guide for Microsoft Advanced Group Policy Management 3.0</span></span>](operations-guide-for-microsoft-advanced-group-policy-management-30-agpm30ops.md)

 

 





