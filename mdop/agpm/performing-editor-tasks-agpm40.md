---
title: 執行編輯器工作
description: 執行編輯器工作
author: dansimp
ms.assetid: 81976a01-2a95-4256-b703-9fb3c884ef34
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b8e23bb91d8762d19eed9ae817967ba5a57505a9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802605"
---
# <span data-ttu-id="cbd7a-103">執行編輯器工作</span><span class="sxs-lookup"><span data-stu-id="cbd7a-103">Performing Editor Tasks</span></span>


<span data-ttu-id="cbd7a-104">在 [高級群組原則管理] （AGPM）中，編輯者是由 AGPM 系統管理員（完全控制）所授權的人員，用來變更群群組原則物件（Gpo）及建立 GPO 範本。</span><span class="sxs-lookup"><span data-stu-id="cbd7a-104">In Advanced Group Policy Management (AGPM), an Editor is a person authorized by an AGPM Administrator (Full Control) to change Group Policy Objects (GPOs) and create GPO templates.</span></span> <span data-ttu-id="cbd7a-105">此外，編輯者還可以要求建立、刪除或還原 GPO。</span><span class="sxs-lookup"><span data-stu-id="cbd7a-105">Additionally, an Editor can request that a GPO be created, deleted, or restored.</span></span> <span data-ttu-id="cbd7a-106">核准者必須核准要實施的要求。</span><span class="sxs-lookup"><span data-stu-id="cbd7a-106">An Approver must approve the request for it to be implemented.</span></span> <span data-ttu-id="cbd7a-107">編輯工具可以將 GPO 匯出至檔案，以便將它複製到另一個樹林中的網域，並匯入從其他網域複製的 GPO。</span><span class="sxs-lookup"><span data-stu-id="cbd7a-107">An Editor can export a GPO to a file so that it can be copied to a domain in another forest, and import a GPO that was copied from another domain.</span></span>

<span data-ttu-id="cbd7a-108">**重要** 確認您是連線到 Gpo 的中央封存。</span><span class="sxs-lookup"><span data-stu-id="cbd7a-108">**Important** Make sure that you are connecting to the central archive for GPOs.</span></span> <span data-ttu-id="cbd7a-109">如需詳細資訊，請參閱[設定 AGPM 服務器](configure-an-agpm-server-connection-agpm40.md)連線。</span><span class="sxs-lookup"><span data-stu-id="cbd7a-109">For more information, see [Configure an AGPM Server Connection](configure-an-agpm-server-connection-agpm40.md).</span></span>

 

-   [<span data-ttu-id="cbd7a-110">建立或控制 GPO</span><span class="sxs-lookup"><span data-stu-id="cbd7a-110">Creating or Controlling a GPO</span></span>](creating-or-controlling-a-gpo-agpm40-ed.md)

-   [<span data-ttu-id="cbd7a-111">編輯 GPO</span><span class="sxs-lookup"><span data-stu-id="cbd7a-111">Editing a GPO</span></span>](editing-a-gpo-agpm40.md)

-   [<span data-ttu-id="cbd7a-112">使用測試環境</span><span class="sxs-lookup"><span data-stu-id="cbd7a-112">Using a Test Environment</span></span>](using-a-test-environment.md)

-   [<span data-ttu-id="cbd7a-113">要求部署 GPO</span><span class="sxs-lookup"><span data-stu-id="cbd7a-113">Request Deployment of a GPO</span></span>](request-deployment-of-a-gpo-agpm40.md)

-   [<span data-ttu-id="cbd7a-114">建立範本和設定預設範本</span><span class="sxs-lookup"><span data-stu-id="cbd7a-114">Creating a Template and Setting a Default Template</span></span>](creating-a-template-and-setting-a-default-template-agpm40.md)

-   [<span data-ttu-id="cbd7a-115">刪除或還原 GPO</span><span class="sxs-lookup"><span data-stu-id="cbd7a-115">Deleting or Restoring a GPO</span></span>](deleting-or-restoring-a-gpo-agpm40.md)

<span data-ttu-id="cbd7a-116">**記事** 因為編輯者角色包含檢閱者角色的許可權，所以編輯工具也可以查看設定及比較 Gpo。</span><span class="sxs-lookup"><span data-stu-id="cbd7a-116">**Note** Because the Editor role includes the permissions for the Reviewer role, an Editor can also review settings and compare GPOs.</span></span> <span data-ttu-id="cbd7a-117">如需詳細資訊，請參閱[執行檢閱者](performing-reviewer-tasks-agpm40.md)工作。</span><span class="sxs-lookup"><span data-stu-id="cbd7a-117">See [Performing Reviewer Tasks](performing-reviewer-tasks-agpm40.md) for more information.</span></span>

 

### <span data-ttu-id="cbd7a-118">其他考量</span><span class="sxs-lookup"><span data-stu-id="cbd7a-118">Additional considerations</span></span>

<span data-ttu-id="cbd7a-119">根據預設，系統會為 Editor 角色提供下列許可權：</span><span class="sxs-lookup"><span data-stu-id="cbd7a-119">By default, the following permissions are provided for the Editor role:</span></span>

-   <span data-ttu-id="cbd7a-120">清單內容</span><span class="sxs-lookup"><span data-stu-id="cbd7a-120">List Contents</span></span>

-   <span data-ttu-id="cbd7a-121">讀取設定</span><span class="sxs-lookup"><span data-stu-id="cbd7a-121">Read Settings</span></span>

-   <span data-ttu-id="cbd7a-122">編輯設定</span><span class="sxs-lookup"><span data-stu-id="cbd7a-122">Edit Settings</span></span>

-   <span data-ttu-id="cbd7a-123">匯出 GPO</span><span class="sxs-lookup"><span data-stu-id="cbd7a-123">Export GPO</span></span>

-   <span data-ttu-id="cbd7a-124">匯入 GPO</span><span class="sxs-lookup"><span data-stu-id="cbd7a-124">Import GPO</span></span>

-   <span data-ttu-id="cbd7a-125">建立範本</span><span class="sxs-lookup"><span data-stu-id="cbd7a-125">Create Template</span></span>

 

 





