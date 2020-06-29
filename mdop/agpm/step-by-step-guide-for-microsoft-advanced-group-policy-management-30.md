---
title: Microsoft 進階群組原則管理 3.0 逐步指南
description: Microsoft 進階群組原則管理 3.0 逐步指南
author: dansimp
ms.assetid: d067f465-d7c8-4f6d-b311-66b9b06874f7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: b4efa5075027e99a3e50a344aafcdf6f6f69a147
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801773"
---
# <span data-ttu-id="3b2ba-103">Microsoft 進階群組原則管理 3.0 逐步指南</span><span class="sxs-lookup"><span data-stu-id="3b2ba-103">Step-by-Step Guide for Microsoft Advanced Group Policy Management 3.0</span></span>


<span data-ttu-id="3b2ba-104">本逐步指南說明使用群組原則管理主控台（GPMC）和 Microsoft 高級群組原則管理（AGPM）的群組原則管理的高級技術。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-104">This step-by-step guide demonstrates advanced techniques for Group Policy management using the Group Policy Management Console (GPMC) and Microsoft Advanced Group Policy Management (AGPM).</span></span> <span data-ttu-id="3b2ba-105">AGPM 會增加 GPMC 的功能，提供：</span><span class="sxs-lookup"><span data-stu-id="3b2ba-105">AGPM increases the capabilities of the GPMC, providing:</span></span>

-   <span data-ttu-id="3b2ba-106">將管理群組原則物件（Gpo）委派給多個群組原則管理員的標準角色，以及委派在生產環境中 Gpo 存取權的功能。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-106">Standard roles for delegating permissions to manage Group Policy objects (GPOs) to multiple Group Policy administrators, as well as the ability to delegate access to GPOs in the production environment.</span></span>

-   <span data-ttu-id="3b2ba-107">[封存] 可讓群組原則管理員在將 Gpo 部署到生產環境之前，建立及修改 Gpo。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-107">An archive to enable Group Policy administrators to create and modify GPOs offline before deploying them to a production environment.</span></span>

-   <span data-ttu-id="3b2ba-108">回滾到封存中任何舊版 GPO 的功能，以及限制儲存在封存中的版本數。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-108">The ability to roll back to any previous version of a GPO in the archive and to limit the number of versions stored in the archive.</span></span>

-   <span data-ttu-id="3b2ba-109">Gpo 的存回/取出功能可確保群組原則管理員不會無意間覆寫對方的工作。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-109">Check-in/check-out capability for GPOs to ensure that Group Policy administrators do not inadvertently overwrite each other's work.</span></span>

## <span data-ttu-id="3b2ba-110">AGPM 案例概述</span><span class="sxs-lookup"><span data-stu-id="3b2ba-110">AGPM scenario overview</span></span>


<span data-ttu-id="3b2ba-111">在這種情況下，您將針對 AGPM 中的每個角色使用個別的使用者帳戶，示範如何在有多個群組原則系統管理員具有不同許可權等級的環境中管理群組原則。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-111">For this scenario, you will use a separate user account for each role in AGPM to demonstrate how Group Policy can be managed in an environment with multiple Group Policy administrators who have different levels of permissions.</span></span> <span data-ttu-id="3b2ba-112">具體來說，您將會執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="3b2ba-112">Specifically, you will perform the following tasks:</span></span>

-   <span data-ttu-id="3b2ba-113">使用網域系統管理員群組成員的帳戶，安裝 AGPM 服務器並將 AGPM 系統管理員角色指派給帳戶或群組。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-113">Using an account that is a member of the Domain Admins group, install AGPM Server and assign the AGPM Administrator role to an account or group.</span></span>

-   <span data-ttu-id="3b2ba-114">使用您將指派 AGPM 角色的帳戶，安裝 AGPM 用戶端。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-114">Using accounts to which you will assign AGPM roles, install AGPM Client.</span></span>

-   <span data-ttu-id="3b2ba-115">使用具有 AGPM 系統管理員角色的帳戶，設定 AGPM 並委派對 Gpo 的存取權，方法是指派角色給其他帳戶。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-115">Using an account with the AGPM Administrator role, configure AGPM and delegate access to GPOs by assigning roles to other accounts.</span></span>

-   <span data-ttu-id="3b2ba-116">將帳戶與 [編輯者角色] 一起使用，要求建立 GPO，然後核准將帳戶與核准者角色一起使用。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-116">Using an account with the Editor role, request the creation of a GPO, which you then approve using an account with the Approver role.</span></span> <span data-ttu-id="3b2ba-117">使用 [編輯者] 帳戶，核取 [封存] 以外的 GPO、編輯 GPO、將 GPO 檢查到封存，然後要求部署。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-117">With the Editor account, check the GPO out of the archive, edit the GPO, check the GPO into the archive, and request deployment.</span></span>

-   <span data-ttu-id="3b2ba-118">將帳戶與核准者角色一起使用，查看 GPO 並將它部署到您的生產環境。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-118">Using an account with the Approver role, review the GPO and deploy it to your production environment.</span></span>

-   <span data-ttu-id="3b2ba-119">將帳戶與編輯者角色搭配使用，建立一個 GPO 範本，並使用它做為建立新 GPO 的起點。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-119">Using an account with the Editor role, create a GPO template and use it as a starting point to create a new GPO.</span></span>

-   <span data-ttu-id="3b2ba-120">將帳戶與核准者角色一起使用，刪除並還原 GPO。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-120">Using an account with the Approver role, delete and restore a GPO.</span></span>

![群組原則物件開發程式](images/ab77a1f3-f430-4e7d-be58-ee8f9bd1140e.gif)

## <span data-ttu-id="3b2ba-122">需求</span><span class="sxs-lookup"><span data-stu-id="3b2ba-122">Requirements</span></span>


<span data-ttu-id="3b2ba-123">您想要安裝 AGPM 的電腦必須符合下列需求，而且您必須建立帳戶才能在這個案例中使用。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-123">Computers on which you want to install AGPM must meet the following requirements, and you must create accounts for use in this scenario.</span></span>

<span data-ttu-id="3b2ba-124">**記事** 如果您已安裝您的 AGPM 2.5，且要從 Windows Server®2003升級至 Windows Server2008 或 WindowsVista®，但沒有將 service pack 安裝至 WindowsVista 與 Service Pack1，您必須先升級作業系統，才能升級至 AGPM 3.0。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-124">**Note** If you have AGPM 2.5 installed and are upgrading from Windows Server®2003 to Windows Server2008 or WindowsVista® with no service packs installed to WindowsVista with Service Pack1, you must upgrade the operating system before you can upgrade to AGPM3.0.</span></span>

 

### <span data-ttu-id="3b2ba-125">AGPM 服務器需求</span><span class="sxs-lookup"><span data-stu-id="3b2ba-125">AGPM Server requirements</span></span>

<span data-ttu-id="3b2ba-126">AGPM Server 3.0 需要 Windows Server2008 或 WindowsVista 搭配 Service Pack1，以及從遠端伺服器管理工具（RSAT）安裝 GPMC。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-126">AGPM Server3.0 requires Windows Server2008 or WindowsVista with Service Pack1 and the GPMC from Remote Server Administration Tools (RSAT) installed.</span></span> <span data-ttu-id="3b2ba-127">支援32位和64位版本。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-127">Both 32-bit and 64-bit versions are supported.</span></span>

<span data-ttu-id="3b2ba-128">在安裝 AGPM Server 之前，您必須是 Domain 系統管理員群組的成員，除非另有說明，否則必須存在下列 Windows 功能：</span><span class="sxs-lookup"><span data-stu-id="3b2ba-128">Before you install AGPM Server, you must be a member of the Domain Admins group and the following Windows features must be present unless otherwise noted:</span></span>

-   <span data-ttu-id="3b2ba-129">GPMC</span><span class="sxs-lookup"><span data-stu-id="3b2ba-129">GPMC</span></span>

    -   <span data-ttu-id="3b2ba-130">Windows Server 2008：如果不存在 GPMC，則會自動由 AGPM 自動安裝 GPMC。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-130">Windows Server 2008: The GPMC is automatically installed by AGPM if not present.</span></span>

    -   <span data-ttu-id="3b2ba-131">Windows Vista：您必須先從 RSAT 安裝 GPMC，然後才能安裝 AGPM。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-131">Windows Vista: You must install the GPMC from RSAT before you install AGPM.</span></span> <span data-ttu-id="3b2ba-132">如需詳細資訊，請參閱 <https://go.microsoft.com/fwlink/?LinkID=116179>。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-132">For more information, see <https://go.microsoft.com/fwlink/?LinkID=116179>.</span></span>

-   <span data-ttu-id="3b2ba-133">.NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="3b2ba-133">.NET Framework 3.5</span></span>

<span data-ttu-id="3b2ba-134">AGPM 服務器需要下列 Windows 功能，如果不存在，就會自動安裝：</span><span class="sxs-lookup"><span data-stu-id="3b2ba-134">The following Windows features are required by AGPM Server and will be automatically installed if not present:</span></span>

-   <span data-ttu-id="3b2ba-135">WCF 啟用;非 HTTP 啟用</span><span class="sxs-lookup"><span data-stu-id="3b2ba-135">WCF Activation; Non-HTTP Activation</span></span>

-   <span data-ttu-id="3b2ba-136">Windows 處理序啟用服務</span><span class="sxs-lookup"><span data-stu-id="3b2ba-136">Windows Process Activation Service</span></span>

    -   <span data-ttu-id="3b2ba-137">處理模型</span><span class="sxs-lookup"><span data-stu-id="3b2ba-137">Process Model</span></span>

    -   <span data-ttu-id="3b2ba-138">.NET 環境</span><span class="sxs-lookup"><span data-stu-id="3b2ba-138">.NET Environment</span></span>

    -   <span data-ttu-id="3b2ba-139">配置 Api</span><span class="sxs-lookup"><span data-stu-id="3b2ba-139">Configuration APIs</span></span>

