---
title: 設定 AGPM 伺服器連線
description: 設定 AGPM 伺服器連線
author: dansimp
ms.assetid: 6062b77b-2fd7-442c-ad1b-6f14419ebd5f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 42f2ac4b219bed99db1ceae12859b992f4976db9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802917"
---
# <span data-ttu-id="8ba5e-103">設定 AGPM 伺服器連線</span><span class="sxs-lookup"><span data-stu-id="8ba5e-103">Configure AGPM Server Connections</span></span>


<span data-ttu-id="8ba5e-104">每個受控制的群組原則物件（GPO）的所有版本都會儲存在中央封存中，讓群組原則系統管理員可以在離線時查看及修改 Gpo，而不會立即影響每個 GPO 的部署版本。</span><span class="sxs-lookup"><span data-stu-id="8ba5e-104">All versions of each controlled Group Policy Object (GPO) are stored in a central archive so that Group Policy administrators can view and modify GPOs offline without immediately impacting the deployed version of each GPO.</span></span>

<span data-ttu-id="8ba5e-105">使用 AGPM 系統管理員（完全控制）角色的使用者帳戶、在這些程式中建立 GPO 所用的核准者使用者帳戶，或是在高級群組原則管理（AGPM）中具有必要許可權的使用者帳戶，都必須完成這些程式來集中設定所有群組原則管理員的封存位置。</span><span class="sxs-lookup"><span data-stu-id="8ba5e-105">A user account with the AGPM Administrator (Full Control) role, the user account of the Approver who created the GPO used in these procedures, or a user account with the necessary permissions in Advanced Group Policy Management (AGPM) is required to complete these procedures for centrally configuring archive locations for all Group Policy administrators.</span></span> <span data-ttu-id="8ba5e-106">請參閱本主題中的「其他注意事項」中的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="8ba5e-106">Review the details in "Additional considerations" in this topic.</span></span>

## <span data-ttu-id="8ba5e-107">配置 AGPM 服務器連線</span><span class="sxs-lookup"><span data-stu-id="8ba5e-107">Configuring AGPM Server connections</span></span>


<span data-ttu-id="8ba5e-108">就像 AGPM 管理員一樣，您可以透過集中設定關聯的設定，以確保所有群組原則管理員都連線到相同的 AGPM 服務器。</span><span class="sxs-lookup"><span data-stu-id="8ba5e-108">As an AGPM Administrator, you can ensure that all Group Policy administrators connect to the same AGPM Server by centrally configuring the associated setting.</span></span> <span data-ttu-id="8ba5e-109">如果您的環境需要部分或所有網域的個別 AGPM 服務器，請將這些額外的 AGPM 服務器設定為預設的例外狀況。</span><span class="sxs-lookup"><span data-stu-id="8ba5e-109">If your environment requires separate AGPM Servers for some or all domains, configure those additional AGPM Servers as exceptions to the default.</span></span> <span data-ttu-id="8ba5e-110">如果您沒有集中設定 AGPM 服務器連線，每個群組原則管理員都必須手動設定要針對每個網域顯示的 AGPM 服務器。</span><span class="sxs-lookup"><span data-stu-id="8ba5e-110">If you do not centrally configure AGPM Server connections, each Group Policy administrator must manually configure the AGPM Server to be displayed for each domain.</span></span>

