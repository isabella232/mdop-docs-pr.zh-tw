---
title: 執行核准者工作
description: 執行核准者工作
author: dansimp
ms.assetid: 9f711824-191b-4b4b-a1c6-a3b2116006a4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d8e4a848608a3be1dbb0632f0145b4fc1d1bc631
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802630"
---
# <span data-ttu-id="753fe-103">執行核准者工作</span><span class="sxs-lookup"><span data-stu-id="753fe-103">Performing Approver Tasks</span></span>


<span data-ttu-id="753fe-104">核准者是由 AGPM 管理員（完全控制）所授權的人員，可用於建立、部署及刪除群組原則物件（Gpo），以及核准或拒絕要求（通常來自編輯者）來建立、部署或刪除 Gpo。</span><span class="sxs-lookup"><span data-stu-id="753fe-104">An Approver is a person authorized by an AGPM Administrator (Full Control) to create, deploy, and delete Group Policy Objects (GPOs) and to approve or reject requests (typically from Editors) to create, deploy, or delete GPOs.</span></span>

<span data-ttu-id="753fe-105">**重要** 確認您是連線到 Gpo 的中央封存。</span><span class="sxs-lookup"><span data-stu-id="753fe-105">**Important** Make sure that you are connecting to the central archive for GPOs.</span></span> <span data-ttu-id="753fe-106">如需詳細資訊，請參閱[設定 AGPM 服務器](configure-an-agpm-server-connection-reviewer-agpm30ops.md)連線。</span><span class="sxs-lookup"><span data-stu-id="753fe-106">For more information, see [Configure an AGPM Server Connection](configure-an-agpm-server-connection-reviewer-agpm30ops.md).</span></span>

 

-   [<span data-ttu-id="753fe-107">核准或拒絕擱置動作</span><span class="sxs-lookup"><span data-stu-id="753fe-107">Approve or Reject a Pending Action</span></span>](approve-or-reject-a-pending-action-agpm30ops.md)

-   [<span data-ttu-id="753fe-108">建立、控制或匯入 GPO</span><span class="sxs-lookup"><span data-stu-id="753fe-108">Creating, Controlling, or Importing a GPO</span></span>](creating-controlling-or-importing-a-gpo-editor-agpm30ops.md)

-   [<span data-ttu-id="753fe-109">存回 GPO</span><span class="sxs-lookup"><span data-stu-id="753fe-109">Check In a GPO</span></span>](check-in-a-gpo-agpm30ops.md)

-   [<span data-ttu-id="753fe-110">部署 GPO</span><span class="sxs-lookup"><span data-stu-id="753fe-110">Deploy a GPO</span></span>](deploy-a-gpo-agpm30ops.md)

-   [<span data-ttu-id="753fe-111">回復至舊版 GPO</span><span class="sxs-lookup"><span data-stu-id="753fe-111">Roll Back to a Previous Version of a GPO</span></span>](roll-back-to-a-previous-version-of-a-gpo-agpm30ops.md)

-   [<span data-ttu-id="753fe-112">刪除、還原或摧毀 GPO</span><span class="sxs-lookup"><span data-stu-id="753fe-112">Deleting, Restoring, or Destroying a GPO</span></span>](deleting-restoring-or-destroying-a-gpo-agpm30ops.md)

<span data-ttu-id="753fe-113">**記事** 在核准 GPO 前，核准者應該檢查其所包含的原則設定。</span><span class="sxs-lookup"><span data-stu-id="753fe-113">**Note** Before approving a GPO, an Approver should review the policy settings that it contains.</span></span> <span data-ttu-id="753fe-114">核准者角色包含檢閱者角色的許可權，讓核准者可以查看原則設定及比較 Gpo。</span><span class="sxs-lookup"><span data-stu-id="753fe-114">The Approver role includes the permissions for the Reviewer role, so that an Approver can review policy settings and compare GPOs.</span></span> <span data-ttu-id="753fe-115">如需詳細資訊，請參閱[執行檢閱者](performing-reviewer-tasks-agpm30ops.md)工作。</span><span class="sxs-lookup"><span data-stu-id="753fe-115">See [Performing Reviewer Tasks](performing-reviewer-tasks-agpm30ops.md) for more information.</span></span>

 

### <span data-ttu-id="753fe-116">其他考量</span><span class="sxs-lookup"><span data-stu-id="753fe-116">Additional considerations</span></span>

<span data-ttu-id="753fe-117">根據預設，系統會為核准者角色提供下列許可權：</span><span class="sxs-lookup"><span data-stu-id="753fe-117">By default, the following permissions are provided for the Approver role:</span></span>

-   <span data-ttu-id="753fe-118">清單內容</span><span class="sxs-lookup"><span data-stu-id="753fe-118">List Contents</span></span>

-   <span data-ttu-id="753fe-119">讀取設定</span><span class="sxs-lookup"><span data-stu-id="753fe-119">Read Settings</span></span>

-   <span data-ttu-id="753fe-120">建立 GPO</span><span class="sxs-lookup"><span data-stu-id="753fe-120">Create GPO</span></span>

-   <span data-ttu-id="753fe-121">部署 GPO</span><span class="sxs-lookup"><span data-stu-id="753fe-121">Deploy GPO</span></span>

-   <span data-ttu-id="753fe-122">刪除 GPO</span><span class="sxs-lookup"><span data-stu-id="753fe-122">Delete GPO</span></span>

<span data-ttu-id="753fe-123">此外，核准者還能完全控制自己建立或控制的 Gpo。</span><span class="sxs-lookup"><span data-stu-id="753fe-123">Also, an Approver has full control over GPOs that he created or controlled.</span></span>

 

 