### <span data-ttu-id="3b2ba-140">AGPM 用戶端需求</span><span class="sxs-lookup"><span data-stu-id="3b2ba-140">AGPM Client requirements</span></span>

<span data-ttu-id="3b2ba-141">AGPM 用戶端3.0 需要 Windows Server2008 或 WindowsVista Service Pack 1 和 GPMC （從遠端伺服器管理工具（RSAT）安裝）。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-141">AGPM Client3.0 requires Windows Server2008 or WindowsVista with Service Pack 1 and the GPMC from Remote Server Administration Tools (RSAT) installed.</span></span> <span data-ttu-id="3b2ba-142">支援32位和64位版本。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-142">Both 32-bit and 64-bit versions are supported.</span></span> <span data-ttu-id="3b2ba-143">您可以在執行 AGPM 服務器的電腦上安裝 AGPM 用戶端。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-143">AGPM Client can be installed on a computer running AGPM Server.</span></span>

<span data-ttu-id="3b2ba-144">下列 Windows 功能是 AGPM 用戶端所需，如果不存在，除非另有說明，否則會自動安裝：</span><span class="sxs-lookup"><span data-stu-id="3b2ba-144">The following Windows features are required by AGPM Client and will be automatically installed if not present unless otherwise noted:</span></span>

-   <span data-ttu-id="3b2ba-145">GPMC</span><span class="sxs-lookup"><span data-stu-id="3b2ba-145">GPMC</span></span>

    -   <span data-ttu-id="3b2ba-146">Windows Server 2008：如果不存在 GPMC，則會自動由 AGPM 自動安裝 GPMC。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-146">Windows Server 2008: The GPMC is automatically installed by AGPM if not present.</span></span>

    -   <span data-ttu-id="3b2ba-147">Windows Vista：您必須先從 RSAT 安裝 GPMC，然後才能安裝 AGPM。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-147">Windows Vista: You must install the GPMC from RSAT before you install AGPM.</span></span> <span data-ttu-id="3b2ba-148">如需詳細資訊，請參閱 <https://go.microsoft.com/fwlink/?LinkID=116179>。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-148">For more information, see <https://go.microsoft.com/fwlink/?LinkID=116179>.</span></span>

-   <span data-ttu-id="3b2ba-149">.NET Framework 3。0</span><span class="sxs-lookup"><span data-stu-id="3b2ba-149">.NET Framework 3.0</span></span>

### <span data-ttu-id="3b2ba-150">案例需求</span><span class="sxs-lookup"><span data-stu-id="3b2ba-150">Scenario requirements</span></span>

<span data-ttu-id="3b2ba-151">開始這個案例之前，請先建立四個使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-151">Before you begin this scenario, create four user accounts.</span></span> <span data-ttu-id="3b2ba-152">在案例中，您會將下列其中一個 AGPM 角色指派給每個帳戶： AGPM 系統管理員（完全控制）、審核者、編輯者和檢閱者。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-152">During the scenario, you will assign one of the following AGPM roles to each of these accounts: AGPM Administrator (Full Control), Approver, Editor, and Reviewer.</span></span> <span data-ttu-id="3b2ba-153">這些帳戶必須能夠傳送及接收電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-153">These accounts must be able to send and receive e-mail messages.</span></span> <span data-ttu-id="3b2ba-154">針對具有 AGPM 管理員、核准者及（選擇性）編輯者角色的帳戶指派**連結 gpo**許可權。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-154">Assign **Link GPOs** permission to the accounts with the AGPM Administrator, Approver, and (optionally) Editor roles.</span></span>

<span data-ttu-id="3b2ba-155">**記事** 
預設會將 [**連結 gpo** ] 許可權指派給網域管理員和企業系統管理員的成員。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-155">**Note**
**Link GPOs** permission is assigned to members of Domain Administrators and Enterprise Administrators by default.</span></span> <span data-ttu-id="3b2ba-156">若要將**連結 gpo**許可權指派給其他使用者或群組（例如擁有 AGPM 系統管理員或核准者角色的帳戶），請按一下該網域的節點，然後按一下 [**委派**] 索引標籤，選取 [**連結 gpo**]，再按一下 [**新增**]，然後選取要指派許可權的使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-156">To assign **Link GPOs** permission to additional users or groups (such as accounts with the roles of AGPM Administrator or Approver), click the node for the domain and then click the **Delegation** tab, select **Link GPOs**, click **Add**, and select users or groups to which to assign the permission.</span></span>

 

## <span data-ttu-id="3b2ba-157">安裝和設定 AGPM 的步驟</span><span class="sxs-lookup"><span data-stu-id="3b2ba-157">Steps for installing and configuring AGPM</span></span>


<span data-ttu-id="3b2ba-158">您必須完成下列步驟，才能安裝及設定 AGPM。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-158">You must complete the following steps to install and configure AGPM.</span></span>