-   [<span data-ttu-id="8ba5e-111">針對所有群組原則管理員設定 AGPM 服務器連線</span><span class="sxs-lookup"><span data-stu-id="8ba5e-111">Configure an AGPM Server connection for all Group Policy administrators</span></span>](#bkmk-defaultarchiveloc)

-   [<span data-ttu-id="8ba5e-112">針對所有群組原則管理員設定其他 AGPM 服務器連線</span><span class="sxs-lookup"><span data-stu-id="8ba5e-112">Configure additional AGPM Server connections for all Group Policy administrators</span></span>](#bkmk-additionalarchiveloc)

-   [<span data-ttu-id="8ba5e-113">針對您的帳戶手動設定 AGPM 服務器連線</span><span class="sxs-lookup"><span data-stu-id="8ba5e-113">Manually configure an AGPM Server connection for your account</span></span>](#bkmk-manuallyconfigurearchiveloc)

### <a href="" id="bkmk-defaultarchiveloc"></a>

**<span data-ttu-id="8ba5e-114">針對所有群組原則管理員設定 AGPM 服務器連線</span><span class="sxs-lookup"><span data-stu-id="8ba5e-114">To configure an AGPM Server connection for all Group Policy administrators</span></span>**

1.  <span data-ttu-id="8ba5e-115">在 [**群組原則管理] 主控台**樹狀結構中，編輯套用至所有群組原則系統管理員的 GPO。</span><span class="sxs-lookup"><span data-stu-id="8ba5e-115">In the **Group Policy Management Console** tree, edit a GPO that is applied to all Group Policy administrators.</span></span> <span data-ttu-id="8ba5e-116">（如需詳細資訊，請參閱[編輯 GPO](editing-a-gpo-agpm30ops.md)）。</span><span class="sxs-lookup"><span data-stu-id="8ba5e-116">(For more information, see [Editing a GPO](editing-a-gpo-agpm30ops.md).)</span></span>

2.  <span data-ttu-id="8ba5e-117">在 [**群組原則管理編輯器**] 視窗中，按一下 [**使用者**設定、**原則**、**管理範本**、 **Windows 元件**及**AGPM**]。</span><span class="sxs-lookup"><span data-stu-id="8ba5e-117">In the **Group Policy Management Editor** window, click **User Configuration**, **Policies**, **Administrative Templates**, **Windows Components**, and **AGPM**.</span></span>

3.  <span data-ttu-id="8ba5e-118">在 [詳細資料] 窗格中，按兩下 [ **agpm]：指定預設的 Agpm 伺服器（所有網域）**。</span><span class="sxs-lookup"><span data-stu-id="8ba5e-118">In the details pane, double-click **AGPM: Specify default AGPM Server (all domains)**.</span></span>

4.  <span data-ttu-id="8ba5e-119">在 [**屬性**] 視窗中，選取 [**啟用**] 核取方塊，然後輸入完整的電腦名稱稱和埠（例如，server.contoso.com:4600）。</span><span class="sxs-lookup"><span data-stu-id="8ba5e-119">In the **Properties** window, select the **Enabled** check box, and type the fully-qualified computer name and port (for example, server.contoso.com:4600).</span></span>

5.  <span data-ttu-id="8ba5e-120">按一下 \[確定\] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8ba5e-120">Click **OK**.</span></span> <span data-ttu-id="8ba5e-121">除非您想要設定其他的 AGPM 服務器連線，否則請關閉 [**群組原則管理編輯器**] 視窗並部署 GPO。</span><span class="sxs-lookup"><span data-stu-id="8ba5e-121">Unless you want to configure additional AGPM Server connections, close the **Group Policy Management Editor** window and deploy the GPO.</span></span> <span data-ttu-id="8ba5e-122">（如需詳細資訊，請參閱[部署 GPO](deploy-a-gpo-agpm30ops.md)）。更新群組原則時，會針對所有群組原則管理員設定 AGPM 服務器連線。</span><span class="sxs-lookup"><span data-stu-id="8ba5e-122">(For more information, see [Deploy a GPO](deploy-a-gpo-agpm30ops.md).) When Group Policy is updated, the AGPM Server connection is configured for all Group Policy administrators.</span></span>

### <a href="" id="bkmk-additionalarchiveloc"></a>

**<span data-ttu-id="8ba5e-123">針對所有群組原則管理員設定其他 AGPM 服務器連線</span><span class="sxs-lookup"><span data-stu-id="8ba5e-123">To configure additional AGPM Server connections for all Group Policy administrators</span></span>**

1.  <span data-ttu-id="8ba5e-124">如果尚未設定任何 AGPM 服務器連線，請依照上述程式來設定所有網域的預設 AGPM 服務器。</span><span class="sxs-lookup"><span data-stu-id="8ba5e-124">If no AGPM Server connection has been configured, follow the preceding procedure to configure a default AGPM Server for all domains.</span></span>

2.  <span data-ttu-id="8ba5e-125">若要針對部分或所有網域設定個別的 AGPM 服務器（覆寫預設的 AGPM 服務器），請在 [**群組原則管理主控台**] 樹狀結構中，編輯套用至所有群組原則系統管理員的 GPO。</span><span class="sxs-lookup"><span data-stu-id="8ba5e-125">To configure separate AGPM Servers for some or all domains (overriding the default AGPM Server), in the **Group Policy Management Console** tree, edit a GPO that is applied to all Group Policy administrators.</span></span> <span data-ttu-id="8ba5e-126">（如需詳細資訊，請參閱[編輯 GPO](editing-a-gpo-agpm30ops.md)）。</span><span class="sxs-lookup"><span data-stu-id="8ba5e-126">(For more information, see [Editing a GPO](editing-a-gpo-agpm30ops.md).)</span></span>

3.  <span data-ttu-id="8ba5e-127">在 [**群組原則管理編輯器**] 視窗中，按一下 [**使用者**設定]、[**原則**]、[系統**管理範本**]、[ **Windows 元件**] 和 [ **AGPM**]。</span><span class="sxs-lookup"><span data-stu-id="8ba5e-127">In the **Group Policy Management Editor** window, click **User Configuration**, **Policies**, **Administrative Templates**, **Windows Components**, and then **AGPM**.</span></span>

4.  <span data-ttu-id="8ba5e-128">在 [詳細資料] 窗格中，按兩下 [ **agpm]： [指定 Agpm 伺服器**]。</span><span class="sxs-lookup"><span data-stu-id="8ba5e-128">In the details pane, double-click **AGPM: Specify AGPM Servers**.</span></span>

5.  <span data-ttu-id="8ba5e-129">在 [**屬性**] 視窗中，選取 [**啟用**] 核取方塊，然後按一下 [**顯示**]。</span><span class="sxs-lookup"><span data-stu-id="8ba5e-129">In the **Properties** window, select the **Enabled** check box, and click **Show**.</span></span>

6.  <span data-ttu-id="8ba5e-130">在 [**顯示內容**] 視窗中：</span><span class="sxs-lookup"><span data-stu-id="8ba5e-130">In the **Show Contents** window:</span></span>

    1.  <span data-ttu-id="8ba5e-131">按一下**新增**。</span><span class="sxs-lookup"><span data-stu-id="8ba5e-131">Click **Add**.</span></span>

    2.  <span data-ttu-id="8ba5e-132">針對 [**值名稱**]，輸入功能變數名稱（例如，server1.contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="8ba5e-132">For **Value Name**, type the domain name (for example, server1.contoso.com).</span></span>

    3.  <span data-ttu-id="8ba5e-133">在 [**值**] 中，輸入要用於此網域的 AGPM 服務器名稱和埠（例如，server2.contoso.com:4600），然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="8ba5e-133">For **Value**, type the AGPM Server name and port to use for this domain (for example, server2.contoso.com:4600), and then click **OK**.</span></span> <span data-ttu-id="8ba5e-134">（根據預設，AGPM 服務會偵聽埠4600。</span><span class="sxs-lookup"><span data-stu-id="8ba5e-134">(By default, the AGPM Service listens on port 4600.</span></span> <span data-ttu-id="8ba5e-135">若要使用不同的埠，請參閱[修改 AGPM 服務](modify-the-agpm-service-agpm30ops.md)。）</span><span class="sxs-lookup"><span data-stu-id="8ba5e-135">To use a different port, see [Modify the AGPM Service](modify-the-agpm-service-agpm30ops.md).)</span></span>

    4.  <span data-ttu-id="8ba5e-136">針對不是使用預設 AGPM 服務器的每個網域重複上述步驟。</span><span class="sxs-lookup"><span data-stu-id="8ba5e-136">Repeat for each domain not using the default AGPM Server.</span></span>

7.  <span data-ttu-id="8ba5e-137">按一下 **[確定]** 以關閉 [**顯示內容**和**屬性**] 視窗。</span><span class="sxs-lookup"><span data-stu-id="8ba5e-137">Click **OK** to close the **Show Contents** and **Properties** windows.</span></span>

8.  <span data-ttu-id="8ba5e-138">關閉 [**群組原則管理編輯器**] 視窗。</span><span class="sxs-lookup"><span data-stu-id="8ba5e-138">Close the **Group Policy Management Editor** window.</span></span> <span data-ttu-id="8ba5e-139">（如需詳細資訊，請參閱[部署 GPO](deploy-a-gpo-agpm30ops.md)）。更新群組原則時，系統會針對所有群組原則管理員設定新的 AGPM 服務器連線。</span><span class="sxs-lookup"><span data-stu-id="8ba5e-139">(For more information, see [Deploy a GPO](deploy-a-gpo-agpm30ops.md).) When Group Policy is updated, the new AGPM Server connections are configured for all Group Policy administrators.</span></span>

### <a href="" id="bkmk-manuallyconfigurearchiveloc"></a>

<span data-ttu-id="8ba5e-140">如果您已集中設定 AGPM 服務器連線，則所有群組原則管理員都無法使用手動設定的選項。</span><span class="sxs-lookup"><span data-stu-id="8ba5e-140">If you have centrally configured the AGPM Server connection, the option to manually configure it is unavailable for all Group Policy administrators.</span></span>

**<span data-ttu-id="8ba5e-141">手動設定要針對您的帳戶顯示的 AGPM 服務器</span><span class="sxs-lookup"><span data-stu-id="8ba5e-141">To manually configure which AGPM Server to display for your account</span></span>**

1.  <span data-ttu-id="8ba5e-142">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="8ba5e-142">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="8ba5e-143">在 [詳細資料] 窗格中，按一下 [ **AGPM 服務器**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="8ba5e-143">In the details pane, click the **AGPM Server** tab.</span></span>

3.  <span data-ttu-id="8ba5e-144">針對管理此網域使用之封存的 AGPM 服務器（例如，server.contoso.com）和 AGPM 服務偵聽的埠（預設為埠4600）輸入完整的電腦名稱稱。</span><span class="sxs-lookup"><span data-stu-id="8ba5e-144">Enter the fully-qualified computer name for the AGPM Server that manages the archive used for this domain (for example, server.contoso.com) and the port on which the AGPM Service listens (by default, port 4600).</span></span>

4.  <span data-ttu-id="8ba5e-145">按一下 [套用] **，然後按一下** **[是]** 以確認。</span><span class="sxs-lookup"><span data-stu-id="8ba5e-145">Click **Apply**, then click **Yes** to confirm.</span></span>

### <span data-ttu-id="8ba5e-146">其他考量</span><span class="sxs-lookup"><span data-stu-id="8ba5e-146">Additional considerations</span></span>

-   <span data-ttu-id="8ba5e-147">您必須能夠編輯和部署 GPO，以執行集中為所有群組原則管理員設定 AGPM 服務器連線的程式。</span><span class="sxs-lookup"><span data-stu-id="8ba5e-147">You must be able to edit and deploy a GPO to perform the procedures for centrally configuring AGPM Server connections for all Group Policy administrators.</span></span> <span data-ttu-id="8ba5e-148">如需更多詳細資料，請參閱[編輯 gpo](editing-a-gpo-agpm30ops.md)及[部署 gpo](deploy-a-gpo-agpm30ops.md) 。</span><span class="sxs-lookup"><span data-stu-id="8ba5e-148">See [Editing a GPO](editing-a-gpo-agpm30ops.md) and [Deploy a GPO](deploy-a-gpo-agpm30ops.md) for additional detail.</span></span>

-   <span data-ttu-id="8ba5e-149">選取的 AGPM 服務器會判斷哪些 Gpo 會顯示在 [**目錄**] 索引標籤上，以及 [**網域委派**] 索引標籤設定的套用位置。</span><span class="sxs-lookup"><span data-stu-id="8ba5e-149">The selected AGPM Server determines which GPOs are displayed on the **Contents** tab and to what location the **Domain Delegation** tab settings are applied.</span></span> <span data-ttu-id="8ba5e-150">如果不是透過管理範本來集中管理，每個群組原則管理員都必須設定此設定，以指向網域的 AGPM 服務器。</span><span class="sxs-lookup"><span data-stu-id="8ba5e-150">If not centrally managed through the Administrative template, each Group Policy administrator must configure this setting to point to the AGPM Server for the domain.</span></span>

-   <span data-ttu-id="8ba5e-151">[群組原則建立人擁有者] 群組中的成員資格應該受到限制，不會使用 soit 來避開對 Gpo 存取的 AGPM 管理。</span><span class="sxs-lookup"><span data-stu-id="8ba5e-151">Membership in the Group Policy Creator Owners group should be restricted, soit is not used to circumvent AGPM management of access to GPOs.</span></span> <span data-ttu-id="8ba5e-152">（在 [**群組原則管理主控台**] 中，按一下要管理 gpo 的林和網域中的 [**群組原則物件**]，按一下 [**委派**]，然後設定設定以符合貴組織的需求。）</span><span class="sxs-lookup"><span data-stu-id="8ba5e-152">(In the **Group Policy Management Console**, click **Group Policy Objects** in the forest and domain in which you want to manage GPOs, click **Delegation**, and then configure the settings to meet the needs of your organization.)</span></span>

### <span data-ttu-id="8ba5e-153">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="8ba5e-153">Additional references</span></span>

-   [<span data-ttu-id="8ba5e-154">設定進階群組原則管理</span><span class="sxs-lookup"><span data-stu-id="8ba5e-154">Configuring Advanced Group Policy Management</span></span>](configuring-advanced-group-policy-management.md)

 

 





