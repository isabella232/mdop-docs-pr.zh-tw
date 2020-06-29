---
title: 設定 AGPM 伺服器連線
description: 設定 AGPM 伺服器連線
author: dansimp
ms.assetid: 9a42b5bc-41be-44ef-a6e2-6f56e2cf1996
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 88182f0e79f1a8bcce53e0d50c014e8d4aa29286
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802006"
---
# <span data-ttu-id="2622a-103">設定 AGPM 伺服器連線</span><span class="sxs-lookup"><span data-stu-id="2622a-103">Configure the AGPM Server Connection</span></span>


<span data-ttu-id="2622a-104">[高級群組原則管理] （AGPM）會將各個受控制的群群組原則物件（GPO）的所有版本儲存在中央封存中，因此群組原則管理員可以在離線時查看及修改 Gpo，而不會立即影響每個 GPO 的部署版本。</span><span class="sxs-lookup"><span data-stu-id="2622a-104">Advanced Group Policy Management (AGPM) stores all versions of each controlled Group Policy object (GPO) in a central archive, so Group Policy administrators can view and modify GPOs offline without immediately impacting the deployed version of each GPO.</span></span>

<span data-ttu-id="2622a-105">具有 [AGPM 管理員] （完全控制）角色的使用者帳戶、在這些程式中建立 GPO 所使用的核准者使用者帳戶，或是在高級群組原則管理中具有必要許可權的使用者帳戶，都必須完成這些程式來集中設定所有群組原則管理員的封存位置。</span><span class="sxs-lookup"><span data-stu-id="2622a-105">A user account with the AGPM Administrator (Full Control) role, the user account of the Approver who created the GPO used in these procedures, or a user account with the necessary permissions in Advanced Group Policy Management is required to complete these procedures for centrally configuring archive locations for all Group Policy administrators.</span></span> <span data-ttu-id="2622a-106">請參閱本主題中的「其他注意事項」中的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="2622a-106">Review the details in "Additional considerations" in this topic.</span></span>

## <span data-ttu-id="2622a-107">設定 AGPM 服務器連線</span><span class="sxs-lookup"><span data-stu-id="2622a-107">Configuring the AGPM Server connection</span></span>


<span data-ttu-id="2622a-108">在 AGPM 系統管理員（完全控制）中，您可以透過集中設定設定，以確保所有群組原則管理員都連線到相同的 AGPM 服務器。</span><span class="sxs-lookup"><span data-stu-id="2622a-108">As an AGPM Administrator (Full Control), you can ensure that all Group Policy administrators connect to the same AGPM Server by centrally configuring the setting.</span></span> <span data-ttu-id="2622a-109">如果您的環境需要部分或所有網域的個別 AGPM 服務器，請將這些額外的 AGPM 服務器設定為預設的例外狀況。</span><span class="sxs-lookup"><span data-stu-id="2622a-109">If your environment requires separate AGPM Servers for some or all domains, configure those additional AGPM Servers as exceptions to the default.</span></span> <span data-ttu-id="2622a-110">如果您沒有集中設定 AGPM 服務器連線，每個群組原則管理員都必須手動設定要針對每個網域顯示的 AGPM 服務器。</span><span class="sxs-lookup"><span data-stu-id="2622a-110">If you do not centrally configure AGPM Server connections, each Group Policy administrator must manually configure the AGPM Server to be displayed for each domain.</span></span>

