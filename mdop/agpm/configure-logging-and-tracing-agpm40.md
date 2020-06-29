---
title: 設定記錄和追蹤
description: 設定記錄和追蹤
author: dansimp
ms.assetid: 2418cb6a-7189-4080-8fe2-9c8d47dec62c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: bfc56d418ae83cbc5db24246bfac057305629df7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802029"
---
# <span data-ttu-id="3210e-103">設定記錄和追蹤</span><span class="sxs-lookup"><span data-stu-id="3210e-103">Configure Logging and Tracing</span></span>


<span data-ttu-id="3210e-104">您可以使用 [系統管理範本] 來集中設定選用記錄和追蹤。</span><span class="sxs-lookup"><span data-stu-id="3210e-104">You can centrally configure optional logging and tracing using Administrative templates.</span></span> <span data-ttu-id="3210e-105">在診斷任何與高級群組原則管理（AGPM）相關的問題時，這可能會很有説明。</span><span class="sxs-lookup"><span data-stu-id="3210e-105">This may be helpful when diagnosing any problems related to Advanced Group Policy Management (AGPM).</span></span>

<span data-ttu-id="3210e-106">具有 AGPM 系統管理員（完全控制）角色的使用者帳戶、在這些程式中建立群組原則物件（GPO）的核准者使用者帳戶，或是在 AGPM 中有必要許可權的使用者帳戶完成這些程式。</span><span class="sxs-lookup"><span data-stu-id="3210e-106">A user account with the AGPM Administrator (Full Control) role, the user account of the Approver who created the Group Policy Object (GPO) used in these procedures, or a user account with the necessary permissions in AGPM is required to complete these procedures.</span></span> <span data-ttu-id="3210e-107">此外，必須擁有 AGPM 服務器存取權的使用者帳戶才能在 AGPM 服務器上開機記錄。</span><span class="sxs-lookup"><span data-stu-id="3210e-107">Additionally, a user account with access to the AGPM Server is required to initiate logging on the AGPM Server.</span></span> <span data-ttu-id="3210e-108">請參閱本主題中的「其他注意事項」中的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="3210e-108">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="3210e-109">設定 AGPM 的記錄和追蹤功能</span><span class="sxs-lookup"><span data-stu-id="3210e-109">To configure logging and tracing for AGPM</span></span>**

1.  <span data-ttu-id="3210e-110">在 [**群組原則管理] 主控台**樹狀結構中，針對您要開啟記錄和追蹤的所有群組原則管理員，編輯已套用的 GPO。</span><span class="sxs-lookup"><span data-stu-id="3210e-110">In the **Group Policy Management Console** tree, edit a GPO that is applied to all Group Policy administrators for which you want to turn on logging and tracing.</span></span> <span data-ttu-id="3210e-111">（如需詳細資訊，請參閱[編輯 GPO](editing-a-gpo-agpm40.md)）。</span><span class="sxs-lookup"><span data-stu-id="3210e-111">(For more information, see [Editing a GPO](editing-a-gpo-agpm40.md).)</span></span>

2.  <span data-ttu-id="3210e-112">按一下 [**群組原則管理編輯器**] 視窗中的 [**電腦**設定]、[**原則**]、[系統**管理範本**]、[ **Windows 元件**] 和 [ **AGPM**]</span><span class="sxs-lookup"><span data-stu-id="3210e-112">In the **Group Policy Management Editor** window, click **Computer Configuration**, **Policies**, **Administrative Templates**, **Windows Components**, and **AGPM**.</span></span>

3.  <span data-ttu-id="3210e-113">在 [詳細資料] 窗格中，按兩下 [ **AGPM：設定記錄**]。</span><span class="sxs-lookup"><span data-stu-id="3210e-113">In the details pane, double-click **AGPM: Configure logging**.</span></span>

4.  <span data-ttu-id="3210e-114">在 [**屬性**] 視窗中，按一下 [**啟用**]，然後設定記錄中要記錄的詳細資料層級。</span><span class="sxs-lookup"><span data-stu-id="3210e-114">In the **Properties** window, click **Enabled**, and configure the level of detail to record in the logs.</span></span>

5.  <span data-ttu-id="3210e-115">按一下 \[確定\] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3210e-115">Click **OK**.</span></span>

6.  <span data-ttu-id="3210e-116">關閉 [**群組原則管理編輯器**] 視窗。</span><span class="sxs-lookup"><span data-stu-id="3210e-116">Close the **Group Policy Management Editor** window.</span></span> <span data-ttu-id="3210e-117">（如需詳細資訊，請參閱[部署 GPO](deploy-a-gpo-agpm40.md)）。更新群組原則之後，您必須重新開機 AGPM 服務，才能啟動、修改或停止 AGPM 服務器上的記錄。</span><span class="sxs-lookup"><span data-stu-id="3210e-117">(For more information, see [Deploy a GPO](deploy-a-gpo-agpm40.md).) After Group Policy is updated, you must restart the AGPM Service to start, modify, or stop logging on the AGPM Server.</span></span> <span data-ttu-id="3210e-118">群組原則管理員必須關閉並重新啟動 GPMC，才能啟動、修改或停止在他們的電腦上記錄。</span><span class="sxs-lookup"><span data-stu-id="3210e-118">Group Policy administrators must close and restart the GPMC to start, modify, or stop logging on their computers.</span></span>

    <span data-ttu-id="3210e-119">**追蹤檔案位置**：</span><span class="sxs-lookup"><span data-stu-id="3210e-119">**Trace file locations**:</span></span>

    -   <span data-ttu-id="3210e-120">用戶端：%LocalAppData%\\Microsoft\\AGPM\\agpm.log</span><span class="sxs-lookup"><span data-stu-id="3210e-120">Client: %LocalAppData%\\Microsoft\\AGPM\\agpm.log</span></span>

    -   <span data-ttu-id="3210e-121">伺服器：%ProgramData%\\Microsoft\\AGPM\\agpmserv.log</span><span class="sxs-lookup"><span data-stu-id="3210e-121">Server: %ProgramData%\\Microsoft\\AGPM\\agpmserv.log</span></span>

### <span data-ttu-id="3210e-122">其他考量</span><span class="sxs-lookup"><span data-stu-id="3210e-122">Additional considerations</span></span>

-   <span data-ttu-id="3210e-123">您必須能夠編輯和部署 GPO，才能設定 AGPM 記錄和追蹤功能。</span><span class="sxs-lookup"><span data-stu-id="3210e-123">You must be able to edit and deploy a GPO to configure AGPM logging and tracing.</span></span> <span data-ttu-id="3210e-124">如需更多詳細資料，請參閱[編輯 gpo](editing-a-gpo-agpm40.md)及[部署 gpo](deploy-a-gpo-agpm40.md) 。</span><span class="sxs-lookup"><span data-stu-id="3210e-124">See [Editing a GPO](editing-a-gpo-agpm40.md) and [Deploy a GPO](deploy-a-gpo-agpm40.md) for additional detail.</span></span>

### <span data-ttu-id="3210e-125">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="3210e-125">Additional references</span></span>

-   [<span data-ttu-id="3210e-126">設定進階群組原則管理</span><span class="sxs-lookup"><span data-stu-id="3210e-126">Configuring Advanced Group Policy Management</span></span>](configuring-advanced-group-policy-management-agpm40.md)

 

 





