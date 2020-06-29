---
title: 設定記錄和追蹤
description: 設定記錄和追蹤
author: dansimp
ms.assetid: 419231f9-e9db-4f91-a7cf-a0a73db25256
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fa3dfa71edb25f6641ade595cd4469e846410ac2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802030"
---
# <span data-ttu-id="ced9d-103">設定記錄和追蹤</span><span class="sxs-lookup"><span data-stu-id="ced9d-103">Configure Logging and Tracing</span></span>


<span data-ttu-id="ced9d-104">您可以使用系統管理範本來集中設定 [高級群組原則管理（AGPM）] 的 [選用記錄] 和 [追蹤]。</span><span class="sxs-lookup"><span data-stu-id="ced9d-104">You can centrally configure optional logging and tracing for Advanced Group Policy Management (AGPM) using Administrative templates.</span></span>

<span data-ttu-id="ced9d-105">具有 AGPM 系統管理員（完全控制）角色的使用者帳戶、在這些程式中建立 GPO 所使用的核准者使用者帳戶，或是必須具備高級群組原則管理中所需許可權的使用者帳戶才能完成這些程式。</span><span class="sxs-lookup"><span data-stu-id="ced9d-105">A user account with the AGPM Administrator (Full Control) role, the user account of the Approver who created the GPO used in these procedures, or a user account with the necessary permissions in Advanced Group Policy Management is required to complete these procedures.</span></span> <span data-ttu-id="ced9d-106">此外，必須擁有 AGPM 服務器存取權的使用者帳戶才能在 AGPM 服務器上開機記錄。</span><span class="sxs-lookup"><span data-stu-id="ced9d-106">Additionally, a user account with access to the AGPM Server is required to initiate logging on the AGPM Server.</span></span> <span data-ttu-id="ced9d-107">請參閱本主題中的「其他注意事項」中的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="ced9d-107">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="ced9d-108">設定 AGPM 的記錄和追蹤功能</span><span class="sxs-lookup"><span data-stu-id="ced9d-108">To configure logging and tracing for AGPM</span></span>**

1.  <span data-ttu-id="ced9d-109">在 [**群組原則管理] 主控台**樹狀結構中，針對您要開啟記錄和追蹤的所有群組原則管理員，編輯已套用的 GPO。</span><span class="sxs-lookup"><span data-stu-id="ced9d-109">In the **Group Policy Management Console** tree, edit a GPO that is applied to all Group Policy administrators for which you want to turn on logging and tracing.</span></span> <span data-ttu-id="ced9d-110">（如需詳細資訊，請參閱[編輯 GPO](editing-a-gpo.md)）。</span><span class="sxs-lookup"><span data-stu-id="ced9d-110">(For more information, see [Editing a GPO](editing-a-gpo.md).)</span></span>

2.  <span data-ttu-id="ced9d-111">在 [**群組原則物件編輯器**] 中，按一下 [電腦設定]、[**系統\*\*\*\*管理範本**] 和 [ **Windows 元件**]。</span><span class="sxs-lookup"><span data-stu-id="ced9d-111">In the **Group Policy Object Editor**, click **Computer Configuration**, **Administrative Templates**, and **Windows Components**.</span></span>

3.  <span data-ttu-id="ced9d-112">如果 [ **Windows 元件**] 下並未列出 [ **AGPM** ]：</span><span class="sxs-lookup"><span data-stu-id="ced9d-112">If **AGPM** is not listed under **Windows Components**:</span></span>

    1.  <span data-ttu-id="ced9d-113">以滑鼠右鍵按一下 [**管理範本**]，然後按一下 [**新增/移除範本**]。</span><span class="sxs-lookup"><span data-stu-id="ced9d-113">Right-click **Administrative Templates** and click **Add/Remove Templates**.</span></span>

    2.  <span data-ttu-id="ced9d-114">按一下 [**新增**]，選取 [ **agpm** ] 或 [ **agpm] .adm**，按一下 [**開啟**]，然後按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="ced9d-114">Click **Add**, select **agpm.admx** or **agpm.adm**, click **Open**, and then click **Close**.</span></span>