-   [<span data-ttu-id="2622a-111">針對所有群組原則管理員設定 AGPM 服務器</span><span class="sxs-lookup"><span data-stu-id="2622a-111">Configure an AGPM Server for all Group Policy administrators</span></span>](#bkmk-defaultarchiveloc)

-   [<span data-ttu-id="2622a-112">針對所有群組原則管理員設定其他 AGPM 服務器</span><span class="sxs-lookup"><span data-stu-id="2622a-112">Configure additional AGPM Servers for all Group Policy administrators</span></span>](#bkmk-additionalarchiveloc)

-   [<span data-ttu-id="2622a-113">針對您的帳戶手動設定 AGPM 服務器</span><span class="sxs-lookup"><span data-stu-id="2622a-113">Manually configure an AGPM Server for your account</span></span>](#bkmk-manuallyconfigurearchiveloc)

### <a href="" id="bkmk-defaultarchiveloc"></a>

**<span data-ttu-id="2622a-114">針對所有群組原則管理員設定 AGPM 服務器</span><span class="sxs-lookup"><span data-stu-id="2622a-114">To configure an AGPM Server for all Group Policy administrators</span></span>**

1.  <span data-ttu-id="2622a-115">在 [**群組原則管理] 主控台**樹狀結構中，編輯套用至所有群組原則系統管理員的 GPO。</span><span class="sxs-lookup"><span data-stu-id="2622a-115">In the **Group Policy Management Console** tree, edit a GPO that is applied to all Group Policy administrators.</span></span> <span data-ttu-id="2622a-116">（如需詳細資訊，請參閱[編輯 GPO](editing-a-gpo.md)）。</span><span class="sxs-lookup"><span data-stu-id="2622a-116">(For more information, see [Editing a GPO](editing-a-gpo.md).)</span></span>

2.  <span data-ttu-id="2622a-117">在 [**群組原則物件編輯器**] 中，按一下 [**使用者**設定]、[系統**管理範本**] 和 [ **Windows 元件**]。</span><span class="sxs-lookup"><span data-stu-id="2622a-117">In the **Group Policy Object Editor**, click **User Configuration**, **Administrative Templates**, and **Windows Components**.</span></span>

3.  <span data-ttu-id="2622a-118">如果 [ **Windows 元件**] 下並未列出 [ **AGPM** ]：</span><span class="sxs-lookup"><span data-stu-id="2622a-118">If **AGPM** is not listed under **Windows Components**:</span></span>

    1.  <span data-ttu-id="2622a-119">以滑鼠右鍵按一下 [**管理範本**]，然後按一下 [**新增/移除範本**]。</span><span class="sxs-lookup"><span data-stu-id="2622a-119">Right-click **Administrative Templates** and click **Add/Remove Templates**.</span></span>

    2.  <span data-ttu-id="2622a-120">按一下 [**新增**]，選取 [ **agpm** ] 或 [ **agpm] .adm**，按一下 [**開啟**]，然後按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="2622a-120">Click **Add**, select **agpm.admx** or **agpm.adm**, click **Open**, and then click **Close**.</span></span>

4.  <span data-ttu-id="2622a-121">在 [ **Windows 元件**] 底下，按兩下 [ **AGPM**]。</span><span class="sxs-lookup"><span data-stu-id="2622a-121">Under **Windows Components**, double-click **AGPM**.</span></span>

5.  <span data-ttu-id="2622a-122">在 [詳細資料] 窗格中，按兩下 **[AGPM Server （所有網域）**]。</span><span class="sxs-lookup"><span data-stu-id="2622a-122">In the details pane, double-click **AGPM Server (all domains)**.</span></span>

6.  <span data-ttu-id="2622a-123">在 [ **AGPM Server （所有網域）屬性**] 視窗中，選取 [**已啟用**] 核取方塊，然後輸入完整的電腦名稱稱和埠（例如，server.contoso.com:4600）。</span><span class="sxs-lookup"><span data-stu-id="2622a-123">In the **AGPM Server (all domains) Properties** window, select the **Enabled** check box, and type the fully-qualified computer name and port (for example, server.contoso.com:4600).</span></span>

7.  <span data-ttu-id="2622a-124">按一下 \[確定\] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2622a-124">Click **OK**.</span></span> <span data-ttu-id="2622a-125">除非您想要設定其他的 AGPM 服務器連線，否則請關閉 [**群組原則物件編輯器**] 並部署 GPO。</span><span class="sxs-lookup"><span data-stu-id="2622a-125">Unless you want to configure additional AGPM Server connections, close the **Group Policy Object Editor** and deploy the GPO.</span></span> <span data-ttu-id="2622a-126">（如需詳細資訊，請參閱[部署 GPO](deploy-a-gpo.md)）。更新群組原則時，會針對所有群組原則管理員設定 AGPM 服務器連線。</span><span class="sxs-lookup"><span data-stu-id="2622a-126">(For more information, see [Deploy a GPO](deploy-a-gpo.md).) When Group Policy is updated, the AGPM Server connection is configured for all Group Policy administrators.</span></span>

### <a href="" id="bkmk-additionalarchiveloc"></a>

**<span data-ttu-id="2622a-127">針對所有群組原則管理員設定其他 AGPM 服務器</span><span class="sxs-lookup"><span data-stu-id="2622a-127">To configure additional AGPM Servers for all Group Policy administrators</span></span>**

1.  <span data-ttu-id="2622a-128">如果尚未設定任何 AGPM 服務器連線，請依照上述程式來設定所有網域的預設 AGPM 服務器。</span><span class="sxs-lookup"><span data-stu-id="2622a-128">If no AGPM Server connection has been configured, follow the preceding procedure to configure a default AGPM Server for all domains.</span></span>

2.  <span data-ttu-id="2622a-129">若要針對部分或所有網域設定個別的 AGPM 服務器（覆寫預設的 AGPM 服務器），請在 [**群組原則管理主控台**] 樹狀結構中，編輯套用至所有群組原則系統管理員的 GPO。</span><span class="sxs-lookup"><span data-stu-id="2622a-129">To configure separate AGPM Servers for some or all domains (overriding the default AGPM Server), in the **Group Policy Management Console** tree, edit a GPO that is applied to all Group Policy administrators.</span></span> <span data-ttu-id="2622a-130">（如需詳細資訊，請參閱[編輯 GPO](editing-a-gpo.md)）。</span><span class="sxs-lookup"><span data-stu-id="2622a-130">(For more information, see [Editing a GPO](editing-a-gpo.md).)</span></span>

3.  <span data-ttu-id="2622a-131">在 [**群組原則物件編輯器**] 中的 [**使用者**設定] 底下，按兩下 [系統**管理範本**]、[ **Windows 元件**]，然後按一下 [ **AGPM**]。</span><span class="sxs-lookup"><span data-stu-id="2622a-131">Under **User Configuration** in the **Group Policy Object Editor**, double-click **Administrative Templates**, **Windows Components**, and then **AGPM**.</span></span>

4.  <span data-ttu-id="2622a-132">在 [詳細資料] 窗格中，按兩下 [ **AGPM Server**]。</span><span class="sxs-lookup"><span data-stu-id="2622a-132">In the details pane, double-click **AGPM Server**.</span></span>

5.  <span data-ttu-id="2622a-133">在 [ **AGPM Server 屬性**] 視窗中，選取 [**啟用**] 核取方塊，然後按一下 [**顯示**]。</span><span class="sxs-lookup"><span data-stu-id="2622a-133">In the **AGPM Server Properties** window, select the **Enabled** check box, and click **Show**.</span></span>

6.  <span data-ttu-id="2622a-134">在 [**顯示內容**] 視窗中：</span><span class="sxs-lookup"><span data-stu-id="2622a-134">In the **Show Contents** window:</span></span>

    1.  <span data-ttu-id="2622a-135">按一下**新增**。</span><span class="sxs-lookup"><span data-stu-id="2622a-135">Click **Add**.</span></span>

    2.  <span data-ttu-id="2622a-136">針對 [**值名稱**]，輸入功能變數名稱（例如，server1.contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="2622a-136">For **Value Name**, type the domain name (for example, server1.contoso.com).</span></span>

    3.  <span data-ttu-id="2622a-137">在 [**值**] 中，輸入要用於此網域的 AGPM 服務器名稱和埠（例如，server2.contoso.com:4600），然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="2622a-137">For **Value**, type the AGPM Server name and port to use for this domain (for example, server2.contoso.com:4600), and then click **OK**.</span></span> <span data-ttu-id="2622a-138">（根據預設，AGPM 服務會偵聽埠4600。</span><span class="sxs-lookup"><span data-stu-id="2622a-138">(By default, the AGPM Service listens on port 4600.</span></span> <span data-ttu-id="2622a-139">若要使用不同的埠，請參閱[修改 AGPM 服務偵聽的埠](modify-the-port-on-which-the-agpm-service-listens.md)。</span><span class="sxs-lookup"><span data-stu-id="2622a-139">To use a different port, see [Modify the Port on Which the AGPM Service Listens](modify-the-port-on-which-the-agpm-service-listens.md).)</span></span>

    4.  <span data-ttu-id="2622a-140">針對不是使用預設 AGPM 服務器的每個網域重複上述步驟。</span><span class="sxs-lookup"><span data-stu-id="2622a-140">Repeat for each domain not using the default AGPM Server.</span></span>

7.  <span data-ttu-id="2622a-141">按一下 **[確定]** 以關閉 [**顯示內容**和**AGPM 服務器屬性**] 視窗。</span><span class="sxs-lookup"><span data-stu-id="2622a-141">Click **OK** to close the **Show Contents** and **AGPM Server Properties** windows.</span></span>

8.  <span data-ttu-id="2622a-142">關閉 [**群組原則物件編輯器**]。</span><span class="sxs-lookup"><span data-stu-id="2622a-142">Close the **Group Policy Object Editor**.</span></span> <span data-ttu-id="2622a-143">（如需詳細資訊，請參閱[部署 GPO](deploy-a-gpo.md)）。更新群組原則時，系統會針對所有群組原則管理員設定新的 AGPM 服務器連線。</span><span class="sxs-lookup"><span data-stu-id="2622a-143">(For more information, see [Deploy a GPO](deploy-a-gpo.md).) When Group Policy is updated, the new AGPM Server connections are configured for all Group Policy administrators.</span></span>

### <a href="" id="bkmk-manuallyconfigurearchiveloc"></a>

<span data-ttu-id="2622a-144">如果您已集中設定 AGPM 服務器連線，則所有群組原則管理員都無法使用手動設定的選項。</span><span class="sxs-lookup"><span data-stu-id="2622a-144">If you have centrally configured the AGPM Server connection, the option to manually it is unavailable for all Group Policy administrators.</span></span>

**<span data-ttu-id="2622a-145">手動設定要針對您的帳戶顯示的 AGPM 服務器</span><span class="sxs-lookup"><span data-stu-id="2622a-145">To manually configure the AGPM Server to display for your account</span></span>**

1.  <span data-ttu-id="2622a-146">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="2622a-146">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="2622a-147">在 [詳細資料] 窗格中，按一下 [ **AGPM 服務器**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="2622a-147">In the details pane, click the **AGPM Server** tab.</span></span>

3.  <span data-ttu-id="2622a-148">針對管理此網域使用之封存的 AGPM 服務器（例如，server.contoso.com）和 AGPM 服務偵聽的埠（預設為埠4600）輸入完整的電腦名稱稱。</span><span class="sxs-lookup"><span data-stu-id="2622a-148">Enter the fully-qualified computer name for the AGPM Server that manages the archive used for this domain (for example, server.contoso.com) and the port on which the AGPM Service listens (by default, port 4600).</span></span>

4.  <span data-ttu-id="2622a-149">按一下 [套用] **，然後按一下** **[是]** 以確認。</span><span class="sxs-lookup"><span data-stu-id="2622a-149">Click **Apply**, then click **Yes** to confirm.</span></span>

### <span data-ttu-id="2622a-150">其他考量</span><span class="sxs-lookup"><span data-stu-id="2622a-150">Additional considerations</span></span>

-   <span data-ttu-id="2622a-151">您必須能夠編輯和部署 GPO，以執行集中為所有群組原則管理員設定 AGPM 服務器連線的程式。</span><span class="sxs-lookup"><span data-stu-id="2622a-151">You must be able to edit and deploy a GPO to perform the procedures for centrally configuring AGPM Server connections for all Group Policy administrators.</span></span> <span data-ttu-id="2622a-152">如需更多詳細資料，請參閱[編輯 gpo](editing-a-gpo.md)及[部署 gpo](deploy-a-gpo.md) 。</span><span class="sxs-lookup"><span data-stu-id="2622a-152">See [Editing a GPO](editing-a-gpo.md) and [Deploy a GPO](deploy-a-gpo.md) for additional detail.</span></span>

-   <span data-ttu-id="2622a-153">已選取的 AGPM 服務器決定在 [**內容**] 索引標籤上顯示哪些 gpo，以及將哪些位置套用到 [**網域委派**] 索引標籤設定。</span><span class="sxs-lookup"><span data-stu-id="2622a-153">The AGPM Server selected determines which GPOs are displayed on the **Contents** tab and to what location the **Domain Delegation** tab settings are applied.</span></span> <span data-ttu-id="2622a-154">如果不是透過管理範本來集中管理，每個群組原則管理員都必須設定此設定，以指向網域的 AGPM 服務器。</span><span class="sxs-lookup"><span data-stu-id="2622a-154">If not centrally managed through the Administrative Template, each Group Policy administrator must configure this setting to point to the AGPM Server for the domain.</span></span>

-   <span data-ttu-id="2622a-155">[群組原則建立者擁有者] 群組中的成員資格應該受到限制，因此不會使用它來避開從 AGPM 存取 Gpo 的管理。</span><span class="sxs-lookup"><span data-stu-id="2622a-155">Membership in the Group Policy Creator Owners group should be restricted so that it is not used to circumvent the management of access to GPOs by AGPM.</span></span> <span data-ttu-id="2622a-156">（在 [**群組原則管理主控台**] 中，按一下要管理 gpo 的林和網域中的 [**群組原則物件**]，按一下 [**委派**]，然後設定設定以符合貴組織的需求。）</span><span class="sxs-lookup"><span data-stu-id="2622a-156">(In the **Group Policy Management Console**, click **Group Policy Objects** in the forest and domain in which you want to manage GPOs, click **Delegation**, and then configure the settings to meet the needs of your organization.)</span></span>

### <span data-ttu-id="2622a-157">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="2622a-157">Additional references</span></span>

-   [<span data-ttu-id="2622a-158">執行 AGPM 系統管理員工作</span><span class="sxs-lookup"><span data-stu-id="2622a-158">Performing AGPM Administrator Tasks</span></span>](performing-agpm-administrator-tasks.md)

 

 





