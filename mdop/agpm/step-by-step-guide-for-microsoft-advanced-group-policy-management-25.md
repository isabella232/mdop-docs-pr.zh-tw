---
title: Microsoft 進階群組原則管理 2.5 逐步指南
description: Microsoft 進階群組原則管理 2.5 逐步指南
author: dansimp
ms.assetid: 454298c9-0fab-497a-9808-c0246a4c8db5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 67925e417e4fb1f5398dfd030f366936f1d36909
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802518"
---
# <span data-ttu-id="6e8cb-103">Microsoft 進階群組原則管理 2.5 逐步指南</span><span class="sxs-lookup"><span data-stu-id="6e8cb-103">Step-by-Step Guide for Microsoft Advanced Group Policy Management 2.5</span></span>


<span data-ttu-id="6e8cb-104">本逐步指南說明使用群組原則管理主控台（GPMC）和 Microsoft 高級群組原則管理（AGPM）的群組原則管理的高級技術。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-104">This step-by-step guide demonstrates advanced techniques for Group Policy management using the Group Policy Management Console (GPMC) and Microsoft Advanced Group Policy Management (AGPM).</span></span> <span data-ttu-id="6e8cb-105">AGPM 會增加 GPMC 的功能，提供：</span><span class="sxs-lookup"><span data-stu-id="6e8cb-105">AGPM increases the capabilities of the GPMC, providing:</span></span>

-   <span data-ttu-id="6e8cb-106">委派許可權以管理群群組原則物件（Gpo）至多個群組原則系統管理員的標準角色。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-106">Standard roles for delegating permissions to manage Group Policy objects (GPOs) to multiple Group Policy administrators.</span></span>

-   <span data-ttu-id="6e8cb-107">[封存] 可讓群組原則管理員在將 Gpo 部署到生產環境之前，建立及修改 Gpo。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-107">An archive to enable Group Policy administrators to create and modify GPOs offline before deploying them to a production environment.</span></span>

-   <span data-ttu-id="6e8cb-108">回滾至任何舊版 GPO 的功能。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-108">The ability to roll back to any previous version of a GPO.</span></span>

-   <span data-ttu-id="6e8cb-109">Gpo 的存回/取出功能可確保群組原則管理員不會無意間覆寫對方的工作。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-109">Check-in/check-out capability for GPOs to ensure that Group Policy administrators do not inadvertently overwrite each other's work.</span></span>

## <span data-ttu-id="6e8cb-110">AGPM 案例概述</span><span class="sxs-lookup"><span data-stu-id="6e8cb-110">AGPM scenario overview</span></span>


<span data-ttu-id="6e8cb-111">在這種情況下，您將針對 AGPM 中的每個角色使用個別的使用者帳戶，示範如何在有多個群組原則系統管理員具有不同許可權等級的環境中管理群組原則。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-111">For this scenario, you will use a separate user account for each role in AGPM to demonstrate how Group Policy can be managed in an environment with multiple Group Policy administrators who have different levels of permissions.</span></span> <span data-ttu-id="6e8cb-112">具體來說，您將會執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="6e8cb-112">Specifically, you will perform the following tasks:</span></span>

-   <span data-ttu-id="6e8cb-113">使用網域系統管理員群組成員的帳戶，安裝 AGPM 服務器並將 AGPM 系統管理員角色指派給帳戶或群組。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-113">Using an account that is a member of the Domain Admins group, install AGPM Server and assign the AGPM Administrator role to an account or group.</span></span>

-   <span data-ttu-id="6e8cb-114">使用您將指派 AGPM 角色的帳戶，安裝 AGPM 用戶端。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-114">Using accounts to which you will assign AGPM roles, install AGPM Client.</span></span>

-   <span data-ttu-id="6e8cb-115">使用具有 AGPM 系統管理員角色的帳戶，設定 AGPM 並委派對 Gpo 的存取權，方法是指派角色給其他帳戶。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-115">Using an account with the AGPM Administrator role, configure AGPM and delegate access to GPOs by assigning roles to other accounts.</span></span>

-   <span data-ttu-id="6e8cb-116">將帳戶與 [編輯者角色] 一起使用，要求建立 GPO，然後核准將帳戶與核准者角色一起使用。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-116">Using an account with the Editor role, request the creation of a GPO, which you then approve using an account with the Approver role.</span></span> <span data-ttu-id="6e8cb-117">使用 [編輯者] 帳戶，核取 [封存] 以外的 GPO、編輯 GPO、將 GPO 檢查到封存，然後要求部署。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-117">With the Editor account, check the GPO out of the archive, edit the GPO, check the GPO into the archive, and request deployment.</span></span>

-   <span data-ttu-id="6e8cb-118">將帳戶與核准者角色一起使用，查看 GPO 並將它部署到您的生產環境。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-118">Using an account with the Approver role, review the GPO and deploy it to your production environment.</span></span>

-   <span data-ttu-id="6e8cb-119">將帳戶與編輯者角色搭配使用，建立一個 GPO 範本，並使用它做為建立新 GPO 的起點。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-119">Using an account with the Editor role, create a GPO template and use it as a starting point to create a new GPO.</span></span>

-   <span data-ttu-id="6e8cb-120">將帳戶與核准者角色一起使用，刪除並還原 GPO。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-120">Using an account with the Approver role, delete and restore a GPO.</span></span>

![群組原則物件開發程式](images/ab77a1f3-f430-4e7d-be58-ee8f9bd1140e.gif)

## <span data-ttu-id="6e8cb-122">需求</span><span class="sxs-lookup"><span data-stu-id="6e8cb-122">Requirements</span></span>


<span data-ttu-id="6e8cb-123">您想要安裝 AGPM 的電腦必須符合下列需求，而且您必須建立帳戶才能在這個案例中使用。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-123">Computers on which you want to install AGPM must meet the following requirements, and you must create accounts for use in this scenario.</span></span>

### <span data-ttu-id="6e8cb-124">AGPM 服務器需求</span><span class="sxs-lookup"><span data-stu-id="6e8cb-124">AGPM Server requirements</span></span>

<span data-ttu-id="6e8cb-125">AGPM Server 2.5 需要 WindowsVista®（32位版本），且未安裝 service pack 或 Windows Server®2003（32位版本），以及 GPMC。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-125">AGPM Server2.5 requires WindowsVista® (32-bit version) with no service packs installed or Windows Server®2003 (32-bit version), as well as the GPMC.</span></span> <span data-ttu-id="6e8cb-126">此外，您必須是網域系統管理員群組的成員，才能安裝 AGPM 服務器。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-126">Additionally, you must be a member of the Domain Admins group to install AGPM Server.</span></span>

<span data-ttu-id="6e8cb-127">您應該在成員伺服器或含有您可供您使用且由 AGPM 支援之最新版本的 GPMC 的網域控制站上安裝 AGPM 服務器。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-127">You should install AGPM Server on a member server or domain controller with the most recent version of the GPMC that is available to you and supported by AGPM.</span></span> <span data-ttu-id="6e8cb-128">AGPM 使用 GPMC 來備份及還原 Gpo，而較新的 GPMC 版本則會提供在先前版本中無法使用的其他原則設定。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-128">AGPM uses the GPMC to back up and restore GPOs, and newer versions of the GPMC provide additional policy settings not available in preceding versions.</span></span> <span data-ttu-id="6e8cb-129">如果您的 AGPM 服務器上的 GPMC 版本比管理員用來管理群組原則之電腦上的版本舊，則 AGPM 服務器將無法儲存無法在舊版 GPMC 中使用的原則設定。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-129">If the version of the GPMC on your AGPM Server is older than the version on the computers that administrators use to manage Group Policy, the AGPM Server will be unable to store those policy settings not available in the older version of the GPMC.</span></span>

<span data-ttu-id="6e8cb-130">具體說來，如果您的 AGPM 服務器執行的是 Windows Server2003 及隨附該版本的 GPMC 版本，而您的群組原則管理員電腦執行 WindowsVista 和隨附該版本的 GPMC，您仍可管理大多數原則設定。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-130">Specifically, if your AGPM Server is running Windows Server2003 and the version of the GPMC that accompanied it, and your Group Policy administrators’ computers are running WindowsVista and the version of the GPMC that accompanied it, you can still manage most policy settings.</span></span> <span data-ttu-id="6e8cb-131">不過，在 windows Server 2003 的 GPMC （例如與資料夾重新導向、無線網路（IEEE 802.11）及部署的印表機）中無法使用 gpmc 的原則設定，即使系統管理員可以在其電腦上使用 AGPM 來設定它們。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-131">However, policy settings from the GPMC in Windows Vista that are not available in the GPMC in Windows Server 2003—such as those related to folder redirection, wireless networking (IEEE 802.11), and deployed printers—cannot be stored by the AGPM Server, even though administrators can configure them using AGPM on their computers.</span></span>

<span data-ttu-id="6e8cb-132">如果您必須在擁有舊版 GPMC 的電腦上安裝 AGPM Server，而不是您的群組原則管理員正在執行，請參閱群組原則設定參考，以取得可供哪些作業系統使用的原則設定的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-132">If you must install AGPM Server on a computer with an older version of GPMC than your Group Policy administrators are running, see the Group Policy Settings Reference for details about which policy settings are available with which operating systems.</span></span> <span data-ttu-id="6e8cb-133">若要下載群組原則設定參考，請參閱 <https://go.microsoft.com/fwlink/?LinkID=106147> 。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-133">To download the Group Policy Settings Reference, see <https://go.microsoft.com/fwlink/?LinkID=106147>.</span></span>

<span data-ttu-id="6e8cb-134">**記事** 無法從 AGPM 服務器或執行 Windows Server2003 的 GPOVault 伺服器將存檔遷移至執行 WindowsVista 的 AGPM 服務器。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-134">**Note** Archives cannot be migrated from an AGPM Server or a GPOVault Server running Windows Server2003 to an AGPM Server running WindowsVista.</span></span>