[<span data-ttu-id="3b2ba-159">步驟1：安裝 AGPM 服務器</span><span class="sxs-lookup"><span data-stu-id="3b2ba-159">Step 1: Install AGPM Server</span></span>](#bkmk-config1)

[<span data-ttu-id="3b2ba-160">步驟2：安裝 AGPM 用戶端</span><span class="sxs-lookup"><span data-stu-id="3b2ba-160">Step 2: Install AGPM Client</span></span>](#bkmk-config2)

[<span data-ttu-id="3b2ba-161">步驟3：設定 AGPM 服務器連線</span><span class="sxs-lookup"><span data-stu-id="3b2ba-161">Step 3: Configure an AGPM Server connection</span></span>](#bkmk-config3)

[<span data-ttu-id="3b2ba-162">步驟4：設定電子郵件通知</span><span class="sxs-lookup"><span data-stu-id="3b2ba-162">Step 4: Configure e-mail notification</span></span>](#bkmk-config4)

[<span data-ttu-id="3b2ba-163">步驟5：委派存取權</span><span class="sxs-lookup"><span data-stu-id="3b2ba-163">Step 5: Delegate access</span></span>](#bkmk-config5)

### <a href="" id="bkmk-config1"></a><span data-ttu-id="3b2ba-164">步驟1：安裝 AGPM 服務器</span><span class="sxs-lookup"><span data-stu-id="3b2ba-164">Step 1: Install AGPM Server</span></span>

<span data-ttu-id="3b2ba-165">在這個步驟中，您會在將執行 AGPM 服務的成員伺服器或網網域控制站上安裝 [AGPM 服務器]，然後設定封存。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-165">In this step, you install AGPM Server on the member server or domain controller that will run the AGPM Service, and you configure the archive.</span></span> <span data-ttu-id="3b2ba-166">所有的 AGPM 作業都是透過此 Windows 服務來管理，並以服務的認證執行。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-166">All AGPM operations are managed through this Windows service and are executed with the service's credentials.</span></span> <span data-ttu-id="3b2ba-167">您可以將 AGPM 服務器所管理的封存放在該伺服器或同一林中的另一台伺服器上。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-167">The archive managed by an AGPM Server can be hosted on that server or on another server in the same forest.</span></span>

**<span data-ttu-id="3b2ba-168">若要在將裝載 AGPM 服務的電腦上安裝 AGPM 服務器</span><span class="sxs-lookup"><span data-stu-id="3b2ba-168">To install AGPM Server on the computer that will host the AGPM Service</span></span>**

1.  <span data-ttu-id="3b2ba-169">以網域系統管理員群組成員的帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-169">Log on with an account that is a member of the Domain Admins group.</span></span>

2.  <span data-ttu-id="3b2ba-170">啟動 Microsoft 桌面優化套件 CD，然後依照螢幕上的指示進行，以選取 [**高級群組原則管理-伺服器**]。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-170">Start the Microsoft Desktop Optimization Pack CD and follow the instructions on screen to select **Advanced Group Policy Management - Server**.</span></span>

3.  <span data-ttu-id="3b2ba-171">在 [**歡迎**] 對話方塊中，按一下 **[下一步**]。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-171">In the **Welcome** dialog box, click **Next**.</span></span>

4.  <span data-ttu-id="3b2ba-172">在 [ **Microsoft 軟體授權條款**] 對話方塊中，接受條款，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-172">In the **Microsoft Software License Terms** dialog box, accept the terms and click **Next**.</span></span>

5.  <span data-ttu-id="3b2ba-173">在 [**應用程式路徑**] 對話方塊中，選取要安裝 [AGPM 服務器] 的位置。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-173">In the **Application Path** dialog box, select a location in which to install AGPM Server.</span></span> <span data-ttu-id="3b2ba-174">安裝了 AGPM 服務器的電腦將會主持 AGPM 服務並管理封存。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-174">The computer on which AGPM Server is installed will host the AGPM Service and manage the archive.</span></span> <span data-ttu-id="3b2ba-175">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-175">Click **Next**.</span></span>

6.  <span data-ttu-id="3b2ba-176">在 [封存**路徑**] 對話方塊中，選取要相對於 AGPM 服務器的封存位置。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-176">In the **Archive Path** dialog box, select a location for the archive relative to the AGPM Server.</span></span> <span data-ttu-id="3b2ba-177">封存路徑可以指向 AGPM 服務器或其他位置的資料夾，但您應該選取一個位置，其中有足夠的空間來儲存此 AGPM 服務器所管理的所有 Gpo 及歷程記錄資料。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-177">The archive path can point to a folder on the AGPM Server or elsewhere, but you should select a location with sufficient space to store all GPOs and history data managed by this AGPM Server.</span></span> <span data-ttu-id="3b2ba-178">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-178">Click **Next**.</span></span>

7.  <span data-ttu-id="3b2ba-179">在 [ **Agpm 服務帳戶**] 對話方塊中，選取 agpm 服務將在其下執行的服務帳戶，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-179">In the **AGPM Service Account** dialog box, select a service account under which the AGPM Service will run and then click **Next**.</span></span>

8.  <span data-ttu-id="3b2ba-180">在 [封存**擁有**者] 對話方塊中，選取最初指派 AGPM 系統管理員（完全控制）角色的帳戶或群組。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-180">In the **Archive Owner** dialog box, select an account or group to which to initially assign the AGPM Administrator (Full Control) role.</span></span> <span data-ttu-id="3b2ba-181">此 AGPM 系統管理員可以為其他群組原則管理員指派 AGPM 角色和許可權（包括 AGPM 系統管理員的角色）。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-181">This AGPM Administrator can assign AGPM roles and permissions to other Group Policy administrators (including the role of AGPM Administrator).</span></span> <span data-ttu-id="3b2ba-182">在此案例中，選取要在 AGPM 系統管理員角色中提供的帳戶。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-182">For this scenario, select the account to serve in the AGPM Administrator role.</span></span> <span data-ttu-id="3b2ba-183">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-183">Click **Next**.</span></span>

9.  <span data-ttu-id="3b2ba-184">在 [**埠**設定] 對話方塊中，輸入 AGPM 服務應該聆聽的埠。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-184">In the **Port Configuration** dialog box, type a port on which the AGPM Service should listen.</span></span> <span data-ttu-id="3b2ba-185">除非您手動設定埠例外狀況，或使用規則來設定埠例外，否則請不要清除 [**將埠例外新增到防火牆**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-185">Do not clear the **Add port exception to firewall** check box unless you manually configure port exceptions or use rules to configure port exceptions.</span></span> <span data-ttu-id="3b2ba-186">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-186">Click **Next**.</span></span>

10. <span data-ttu-id="3b2ba-187">在 [**語言**] 對話方塊中，選取一或多個要為 AGPM 服務器安裝的顯示語言。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-187">In the **Languages** dialog box, select one or more display languages to install for AGPM Server.</span></span>

11. <span data-ttu-id="3b2ba-188">按一下 [**安裝**]，然後按一下 **[完成] 結束**設定向導。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-188">Click **Install**, and then click **Finish** to exit the Setup Wizard.</span></span>

    <span data-ttu-id="3b2ba-189">**小心** 請勿透過作業系統中的 [**管理工具**] 和 [**服務**] 來修改 AGPM 服務的設定。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-189">**Caution** Do not modify settings for the AGPM Service through **Administrative Tools** and **Services** in the operating system.</span></span> <span data-ttu-id="3b2ba-190">如此一來，就能防止 AGPM 服務啟動。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-190">Doing so can prevent the AGPM Service from starting.</span></span> <span data-ttu-id="3b2ba-191">如需如何修改服務設定的相關資訊，請參閱高級群組原則管理的說明。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-191">For information on how to modify settings for the service, see Help for Advanced Group Policy Management.</span></span>

     

### <a href="" id="bkmk-config2"></a><span data-ttu-id="3b2ba-192">步驟2：安裝 AGPM 用戶端</span><span class="sxs-lookup"><span data-stu-id="3b2ba-192">Step 2: Install AGPM Client</span></span>

<span data-ttu-id="3b2ba-193">每個群組原則管理員（任何建立、編輯、部署、評論或刪除 Gpo 的人）都必須在其所用的電腦上安裝 AGPM 用戶端，才能管理 Gpo。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-193">Each Group Policy administrator—anyone who creates, edits, deploys, reviews, or deletes GPOs—must have AGPM Client installed on computers that they use to manage GPOs.</span></span> <span data-ttu-id="3b2ba-194">在這種情況下，您必須在至少一部電腦上安裝 [AGPM 用戶端]。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-194">For this scenario, you install AGPM Client on at least one computer.</span></span> <span data-ttu-id="3b2ba-195">您不需要在不執行「組原則管理」的最終使用者電腦上安裝 AGPM 用戶端。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-195">You do not need to install AGPM Client on the computers of end users who do not perform Group Policy administration.</span></span>

**<span data-ttu-id="3b2ba-196">在群組原則系統管理員的電腦上安裝 AGPM 用戶端</span><span class="sxs-lookup"><span data-stu-id="3b2ba-196">To install AGPM Client on the computer of a Group Policy administrator</span></span>**

1.  <span data-ttu-id="3b2ba-197">啟動 Microsoft 桌面優化套件 CD，然後依照螢幕上的指示選取 [**高級組原則管理-用戶端**]。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-197">Start the Microsoft Desktop Optimization Pack CD and follow the instructions on screen to select **Advanced Group Policy Management - Client**.</span></span>

2.  <span data-ttu-id="3b2ba-198">在 [**歡迎**] 對話方塊中，按一下 **[下一步**]。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-198">In the **Welcome** dialog box, click **Next**.</span></span>

3.  <span data-ttu-id="3b2ba-199">在 [ **Microsoft 軟體授權條款**] 對話方塊中，接受條款，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-199">In the **Microsoft Software License Terms** dialog box, accept the terms and click **Next**.</span></span>

4.  <span data-ttu-id="3b2ba-200">在 [**應用程式路徑**] 對話方塊中，選取要安裝 AGPM 用戶端的位置。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-200">In the **Application Path** dialog box, select a location in which to install AGPM Client.</span></span> <span data-ttu-id="3b2ba-201">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-201">Click **Next**.</span></span>

5.  <span data-ttu-id="3b2ba-202">在 [ **AGPM 服務器**] 對話方塊中，為 AGPM 服務器以及要連接的埠輸入完整的電腦名稱稱。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-202">In the **AGPM Server** dialog box, type the fully-qualified computer name for the AGPM Server and the port to which to connect.</span></span> <span data-ttu-id="3b2ba-203">AGPM 服務的預設埠是4600。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-203">The default port for the AGPM Service is 4600.</span></span> <span data-ttu-id="3b2ba-204">請勿清除 [**透過防火牆允許 Microsoft 管理主控台**] 核取方塊，除非您手動設定埠例外狀況，或使用規則來設定埠例外狀況。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-204">Do not clear the **Allow Microsoft Management Console through the firewall** check box unless you manually configure port exceptions or use rules to configure port exceptions.</span></span> <span data-ttu-id="3b2ba-205">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-205">Click **Next**.</span></span>

6.  <span data-ttu-id="3b2ba-206">在 [**語言**] 對話方塊中，選取一或多個要為 AGPM 用戶端安裝的顯示語言。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-206">In the **Languages** dialog box, select one or more display languages to install for AGPM Client.</span></span>

7.  <span data-ttu-id="3b2ba-207">按一下 [**安裝**]，然後按一下 **[完成] 結束**設定向導。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-207">Click **Install**, and then click **Finish** to exit the Setup Wizard.</span></span>

### <a href="" id="bkmk-config3"></a><span data-ttu-id="3b2ba-208">步驟3：設定 AGPM 服務器連線</span><span class="sxs-lookup"><span data-stu-id="3b2ba-208">Step 3: Configure an AGPM Server connection</span></span>

<span data-ttu-id="3b2ba-209">AGPM 會儲存每個受控制的群組原則物件（GPO）的所有版本，也就是在中央封存中，AGPM 提供變更控制的 GPO，所以群組原則管理員可以在離線時查看及修改 Gpo，而不會立即影響每個 GPO 的部署版本。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-209">AGPM stores all versions of each controlled Group Policy object (GPO)—a GPO for which AGPM provides change control—in a central archive, so Group Policy administrators can view and modify GPOs offline without immediately impacting the deployed version of each GPO.</span></span>

<span data-ttu-id="3b2ba-210">在這個步驟中，您要設定 AGPM 服務器連線，並確保所有群組原則管理員都連線到相同的 AGPM 服務器。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-210">In this step, you configure an AGPM Server connection and ensure that all Group Policy administrators connect to the same AGPM Server.</span></span> <span data-ttu-id="3b2ba-211">（如需有關設定多個 AGPM 服務器的詳細資訊，請參閱高級群組原則管理的說明。）</span><span class="sxs-lookup"><span data-stu-id="3b2ba-211">(For information about configuring multiple AGPM Servers, see Help for Advanced Group Policy Management.)</span></span>

**<span data-ttu-id="3b2ba-212">針對所有群組原則管理員設定 AGPM 服務器連線</span><span class="sxs-lookup"><span data-stu-id="3b2ba-212">To configure an AGPM Server connection for all Group Policy administrators</span></span>**

1.  <span data-ttu-id="3b2ba-213">在已安裝 AGPM 用戶端的電腦上，以您選取做為封存擁有者的使用者帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-213">On a computer on which you have installed AGPM Client, log on with the user account that you selected as the Archive Owner.</span></span> <span data-ttu-id="3b2ba-214">此使用者擁有 AGPM 系統管理員的角色（完全控制）。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-214">This user has the role of AGPM Administrator (Full Control).</span></span>

2.  <span data-ttu-id="3b2ba-215">按一下 [**開始**]，指向 [系統**管理工具**]，然後按一下 [**群組原則管理**] 來開啟 GPMC。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-215">Click **Start**, point to **Administrative Tools**, and click **Group Policy Management** to open the GPMC.</span></span>

3.  <span data-ttu-id="3b2ba-216">編輯套用至所有群組原則系統管理員的 GPO。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-216">Edit a GPO that is applied to all Group Policy administrators.</span></span>

4.  <span data-ttu-id="3b2ba-217">在 [**群組原則管理編輯器**] 視窗中，按兩下 [**使用者**設定]、[**原則**]、[系統**管理範本**]、[ **Windows 元件**] 和 [ **AGPM**]。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-217">In the **Group Policy Management Editor** window, double-click **User Configuration**, **Policies**, **Administrative Templates**, **Windows Components**, and **AGPM**.</span></span>

5.  <span data-ttu-id="3b2ba-218">在 [詳細資料] 窗格中，按兩下 [ **agpm]：指定預設的 Agpm 伺服器（所有網域）**。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-218">In the details pane, double-click **AGPM: Specify default AGPM Server (all domains)**.</span></span>

6.  <span data-ttu-id="3b2ba-219">在 [**屬性**] 視窗中，選取 [**啟用**]，然後為裝載封存的伺服器輸入完整的電腦名稱稱和埠（例如， **server.contoso.com:4600**）。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-219">In the **Properties** window, select **Enabled** and type the fully-qualified computer name and port (for example, **server.contoso.com:4600**) for the server hosting the archive.</span></span> <span data-ttu-id="3b2ba-220">根據預設，AGPM 服務會使用埠4600。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-220">By default, the AGPM Service uses port 4600.</span></span>

7.  <span data-ttu-id="3b2ba-221">按一下 **[確定]**，然後關閉 [**群組原則管理編輯器**] 視窗。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-221">Click **OK**, and then close the **Group Policy Management Editor** window.</span></span> <span data-ttu-id="3b2ba-222">更新群組原則時，會針對每個群組原則管理員設定 AGPM 服務器連線。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-222">When Group Policy is updated, the AGPM Server connection is configured for each Group Policy administrator.</span></span>

### <a href="" id="bkmk-config4"></a><span data-ttu-id="3b2ba-223">步驟4：設定電子郵件通知</span><span class="sxs-lookup"><span data-stu-id="3b2ba-223">Step 4: Configure e-mail notification</span></span>

<span data-ttu-id="3b2ba-224">在 AGPM 系統管理員（完全控制）中，您可以指定當編輯者嘗試建立、部署或刪除 GPO 時，傳送包含要求之電子郵件訊息之核准者和 AGPM 系統管理員的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-224">As an AGPM Administrator (Full Control), you designate the e-mail addresses of Approvers and AGPM Administrators to whom an e-mail message containing a request is sent when an Editor attempts to create, deploy, or delete a GPO.</span></span> <span data-ttu-id="3b2ba-225">您也可以決定要從哪個別名傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-225">You also determine the alias from which these messages are sent.</span></span>

**<span data-ttu-id="3b2ba-226">若要設定 AGPM 的電子郵件通知</span><span class="sxs-lookup"><span data-stu-id="3b2ba-226">To configure e-mail notification for AGPM</span></span>**

1.  <span data-ttu-id="3b2ba-227">在 [詳細資料] 窗格中，按一下 [**網域委派**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-227">In the details pane, click the **Domain Delegation** tab.</span></span>

2.  <span data-ttu-id="3b2ba-228">在 [**寄件者電子郵件地址**] 欄位中，輸入要傳送通知的 AGPM 電子郵件別名。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-228">In the **From e-mail address** field, type the e-mail alias for AGPM from which notifications should be sent.</span></span>

3.  <span data-ttu-id="3b2ba-229">在 [收**件者電子郵件地址**] 欄位中，輸入您要指派核准者角色的使用者帳戶的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-229">In the **To e-mail address** field, type the e-mail address for the user account to which you intend to assign the Approver role.</span></span>

4.  <span data-ttu-id="3b2ba-230">在 [ **SMTP 伺服器**] 欄位中，輸入有效的 SMTP 郵件伺服器。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-230">In the **SMTP server** field, type a valid SMTP mail server.</span></span>

5.  <span data-ttu-id="3b2ba-231">在 [**使用者名稱**] 和 [**密碼**] 欄位中，輸入擁有 SMTP 服務存取權的使用者認證。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-231">In the **User name** and **Password** fields, type the credentials of a user with access to the SMTP service.</span></span> <span data-ttu-id="3b2ba-232">按一下 **\[Apply\]** (套用)。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-232">Click **Apply**.</span></span>

### <a href="" id="bkmk-config5"></a><span data-ttu-id="3b2ba-233">步驟5：委派存取權</span><span class="sxs-lookup"><span data-stu-id="3b2ba-233">Step 5: Delegate access</span></span>

<span data-ttu-id="3b2ba-234">作為 AGPM 系統管理員（完全控制），您可以委派網域層級對 Gpo 的存取權，將角色指派給每個群組原則管理員的帳戶。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-234">As an AGPM Administrator (Full Control), you delegate domain-level access to GPOs, assigning roles to the account of each Group Policy administrator.</span></span>

<span data-ttu-id="3b2ba-235">**記事** 您也可以在 GPO 層級（而非網域層級）委派存取權。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-235">**Note** You can also delegate access at the GPO level rather than the domain level.</span></span> <span data-ttu-id="3b2ba-236">如需詳細資訊，請參閱高級群組原則管理的說明。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-236">For details, see Help for Advanced Group Policy Management.</span></span>

 

<span data-ttu-id="3b2ba-237">**重要** 您應該限制 [群組原則建立者擁有者] 群組中的成員資格，因此不能用來避開對 Gpo 存取的 AGPM 管理。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-237">**Important** You should restrict membership in the Group Policy Creator Owners group, so it cannot be used to circumvent AGPM management of access to GPOs.</span></span> <span data-ttu-id="3b2ba-238">（在 [**群組原則管理主控台**] 中，按一下要管理 gpo 的林和網域中的 [**群組原則物件**]，按一下 [**委派**]，然後設定設定以符合貴組織的需求。）</span><span class="sxs-lookup"><span data-stu-id="3b2ba-238">(In the **Group Policy Management Console**, click **Group Policy Objects** in the forest and domain in which you want to manage GPOs, click **Delegation**, and then configure the settings to meet the needs of your organization.)</span></span>

 

**<span data-ttu-id="3b2ba-239">若要委派整個網域中所有 Gpo 的存取權</span><span class="sxs-lookup"><span data-stu-id="3b2ba-239">To delegate access to all GPOs throughout a domain</span></span>**

1.  <span data-ttu-id="3b2ba-240">在 [**網域委派**] 索引標籤上，按一下 [**新增**] 按鈕，選取 [群組原則管理員] 的使用者帳戶作為 [核准者]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-240">On the **Domain Delegation** tab, click the **Add** button, select the user account of the Group Policy administrator to serve as Approver, and then click **OK**.</span></span>

2.  <span data-ttu-id="3b2ba-241">在 [**新增群組或使用者**] 對話方塊中，選取要指派該角色給帳戶的**核准者**角色，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-241">In the **Add Group or User** dialog box, select the **Approver** role to assign that role to the account, and then click **OK**.</span></span> <span data-ttu-id="3b2ba-242">（此角色包含檢閱者角色）。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-242">(This role includes the Reviewer role.)</span></span>

3.  <span data-ttu-id="3b2ba-243">按一下 [**新增**] 按鈕，選取 [群組原則管理員] 的使用者帳戶做為 [編輯者]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-243">Click the **Add** button, select the user account of the Group Policy administrator to serve as Editor, and then click **OK**.</span></span>

4.  <span data-ttu-id="3b2ba-244">在 [**新增群組或使用者**] 對話方塊中，選取要將該角色指派給帳戶的 [**編輯**者角色]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-244">In the **Add Group or User** dialog box, select the **Editor** role to assign that role to the account, and then click **OK**.</span></span> <span data-ttu-id="3b2ba-245">（此角色包含檢閱者角色）。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-245">(This role includes the Reviewer role.)</span></span>

5.  <span data-ttu-id="3b2ba-246">按一下 [**新增**] 按鈕，選取 [群組原則管理員] 的使用者帳戶作為 [審查員]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-246">Click the **Add** button, select the user account of the Group Policy administrator to serve as Reviewer, and then click **OK**.</span></span>

6.  <span data-ttu-id="3b2ba-247">在 [**新增群組或使用者**] 對話方塊中，選取**檢閱者**角色，只將該角色指派給該帳戶。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-247">In the **Add Group or User** dialog box, select the **Reviewer** role to assign only that role to the account.</span></span>

## <span data-ttu-id="3b2ba-248">管理 Gpo 的步驟</span><span class="sxs-lookup"><span data-stu-id="3b2ba-248">Steps for managing GPOs</span></span>


<span data-ttu-id="3b2ba-249">您必須完成下列步驟，才能使用 AGPM 來建立、編輯、審閱及部署 Gpo。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-249">You must complete the following steps to create, edit, review, and deploy GPOs using AGPM.</span></span> <span data-ttu-id="3b2ba-250">此外，您還會建立範本、刪除 GPO，並還原刪除的 GPO。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-250">Additionally, you will create a template, delete a GPO, and restore a deleted GPO.</span></span>

[<span data-ttu-id="3b2ba-251">步驟1：建立 GPO</span><span class="sxs-lookup"><span data-stu-id="3b2ba-251">Step 1: Create a GPO</span></span>](#bkmk-manage1)

[<span data-ttu-id="3b2ba-252">步驟2：編輯 GPO</span><span class="sxs-lookup"><span data-stu-id="3b2ba-252">Step 2: Edit a GPO</span></span>](#bkmk-manage2)

[<span data-ttu-id="3b2ba-253">步驟3：審查及部署 GPO</span><span class="sxs-lookup"><span data-stu-id="3b2ba-253">Step 3: Review and deploy a GPO</span></span>](#bkmk-manage3)

[<span data-ttu-id="3b2ba-254">步驟4：使用範本建立 GPO</span><span class="sxs-lookup"><span data-stu-id="3b2ba-254">Step 4: Use a template to create a GPO</span></span>](#bkmk-manage4)

[<span data-ttu-id="3b2ba-255">步驟5：刪除及還原 GPO</span><span class="sxs-lookup"><span data-stu-id="3b2ba-255">Step 5: Delete and restore a GPO</span></span>](#bkmk-manage5)

### <a href="" id="bkmk-manage1"></a><span data-ttu-id="3b2ba-256">步驟1：建立 GPO</span><span class="sxs-lookup"><span data-stu-id="3b2ba-256">Step 1: Create a GPO</span></span>

<span data-ttu-id="3b2ba-257">在有多個群組原則系統管理員的環境中，擁有 [編輯者角色] 的使用者可以要求建立新的 Gpo，但必須由擁有核准者角色的人員核准此要求，因為建立新的 GPO 會影響生產環境。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-257">In an environment with multiple Group Policy administrators, those with the Editor role have the ability to request the creation of new GPOs, but such a request must be approved by someone with the Approver role because the creation of a new GPO impacts the production environment.</span></span>

<span data-ttu-id="3b2ba-258">在這個步驟中，您會將帳戶與編輯者角色搭配使用，以要求建立新的 GPO。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-258">In this step, you use an account with the Editor role to request the creation of a new GPO.</span></span> <span data-ttu-id="3b2ba-259">將帳戶與核准者角色結合使用，即可核准此要求並完成建立 GPO。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-259">Using an account with the Approver role, you approve this request and complete the creation of a GPO.</span></span>

**<span data-ttu-id="3b2ba-260">要求建立透過 AGPM 管理的新 GPO</span><span class="sxs-lookup"><span data-stu-id="3b2ba-260">To request the creation of a new GPO managed through AGPM</span></span>**

1.  <span data-ttu-id="3b2ba-261">在已安裝 AGPM 用戶端的電腦上，以已在 AGPM 中指派了 [編輯者角色] 的使用者帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-261">On a computer on which you have installed AGPM Client, log on with a user account that has been assigned the Editor role in AGPM.</span></span>

2.  <span data-ttu-id="3b2ba-262">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-262">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

3.  <span data-ttu-id="3b2ba-263">以滑鼠右鍵按一下 [**變更控制**] 節點，然後按一下 [**新增受控制的 GPO**]。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-263">Right-click the **Change Control** node, and then click **New Controlled GPO**.</span></span>

4.  <span data-ttu-id="3b2ba-264">在 [**新的受控 GPO** ] 對話方塊中：</span><span class="sxs-lookup"><span data-stu-id="3b2ba-264">In the **New Controlled GPO** dialog box:</span></span>

    1.  <span data-ttu-id="3b2ba-265">若要接收申請的複本，請在 [**抄送**] 欄位中輸入您的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-265">To receive a copy of the request, type your e-mail address in the **Cc** field.</span></span>

    2.  <span data-ttu-id="3b2ba-266">輸入**MyGPO**做為新 GPO 的名稱。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-266">Type **MyGPO** as the name for the new GPO.</span></span>

    3.  <span data-ttu-id="3b2ba-267">輸入新 GPO 的批註。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-267">Type a comment for the new GPO.</span></span>

    4.  <span data-ttu-id="3b2ba-268">按一下 [**建立即時**]，讓新的 GPO 在核准後立即部署到生產環境。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-268">Click **Create live** so the new GPO will be deployed to the production environment immediately upon approval.</span></span> <span data-ttu-id="3b2ba-269">按一下 **\[提交\]**。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-269">Click **Submit**.</span></span>

5.  <span data-ttu-id="3b2ba-270">當 [ **AGPM 進度**] 視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-270">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="3b2ba-271">新的 GPO 會顯示在 [**擱置**] 索引標籤上。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-271">The new GPO is displayed on the **Pending** tab.</span></span>

**<span data-ttu-id="3b2ba-272">核准擱置的要求以建立 GPO</span><span class="sxs-lookup"><span data-stu-id="3b2ba-272">To approve the pending request to create a GPO</span></span>**

1.  <span data-ttu-id="3b2ba-273">在已安裝 [AGPM 用戶端] 的電腦上，使用已指派給 AGPM 中核准者角色的使用者帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-273">On a computer on which you have installed AGPM Client, log on with a user account that has been assigned the role of Approver in AGPM.</span></span>

2.  <span data-ttu-id="3b2ba-274">開啟該帳戶的電子郵件收件匣，請注意，您已從 AGPM 別名收到一封電子郵件，並要求您建立 GPO。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-274">Open the e-mail inbox for the account, and note that you have received an e-mail message from the AGPM alias with the Editor's request to create a GPO.</span></span>

3.  <span data-ttu-id="3b2ba-275">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-275">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

4.  <span data-ttu-id="3b2ba-276">在 [**內容**] 索引標籤上，按一下 [**未決**] 索引標籤以顯示擱置中的 gpo。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-276">On the **Contents** tab, click the **Pending** tab to display the pending GPOs.</span></span>

5.  <span data-ttu-id="3b2ba-277">以滑鼠右鍵按一下 [ **MyGPO**]，然後按一下 [**核准**]。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-277">Right-click **MyGPO**, and then click **Approve**.</span></span>

6.  <span data-ttu-id="3b2ba-278">按一下 **[是]** ，確認已核准建立 GPO。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-278">Click **Yes** to confirm approval of the creation of the GPO.</span></span> <span data-ttu-id="3b2ba-279">GPO 會移至 [**受控**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-279">The GPO is moved to the **Controlled** tab.</span></span>

### <a href="" id="bkmk-manage2"></a><span data-ttu-id="3b2ba-280">步驟2：編輯 GPO</span><span class="sxs-lookup"><span data-stu-id="3b2ba-280">Step 2: Edit a GPO</span></span>

<span data-ttu-id="3b2ba-281">您可以使用 Gpo 來設定電腦或使用者設定，並將它們部署到許多電腦或使用者。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-281">You can use GPOs to configure computer or user settings and deploy them to many computers or users.</span></span> <span data-ttu-id="3b2ba-282">在這個步驟中，您會使用具有編輯者角色的帳戶來從封存中取出 GPO、離線編輯 GPO、將編輯過的 GPO 核取到封存，並要求將 GPO 部署到生產環境。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-282">In this step, you use an account with the Editor role to check out a GPO from the archive, edit the GPO offline, check the edited GPO into the archive, and request deployment of the GPO to the production environment.</span></span> <span data-ttu-id="3b2ba-283">在這種情況下，您可以設定 GPO 中的設定，要求密碼長度必須至少為八個字元。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-283">For this scenario, you configure a setting in the GPO to require that the password be at least eight characters in length.</span></span>

**<span data-ttu-id="3b2ba-284">從封存檢查 GPO 以進行編輯</span><span class="sxs-lookup"><span data-stu-id="3b2ba-284">To check the GPO out from the archive for editing</span></span>**

1.  <span data-ttu-id="3b2ba-285">在已安裝 AGPM 用戶端的電腦上，以 AGPM 中已獲「編輯者角色」的使用者帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-285">On a computer on which you have installed AGPM Client, log on with a user account that has been assigned the role of Editor in AGPM.</span></span>

2.  <span data-ttu-id="3b2ba-286">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-286">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

3.  <span data-ttu-id="3b2ba-287">在 [詳細資料] 窗格的 [**內容**] 索引標籤上，按一下 [**受控**] 索引標籤以顯示受控 gpo。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-287">On the **Contents** tab in the details pane, click the **Controlled** tab to display the controlled GPOs.</span></span>

4.  <span data-ttu-id="3b2ba-288">以滑鼠右鍵按一下 [ **MyGPO**]，然後按一下 **[取出]。**</span><span class="sxs-lookup"><span data-stu-id="3b2ba-288">Right-click **MyGPO**, and then click **Check Out**.</span></span>

5.  <span data-ttu-id="3b2ba-289">輸入要在已取出之 GPO 之歷程記錄中顯示的批註，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-289">Type a comment to be displayed in the history of the GPO while it is checked out, and then click **OK**.</span></span>

6.  <span data-ttu-id="3b2ba-290">當 [ **AGPM 進度**] 視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-290">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="3b2ba-291">在 [**受控**] 索引標籤上，GPO 的狀態會標示為 [**已取出**]。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-291">On the **Controlled** tab, the state of the GPO is identified as **Checked Out**.</span></span>

**<span data-ttu-id="3b2ba-292">若要離線編輯 GPO 並設定最小密碼長度</span><span class="sxs-lookup"><span data-stu-id="3b2ba-292">To edit the GPO offline and configure the minimum password length</span></span>**

1.  <span data-ttu-id="3b2ba-293">在 [**受控**] 索引標籤上，以滑鼠右鍵按一下 [ **MyGPO**]，然後按一下 [**編輯**] 以開啟 [**群組原則管理編輯器**] 視窗，並變更 GPO 的離線複本。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-293">On the **Controlled** tab, right-click **MyGPO**, and then click **Edit** to open the **Group Policy Management Editor** window and make changes to an offline copy of the GPO.</span></span> <span data-ttu-id="3b2ba-294">在此案例中，請設定最小密碼長度：</span><span class="sxs-lookup"><span data-stu-id="3b2ba-294">For this scenario, configure the minimum password length:</span></span>

    1.  <span data-ttu-id="3b2ba-295">在 [**電腦**設定] 底下，按兩下 [**原則**]、[ **Windows 設定**]、[**安全性設定**]、[**帳戶原則**] 和 [**密碼原則**]。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-295">Under **Computer Configuration**, double-click **Policies**, **Windows Settings**, **Security Settings**, **Account Policies**, and **Password Policy**.</span></span>

    2.  <span data-ttu-id="3b2ba-296">在 [詳細資料] 窗格中，按兩下 [**最小密碼長度**]。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-296">In the details pane, double-click **Minimum password length**.</span></span>

    3.  <span data-ttu-id="3b2ba-297">在 [屬性] 視窗中，選取 [**定義這個原則設定**] 核取方塊，將字元數設為**8**，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-297">In the properties window, select the **Define this policy setting** check box, set the number of characters to **8**, and then click **OK**.</span></span>

2.  <span data-ttu-id="3b2ba-298">關閉 [**群組原則管理編輯器**] 視窗。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-298">Close the **Group Policy Management Editor** window.</span></span>

**<span data-ttu-id="3b2ba-299">將 GPO 檢查到封存</span><span class="sxs-lookup"><span data-stu-id="3b2ba-299">To check the GPO into the archive</span></span>**

1.  <span data-ttu-id="3b2ba-300">在 [**受控**] 索引標籤上，以滑鼠右鍵按一下**MyGPO** ，然後按一下 [**存回**]。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-300">On the **Controlled** tab, right-click **MyGPO** and then click **Check In**.</span></span>

2.  <span data-ttu-id="3b2ba-301">輸入批註，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-301">Type a comment, and then click **OK**.</span></span>

3.  <span data-ttu-id="3b2ba-302">當 [ **AGPM 進度**] 視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-302">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="3b2ba-303">在 [**受控**] 索引標籤上，GPO 的狀態會標示為 [**已核**取]。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-303">On the **Controlled** tab, the state of the GPO is identified as **Checked In**.</span></span>

**<span data-ttu-id="3b2ba-304">向生產環境要求 GPO 部署</span><span class="sxs-lookup"><span data-stu-id="3b2ba-304">To request the deployment of the GPO to the production environment</span></span>**

1.  <span data-ttu-id="3b2ba-305">在 [**受控**] 索引標籤上，以滑鼠右鍵按一下**MyGPO** ，然後按一下 [**部署**]。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-305">On the **Controlled** tab, right-click **MyGPO** and then click **Deploy**.</span></span>

2.  <span data-ttu-id="3b2ba-306">因為此帳戶不是核准者或 AGPM 管理員，所以您必須提交部署的要求。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-306">Because this account is not an Approver or AGPM Administrator, you must submit a request for deployment.</span></span> <span data-ttu-id="3b2ba-307">若要接收申請的複本，請在 [**抄送**] 欄位中輸入您的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-307">To receive a copy of the request, type your e-mail address in the **Cc** field.</span></span> <span data-ttu-id="3b2ba-308">輸入要顯示在 GPO 歷程記錄中的批註，然後按一下 [**提交**]。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-308">Type a comment to be displayed in the history of the GPO, and then click **Submit**.</span></span>

3.  <span data-ttu-id="3b2ba-309">當 [ **AGPM 進度**] 視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-309">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="3b2ba-310">**MyGPO**會顯示在 [**擱置**] 索引標籤上的 [gpo] 清單中。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-310">**MyGPO** is displayed on the list of GPOs on the **Pending** tab.</span></span>

### <a href="" id="bkmk-manage3"></a><span data-ttu-id="3b2ba-311">步驟3：審查及部署 GPO</span><span class="sxs-lookup"><span data-stu-id="3b2ba-311">Step 3: Review and deploy a GPO</span></span>

<span data-ttu-id="3b2ba-312">在這個步驟中，您會擔當核准者、建立報告並分析設定，以及變更 GPO 中的設定，以判斷是否應該核准。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-312">In this step, you act as an Approver, creating reports and analyzing the settings and changes to settings in the GPO to determine whether you should approve them.</span></span> <span data-ttu-id="3b2ba-313">在評估 GPO 之後，您可以將它部署到生產環境，並將它連結至網域或組織單位（OU），使其在針對該域或 OU 中的電腦重新整理群組原則時生效。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-313">After evaluating the GPO, you deploy it to the production environment and link it to a domain or an organizational unit (OU) so that it takes effect when Group Policy is refreshed for computers in that domain or OU.</span></span>

**<span data-ttu-id="3b2ba-314">若要查看 GPO 中的設定</span><span class="sxs-lookup"><span data-stu-id="3b2ba-314">To review settings in the GPO</span></span>**

1. <span data-ttu-id="3b2ba-315">在已安裝 [AGPM 用戶端] 的電腦上，使用已指派給 AGPM 中核准者角色的使用者帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-315">On a computer on which you have installed AGPM Client, log on with a user account that has been assigned the role of Approver in AGPM.</span></span> <span data-ttu-id="3b2ba-316">（任何具有檢閱者角色且包含在其他所有角色中的群組原則管理員，都可以查看 GPO 中的設定）。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-316">(Any Group Policy administrator with the Reviewer role, which is included in all of the other roles, can review the settings in a GPO.)</span></span>

2. <span data-ttu-id="3b2ba-317">開啟該帳戶的電子郵件收件匣，請注意，您已收到來自 AGPM 別名的電子郵件，並要求您要部署 GPO。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-317">Open the e-mail inbox for the account and note that you have received an e-mail message from the AGPM alias with an Editor's request to deploy a GPO.</span></span>

3. <span data-ttu-id="3b2ba-318">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-318">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

4. <span data-ttu-id="3b2ba-319">在 [詳細資料] 窗格的 [**內容**] 索引標籤上，按一下 [**擱置**] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="3b2ba-319">On the **Contents** tab in the details pane, click the **Pending** tab.</span></span>

5. <span data-ttu-id="3b2ba-320">按兩下 [ **MyGPO** ] 以顯示其歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-320">Double-click **MyGPO** to display its history.</span></span>

6. <span data-ttu-id="3b2ba-321">查看最新版本的 MyGPO 中的設定：</span><span class="sxs-lookup"><span data-stu-id="3b2ba-321">Review the settings in the most recent version of MyGPO:</span></span>

   1.  <span data-ttu-id="3b2ba-322">在 [歷程**記錄**] 視窗中，以滑鼠右鍵按一下包含最近時間戳記的 GPO 版本，按一下 [**設定**]，然後按一下 [ **HTML 報告**]，以顯示 GPO 設定的摘要。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-322">In the **History** window, right-click the GPO version with the most recent timestamp, click **Settings**, and then click **HTML Report** to display a summary of the GPO's settings.</span></span>

   2.  <span data-ttu-id="3b2ba-323">在網頁瀏覽器中，按一下 [**全部顯示**] 以顯示 GPO 中的所有設定。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-323">In the Web browser, click **show all** to display all of the settings in the GPO.</span></span> <span data-ttu-id="3b2ba-324">關閉瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-324">Close the browser.</span></span>

7. <span data-ttu-id="3b2ba-325">將最新版本的 MyGPO 與簽入到封存的第一個版本進行比較：</span><span class="sxs-lookup"><span data-stu-id="3b2ba-325">Compare the most recent version of MyGPO to the first version checked in to the archive:</span></span>

   1. <span data-ttu-id="3b2ba-326">在 [歷程**記錄**] 視窗中，按一下包含最近時間戳記的 GPO 版本。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-326">In the **History** window, click the GPO version with the most recent time stamp.</span></span> <span data-ttu-id="3b2ba-327">按住 CTRL，然後按一下**電腦版本**不是 \* \* \* \* \* 的最舊 GPO 版本。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-327">Press CTRL and click the oldest GPO version for which the **Computer Version** is not \*\*\\*\*\*.</span></span>

   2. <span data-ttu-id="3b2ba-328">按一下 [**差異**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-328">Click the **Differences** button.</span></span> <span data-ttu-id="3b2ba-329">[**帳戶原則/密碼原則**] 區段會以綠色醒目提示，並在前面加上**\ [+ \]**，指出此設定僅在後一個 GPO 版本中設定。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-329">The **Account Policies/Password Policy** section is highlighted in green and preceded by **\[+\]**, indicating that this setting is configured only in the latter version of the GPO.</span></span>

   3. <span data-ttu-id="3b2ba-330">按一下 [**帳戶原則/密碼原則**]。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-330">Click **Account Policies/Password Policy**.</span></span> <span data-ttu-id="3b2ba-331">[**最小密碼長度**] 設定也會以綠色醒目提示，並在前面加上**\ [+ \]**，指出它僅在後一個 GPO 版本中進行設定。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-331">The **Minimum password length** setting is also highlighted in green and preceded by **\[+\]**, indicating that it is configured only in the latter version of the GPO.</span></span>

   4. <span data-ttu-id="3b2ba-332">關閉網頁瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-332">Close the Web browser.</span></span>

**<span data-ttu-id="3b2ba-333">將 GPO 部署到生產環境</span><span class="sxs-lookup"><span data-stu-id="3b2ba-333">To deploy the GPO to the production environment</span></span>**

1.  <span data-ttu-id="3b2ba-334">在 [**擱置**] 索引標籤上，以滑鼠右鍵按一下 [ **MyGPO** ]，然後按一下 [**核准**]</span><span class="sxs-lookup"><span data-stu-id="3b2ba-334">On the **Pending** tab, right-click **MyGPO** and then click **Approve**.</span></span>

2.  <span data-ttu-id="3b2ba-335">輸入要包含在 GPO 歷程記錄中的批註。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-335">Type a comment to include in the history of the GPO.</span></span>

3.  <span data-ttu-id="3b2ba-336">按一下 **\[是\]**。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-336">Click **Yes**.</span></span> <span data-ttu-id="3b2ba-337">當 [ **AGPM 進度**] 視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-337">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="3b2ba-338">GPO 已部署至生產環境。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-338">The GPO is deployed to the production environment.</span></span>

**<span data-ttu-id="3b2ba-339">將 GPO 連結至網域或組織單位</span><span class="sxs-lookup"><span data-stu-id="3b2ba-339">To link the GPO to a domain or organizational unit</span></span>**

1.  <span data-ttu-id="3b2ba-340">在 GPMC 中，以滑鼠右鍵按一下要套用您所設定之 GPO 的網域或 OU，然後按一下 [**連結現有的 gpo**]。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-340">In the GPMC, right-click the domain or an OU to which to apply the GPO that you configured, and then click **Link an Existing GPO**.</span></span>

2.  <span data-ttu-id="3b2ba-341">在 [**選取 GPO** ] 對話方塊中，按一下 [ **MyGPO**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-341">In the **Select GPO** dialog box, click **MyGPO**, and then click **OK**.</span></span>

### <a href="" id="bkmk-manage4"></a><span data-ttu-id="3b2ba-342">步驟4：使用範本建立 GPO</span><span class="sxs-lookup"><span data-stu-id="3b2ba-342">Step 4: Use a template to create a GPO</span></span>

<span data-ttu-id="3b2ba-343">在這個步驟中，您會將帳戶與編輯者角色搭配使用，以建立範本（即無法編輯、靜態版本的 GPO）做為建立新 Gpo 的起點，然後根據該範本建立新的 GPO。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-343">In this step, you use an account with the Editor role to create a template—an uneditable, static version of a GPO for use as a starting point for creating new GPOs—and then create a new GPO based upon that template.</span></span> <span data-ttu-id="3b2ba-344">範本對於快速建立包含許多相同設定的多個 Gpo 很有用。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-344">Templates are useful for quickly creating multiple GPOs that include many of the same settings.</span></span>

**<span data-ttu-id="3b2ba-345">根據現有的 GPO 建立範本</span><span class="sxs-lookup"><span data-stu-id="3b2ba-345">To create a template based on an existing GPO</span></span>**

1.  <span data-ttu-id="3b2ba-346">在已安裝 AGPM 用戶端的電腦上，以 AGPM 中已獲「編輯者角色」的使用者帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-346">On a computer on which you have installed AGPM Client, log on with a user account that has been assigned the role of Editor in AGPM.</span></span>

2.  <span data-ttu-id="3b2ba-347">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-347">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

3.  <span data-ttu-id="3b2ba-348">在 [詳細資料] 窗格的 [**內容**] 索引標籤上，按一下 [**受控**] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="3b2ba-348">On the **Contents** tab in the details pane, click the **Controlled** tab.</span></span>

4.  <span data-ttu-id="3b2ba-349">以滑鼠右鍵按一下 [ **MyGPO**]，然後按一下 [**另存為範本**]，建立包含目前 MyGPO 中所有設定的範本。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-349">Right-click **MyGPO**, and then click **Save as Template** to create a template incorporating all settings currently in MyGPO.</span></span>

5.  <span data-ttu-id="3b2ba-350">輸入**MyTemplate**做為範本的名稱和批註，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-350">Type **MyTemplate** as the name for the template and a comment, and then click **OK**.</span></span>

6.  <span data-ttu-id="3b2ba-351">當 [ **AGPM 進度**] 視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-351">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="3b2ba-352">新範本隨即出現在 [**範本**] 索引標籤上。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-352">The new template appears on the **Templates** tab.</span></span>

**<span data-ttu-id="3b2ba-353">要求建立透過 AGPM 管理的新 GPO</span><span class="sxs-lookup"><span data-stu-id="3b2ba-353">To request the creation of a new GPO managed through AGPM</span></span>**

1.  <span data-ttu-id="3b2ba-354">按一下 [**受控**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-354">Click the **Controlled** tab.</span></span>

2.  <span data-ttu-id="3b2ba-355">以滑鼠右鍵按一下 [**變更控制**] 節點，然後按一下 [**新增受控制的 GPO**]。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-355">Right-click the **Change Control** node, and then click **New Controlled GPO**.</span></span>

3.  <span data-ttu-id="3b2ba-356">在 [**新的受控 GPO** ] 對話方塊中：</span><span class="sxs-lookup"><span data-stu-id="3b2ba-356">In the **New Controlled GPO** dialog box:</span></span>

    1.  <span data-ttu-id="3b2ba-357">若要接收申請的複本，請在 [**抄送**] 欄位中輸入您的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-357">To receive a copy of the request, type your e-mail address in the **Cc** field.</span></span>

    2.  <span data-ttu-id="3b2ba-358">輸入**MyOtherGPO**做為新 GPO 的名稱。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-358">Type **MyOtherGPO** as the name for the new GPO.</span></span>

    3.  <span data-ttu-id="3b2ba-359">輸入新 GPO 的批註。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-359">Type a comment for the new GPO.</span></span>

    4.  <span data-ttu-id="3b2ba-360">按一下 [**建立即時**]，讓新的 GPO 在核准後立即部署到生產環境。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-360">Click **Create live**, so the new GPO will be deployed to the production environment immediately upon approval.</span></span>

    5.  <span data-ttu-id="3b2ba-361">針對 [ **GPO 範本**]，選取 [ **MyTemplate**]。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-361">For **From GPO template**, select **MyTemplate**.</span></span> <span data-ttu-id="3b2ba-362">按一下 **\[提交\]**。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-362">Click **Submit**.</span></span>

4.  <span data-ttu-id="3b2ba-363">當 [ **AGPM 進度**] 視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-363">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="3b2ba-364">新的 GPO 會顯示在 [**擱置**] 索引標籤上。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-364">The new GPO is displayed on the **Pending** tab.</span></span>

<span data-ttu-id="3b2ba-365">使用已指派核准者角色的帳戶，以核准擱置的要求來建立 GPO，就像您在[步驟1：建立 gpo](#bkmk-manage1)一樣。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-365">Use an account that has been assigned the role of Approver to approve the pending request to create the GPO as you did in [Step 1: Create a GPO](#bkmk-manage1).</span></span> <span data-ttu-id="3b2ba-366">MyTemplate 包含您在 MyGPO 中設定的所有設定。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-366">MyTemplate incorporates all of the settings that you configured in MyGPO.</span></span> <span data-ttu-id="3b2ba-367">因為 MyOtherGPO 是使用 MyTemplate 建立的，所以它最初會包含 MyTemplate 建立時 MyGPO 所包含的所有設定。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-367">Because MyOtherGPO was created using MyTemplate, it initially contains all of the settings that MyGPO contained at the time that MyTemplate was created.</span></span> <span data-ttu-id="3b2ba-368">您可以產生差異報告來比較 MyOtherGPO 與 MyTemplate，以進行確認。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-368">You can confirm this by generating a difference report to compare MyOtherGPO to MyTemplate.</span></span>

**<span data-ttu-id="3b2ba-369">從封存檢查 GPO 以進行編輯</span><span class="sxs-lookup"><span data-stu-id="3b2ba-369">To check the GPO out from the archive for editing</span></span>**

1.  <span data-ttu-id="3b2ba-370">在已安裝 AGPM 用戶端的電腦上，以 AGPM 中已獲「編輯者角色」的使用者帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-370">On a computer on which you have installed AGPM Client, log on with a user account that has been assigned the role of Editor in AGPM.</span></span>

2.  <span data-ttu-id="3b2ba-371">以滑鼠右鍵按一下 [ **MyOtherGPO**]，然後按一下 **[取出]。**</span><span class="sxs-lookup"><span data-stu-id="3b2ba-371">Right-click **MyOtherGPO**, and then click **Check Out**.</span></span>

3.  <span data-ttu-id="3b2ba-372">輸入要在已取出之 GPO 之歷程記錄中顯示的批註，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-372">Type a comment to be displayed in the history of the GPO while it is checked out, and then click **OK**.</span></span>

4.  <span data-ttu-id="3b2ba-373">當 [ **AGPM 進度**] 視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-373">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="3b2ba-374">在 [**受控**] 索引標籤上，GPO 的狀態會標示為 [**已取出**]。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-374">On the **Controlled** tab, the state of the GPO is identified as **Checked Out**.</span></span>

**<span data-ttu-id="3b2ba-375">若要離線編輯 GPO 並設定帳戶鎖定時間</span><span class="sxs-lookup"><span data-stu-id="3b2ba-375">To edit the GPO offline and configure the account lockout duration</span></span>**

1.  <span data-ttu-id="3b2ba-376">在 [**受控**] 索引標籤上，以滑鼠右鍵按一下 [ **MyOtherGPO**]，然後按一下 [**編輯**] 以開啟 [**群組原則管理編輯器**] 視窗，並變更 GPO 的離線複本。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-376">On the **Controlled** tab, right-click **MyOtherGPO**, and then click **Edit** to open the **Group Policy Management Editor** window and make changes to an offline copy of the GPO.</span></span> <span data-ttu-id="3b2ba-377">在此案例中，請設定最小密碼長度：</span><span class="sxs-lookup"><span data-stu-id="3b2ba-377">For this scenario, configure the minimum password length:</span></span>

    1.  <span data-ttu-id="3b2ba-378">在 [**電腦**設定] 底下，按兩下 [**原則**]、[ **Windows 設定**]、[**安全性設定**]、[**帳戶原則**] 和 [**帳戶封鎖原則**]。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-378">Under **Computer Configuration**, double-click **Policies**, **Windows Settings**, **Security Settings**, **Account Policies**, and **Account Lockout Policy**.</span></span>

    2.  <span data-ttu-id="3b2ba-379">在 [詳細資料] 窗格中，按兩下 [**帳戶鎖定時間**]。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-379">In the details pane, double-click **Account lockout duration**.</span></span>

    3.  <span data-ttu-id="3b2ba-380">在 [屬性] 視窗中，核取 [**定義此原則設定**]，將 [持續時間] 設定為**30**分鐘，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-380">In the properties window, check **Define this policy setting**, set the duration to **30** minutes, and then click **OK**.</span></span>

2.  <span data-ttu-id="3b2ba-381">關閉 [**群組原則管理編輯器**] 視窗。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-381">Close the **Group Policy Management Editor** window.</span></span>

<span data-ttu-id="3b2ba-382">將 MyOtherGPO 簽入封存並要求部署，就像您在[步驟2：編輯 GPO](#bkmk-manage2)中所做的一樣。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-382">Check MyOtherGPO into the archive and request deployment as you did for MyGPO in [Step 2: Edit a GPO](#bkmk-manage2).</span></span> <span data-ttu-id="3b2ba-383">您可以使用 [差異] 報告，將 MyOtherGPO 與 MyGPO 或 MyTemplate 進行比較。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-383">You can compare MyOtherGPO to MyGPO or to MyTemplate using difference reports.</span></span> <span data-ttu-id="3b2ba-384">任何包含檢閱者角色的帳戶（AGPM 系統管理員 \ [完全控制 \]、審核者、編輯者或檢閱者）都可以產生報告。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-384">Any account that includes the Reviewer role (AGPM Administrator \[Full Control\], Approver, Editor, or Reviewer) can generate reports.</span></span>

**<span data-ttu-id="3b2ba-385">比較 GPO 與另一個 GPO 及範本</span><span class="sxs-lookup"><span data-stu-id="3b2ba-385">To compare a GPO to another GPO and to a template</span></span>**

1.  <span data-ttu-id="3b2ba-386">若要比較 MyGPO 和 MyOtherGPO：</span><span class="sxs-lookup"><span data-stu-id="3b2ba-386">To compare MyGPO and MyOtherGPO:</span></span>

    1.  <span data-ttu-id="3b2ba-387">在 [**受控**] 索引標籤上，按一下 [ **MyGPO**]。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-387">On the **Controlled** tab, click **MyGPO**.</span></span> <span data-ttu-id="3b2ba-388">按 CTRL 鍵，然後按一下 [ **MyOtherGPO**]。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-388">Press CTRL and then click **MyOtherGPO**.</span></span>

    2.  <span data-ttu-id="3b2ba-389">以滑鼠右鍵按一下 [ **MyOtherGPO**]，指向 [**差異**]，然後按一下 [ **HTML 報表**]。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-389">Right-click **MyOtherGPO**, point to **Differences**, and click **HTML Report**.</span></span>

2.  <span data-ttu-id="3b2ba-390">若要比較 MyOtherGPO 和 MyTemplate：</span><span class="sxs-lookup"><span data-stu-id="3b2ba-390">To compare MyOtherGPO and MyTemplate:</span></span>

    1.  <span data-ttu-id="3b2ba-391">在 [**受控**] 索引標籤上，按一下 [ **MyOtherGPO**]。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-391">On the **Controlled** tab, click **MyOtherGPO**.</span></span>

    2.  <span data-ttu-id="3b2ba-392">以滑鼠右鍵按一下 [ **MyOtherGPO**]，指向 [**差異**]，然後按一下 [**範本**]。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-392">Right-click **MyOtherGPO**, point to **Differences**, and click **Template**.</span></span>

    3.  <span data-ttu-id="3b2ba-393">選取 [ **MyTemplate**及**HTML 報表**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-393">Select **MyTemplate** and **HTML Report**, and then click **OK**.</span></span>

### <a href="" id="bkmk-manage5"></a><span data-ttu-id="3b2ba-394">步驟5：刪除及還原 GPO</span><span class="sxs-lookup"><span data-stu-id="3b2ba-394">Step 5: Delete and restore a GPO</span></span>

<span data-ttu-id="3b2ba-395">在此步驟中，您會擔任核准者來刪除 GPO。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-395">In this step, you act as an Approver to delete a GPO.</span></span>

**<span data-ttu-id="3b2ba-396">刪除 GPO</span><span class="sxs-lookup"><span data-stu-id="3b2ba-396">To delete a GPO</span></span>**

1.  <span data-ttu-id="3b2ba-397">在已安裝 AGPM 用戶端的電腦上，以已指派核准者角色的使用者帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-397">On a computer on which you have installed AGPM Client, log on with a user account that has been assigned the role of Approver.</span></span>

2.  <span data-ttu-id="3b2ba-398">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-398">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

3.  <span data-ttu-id="3b2ba-399">在 [**內容**] 索引標籤上，按一下 [**受控**] 索引標籤以顯示受控制的 gpo。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-399">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

4.  <span data-ttu-id="3b2ba-400">以滑鼠右鍵按一下 [ **MyGPO**]，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-400">Right-click **MyGPO**, and then click **Delete**.</span></span> <span data-ttu-id="3b2ba-401">按一下 [**從封存及生產刪除 GPO** ]，即可刪除封存中的版本，以及在生產環境中已部署的 gpo 版本。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-401">Click **Delete GPO from archive and production** to delete both the version in the archive as well as the deployed version of the GPO in the production environment.</span></span>

5.  <span data-ttu-id="3b2ba-402">輸入要顯示在 GPO 的審核追蹤中的批註，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-402">Type a comment to be displayed in the audit trail for the GPO, and then click **OK**.</span></span>

6.  <span data-ttu-id="3b2ba-403">當 [ **AGPM 進度**] 視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-403">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="3b2ba-404">該 GPO 隨即會從 [**受控**] 索引標籤中移除，並顯示在 [**回收站**] 索引標籤上，可供您還原或銷毀。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-404">The GPO is removed from the **Controlled** tab and is displayed on the **Recycle Bin** tab, where it can be restored or destroyed.</span></span>

<span data-ttu-id="3b2ba-405">有時候，您可能會在刪除仍需要的 GPO 之後進行探索。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-405">Occasionally you may discover after deleting a GPO that it is still needed.</span></span> <span data-ttu-id="3b2ba-406">在此步驟中，您會擔任核准者來還原已刪除的 GPO。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-406">In this step, you act as an Approver to restore a GPO that has been deleted.</span></span>

**<span data-ttu-id="3b2ba-407">還原已刪除的 GPO</span><span class="sxs-lookup"><span data-stu-id="3b2ba-407">To restore a deleted GPO</span></span>**

1.  <span data-ttu-id="3b2ba-408">在 [**內容**] 索引標籤上，按一下 [**回收站**] 索引標籤以顯示已刪除的 gpo。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-408">On the **Contents** tab, click the **Recycle Bin** tab to display deleted GPOs.</span></span>

2.  <span data-ttu-id="3b2ba-409">以滑鼠右鍵按一下 [ **MyGPO**]，然後按一下 [**還原**]。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-409">Right-click **MyGPO**, and then click **Restore**.</span></span>

3.  <span data-ttu-id="3b2ba-410">輸入要顯示在 GPO 歷程記錄中的批註，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-410">Type a comment to be displayed in the history of the GPO, and then click **OK**.</span></span>

4.  <span data-ttu-id="3b2ba-411">當 [ **AGPM 進度**] 視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-411">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="3b2ba-412">該 GPO 隨即會從 [**回收站**] 索引標籤中移除，並顯示在 [**受控**] 索引標籤上。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-412">The GPO is removed from the **Recycle Bin** tab and is displayed on the **Controlled** tab.</span></span>

    <span data-ttu-id="3b2ba-413">**記事** 將 GPO 還原到封存後並不會自動將它重新部署到生產環境。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-413">**Note** Restoring a GPO to the archive does not automatically redeploy it to the production environment.</span></span> <span data-ttu-id="3b2ba-414">若要將 GPO 傳回生產環境，請像在步驟3中一樣部署 GPO [：審查及部署 gpo](#bkmk-manage3)。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-414">To return the GPO to the production environment, deploy the GPO as in [Step 3: Review and deploy a GPO](#bkmk-manage3).</span></span>

     

<span data-ttu-id="3b2ba-415">在編輯和部署 GPO 之後，您可能會發現對 GPO 所做的最近變更會造成問題。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-415">After editing and deploying a GPO, you may discover that recent changes to the GPO are causing a problem.</span></span> <span data-ttu-id="3b2ba-416">在這個步驟中，您會擔任核准者來回滾到舊版的 GPO。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-416">In this step, you act as an Approver to roll back to a previous version of the GPO.</span></span> <span data-ttu-id="3b2ba-417">您可以返回 GPO 歷程記錄中的任何版本。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-417">You can roll back to any version in the history of the GPO.</span></span> <span data-ttu-id="3b2ba-418">您可以使用 [批註] 和 [標籤] 來識別已知良好的版本，以及何時進行特定的變更。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-418">You can use comments and labels to identify known good versions and when specific changes were made.</span></span>

**<span data-ttu-id="3b2ba-419">回退到舊版的 GPO</span><span class="sxs-lookup"><span data-stu-id="3b2ba-419">To roll back to a previous version of a GPO</span></span>**

1.  <span data-ttu-id="3b2ba-420">在 [**內容**] 索引標籤上，按一下 [**受控**] 索引標籤以顯示受控制的 gpo。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-420">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

2.  <span data-ttu-id="3b2ba-421">按兩下 [ **MyGPO** ] 以顯示其歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-421">Double-click **MyGPO** to display its history.</span></span>

3.  <span data-ttu-id="3b2ba-422">以滑鼠右鍵按一下要部署的版本，按一下 [**部署**]，然後按一下 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-422">Right-click the version to be deployed, click **Deploy**, and then click **Yes**.</span></span>

4.  <span data-ttu-id="3b2ba-423">當**進度**視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-423">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="3b2ba-424">在 [歷程**記錄**] 視窗中，按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-424">In the **History** window, click **Close**.</span></span>

    <span data-ttu-id="3b2ba-425">**記事** 若要驗證已重新部署的版本是否為所需版本，請檢查兩個版本的差異報告。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-425">**Note** To verify that the version that has been redeployed is the version intended, examine a difference report for the two versions.</span></span> <span data-ttu-id="3b2ba-426">在 GPO 的 [歷程**記錄**] 視窗中，選取兩個版本，以滑鼠右鍵按一下這些版本，指向 [**差異**]，然後按一下 [ **HTML 報表**] 或 [ **XML 報表**]。</span><span class="sxs-lookup"><span data-stu-id="3b2ba-426">In the **History** window for the GPO, select the two versions, right-click them, point to **Difference**, and then click either **HTML Report** or **XML Report**.</span></span>

     

 

 