4.  <span data-ttu-id="ced9d-115">在 [ **Windows 元件**] 底下，按兩下 [ **AGPM**]。</span><span class="sxs-lookup"><span data-stu-id="ced9d-115">Under **Windows Components**, double-click **AGPM**.</span></span>

5.  <span data-ttu-id="ced9d-116">在 [詳細資料] 窗格中，按兩下 [ **AGPM 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="ced9d-116">In the details pane, double-click **AGPM Logging**.</span></span>

6.  <span data-ttu-id="ced9d-117">在 [ **AGPM 記錄屬性**] 視窗中，按一下 [**啟用**]，然後設定記錄中要記錄的詳細資料層級。</span><span class="sxs-lookup"><span data-stu-id="ced9d-117">In the **AGPM Logging Properties** window, click **Enabled**, and configure the level of detail to record in the logs.</span></span>

7.  <span data-ttu-id="ced9d-118">按一下 \[確定\] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ced9d-118">Click **OK**.</span></span>

8.  <span data-ttu-id="ced9d-119">關閉 [**群組原則物件編輯器**]。</span><span class="sxs-lookup"><span data-stu-id="ced9d-119">Close the **Group Policy Object Editor**.</span></span> <span data-ttu-id="ced9d-120">（如需詳細資訊，請參閱[部署 GPO](deploy-a-gpo.md)）。更新群組原則之後，您必須重新開機 AGPM 服務，才能在 AGPM 服務器上開始記錄。</span><span class="sxs-lookup"><span data-stu-id="ced9d-120">(For more information, see [Deploy a GPO](deploy-a-gpo.md).) After Group Policy is updated, you must restart the AGPM Service to begin logging on the AGPM Server.</span></span> <span data-ttu-id="ced9d-121">群組原則管理員必須關閉並重新啟動 GPMC，才能開始記錄其電腦。</span><span class="sxs-lookup"><span data-stu-id="ced9d-121">Group Policy administrators must close and restart the GPMC to begin logging on their computers.</span></span>

    <span data-ttu-id="ced9d-122">**追蹤檔案位置**：</span><span class="sxs-lookup"><span data-stu-id="ced9d-122">**Trace file locations**:</span></span>

    -   <span data-ttu-id="ced9d-123">用戶端：%LocalAppData%\\Microsoft\\AGPM\\agpm.log</span><span class="sxs-lookup"><span data-stu-id="ced9d-123">Client: %LocalAppData%\\Microsoft\\AGPM\\agpm.log</span></span>

    -   <span data-ttu-id="ced9d-124">伺服器：%ProgramData%\\Microsoft\\AGPM\\agpmserv.log</span><span class="sxs-lookup"><span data-stu-id="ced9d-124">Server: %ProgramData%\\Microsoft\\AGPM\\agpmserv.log</span></span>

### <span data-ttu-id="ced9d-125">其他考量</span><span class="sxs-lookup"><span data-stu-id="ced9d-125">Additional considerations</span></span>

-   <span data-ttu-id="ced9d-126">您必須能夠編輯和部署 GPO，才能設定 AGPM 記錄和追蹤功能。</span><span class="sxs-lookup"><span data-stu-id="ced9d-126">You must be able to edit and deploy a GPO to configure AGPM logging and tracing.</span></span> <span data-ttu-id="ced9d-127">如需更多詳細資料，請參閱[編輯 gpo](editing-a-gpo.md)及[部署 gpo](deploy-a-gpo.md) 。</span><span class="sxs-lookup"><span data-stu-id="ced9d-127">See [Editing a GPO](editing-a-gpo.md) and [Deploy a GPO](deploy-a-gpo.md) for additional detail.</span></span>

### <span data-ttu-id="ced9d-128">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="ced9d-128">Additional references</span></span>

-   [<span data-ttu-id="ced9d-129">執行 AGPM 系統管理員工作</span><span class="sxs-lookup"><span data-stu-id="ced9d-129">Performing AGPM Administrator Tasks</span></span>](performing-agpm-administrator-tasks.md)

 

 





