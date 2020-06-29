---
title: 設定電子郵件通知
description: 設定電子郵件通知
author: dansimp
ms.assetid: 6e152de0-4376-4963-8d1a-3e7f5866d30f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 46e8d00c2446a0185de30bbd1f39a7e3eaf90080
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802033"
---
# <span data-ttu-id="4db69-103">設定電子郵件通知</span><span class="sxs-lookup"><span data-stu-id="4db69-103">Configure E-Mail Notification</span></span>


<span data-ttu-id="4db69-104">當編輯人員或檢閱者嘗試建立、部署或刪除群組原則物件（GPO）時，會將此動作的要求傳送至指定的電子郵件地址或位址，以便讓核准者評估該要求並執行或拒絕它。</span><span class="sxs-lookup"><span data-stu-id="4db69-104">When an Editor or a Reviewer attempts to create, deploy, or delete a Group Policy object (GPO), a request for this action is sent to a designated e-mail address or addresses so that an Approver can evaluate the request and implement or deny it.</span></span> <span data-ttu-id="4db69-105">您可以決定要傳送通知的電子郵件地址或位址，以及傳送通知的別名。</span><span class="sxs-lookup"><span data-stu-id="4db69-105">You determine the e-mail address or addresses to which notifications are sent, as well as the alias from which notifications are sent.</span></span>

<span data-ttu-id="4db69-106">具有 AGPM 系統管理員（完全控制）角色的使用者帳戶或高級群組原則管理中的必要許可權，才能完成此程式。</span><span class="sxs-lookup"><span data-stu-id="4db69-106">A user account with the AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management is required to complete this procedure.</span></span> <span data-ttu-id="4db69-107">請參閱本主題中的「其他注意事項」中的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="4db69-107">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="4db69-108">若要設定 AGPM 的電子郵件通知</span><span class="sxs-lookup"><span data-stu-id="4db69-108">To configure e-mail notification for AGPM</span></span>**

1.  <span data-ttu-id="4db69-109">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="4db69-109">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="4db69-110">在 [詳細資料] 窗格中，按一下 [**網域委派**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="4db69-110">In the details pane, click the **Domain Delegation** tab.</span></span>

3.  <span data-ttu-id="4db69-111">在 [**發件**人] 欄位中，輸入您應該傳送通知的 AGPM 電子郵件別名。</span><span class="sxs-lookup"><span data-stu-id="4db69-111">In the **From** field, type the e-mail alias for AGPM from which notifications should be sent.</span></span>

4.  <span data-ttu-id="4db69-112">在 [收件者] 欄位中，輸入應接收核准要求**的以逗號**分隔的電子郵件地址清單。</span><span class="sxs-lookup"><span data-stu-id="4db69-112">In the **To** field, type a comma-delimited list of e-mail addresses of Approvers who should receive requests for approval.</span></span>

5.  <span data-ttu-id="4db69-113">在 [ **SMTP 伺服器**] 欄位中，輸入有效的 SMTP 郵件伺服器。</span><span class="sxs-lookup"><span data-stu-id="4db69-113">In the **SMTP server** field, type a valid SMTP mail server.</span></span>

6.  <span data-ttu-id="4db69-114">在 [**使用者名稱**] 和 [**密碼**] 欄位中，輸入擁有 SMTP 服務存取權的使用者認證。</span><span class="sxs-lookup"><span data-stu-id="4db69-114">In the **User name** and **Password** fields, type the credentials of a user with access to the SMTP service.</span></span>

7.  <span data-ttu-id="4db69-115">按一下 **\[Apply\]** (套用)。</span><span class="sxs-lookup"><span data-stu-id="4db69-115">Click **Apply**.</span></span>

### <span data-ttu-id="4db69-116">其他考量</span><span class="sxs-lookup"><span data-stu-id="4db69-116">Additional considerations</span></span>

-   <span data-ttu-id="4db69-117">根據預設，您必須是 AGPM 系統管理員（完全控制）才能執行此程式。</span><span class="sxs-lookup"><span data-stu-id="4db69-117">By default, you must be an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="4db69-118">具體說來，您必須擁有 [**清單內容**] 和 [修改網域的**選項**] 許可權。</span><span class="sxs-lookup"><span data-stu-id="4db69-118">Specifically, you must have **List Contents** and **Modify Options** permissions for the domain.</span></span>

-   <span data-ttu-id="4db69-119">AGPM 的電子郵件通知是網域層級設定。</span><span class="sxs-lookup"><span data-stu-id="4db69-119">E-mail notification for AGPM is a domain-level setting.</span></span> <span data-ttu-id="4db69-120">您可以在每個網域的 [**網域委派**] 索引標籤上提供不同的核准者電子郵件地址或 AGPM 電子郵件別名，或在整個環境中使用相同的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="4db69-120">You can provide different Approver e-mail addresses or AGPM e-mail aliases on each domain's **Domain Delegation** tab, or use the same e-mail addresses throughout your environment.</span></span>

### <span data-ttu-id="4db69-121">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="4db69-121">Additional references</span></span>

-   [<span data-ttu-id="4db69-122">執行 AGPM 系統管理員工作</span><span class="sxs-lookup"><span data-stu-id="4db69-122">Performing AGPM Administrator Tasks</span></span>](performing-agpm-administrator-tasks.md)

 

 