<span data-ttu-id="6e8cb-135">針對 Windows Server2003，如果您要安裝 [AGPM Server] 的電腦上已安裝 GPOVault Server，建議您在開始安裝前不要卸載 GPOVault 伺服器。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-135">For Windows Server2003, if GPOVault Server is installed on the computer on which you want to install AGPM Server, it is recommended that you do not uninstall GPOVault Server before beginning the installation.</span></span> <span data-ttu-id="6e8cb-136">安裝 AGPM Server 時會卸載 GPOVault Server，並自動將現有的 GPOVault 封存資料傳輸到 AGPM 封存。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-136">The installation of AGPM Server will uninstall GPOVault Server and automatically transfer your existing GPOVault archive data to an AGPM archive.</span></span>

 

### <span data-ttu-id="6e8cb-137">AGPM 用戶端需求</span><span class="sxs-lookup"><span data-stu-id="6e8cb-137">AGPM Client requirements</span></span>

<span data-ttu-id="6e8cb-138">AGPM 用戶端2.5 需要 WindowsVista （32位版本），且未安裝 service pack 或 Windows Server2003 （32位版本），以及 GPMC。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-138">AGPM Client2.5 requires WindowsVista (32-bit version) with no service packs installed or Windows Server2003 (32-bit version), as well as the GPMC.</span></span> <span data-ttu-id="6e8cb-139">您可以在執行 AGPM 服務器的電腦上安裝 AGPM 用戶端。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-139">AGPM Client can be installed on a computer running AGPM Server.</span></span>

### <span data-ttu-id="6e8cb-140">案例需求</span><span class="sxs-lookup"><span data-stu-id="6e8cb-140">Scenario requirements</span></span>

<span data-ttu-id="6e8cb-141">開始這個案例之前，請先建立四個使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-141">Before you begin this scenario, create four user accounts.</span></span> <span data-ttu-id="6e8cb-142">在案例中，您會將下列其中一個 AGPM 角色指派給每個帳戶： AGPM 系統管理員（完全控制）、審核者、編輯者和檢閱者。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-142">During the scenario, you will assign one of the following AGPM roles to each of these accounts: AGPM Administrator (Full Control), Approver, Editor, and Reviewer.</span></span> <span data-ttu-id="6e8cb-143">這些帳戶必須能夠傳送及接收電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-143">These accounts must be able to send and receive e-mail messages.</span></span> <span data-ttu-id="6e8cb-144">針對具有 AGPM 管理員、核准者及（選擇性）編輯者角色的帳戶指派**連結 gpo**許可權。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-144">Assign **Link GPOs** permission to the accounts with the AGPM Administrator, Approver, and (optionally) Editor roles.</span></span>

<span data-ttu-id="6e8cb-145">**記事** 
預設會將 [**連結 gpo** ] 許可權指派給網域管理員和企業系統管理員的成員。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-145">**Note**
**Link GPOs** permission is assigned to members of Domain Administrators and Enterprise Administrators by default.</span></span> <span data-ttu-id="6e8cb-146">若要將**連結 gpo**許可權指派給其他使用者或群組（例如擁有 AGPM 系統管理員或核准者角色的帳戶），請按一下該網域的節點，然後按一下 [**委派**] 索引標籤，選取 [**連結 gpo**]，再按一下 [**新增**]，然後選取要指派許可權的使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-146">To assign **Link GPOs** permission to additional users or groups (such as accounts with the roles of AGPM Administrator or Approver), click the node for the domain and then click the **Delegation** tab, select **Link GPOs**, click **Add**, and select users or groups to which to assign the permission.</span></span>

 

<span data-ttu-id="6e8cb-147">在這種情況下，您會使用不同的帳戶執行動作。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-147">For this scenario, you perform actions with different accounts.</span></span> <span data-ttu-id="6e8cb-148">您可以以所示的每個帳戶登入，或者，您可以使用 [**執行方式**] 命令，以指定的帳號啟動 GPMC。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-148">You can either log on with each account as indicated, or you can use the **Run as** command to start the GPMC with the indicated account.</span></span>

<span data-ttu-id="6e8cb-149">**記事** 若要在 Windows Server2003 上將 [**執行方式**] 命令與 GPMC 搭配使用，請按一下 [**開始**]，指向 [**管理工具**]，以滑鼠右鍵按一下 [**群組原則管理**]，然後按一下 [**執行方式**]</span><span class="sxs-lookup"><span data-stu-id="6e8cb-149">**Note** To use the **Run as** command with GPMC on Windows Server2003, click **Start**, point to **Administrative Tools**, right-click **Group Policy Management**, and click **Run as**.</span></span> <span data-ttu-id="6e8cb-150">按一下 **[下列使用者**]，然後輸入帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-150">Click **The following user** and enter credentials for an account.</span></span>

<span data-ttu-id="6e8cb-151">若要在 Windows Vista 上將 [**執行方式**] 命令與 GPMC 搭配使用，請按一下 [**開始**] 按鈕，指向 [**執行**]，然後輸入**runas/user：** <em> DomainName\\UserName </em> **"mmc%windir%\\system32\\gpmc.msc"**，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-151">To use the **Run as** command with GPMC on Windows Vista, click the **Start** button, point to **Run**, and type **runas /user:**<em>DomainName\\UserName</em>**"mmc %windir%\\system32\\gpmc.msc"**, and click **OK**.</span></span> <span data-ttu-id="6e8cb-152">出現提示時，請輸入帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-152">Type the password for the account when prompted.</span></span>

 

## <span data-ttu-id="6e8cb-153">安裝和設定 AGPM 的步驟</span><span class="sxs-lookup"><span data-stu-id="6e8cb-153">Steps for installing and configuring AGPM</span></span>


<span data-ttu-id="6e8cb-154">您必須完成下列步驟，才能安裝及設定 AGPM。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-154">You must complete the following steps to install and configure AGPM.</span></span>

