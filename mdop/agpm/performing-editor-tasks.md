---
title: 執行編輯器工作
description: 執行編輯器工作
author: dansimp
ms.assetid: b1e62615-2e02-460e-81d1-4a3fbe59f62d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a3b911a0142875ef906de9b522148236fe656435
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801889"
---
# <span data-ttu-id="ddeb8-103">執行編輯器工作</span><span class="sxs-lookup"><span data-stu-id="ddeb8-103">Performing Editor Tasks</span></span>


<span data-ttu-id="ddeb8-104">編輯者是由 AGPM 系統管理員（完全控制）所授權的人員，以變更群組原則物件（Gpo）及建立 GPO 範本。</span><span class="sxs-lookup"><span data-stu-id="ddeb8-104">An Editor is a person authorized by an AGPM Administrator (Full Control) to make changes to Group Policy objects (GPOs) and create GPO templates.</span></span> <span data-ttu-id="ddeb8-105">此外，編輯工具也可以啟動建立或刪除 GPO 的程式，但預設必須要求核准者核准。</span><span class="sxs-lookup"><span data-stu-id="ddeb8-105">Additionally, an Editor can initiate the process of creating or deleting a GPO, but by default must request approval from an Approver.</span></span>

<span data-ttu-id="ddeb8-106">**重要** 確定您連線到 Gpo 的中央封存。</span><span class="sxs-lookup"><span data-stu-id="ddeb8-106">**Important** Ensure that you are connecting to the central archive for GPOs.</span></span> <span data-ttu-id="ddeb8-107">如需詳細資訊，請參閱[設定 AGPM 服務器](configure-the-agpm-server-connection-reviewer.md)連線。</span><span class="sxs-lookup"><span data-stu-id="ddeb8-107">For more information, see [Configure the AGPM Server Connection](configure-the-agpm-server-connection-reviewer.md).</span></span>

 

-   [<span data-ttu-id="ddeb8-108">建立、控制或匯入 GPO</span><span class="sxs-lookup"><span data-stu-id="ddeb8-108">Creating, Controlling, or Importing a GPO</span></span>](creating-controlling-or-importing-a-gpo-editor.md)

-   [<span data-ttu-id="ddeb8-109">編輯 GPO</span><span class="sxs-lookup"><span data-stu-id="ddeb8-109">Editing a GPO</span></span>](editing-a-gpo.md)

-   [<span data-ttu-id="ddeb8-110">建立範本和設定預設範本</span><span class="sxs-lookup"><span data-stu-id="ddeb8-110">Creating a Template and Setting a Default Template</span></span>](creating-a-template-and-setting-a-default-template.md)

-   [<span data-ttu-id="ddeb8-111">刪除 GPO</span><span class="sxs-lookup"><span data-stu-id="ddeb8-111">Delete a GPO</span></span>](delete-a-gpo-editor.md)

<span data-ttu-id="ddeb8-112">**記事** 因為編輯者角色包含檢閱者角色的許可權，所以編輯工具也可以查看設定及比較 Gpo。</span><span class="sxs-lookup"><span data-stu-id="ddeb8-112">**Note** Because the Editor role includes the permissions for the Reviewer role, an Editor can also review settings and compare GPOs.</span></span> <span data-ttu-id="ddeb8-113">如需詳細資訊，請參閱[執行檢閱者](performing-reviewer-tasks.md)工作。</span><span class="sxs-lookup"><span data-stu-id="ddeb8-113">See [Performing Reviewer Tasks](performing-reviewer-tasks.md) for more information.</span></span>

 

### <span data-ttu-id="ddeb8-114">其他考量</span><span class="sxs-lookup"><span data-stu-id="ddeb8-114">Additional considerations</span></span>

<span data-ttu-id="ddeb8-115">根據預設，系統會為 Editor 角色提供下列許可權：</span><span class="sxs-lookup"><span data-stu-id="ddeb8-115">By default, the following permissions are provided for the Editor role:</span></span>

-   <span data-ttu-id="ddeb8-116">清單內容</span><span class="sxs-lookup"><span data-stu-id="ddeb8-116">List Contents</span></span>

-   <span data-ttu-id="ddeb8-117">讀取設定</span><span class="sxs-lookup"><span data-stu-id="ddeb8-117">Read Settings</span></span>

-   <span data-ttu-id="ddeb8-118">編輯設定</span><span class="sxs-lookup"><span data-stu-id="ddeb8-118">Edit Settings</span></span>

-   <span data-ttu-id="ddeb8-119">建立範本</span><span class="sxs-lookup"><span data-stu-id="ddeb8-119">Create Template</span></span>

 

 