[<span data-ttu-id="6e8cb-155">步驟1：安裝 AGPM 服務器</span><span class="sxs-lookup"><span data-stu-id="6e8cb-155">Step 1: Install AGPM Server</span></span>](#bkmk-config1)

[<span data-ttu-id="6e8cb-156">步驟2：安裝 AGPM 用戶端</span><span class="sxs-lookup"><span data-stu-id="6e8cb-156">Step 2: Install AGPM Client</span></span>](#bkmk-config2)

[<span data-ttu-id="6e8cb-157">步驟3：設定 AGPM 服務器連線</span><span class="sxs-lookup"><span data-stu-id="6e8cb-157">Step 3: Configure an AGPM Server connection</span></span>](#bkmk-config3)

[<span data-ttu-id="6e8cb-158">步驟4：設定電子郵件通知</span><span class="sxs-lookup"><span data-stu-id="6e8cb-158">Step 4: Configure e-mail notification</span></span>](#bkmk-config4)

[<span data-ttu-id="6e8cb-159">步驟5：委派存取權</span><span class="sxs-lookup"><span data-stu-id="6e8cb-159">Step 5: Delegate access</span></span>](#bkmk-config5)

### <a href="" id="bkmk-config1"></a><span data-ttu-id="6e8cb-160">步驟1：安裝 AGPM 服務器</span><span class="sxs-lookup"><span data-stu-id="6e8cb-160">Step 1: Install AGPM Server</span></span>

<span data-ttu-id="6e8cb-161">在這個步驟中，您會在將執行 AGPM 服務的成員伺服器或網網域控制站上安裝 [AGPM 服務器]，然後設定封存。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-161">In this step, you install AGPM Server on the member server or domain controller that will run the AGPM Service, and you configure the archive.</span></span> <span data-ttu-id="6e8cb-162">所有的 AGPM 作業都是透過此 Windows 服務來管理，並以服務的認證執行。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-162">All AGPM operations are managed through this Windows service and are executed with the service's credentials.</span></span> <span data-ttu-id="6e8cb-163">您可以將 AGPM 服務器所管理的封存放在該伺服器或同一林中的另一台伺服器上。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-163">The archive managed by an AGPM Server can be hosted on that server or on another server in the same forest.</span></span>

**<span data-ttu-id="6e8cb-164">若要在將裝載 AGPM 服務的電腦上安裝 AGPM 服務器</span><span class="sxs-lookup"><span data-stu-id="6e8cb-164">To install AGPM Server on the computer that will host the AGPM Service</span></span>**

1.  <span data-ttu-id="6e8cb-165">以網域系統管理員群組成員的帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-165">Log on with an account that is a member of the Domain Admins group.</span></span>

2.  <span data-ttu-id="6e8cb-166">啟動 Microsoft 桌面優化套件 CD，然後依照螢幕上的指示進行，以選取 [**高級群組原則管理-伺服器**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-166">Start the Microsoft Desktop Optimization Pack CD and follow the instructions on screen to select **Advanced Group Policy Management - Server**.</span></span>

3.  <span data-ttu-id="6e8cb-167">在 [**歡迎**] 對話方塊中，按一下 **[下一步**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-167">In the **Welcome** dialog box, click **Next**.</span></span>

4.  <span data-ttu-id="6e8cb-168">在 [ **Microsoft 軟體授權條款**] 對話方塊中，接受條款，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-168">In the **Microsoft Software License Terms** dialog box, accept the terms and click **Next**.</span></span>

5.  <span data-ttu-id="6e8cb-169">在 [**應用程式路徑**] 對話方塊中，選取要安裝 [AGPM 服務器] 的位置。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-169">In the **Application Path** dialog box, select a location in which to install AGPM Server.</span></span> <span data-ttu-id="6e8cb-170">安裝了 AGPM 服務器的電腦將會主持 AGPM 服務並管理封存。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-170">The computer on which AGPM Server is installed will host the AGPM Service and manage the archive.</span></span> <span data-ttu-id="6e8cb-171">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-171">Click **Next**.</span></span>

6.  <span data-ttu-id="6e8cb-172">在 [封存**路徑**] 對話方塊中，選取要相對於 AGPM 服務器的封存位置。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-172">In the **Archive Path** dialog box, select a location for the archive relative to the AGPM Server.</span></span> <span data-ttu-id="6e8cb-173">封存路徑可以指向 AGPM 服務器或其他位置的資料夾，但您應該選取一個位置，其中有足夠的空間來儲存此 AGPM 服務器所管理的所有 Gpo 及歷程記錄資料。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-173">The archive path can point to a folder on the AGPM Server or elsewhere, but you should select a location with sufficient space to store all GPOs and history data managed by this AGPM Server.</span></span> <span data-ttu-id="6e8cb-174">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-174">Click **Next**.</span></span>

7.  <span data-ttu-id="6e8cb-175">在 [ **Agpm 服務帳戶**] 對話方塊中，選取 agpm 服務將在其下執行的服務帳戶，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-175">In the **AGPM Service Account** dialog box, select a service account under which the AGPM Service will run and then click **Next**.</span></span>

8.  <span data-ttu-id="6e8cb-176">在 [封存**擁有**者] 對話方塊中，選取最初指派 AGPM 系統管理員（完全控制）角色的帳戶或群組。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-176">In the **Archive Owner** dialog box, select an account or group to which to initially assign the AGPM Administrator (Full Control) role.</span></span> <span data-ttu-id="6e8cb-177">此 AGPM 系統管理員可以為其他群組原則管理員指派 AGPM 角色和許可權（包括 AGPM 系統管理員的角色）。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-177">This AGPM Administrator can assign AGPM roles and permissions to other Group Policy administrators (including the role of AGPM Administrator).</span></span> <span data-ttu-id="6e8cb-178">在此案例中，選取要在 AGPM 系統管理員角色中提供的帳戶。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-178">For this scenario, select the account to serve in the AGPM Administrator role.</span></span> <span data-ttu-id="6e8cb-179">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-179">Click **Next**.</span></span>

9.  <span data-ttu-id="6e8cb-180">按一下 [**安裝**]，然後按一下 **[完成] 結束**設定向導。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-180">Click **Install**, and then click **Finish** to exit the Setup Wizard.</span></span>

    <span data-ttu-id="6e8cb-181">**小心** 請勿透過作業系統中的 [**管理工具**] 和 [**服務**] 來修改 AGPM 服務的設定。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-181">**Caution** Do not modify settings for the AGPM Service through **Administrative Tools** and **Services** in the operating system.</span></span> <span data-ttu-id="6e8cb-182">如此一來，就能防止 AGPM 服務啟動。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-182">Doing so can prevent the AGPM Service from starting.</span></span> <span data-ttu-id="6e8cb-183">如需如何修改服務設定的相關資訊，請參閱高級群組原則管理的說明。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-183">For information on how to modify settings for the service, see Help for Advanced Group Policy Management.</span></span>

     

### <a href="" id="bkmk-config2"></a><span data-ttu-id="6e8cb-184">步驟2：安裝 AGPM 用戶端</span><span class="sxs-lookup"><span data-stu-id="6e8cb-184">Step 2: Install AGPM Client</span></span>

<span data-ttu-id="6e8cb-185">每個群組原則管理員（任何建立、編輯、部署、評論或刪除 Gpo 的人）都必須在其所用的電腦上安裝 AGPM 用戶端，才能管理 Gpo。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-185">Each Group Policy administrator—anyone who creates, edits, deploys, reviews, or deletes GPOs—must have AGPM Client installed on computers that they use to manage GPOs.</span></span> <span data-ttu-id="6e8cb-186">在這種情況下，您必須在至少一部電腦上安裝 [AGPM 用戶端]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-186">For this scenario, you install AGPM Client on at least one computer.</span></span> <span data-ttu-id="6e8cb-187">您不需要在不執行「組原則管理」的最終使用者電腦上安裝 AGPM 用戶端。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-187">You do not need to install AGPM Client on the computers of end users who do not perform Group Policy administration.</span></span>

**<span data-ttu-id="6e8cb-188">在群組原則系統管理員的電腦上安裝 AGPM 用戶端</span><span class="sxs-lookup"><span data-stu-id="6e8cb-188">To install AGPM Client on the computer of a Group Policy administrator</span></span>**

1.  <span data-ttu-id="6e8cb-189">啟動 Microsoft 桌面優化套件 CD，然後依照螢幕上的指示選取 [**高級組原則管理-用戶端**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-189">Start the Microsoft Desktop Optimization Pack CD and follow the instructions on screen to select **Advanced Group Policy Management - Client**.</span></span>

2.  <span data-ttu-id="6e8cb-190">在 [**歡迎**] 對話方塊中，按一下 **[下一步**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-190">In the **Welcome** dialog box, click **Next**.</span></span>

3.  <span data-ttu-id="6e8cb-191">在 [ **Microsoft 軟體授權條款**] 對話方塊中，接受條款，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-191">In the **Microsoft Software License Terms** dialog box, accept the terms and click **Next**.</span></span>

4.  <span data-ttu-id="6e8cb-192">在 [**應用程式路徑**] 對話方塊中，選取要安裝 AGPM 用戶端的位置。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-192">In the **Application Path** dialog box, select a location in which to install AGPM Client.</span></span> <span data-ttu-id="6e8cb-193">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-193">Click **Next**.</span></span>

5.  <span data-ttu-id="6e8cb-194">在 [ **AGPM 服務器**] 對話方塊中，輸入要連接之 AGPM 服務器的完整電腦名稱稱和埠。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-194">In the **AGPM Server** dialog box, type the fully-qualified computer name and the port for the AGPM Server to which to connect.</span></span> <span data-ttu-id="6e8cb-195">AGPM 服務的預設埠是4600。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-195">The default port for the AGPM Service is 4600.</span></span> <span data-ttu-id="6e8cb-196">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-196">Click **Next**.</span></span>

6.  <span data-ttu-id="6e8cb-197">按一下 [**安裝**]，然後按一下 **[完成] 結束**設定向導。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-197">Click **Install**, and then click **Finish** to exit the Setup Wizard.</span></span>

### <a href="" id="bkmk-config3"></a><span data-ttu-id="6e8cb-198">步驟3：設定 AGPM 服務器連線</span><span class="sxs-lookup"><span data-stu-id="6e8cb-198">Step 3: Configure an AGPM Server connection</span></span>

<span data-ttu-id="6e8cb-199">AGPM 會儲存每個受控制的群組原則物件（GPO）的所有版本，也就是在中央封存中，AGPM 提供變更控制的 GPO，所以群組原則管理員可以在離線時查看及修改 Gpo，而不會立即影響每個 GPO 的部署版本。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-199">AGPM stores all versions of each controlled Group Policy object (GPO)—a GPO for which AGPM provides change control—in a central archive, so Group Policy administrators can view and modify GPOs offline without immediately impacting the deployed version of each GPO.</span></span>

<span data-ttu-id="6e8cb-200">在這個步驟中，您要設定 AGPM 服務器連線，並確保所有群組原則管理員都連線到相同的 AGPM 服務器。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-200">In this step, you configure an AGPM Server connection and ensure that all Group Policy administrators connect to the same AGPM Server.</span></span> <span data-ttu-id="6e8cb-201">（如需有關設定多個 AGPM 服務器的詳細資訊，請參閱高級群組原則管理的說明。）</span><span class="sxs-lookup"><span data-stu-id="6e8cb-201">(For information about configuring multiple AGPM Servers, see Help for Advanced Group Policy Management.)</span></span>

**<span data-ttu-id="6e8cb-202">針對所有群組原則管理員設定 AGPM 服務器連線</span><span class="sxs-lookup"><span data-stu-id="6e8cb-202">To configure an AGPM Server connection for all Group Policy administrators</span></span>**

1.  <span data-ttu-id="6e8cb-203">在已安裝 AGPM 用戶端的電腦上，以您選取做為封存擁有者的使用者帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-203">On a computer on which you have installed AGPM Client, log on with the user account that you selected as the Archive Owner.</span></span> <span data-ttu-id="6e8cb-204">此使用者擁有 AGPM 系統管理員的角色（完全控制）。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-204">This user has the role of AGPM Administrator (Full Control).</span></span>

2.  <span data-ttu-id="6e8cb-205">按一下 [**開始**]，指向 [系統**管理工具**]，然後按一下 [**群組原則管理**] 來開啟**群組原則管理主控台（GPMC）**。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-205">Click **Start**, point to **Administrative Tools**, and click **Group Policy Management** to open the **Group Policy Management Console (GPMC)**.</span></span>

3.  <span data-ttu-id="6e8cb-206">在 [**群組原則管理] 主控台**樹狀結構中，編輯套用至所有群組原則系統管理員的 GPO。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-206">In the **Group Policy Management Console** tree, edit a GPO that is applied to all Group Policy administrators.</span></span>

4.  <span data-ttu-id="6e8cb-207">在 [**群群組原則物件編輯器**] 視窗中，按一下 [**使用者**設定]、[系統**管理範本**] 和 [ **Windows 元件**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-207">In the **Group Policy Object Editor** window, click **User Configuration**, **Administrative Templates**, and **Windows Components**.</span></span>

5.  <span data-ttu-id="6e8cb-208">如果 [ **Windows 元件**] 下並未列出 [ **AGPM** ]：</span><span class="sxs-lookup"><span data-stu-id="6e8cb-208">If **AGPM** is not listed under **Windows Components**:</span></span>

    1.  <span data-ttu-id="6e8cb-209">以滑鼠右鍵按一下 [**管理範本**]，然後選取 [**新增/移除範本**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-209">Right-click **Administrative Templates** and select **Add/Remove Templates**.</span></span>

    2.  <span data-ttu-id="6e8cb-210">按一下 [**新增**]，選取 [ **agpm** ] 或 [ **agpm] .adm**，按一下 [**開啟**]，然後按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-210">Click **Add**, select **agpm.admx** or **agpm.adm**, click **Open**, and then click **Close**.</span></span>

6.  <span data-ttu-id="6e8cb-211">在 [ **Windows 元件**] 底下，按兩下 [ **AGPM**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-211">Under **Windows Components**, double-click **AGPM**.</span></span>

7.  <span data-ttu-id="6e8cb-212">在 [詳細資料] 窗格中，按兩下 **[AGPM Server （所有網域）**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-212">In the details pane, double-click **AGPM Server (all domains)**.</span></span>

8.  <span data-ttu-id="6e8cb-213">在 [ **AGPM Server （所有網域）屬性**] 視窗中，選取 [**啟用**]，然後為裝載封存的伺服器輸入完整的電腦名稱稱和埠（例如，server.contoso.com:4600）。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-213">In the **AGPM Server (all domains) Properties** window, select **Enabled** and type the fully-qualified computer name and port (for example, server.contoso.com:4600) for the server hosting the archive.</span></span> <span data-ttu-id="6e8cb-214">AGPM 服務所使用的埠是埠4600。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-214">The port used by the AGPM Service is port 4600.</span></span>

9.  <span data-ttu-id="6e8cb-215">按一下 **[確定]**，然後關閉 [**群群組原則物件編輯器**] 視窗。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-215">Click **OK**, and then close the **Group Policy Object Editor** window.</span></span> <span data-ttu-id="6e8cb-216">更新群組原則時，會針對每個群組原則管理員設定 AGPM 服務器連線。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-216">When Group Policy is updated, the AGPM Server connection is configured for each Group Policy administrator.</span></span>

### <a href="" id="bkmk-config4"></a><span data-ttu-id="6e8cb-217">步驟4：設定電子郵件通知</span><span class="sxs-lookup"><span data-stu-id="6e8cb-217">Step 4: Configure e-mail notification</span></span>

<span data-ttu-id="6e8cb-218">在 AGPM 系統管理員（完全控制）中，您可以指定當編輯者嘗試建立、部署或刪除 GPO 時，傳送包含要求之電子郵件訊息之核准者和 AGPM 系統管理員的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-218">As an AGPM Administrator (Full Control), you designate the e-mail addresses of Approvers and AGPM Administrators to whom an e-mail message containing a request is sent when an Editor attempts to create, deploy, or delete a GPO.</span></span> <span data-ttu-id="6e8cb-219">您也可以決定要從哪個別名傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-219">You also determine the alias from which these messages are sent.</span></span>

**<span data-ttu-id="6e8cb-220">若要設定 AGPM 的電子郵件通知</span><span class="sxs-lookup"><span data-stu-id="6e8cb-220">To configure e-mail notification for AGPM</span></span>**

1.  <span data-ttu-id="6e8cb-221">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-221">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="6e8cb-222">在 [詳細資料] 窗格中，按一下 [**網域委派**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-222">In the details pane, click the **Domain Delegation** tab.</span></span>

3.  <span data-ttu-id="6e8cb-223">在 [**發件**人] 欄位中，輸入您應該傳送通知的 AGPM 電子郵件別名。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-223">In the **From** field, type the e-mail alias for AGPM from which notifications should be sent.</span></span>

4.  <span data-ttu-id="6e8cb-224">**在 [收**件者] 欄位中，輸入您要指派核准者角色的使用者帳戶的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-224">In the **To** field, type the e-mail address for the user account to which you intend to assign the Approver role.</span></span>

5.  <span data-ttu-id="6e8cb-225">在 [ **SMTP 伺服器**] 欄位中，輸入有效的 SMTP 郵件伺服器。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-225">In the **SMTP server** field, type a valid SMTP mail server.</span></span>

6.  <span data-ttu-id="6e8cb-226">在 [**使用者名稱**] 和 [**密碼**] 欄位中，輸入擁有 SMTP 服務存取權的使用者認證。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-226">In the **User name** and **Password** fields, type the credentials of a user with access to the SMTP service.</span></span>

7.  <span data-ttu-id="6e8cb-227">按一下 **\[Apply\]** (套用)。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-227">Click **Apply**.</span></span>

### <a href="" id="bkmk-config5"></a><span data-ttu-id="6e8cb-228">步驟5：委派存取權</span><span class="sxs-lookup"><span data-stu-id="6e8cb-228">Step 5: Delegate access</span></span>

<span data-ttu-id="6e8cb-229">作為 AGPM 系統管理員（完全控制），您可以委派網域層級對 Gpo 的存取權，將角色指派給每個群組原則管理員的帳戶。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-229">As an AGPM Administrator (Full Control), you delegate domain-level access to GPOs, assigning roles to the account of each Group Policy administrator.</span></span>

<span data-ttu-id="6e8cb-230">**記事** 您也可以在 GPO 層級（而非網域層級）委派存取權。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-230">**Note** You can also delegate access at the GPO level rather than the domain level.</span></span> <span data-ttu-id="6e8cb-231">如需詳細資訊，請參閱高級群組原則管理的說明。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-231">For details, see Help for Advanced Group Policy Management.</span></span>

 

<span data-ttu-id="6e8cb-232">**重要** 您應該限制 [群組原則建立者擁有者] 群組中的成員資格，因此不能用來避開對 Gpo 存取的 AGPM 管理。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-232">**Important** You should restrict membership in the Group Policy Creator Owners group, so it cannot be used to circumvent AGPM management of access to GPOs.</span></span> <span data-ttu-id="6e8cb-233">（在 [**群組原則管理主控台**] 中，按一下要管理 gpo 的林和網域中的 [**群組原則物件**]，按一下 [**委派**]，然後設定設定以符合貴組織的需求。）</span><span class="sxs-lookup"><span data-stu-id="6e8cb-233">(In the **Group Policy Management Console**, click **Group Policy Objects** in the forest and domain in which you want to manage GPOs, click **Delegation**, and then configure the settings to meet the needs of your organization.)</span></span>

 

**<span data-ttu-id="6e8cb-234">若要委派整個網域中所有 Gpo 的存取權</span><span class="sxs-lookup"><span data-stu-id="6e8cb-234">To delegate access to all GPOs throughout a domain</span></span>**

1.  <span data-ttu-id="6e8cb-235">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-235">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="6e8cb-236">在 [**網域委派**] 索引標籤上，按一下 [**高級**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-236">On the **Domain Delegation** tab, click the **Advanced** button.</span></span>

3.  <span data-ttu-id="6e8cb-237">在 [**許可權**] 對話方塊中：</span><span class="sxs-lookup"><span data-stu-id="6e8cb-237">In the **Permissions** dialog box:</span></span>

    1.  <span data-ttu-id="6e8cb-238">按一下 [群組原則管理員] 的使用者帳戶，然後選取 [**核准者**] 核取方塊，將該角色指派給該帳戶。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-238">Click the user account of a Group Policy administrator, and then select the **Approver** check box to assign that role to the account.</span></span> <span data-ttu-id="6e8cb-239">清除 [**編輯器**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-239">Clear the **Editor** check box.</span></span> <span data-ttu-id="6e8cb-240">（此角色包含檢閱者角色）。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-240">(This role includes the Reviewer role.)</span></span>

    2.  <span data-ttu-id="6e8cb-241">按一下另一個群組原則系統管理員的使用者帳戶，然後選取 [**編輯**者] 核取方塊，將該角色指派給帳戶。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-241">Click the user account of another Group Policy administrator, and then select the **Editor** check box to assign that role to the account.</span></span> <span data-ttu-id="6e8cb-242">（此角色包含檢閱者角色）。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-242">(This role includes the Reviewer role.)</span></span>

    3.  <span data-ttu-id="6e8cb-243">按一下第三個帳戶，然後選取 [**檢閱者**] 核取方塊，只會將 [檢閱者] 角色指派給該群組原則管理員的帳戶。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-243">Click a third account and then select the **Reviewer** check box to assign only the Reviewer role to the account of that Group Policy administrator.</span></span> <span data-ttu-id="6e8cb-244">清除 [**編輯器**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-244">Clear the **Editor** check box.</span></span>

    4.  <span data-ttu-id="6e8cb-245">按一下 [**高級**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-245">Click the **Advanced** button.</span></span>

4.  <span data-ttu-id="6e8cb-246">在 [**高級安全性設定**] 對話方塊中：</span><span class="sxs-lookup"><span data-stu-id="6e8cb-246">In the **Advanced Security Settings** dialog box:</span></span>

    1.  <span data-ttu-id="6e8cb-247">選取 [群組原則系統管理員]，然後按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-247">Select a Group Policy administrator, and then click **Edit**.</span></span>

    2.  <span data-ttu-id="6e8cb-248">若要套用**到**，請選取**這個物件和嵌套物件**，然後按一下 [**許可權\*\*\*\*專案**] 對話方塊中的 **[確定**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-248">For **Apply onto**, select **This object and nested objects**, and then click **OK** in the **Permission** **Entry** dialog box.</span></span>

    3.  <span data-ttu-id="6e8cb-249">針對每個群組原則管理員重複上述步驟。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-249">Repeat for each Group Policy administrator.</span></span>

5.  <span data-ttu-id="6e8cb-250">在 [**高級安全設定**] 對話方塊中，按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-250">In the **Advanced Security Settings** dialog box, click **OK**.</span></span>

6.  <span data-ttu-id="6e8cb-251">在 [**許可權**] 對話方塊中，按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-251">In the **Permissions** dialog box, click **OK**.</span></span>

## <span data-ttu-id="6e8cb-252">管理 Gpo 的步驟</span><span class="sxs-lookup"><span data-stu-id="6e8cb-252">Steps for managing GPOs</span></span>


<span data-ttu-id="6e8cb-253">您必須完成下列步驟，才能使用 AGPM 來建立、編輯、審閱及部署 Gpo。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-253">You must complete the following steps to create, edit, review, and deploy GPOs using AGPM.</span></span> <span data-ttu-id="6e8cb-254">此外，您還會建立範本、刪除 GPO，並還原刪除的 GPO。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-254">Additionally, you will create a template, delete a GPO, and restore a deleted GPO.</span></span>

[<span data-ttu-id="6e8cb-255">步驟1：建立 GPO</span><span class="sxs-lookup"><span data-stu-id="6e8cb-255">Step 1: Create a GPO</span></span>](#bkmk-manage1)

[<span data-ttu-id="6e8cb-256">步驟2：編輯 GPO</span><span class="sxs-lookup"><span data-stu-id="6e8cb-256">Step 2: Edit a GPO</span></span>](#bkmk-manage2)

[<span data-ttu-id="6e8cb-257">步驟3：審查及部署 GPO</span><span class="sxs-lookup"><span data-stu-id="6e8cb-257">Step 3: Review and deploy a GPO</span></span>](#bkmk-manage3)

[<span data-ttu-id="6e8cb-258">步驟4：使用範本建立 GPO</span><span class="sxs-lookup"><span data-stu-id="6e8cb-258">Step 4: Use a template to create a GPO</span></span>](#bkmk-manage4)

[<span data-ttu-id="6e8cb-259">步驟5：刪除及還原 GPO</span><span class="sxs-lookup"><span data-stu-id="6e8cb-259">Step 5: Delete and restore a GPO</span></span>](#bkmk-manage5)

### <a href="" id="bkmk-manage1"></a><span data-ttu-id="6e8cb-260">步驟1：建立 GPO</span><span class="sxs-lookup"><span data-stu-id="6e8cb-260">Step 1: Create a GPO</span></span>

<span data-ttu-id="6e8cb-261">在有多個群組原則系統管理員的環境中，擁有 [編輯者角色] 的使用者可以要求建立新的 Gpo，但必須由擁有核准者角色的人員核准此要求，因為建立新的 GPO 會影響生產環境。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-261">In an environment with multiple Group Policy administrators, those with the Editor role have the ability to request the creation of new GPOs, but such a request must be approved by someone with the Approver role because the creation of a new GPO impacts the production environment.</span></span>

<span data-ttu-id="6e8cb-262">在這個步驟中，您會將帳戶與編輯者角色搭配使用，以要求建立新的 GPO。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-262">In this step, you use an account with the Editor role to request the creation of a new GPO.</span></span> <span data-ttu-id="6e8cb-263">將帳戶與核准者角色結合使用，即可核准此要求並完成建立 GPO。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-263">Using an account with the Approver role, you approve this request and complete the creation of a GPO.</span></span>

**<span data-ttu-id="6e8cb-264">要求建立透過 AGPM 管理的新 GPO</span><span class="sxs-lookup"><span data-stu-id="6e8cb-264">To request the creation of a new GPO managed through AGPM</span></span>**

1.  <span data-ttu-id="6e8cb-265">在已安裝 AGPM 用戶端的電腦上，以已在 AGPM 中指派了 [編輯者角色] 的使用者帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-265">On a computer on which you have installed AGPM Client, log on with a user account that has been assigned the Editor role in AGPM.</span></span>

2.  <span data-ttu-id="6e8cb-266">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-266">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

3.  <span data-ttu-id="6e8cb-267">以滑鼠右鍵按一下 [**變更控制**] 節點，然後按一下 [**新增受控制的 GPO**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-267">Right-click the **Change Control** node, and then click **New Controlled GPO**.</span></span>

4.  <span data-ttu-id="6e8cb-268">在 [**新的受控 GPO** ] 對話方塊中：</span><span class="sxs-lookup"><span data-stu-id="6e8cb-268">In the **New Controlled GPO** dialog box:</span></span>

    1.  <span data-ttu-id="6e8cb-269">若要接收申請的複本，請在 [**抄送**] 欄位中輸入您的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-269">To receive a copy of the request, type your e-mail address in the **Cc** field.</span></span>

    2.  <span data-ttu-id="6e8cb-270">輸入**MyGPO**做為新 GPO 的名稱。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-270">Type **MyGPO** as the name for the new GPO.</span></span>

    3.  <span data-ttu-id="6e8cb-271">輸入新 GPO 的批註。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-271">Type a comment for the new GPO.</span></span>

    4.  <span data-ttu-id="6e8cb-272">按一下 [**建立即時**]，讓新的 GPO 在核准後立即部署到生產環境。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-272">Click **Create live** so the new GPO will be deployed to the production environment immediately upon approval.</span></span>

    5.  <span data-ttu-id="6e8cb-273">按一下 **\[提交\]**。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-273">Click **Submit**.</span></span>

5.  <span data-ttu-id="6e8cb-274">當 [ **AGPM 進度**] 視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-274">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="6e8cb-275">新的 GPO 會顯示在 [**擱置**] 索引標籤上。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-275">The new GPO is displayed on the **Pending** tab.</span></span>

**<span data-ttu-id="6e8cb-276">核准擱置的要求以建立 GPO</span><span class="sxs-lookup"><span data-stu-id="6e8cb-276">To approve the pending request to create a GPO</span></span>**

1.  <span data-ttu-id="6e8cb-277">在已安裝 [AGPM 用戶端] 的電腦上，使用已指派給 AGPM 中核准者角色的使用者帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-277">On a computer on which you have installed AGPM Client, log on with a user account that has been assigned the role of Approver in AGPM.</span></span>

2.  <span data-ttu-id="6e8cb-278">開啟該帳戶的電子郵件收件匣，請注意，您已從 AGPM 別名收到一封電子郵件，並要求您建立 GPO。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-278">Open the e-mail inbox for the account, and note that you have received an e-mail message from the AGPM alias with the Editor's request to create a GPO.</span></span>

3.  <span data-ttu-id="6e8cb-279">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-279">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

4.  <span data-ttu-id="6e8cb-280">在 [**內容**] 索引標籤上，按一下 [**未決**] 索引標籤以顯示擱置中的 gpo。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-280">On the **Contents** tab, click the **Pending** tab to display the pending GPOs.</span></span>

5.  <span data-ttu-id="6e8cb-281">以滑鼠右鍵按一下 [ **MyGPO**]，然後按一下 [**核准**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-281">Right-click **MyGPO**, and then click **Approve**.</span></span>

6.  <span data-ttu-id="6e8cb-282">按一下 **[是]** ，確認已核准建立 GPO。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-282">Click **Yes** to confirm approval of the creation of the GPO.</span></span> <span data-ttu-id="6e8cb-283">GPO 會移至 [**受控**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-283">The GPO is moved to the **Controlled** tab.</span></span>

### <a href="" id="bkmk-manage2"></a><span data-ttu-id="6e8cb-284">步驟2：編輯 GPO</span><span class="sxs-lookup"><span data-stu-id="6e8cb-284">Step 2: Edit a GPO</span></span>

<span data-ttu-id="6e8cb-285">您可以使用 Gpo 來設定電腦或使用者設定，並將它們部署到許多電腦或使用者。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-285">You can use GPOs to configure computer or user settings and deploy them to many computers or users.</span></span> <span data-ttu-id="6e8cb-286">在這個步驟中，您會使用具有編輯者角色的帳戶來從封存中取出 GPO、離線編輯 GPO、將編輯過的 GPO 核取到封存，並要求將 GPO 部署到生產環境。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-286">In this step, you use an account with the Editor role to check out a GPO from the archive, edit the GPO offline, check the edited GPO into the archive, and request deployment of the GPO to the production environment.</span></span> <span data-ttu-id="6e8cb-287">在這種情況下，您可以設定 GPO 中的設定，要求密碼長度必須至少為八個字元。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-287">For this scenario, you configure a setting in the GPO to require that the password be at least eight characters in length.</span></span>

**<span data-ttu-id="6e8cb-288">從封存檢查 GPO 以進行編輯</span><span class="sxs-lookup"><span data-stu-id="6e8cb-288">To check the GPO out from the archive for editing</span></span>**

1.  <span data-ttu-id="6e8cb-289">在已安裝 AGPM 用戶端的電腦上，以 AGPM 中已獲「編輯者角色」的使用者帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-289">On a computer on which you have installed AGPM Client, log on with a user account that has been assigned the role of Editor in AGPM.</span></span>

2.  <span data-ttu-id="6e8cb-290">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-290">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

3.  <span data-ttu-id="6e8cb-291">在 [詳細資料] 窗格的 [**內容**] 索引標籤上，按一下 [**受控**] 索引標籤以顯示受控 gpo。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-291">On the **Contents** tab in the details pane, click the **Controlled** tab to display the controlled GPOs.</span></span>

4.  <span data-ttu-id="6e8cb-292">以滑鼠右鍵按一下 [ **MyGPO**]，然後按一下 **[取出]。**</span><span class="sxs-lookup"><span data-stu-id="6e8cb-292">Right-click **MyGPO**, and then click **Check Out**.</span></span>

5.  <span data-ttu-id="6e8cb-293">輸入要在已取出之 GPO 之歷程**記錄**中顯示的批註，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-293">Type a comment to be displayed in the **History** of the GPO while it is checked out, and then click **OK**.</span></span>

6.  <span data-ttu-id="6e8cb-294">當 [ **AGPM 進度**] 視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-294">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="6e8cb-295">在 [**受控**] 索引標籤上，GPO 的狀態會標示為 [**已取出**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-295">On the **Controlled** tab, the state of the GPO is identified as **Checked Out**.</span></span>

**<span data-ttu-id="6e8cb-296">若要離線編輯 GPO 並設定最小密碼長度</span><span class="sxs-lookup"><span data-stu-id="6e8cb-296">To edit the GPO offline and configure the minimum password length</span></span>**

1.  <span data-ttu-id="6e8cb-297">在 [**受控**] 索引標籤上，以滑鼠右鍵按一下 [ **MyGPO**]，然後按一下 [**編輯**] 以開啟 [**群組原則物件編輯器**] 視窗，並變更 GPO 的離線複本。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-297">On the **Controlled** tab, right-click **MyGPO**, and then click **Edit** to open the **Group Policy Object Editor** window and make changes to an offline copy of the GPO.</span></span> <span data-ttu-id="6e8cb-298">在此案例中，請設定最小密碼長度：</span><span class="sxs-lookup"><span data-stu-id="6e8cb-298">For this scenario, configure the minimum password length:</span></span>

    1.  <span data-ttu-id="6e8cb-299">按兩下 **[電腦**設定] 底下的 **[Windows 設定**]，按兩下 [**安全性設定**]，按兩下 [**帳戶原則**]，然後按兩下 [**密碼原則**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-299">Under **Computer Configuration**, double-click **Windows Settings**, double-click **Security Settings**, double-click **Account Policies**, and double-click **Password Policy**.</span></span>

    2.  <span data-ttu-id="6e8cb-300">在 [詳細資料] 窗格中，按兩下 [**最小密碼長度**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-300">In the details pane, double-click **Minimum password length**.</span></span>

    3.  <span data-ttu-id="6e8cb-301">在 [屬性] 視窗中，選取 [**定義這個原則設定**] 核取方塊，將字元數設為**8**，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-301">In the properties window, select the **Define this policy setting** check box, set the number of characters to **8**, and then click **OK**.</span></span>

2.  <span data-ttu-id="6e8cb-302">關閉 [**群組原則物件編輯器**] 視窗。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-302">Close the **Group Policy Object Editor** window.</span></span>

**<span data-ttu-id="6e8cb-303">將 GPO 檢查到封存</span><span class="sxs-lookup"><span data-stu-id="6e8cb-303">To check the GPO into the archive</span></span>**

1.  <span data-ttu-id="6e8cb-304">在 [**受控**] 索引標籤上，以滑鼠右鍵按一下**MyGPO** ，然後按一下 [**存回**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-304">On the **Controlled** tab, right-click **MyGPO** and then click **Check In**.</span></span>

2.  <span data-ttu-id="6e8cb-305">輸入批註，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-305">Type a comment, and then click **OK**.</span></span>

3.  <span data-ttu-id="6e8cb-306">當 [ **AGPM 進度**] 視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-306">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="6e8cb-307">在 [**受控**] 索引標籤上，GPO 的狀態會標示為 [**已核**取]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-307">On the **Controlled** tab, the state of the GPO is identified as **Checked In**.</span></span>

**<span data-ttu-id="6e8cb-308">向生產環境要求 GPO 部署</span><span class="sxs-lookup"><span data-stu-id="6e8cb-308">To request the deployment of the GPO to the production environment</span></span>**

1.  <span data-ttu-id="6e8cb-309">在 [**受控**] 索引標籤上，以滑鼠右鍵按一下**MyGPO** ，然後按一下 [**部署**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-309">On the **Controlled** tab, right-click **MyGPO** and then click **Deploy**.</span></span>

2.  <span data-ttu-id="6e8cb-310">因為此帳戶不是核准者或 AGPM 管理員，所以您必須提交部署的要求。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-310">Because this account is not an Approver or AGPM Administrator, you must submit a request for deployment.</span></span> <span data-ttu-id="6e8cb-311">若要接收申請的複本，請在 [**抄送**] 欄位中輸入您的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-311">To receive a copy of the request, type your e-mail address in the **Cc** field.</span></span> <span data-ttu-id="6e8cb-312">輸入要顯示在 GPO 歷程**記錄**中的批註，然後按一下 [**提交**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-312">Type a comment to be displayed in the **History** of the GPO, and then click **Submit**.</span></span>

3.  <span data-ttu-id="6e8cb-313">當 [ **AGPM 進度**] 視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-313">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="6e8cb-314">**MyGPO**會顯示在 [**擱置**] 索引標籤上的 [gpo] 清單中。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-314">**MyGPO** is displayed on the list of GPOs on the **Pending** tab.</span></span>

### <a href="" id="bkmk-manage3"></a><span data-ttu-id="6e8cb-315">步驟3：審查及部署 GPO</span><span class="sxs-lookup"><span data-stu-id="6e8cb-315">Step 3: Review and deploy a GPO</span></span>

<span data-ttu-id="6e8cb-316">在這個步驟中，您會擔當核准者、建立報告並分析設定，以及變更 GPO 中的設定，以判斷是否應該核准。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-316">In this step, you act as an Approver, creating reports and analyzing the settings and changes to settings in the GPO to determine whether you should approve them.</span></span> <span data-ttu-id="6e8cb-317">在評估 GPO 之後，您可以將它部署到生產環境，並將它連結至網域或組織單位（OU），使其在針對該域或 OU 中的電腦重新整理群組原則時生效。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-317">After evaluating the GPO, you deploy it to the production environment and link it to a domain or an organizational unit (OU) so that it takes effect when Group Policy is refreshed for computers in that domain or OU.</span></span>

**<span data-ttu-id="6e8cb-318">若要查看 GPO 中的設定</span><span class="sxs-lookup"><span data-stu-id="6e8cb-318">To review settings in the GPO</span></span>**

1.  <span data-ttu-id="6e8cb-319">在已安裝 [AGPM 用戶端] 的電腦上，使用已指派給 AGPM 中核准者角色的使用者帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-319">On a computer on which you have installed AGPM Client, log on with a user account that has been assigned the role of Approver in AGPM.</span></span> <span data-ttu-id="6e8cb-320">（任何具有檢閱者角色且包含在其他所有角色中的群組原則管理員，都可以查看 GPO 中的設定）。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-320">(Any Group Policy administrator with the Reviewer role, which is included in all of the other roles, can review the settings in a GPO.)</span></span>

2.  <span data-ttu-id="6e8cb-321">開啟該帳戶的電子郵件收件匣，請注意，您已收到來自 AGPM 別名的電子郵件，並要求您要部署 GPO。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-321">Open the e-mail inbox for the account and note that you have received an e-mail message from the AGPM alias with an Editor's request to deploy a GPO.</span></span>

3.  <span data-ttu-id="6e8cb-322">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-322">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

4.  <span data-ttu-id="6e8cb-323">在 [詳細資料] 窗格的 [**內容**] 索引標籤上，按一下 [**擱置**] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="6e8cb-323">On the **Contents** tab in the details pane, click the **Pending** tab.</span></span>

5.  <span data-ttu-id="6e8cb-324">按兩下 [ **MyGPO** ] 以顯示其歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-324">Double-click **MyGPO** to display its history.</span></span>

6.  <span data-ttu-id="6e8cb-325">查看最新版本的 MyGPO 中的設定：</span><span class="sxs-lookup"><span data-stu-id="6e8cb-325">Review the settings in the most recent version of MyGPO:</span></span>

    1.  <span data-ttu-id="6e8cb-326">在 [歷程**記錄**] 視窗中，以滑鼠右鍵按一下包含最近時間戳記的 GPO 版本，按一下 [**設定**]，然後按一下 [ **HTML 報告**]，以顯示 GPO 設定的摘要。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-326">In the **History** window, right-click the GPO version with the most recent timestamp, click **Settings**, and then click **HTML Report** to display a summary of the GPO's settings.</span></span>

    2.  <span data-ttu-id="6e8cb-327">在網頁瀏覽器中，按一下 [**全部顯示**] 以顯示 GPO 中的所有設定。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-327">In the Web browser, click **show all** to display all of the settings in the GPO.</span></span>

    3.  <span data-ttu-id="6e8cb-328">關閉瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-328">Close the browser.</span></span>

7.  <span data-ttu-id="6e8cb-329">將最新版本的 MyGPO 與簽入到封存的第一個版本進行比較：</span><span class="sxs-lookup"><span data-stu-id="6e8cb-329">Compare the most recent version of MyGPO to the first version checked in to the archive:</span></span>

    1.  <span data-ttu-id="6e8cb-330">在 [歷程**記錄**] 視窗中，按一下包含最新時間戳記的 GPO 版本。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-330">In the **History** window, click the GPO version with the most recent timestamp.</span></span> <span data-ttu-id="6e8cb-331">按住**CTRL** ，並按一下已**檢入**狀態的最舊 GPO 版本。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-331">Press **CTRL** and click the oldest GPO version that has a state of **Checked In**.</span></span>

    2.  <span data-ttu-id="6e8cb-332">按一下 [**差異**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-332">Click the **Differences** button.</span></span> <span data-ttu-id="6e8cb-333">[**帳戶原則/密碼原則**] 區段會以綠色醒目提示，並在前面加上**\ [+ \]**，指出此設定僅在後一個 GPO 版本中設定。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-333">The **Account Policies/Password Policy** section is highlighted in green and preceded by **\[+\]**, indicating that this setting is configured only in the latter version of the GPO.</span></span>

    3.  <span data-ttu-id="6e8cb-334">按一下 [**帳戶原則/密碼原則**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-334">Click **Account Policies/Password Policy**.</span></span> <span data-ttu-id="6e8cb-335">[**最小密碼長度**] 設定也會以綠色醒目提示，並在前面加上**\ [+ \]**，指出它僅在後一個 GPO 版本中進行設定。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-335">The **Minimum password length** setting is also highlighted in green and preceded by **\[+\]**, indicating that it is configured only in the latter version of the GPO.</span></span>

    4.  <span data-ttu-id="6e8cb-336">關閉網頁瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-336">Close the Web browser.</span></span>

**<span data-ttu-id="6e8cb-337">將 GPO 部署到生產環境</span><span class="sxs-lookup"><span data-stu-id="6e8cb-337">To deploy the GPO to the production environment</span></span>**

1.  <span data-ttu-id="6e8cb-338">在 [**擱置**] 索引標籤上，以滑鼠右鍵按一下 [ **MyGPO** ]，然後按一下 [**核准**]</span><span class="sxs-lookup"><span data-stu-id="6e8cb-338">On the **Pending** tab, right-click **MyGPO** and then click **Approve**.</span></span>

2.  <span data-ttu-id="6e8cb-339">輸入要包含在 GPO 歷程記錄中的批註。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-339">Type a comment to include in the history of the GPO.</span></span>

3.  <span data-ttu-id="6e8cb-340">按一下 **\[是\]**。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-340">Click **Yes**.</span></span> <span data-ttu-id="6e8cb-341">當 [ **AGPM 進度**] 視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-341">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="6e8cb-342">GPO 已部署至生產環境。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-342">The GPO is deployed to the production environment.</span></span>

**<span data-ttu-id="6e8cb-343">將 GPO 連結至網域或組織單位</span><span class="sxs-lookup"><span data-stu-id="6e8cb-343">To link the GPO to a domain or organizational unit</span></span>**

1.  <span data-ttu-id="6e8cb-344">在 GPMC 中，以滑鼠右鍵按一下要套用您所設定之 GPO 的網域或 OU，然後按一下 [**連結現有的 gpo**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-344">In the GPMC, right-click the domain or an OU to which to apply the GPO that you configured, and then click **Link an Existing GPO**.</span></span>

2.  <span data-ttu-id="6e8cb-345">在 [**選取 GPO** ] 對話方塊中，按一下 [ **MyGPO**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-345">In the **Select GPO** dialog box, click **MyGPO**, and then click **OK**.</span></span>

### <a href="" id="bkmk-manage4"></a><span data-ttu-id="6e8cb-346">步驟4：使用範本建立 GPO</span><span class="sxs-lookup"><span data-stu-id="6e8cb-346">Step 4: Use a template to create a GPO</span></span>

<span data-ttu-id="6e8cb-347">在這個步驟中，您會將帳戶與編輯者角色搭配使用，以建立範本（即無法編輯、靜態版本的 GPO）做為建立新 Gpo 的起點，然後根據該範本建立新的 GPO。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-347">In this step, you use an account with the Editor role to create a template—an uneditable, static version of a GPO for use as a starting point for creating new GPOs—and then create a new GPO based upon that template.</span></span> <span data-ttu-id="6e8cb-348">範本對於快速建立包含許多相同設定的多個 Gpo 很有用。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-348">Templates are useful for quickly creating multiple GPOs that include many of the same settings.</span></span>

**<span data-ttu-id="6e8cb-349">根據現有的 GPO 建立範本</span><span class="sxs-lookup"><span data-stu-id="6e8cb-349">To create a template based on an existing GPO</span></span>**

1.  <span data-ttu-id="6e8cb-350">在已安裝 AGPM 用戶端的電腦上，以 AGPM 中已獲「編輯者角色」的使用者帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-350">On a computer on which you have installed AGPM Client, log on with a user account that has been assigned the role of Editor in AGPM.</span></span>

2.  <span data-ttu-id="6e8cb-351">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-351">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

3.  <span data-ttu-id="6e8cb-352">在 [詳細資料] 窗格的 [**內容**] 索引標籤上，按一下 [**受控**] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="6e8cb-352">On the **Contents** tab in the details pane, click the **Controlled** tab.</span></span>

4.  <span data-ttu-id="6e8cb-353">以滑鼠右鍵按一下 [ **MyGPO**]，然後按一下 [**另存為範本**]，建立包含目前 MyGPO 中所有設定的範本。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-353">Right-click **MyGPO**, and then click **Save as Template** to create a template incorporating all settings currently in MyGPO.</span></span>

5.  <span data-ttu-id="6e8cb-354">輸入**MyTemplate**做為範本的名稱和批註，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-354">Type **MyTemplate** as the name for the template and a comment, and then click **OK**.</span></span>

6.  <span data-ttu-id="6e8cb-355">當 [ **AGPM 進度**] 視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-355">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="6e8cb-356">新範本隨即出現在 [**範本**] 索引標籤上。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-356">The new template appears on the **Templates** tab.</span></span>

**<span data-ttu-id="6e8cb-357">要求建立透過 AGPM 管理的新 GPO</span><span class="sxs-lookup"><span data-stu-id="6e8cb-357">To request the creation of a new GPO managed through AGPM</span></span>**

1.  <span data-ttu-id="6e8cb-358">按一下 [**受控**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-358">Click the **Controlled** tab.</span></span>

2.  <span data-ttu-id="6e8cb-359">以滑鼠右鍵按一下 [**變更控制**] 節點，然後按一下 [**新增受控制的 GPO**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-359">Right-click the **Change Control** node, and then click **New Controlled GPO**.</span></span>

3.  <span data-ttu-id="6e8cb-360">在 [**新的受控 GPO** ] 對話方塊中：</span><span class="sxs-lookup"><span data-stu-id="6e8cb-360">In the **New Controlled GPO** dialog box:</span></span>

    1.  <span data-ttu-id="6e8cb-361">若要接收申請的複本，請在 [**抄送**] 欄位中輸入您的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-361">To receive a copy of the request, type your e-mail address in the **Cc** field.</span></span>

    2.  <span data-ttu-id="6e8cb-362">輸入**MyOtherGPO**做為新 GPO 的名稱。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-362">Type **MyOtherGPO** as the name for the new GPO.</span></span>

    3.  <span data-ttu-id="6e8cb-363">輸入新 GPO 的批註。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-363">Type a comment for the new GPO.</span></span>

    4.  <span data-ttu-id="6e8cb-364">按一下 [**建立即時**]，讓新的 GPO 在核准後立即部署到生產環境。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-364">Click **Create live**, so the new GPO will be deployed to the production environment immediately upon approval.</span></span>

    5.  <span data-ttu-id="6e8cb-365">針對 [ **GPO 範本**]，選取 [ **MyTemplate**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-365">For **From GPO template**, select **MyTemplate**.</span></span>

    6.  <span data-ttu-id="6e8cb-366">按一下 **\[提交\]**。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-366">Click **Submit**.</span></span>

4.  <span data-ttu-id="6e8cb-367">當 [ **AGPM 進度**] 視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-367">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="6e8cb-368">新的 GPO 會顯示在 [**擱置**] 索引標籤上。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-368">The new GPO is displayed on the **Pending** tab.</span></span>

<span data-ttu-id="6e8cb-369">使用已指派核准者角色的帳戶，以核准擱置的要求來建立 GPO，就像您在[步驟1：建立 gpo](#bkmk-manage1)一樣。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-369">Use an account that has been assigned the role of Approver to approve the pending request to create the GPO as you did in [Step 1: Create a GPO](#bkmk-manage1).</span></span> <span data-ttu-id="6e8cb-370">MyTemplate 包含您在 MyGPO 中設定的所有設定。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-370">MyTemplate incorporates all of the settings that you configured in MyGPO.</span></span> <span data-ttu-id="6e8cb-371">因為 MyOtherGPO 是使用 MyTemplate 建立的，所以它最初會包含 MyTemplate 建立時 MyGPO 所包含的所有設定。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-371">Because MyOtherGPO was created using MyTemplate, it initially contains all of the settings that MyGPO contained at the time that MyTemplate was created.</span></span> <span data-ttu-id="6e8cb-372">您可以產生差異報告來比較 MyOtherGPO 與 MyTemplate，以進行確認。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-372">You can confirm this by generating a difference report to compare MyOtherGPO to MyTemplate.</span></span>

**<span data-ttu-id="6e8cb-373">從封存檢查 GPO 以進行編輯</span><span class="sxs-lookup"><span data-stu-id="6e8cb-373">To check the GPO out from the archive for editing</span></span>**

1.  <span data-ttu-id="6e8cb-374">在已安裝 AGPM 用戶端的電腦上，以 AGPM 中已獲「編輯者角色」的使用者帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-374">On a computer on which you have installed AGPM Client, log on with a user account that has been assigned the role of Editor in AGPM.</span></span>

2.  <span data-ttu-id="6e8cb-375">以滑鼠右鍵按一下 [ **MyOtherGPO**]，然後按一下 **[取出]。**</span><span class="sxs-lookup"><span data-stu-id="6e8cb-375">Right-click **MyOtherGPO**, and then click **Check Out**.</span></span>

3.  <span data-ttu-id="6e8cb-376">輸入要在已取出之 GPO 之歷程記錄中顯示的批註，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-376">Type a comment to be displayed in the history of the GPO while it is checked out, and then click **OK**.</span></span>

4.  <span data-ttu-id="6e8cb-377">當 [ **AGPM 進度**] 視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-377">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="6e8cb-378">在 [**受控**] 索引標籤上，GPO 的狀態會標示為 [**已取出**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-378">On the **Controlled** tab, the state of the GPO is identified as **Checked Out**.</span></span>

**<span data-ttu-id="6e8cb-379">若要離線編輯 GPO 並設定帳戶鎖定時間</span><span class="sxs-lookup"><span data-stu-id="6e8cb-379">To edit the GPO offline and configure the account lockout duration</span></span>**

1.  <span data-ttu-id="6e8cb-380">在 [**受控**] 索引標籤上，以滑鼠右鍵按一下 [ **MyOtherGPO**]，然後按一下 [**編輯**] 以開啟 [**群組原則物件編輯器**] 視窗，並變更 GPO 的離線複本。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-380">On the **Controlled** tab, right-click **MyOtherGPO**, and then click **Edit** to open the **Group Policy Object Editor** window and make changes to an offline copy of the GPO.</span></span> <span data-ttu-id="6e8cb-381">在此案例中，請設定最小密碼長度：</span><span class="sxs-lookup"><span data-stu-id="6e8cb-381">For this scenario, configure the minimum password length:</span></span>

    1.  <span data-ttu-id="6e8cb-382">按兩下 [**電腦**設定] 底下的 **[Windows 設定**]，按兩下 [**安全性設定**]，按兩下 [**帳戶原則**]，然後按兩下 [**帳戶封鎖原則**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-382">Under **Computer Configuration**, double-click **Windows Settings**, double-click **Security Settings**, double-click **Account Policies**, and double-click **Account Lockout Policy**.</span></span>

    2.  <span data-ttu-id="6e8cb-383">在 [詳細資料] 窗格中，按兩下 [**帳戶鎖定時間**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-383">In the details pane, double-click **Account lockout duration**.</span></span>

    3.  <span data-ttu-id="6e8cb-384">在 [屬性] 視窗中，核取 [**定義此原則設定**]，將 [持續時間] 設定為**30**分鐘，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-384">In the properties window, check **Define this policy setting**, set the duration to **30** minutes, and then click **OK**.</span></span>

2.  <span data-ttu-id="6e8cb-385">關閉 [**群組原則物件編輯器**] 視窗。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-385">Close the **Group Policy Object Editor** window.</span></span>

<span data-ttu-id="6e8cb-386">將 MyOtherGPO 簽入封存並要求部署，就像您在[步驟2：編輯 GPO](#bkmk-manage2)中所做的一樣。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-386">Check MyOtherGPO into the archive and request deployment as you did for MyGPO in [Step 2: Edit a GPO](#bkmk-manage2).</span></span> <span data-ttu-id="6e8cb-387">您可以使用 [差異] 報告，將 MyOtherGPO 與 MyGPO 或 MyTemplate 進行比較。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-387">You can compare MyOtherGPO to MyGPO or to MyTemplate using difference reports.</span></span> <span data-ttu-id="6e8cb-388">任何包含檢閱者角色的帳戶（AGPM 系統管理員 \ [完全控制 \]、審核者、編輯者或檢閱者）都可以產生報告。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-388">Any account that includes the Reviewer role (AGPM Administrator \[Full Control\], Approver, Editor, or Reviewer) can generate reports.</span></span>

**<span data-ttu-id="6e8cb-389">比較 GPO 與另一個 GPO 及範本</span><span class="sxs-lookup"><span data-stu-id="6e8cb-389">To compare a GPO to another GPO and to a template</span></span>**

1.  <span data-ttu-id="6e8cb-390">若要比較 MyGPO 和 MyOtherGPO：</span><span class="sxs-lookup"><span data-stu-id="6e8cb-390">To compare MyGPO and MyOtherGPO:</span></span>

    1.  <span data-ttu-id="6e8cb-391">在 [**受控**] 索引標籤上，按一下 [ **MyGPO**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-391">On the **Controlled** tab, click **MyGPO**.</span></span> <span data-ttu-id="6e8cb-392">按**CTRL**鍵，然後按一下 [ **MyOtherGPO**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-392">Press **CTRL** and then click **MyOtherGPO**.</span></span>

    2.  <span data-ttu-id="6e8cb-393">以滑鼠右鍵按一下 [ **MyOtherGPO**]，指向 [**差異**]，然後按一下 [ **HTML 報表**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-393">Right-click **MyOtherGPO**, point to **Differences**, and click **HTML Report**.</span></span>

2.  <span data-ttu-id="6e8cb-394">若要比較 MyOtherGPO 和 MyTemplate：</span><span class="sxs-lookup"><span data-stu-id="6e8cb-394">To compare MyOtherGPO and MyTemplate:</span></span>

    1.  <span data-ttu-id="6e8cb-395">在 [**受控**] 索引標籤上，按一下 [ **MyOtherGPO**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-395">On the **Controlled** tab, click **MyOtherGPO**.</span></span>

    2.  <span data-ttu-id="6e8cb-396">以滑鼠右鍵按一下 [ **MyOtherGPO**]，指向 [**差異**]，然後按一下 [**範本**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-396">Right-click **MyOtherGPO**, point to **Differences**, and click **Template**.</span></span>

    3.  <span data-ttu-id="6e8cb-397">選取 [ **MyTemplate**及**HTML 報表**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-397">Select **MyTemplate** and **HTML Report**, and then click **OK**.</span></span>

### <a href="" id="bkmk-manage5"></a><span data-ttu-id="6e8cb-398">步驟5：刪除及還原 GPO</span><span class="sxs-lookup"><span data-stu-id="6e8cb-398">Step 5: Delete and restore a GPO</span></span>

<span data-ttu-id="6e8cb-399">在此步驟中，您會擔任核准者來刪除 GPO。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-399">In this step, you act as an Approver to delete a GPO.</span></span>

**<span data-ttu-id="6e8cb-400">刪除 GPO</span><span class="sxs-lookup"><span data-stu-id="6e8cb-400">To delete a GPO</span></span>**

1.  <span data-ttu-id="6e8cb-401">在已安裝 AGPM 用戶端的電腦上，以已指派核准者角色的使用者帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-401">On a computer on which you have installed AGPM Client, log on with a user account that has been assigned the role of Approver.</span></span>

2.  <span data-ttu-id="6e8cb-402">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-402">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

3.  <span data-ttu-id="6e8cb-403">在 [**內容**] 索引標籤上，按一下 [**受控**] 索引標籤以顯示受控制的 gpo。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-403">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

4.  <span data-ttu-id="6e8cb-404">以滑鼠右鍵按一下 [ **MyGPO**]，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-404">Right-click **MyGPO**, and then click **Delete**.</span></span> <span data-ttu-id="6e8cb-405">按一下 [**從封存及生產刪除 GPO** ]，即可刪除封存中的版本，以及在生產環境中已部署的 gpo 版本。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-405">Click **Delete GPO from archive and production** to delete both the version in the archive as well as the deployed version of the GPO in the production environment.</span></span>

5.  <span data-ttu-id="6e8cb-406">輸入要顯示在 GPO 的審核追蹤中的批註，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-406">Type a comment to be displayed in the audit trail for the GPO, and then click **OK**.</span></span>

6.  <span data-ttu-id="6e8cb-407">當 [ **AGPM 進度**] 視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-407">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="6e8cb-408">該 GPO 隨即會從 [**受控**] 索引標籤中移除，並顯示在 [**回收站**] 索引標籤上，可供您還原或銷毀。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-408">The GPO is removed from the **Controlled** tab and is displayed on the **Recycle Bin** tab, where it can be restored or destroyed.</span></span>

<span data-ttu-id="6e8cb-409">有時候，您可能會在刪除仍需要的 GPO 之後進行探索。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-409">Occasionally you may discover after deleting a GPO that it is still needed.</span></span> <span data-ttu-id="6e8cb-410">在此步驟中，您會擔任核准者來還原已刪除的 GPO。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-410">In this step, you act as an Approver to restore a GPO that has been deleted.</span></span>

**<span data-ttu-id="6e8cb-411">還原已刪除的 GPO</span><span class="sxs-lookup"><span data-stu-id="6e8cb-411">To restore a deleted GPO</span></span>**

1.  <span data-ttu-id="6e8cb-412">在 [**內容**] 索引標籤上，按一下 [**回收站**] 索引標籤以顯示已刪除的 gpo。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-412">On the **Contents** tab, click the **Recycle Bin** tab to display deleted GPOs.</span></span>

2.  <span data-ttu-id="6e8cb-413">以滑鼠右鍵按一下 [ **MyGPO**]，然後按一下 [**還原**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-413">Right-click **MyGPO**, and then click **Restore**.</span></span>

3.  <span data-ttu-id="6e8cb-414">輸入要顯示在 GPO 歷程記錄中的批註，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-414">Type a comment to be displayed in the history of the GPO, and then click **OK**.</span></span>

4.  <span data-ttu-id="6e8cb-415">當 [ **AGPM 進度**] 視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-415">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="6e8cb-416">該 GPO 隨即會從 [**回收站**] 索引標籤中移除，並顯示在 [**受控**] 索引標籤上。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-416">The GPO is removed from the **Recycle Bin** tab and is displayed on the **Controlled** tab.</span></span>

    <span data-ttu-id="6e8cb-417">**記事** 將 GPO 還原到封存後並不會自動將它重新部署到生產環境。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-417">**Note** Restoring a GPO to the archive does not automatically redeploy it to the production environment.</span></span> <span data-ttu-id="6e8cb-418">若要將 GPO 傳回生產環境，請像在步驟3中一樣部署 GPO [：審查及部署 gpo](#bkmk-manage3)。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-418">To return the GPO to the production environment, deploy the GPO as in [Step 3: Review and deploy a GPO](#bkmk-manage3).</span></span>

     

<span data-ttu-id="6e8cb-419">在編輯和部署 GPO 之後，您可能會發現對 GPO 所做的最近變更會造成問題。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-419">After editing and deploying a GPO, you may discover that recent changes to the GPO are causing a problem.</span></span> <span data-ttu-id="6e8cb-420">在這個步驟中，您會擔任核准者來回滾到舊版的 GPO。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-420">In this step, you act as an Approver to roll back to a previous version of the GPO.</span></span> <span data-ttu-id="6e8cb-421">您可以返回 GPO 歷程記錄中的任何版本。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-421">You can roll back to any version in the history of the GPO.</span></span> <span data-ttu-id="6e8cb-422">您可以使用 [批註] 和 [標籤] 來識別已知良好的版本，以及何時進行特定的變更。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-422">You can use comments and labels to identify known good versions and when specific changes were made.</span></span>

**<span data-ttu-id="6e8cb-423">回退到舊版的 GPO</span><span class="sxs-lookup"><span data-stu-id="6e8cb-423">To roll back to a previous version of a GPO</span></span>**

1.  <span data-ttu-id="6e8cb-424">在 [**內容**] 索引標籤上，按一下 [**受控**] 索引標籤以顯示受控制的 gpo。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-424">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

2.  <span data-ttu-id="6e8cb-425">按兩下 [ **MyGPO** ] 以顯示其歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-425">Double-click **MyGPO** to display its history.</span></span>

3.  <span data-ttu-id="6e8cb-426">以滑鼠右鍵按一下要部署的版本，按一下 [**部署**]，然後按一下 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-426">Right-click the version to be deployed, click **Deploy**, and then click **Yes**.</span></span>

4.  <span data-ttu-id="6e8cb-427">當**進度**視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-427">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="6e8cb-428">在 [歷程**記錄**] 視窗中，按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-428">In the **History** window, click **Close**.</span></span>

    <span data-ttu-id="6e8cb-429">**記事** 若要驗證已重新部署的版本是否為所需版本，請檢查兩個版本的差異報告。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-429">**Note** To verify that the version that has been redeployed is the version intended, examine a difference report for the two versions.</span></span> <span data-ttu-id="6e8cb-430">在 GPO 的 [歷程**記錄**] 視窗中，選取兩個版本，以滑鼠右鍵按一下這些版本，指向 [**差異**]，然後按一下 [ **HTML 報表**] 或 [ **XML 報表**]。</span><span class="sxs-lookup"><span data-stu-id="6e8cb-430">In the **History** window for the GPO, select the two versions, right-click them, point to **Difference**, and then click either **HTML Report** or **XML Report**.</span></span>

     

 

 





