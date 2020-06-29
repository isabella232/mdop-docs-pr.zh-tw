---
title: 修改 AGPM 服務
description: 修改 AGPM 服務
author: dansimp
ms.assetid: 3485f85f-59d1-48dc-8748-36826214dcb1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3f6111a2713fcbe59ffb4336fc84bfa4697ffdeb
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802642"
---
# <span data-ttu-id="0fa15-103">修改 AGPM 服務</span><span class="sxs-lookup"><span data-stu-id="0fa15-103">Modify the AGPM Service</span></span>


<span data-ttu-id="0fa15-104">AGPM 服務是一個充當安全性 proxy 的 Windows 服務，管理用戶端對封存和生產環境中的群組原則物件（Gpo）的存取權。</span><span class="sxs-lookup"><span data-stu-id="0fa15-104">The AGPM Service is a Windows service that acts as a security proxy, managing client access to Group Policy Objects (GPOs) in the archive and production environment.</span></span> <span data-ttu-id="0fa15-105">如果此服務已停止或停用，則 AGPM 用戶端無法透過伺服器執行作業。</span><span class="sxs-lookup"><span data-stu-id="0fa15-105">If this service is stopped or disabled, AGPM Clients cannot perform operations through the server.</span></span> <span data-ttu-id="0fa15-106">您可以修改封存路徑、AGPM 服務帳戶，以及 AGPM 服務偵聽的埠。</span><span class="sxs-lookup"><span data-stu-id="0fa15-106">You can modify the archive path, the AGPM Service Account, and the port on which the AGPM Service listens.</span></span>

<span data-ttu-id="0fa15-107">**小心** 請勿透過作業系統中的 [**管理工具**] 和 [**服務**] 來修改 AGPM 服務的設定。</span><span class="sxs-lookup"><span data-stu-id="0fa15-107">**Caution** Do not modify settings for the AGPM Service through **Administrative Tools** and **Services** in the operating system.</span></span> <span data-ttu-id="0fa15-108">如此一來，就能防止 AGPM 服務啟動。</span><span class="sxs-lookup"><span data-stu-id="0fa15-108">Doing so can prevent the AGPM Service from starting.</span></span>

 

<span data-ttu-id="0fa15-109">使用者帳戶是 Domain Admins 群組的成員，且有權存取 AGPM 服務器（安裝 Microsoft 高級群組原則管理-伺服器的電腦）需要完成此程式。</span><span class="sxs-lookup"><span data-stu-id="0fa15-109">A user account that is a member of the Domain Admins group and has access to the AGPM Server (the computer on which Microsoft Advanced Group Policy Management - Server is installed) is required to complete this procedure.</span></span> <span data-ttu-id="0fa15-110">此外，您必須提供 AGPM 服務帳戶的認證，才能完成此程式。</span><span class="sxs-lookup"><span data-stu-id="0fa15-110">Additionally, you must provide credentials for the AGPM Service Account to complete this procedure.</span></span>

**<span data-ttu-id="0fa15-111">修改 AGPM 服務</span><span class="sxs-lookup"><span data-stu-id="0fa15-111">To modify the AGPM Service</span></span>**

1.  <span data-ttu-id="0fa15-112">在已安裝 Microsoft 高級群組原則管理-伺服器的電腦上：</span><span class="sxs-lookup"><span data-stu-id="0fa15-112">On the computer on which Microsoft Advanced Group Policy Management - Server is installed:</span></span>

    -   <span data-ttu-id="0fa15-113">針對 WindowsServer2008，按一下 [**開始**]、[**控制台**]，以及 [**程式和功能**]。</span><span class="sxs-lookup"><span data-stu-id="0fa15-113">For WindowsServer2008, click **Start**, **Control Panel**, and **Programs and Features**.</span></span>

    -   <span data-ttu-id="0fa15-114">針對 WindowsVista，按一下 [**開始**]、[**控制台**]、[**程式**] 和 [**程式和功能**]。</span><span class="sxs-lookup"><span data-stu-id="0fa15-114">For WindowsVista, click **Start**, **Control Panel**, **Programs**, and **Programs and Features**.</span></span>

2.  <span data-ttu-id="0fa15-115">以滑鼠右鍵按一下 [ **Microsoft 高級群組原則管理-伺服器**]，然後按一下 [**變更**]。</span><span class="sxs-lookup"><span data-stu-id="0fa15-115">Right-click **Microsoft Advanced Group Policy Management - Server**, and then click **Change**.</span></span>

3.  <span data-ttu-id="0fa15-116">按一下 **[下一步]**，然後按一下 [**修改**]。</span><span class="sxs-lookup"><span data-stu-id="0fa15-116">Click **Next**, and then click **Modify**.</span></span>

4.  <span data-ttu-id="0fa15-117">依照指示來設定 AGPM 服務：</span><span class="sxs-lookup"><span data-stu-id="0fa15-117">Follow the instructions to configure the AGPM Service:</span></span>

    1.  <span data-ttu-id="0fa15-118">在 [封存**路徑**] 對話方塊中，輸入與 AGPM 服務器相對的新檔案位置，或確認目前的封存路徑，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="0fa15-118">In the **Archive Path** dialog box, enter a new location for the archive relative to the AGPM Server, or confirm the current archive path, and then click **Next**.</span></span>

        <span data-ttu-id="0fa15-119">**重要** 封存路徑可以指向 AGPM 服務器或其他位置的資料夾，但該位置應該有足夠的空間來儲存此 AGPM 服務器所管理的所有 Gpo 及歷程記錄資料。</span><span class="sxs-lookup"><span data-stu-id="0fa15-119">**Important** The archive path can point to a folder on the AGPM Server or elsewhere, but the location should have sufficient space to store all GPOs and history data managed by this AGPM Server.</span></span>

         

    2.  <span data-ttu-id="0fa15-120">在 [ **Agpm 服務帳戶**] 對話方塊中，輸入要在其下執行 AGPM 服務的服務帳戶的認證，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="0fa15-120">In the **AGPM Service Account** dialog box, enter credentials for a service account under which the AGPM Service will run, and click **Next**.</span></span>

        <span data-ttu-id="0fa15-121">**重要** 修改安裝會清除 AGPM 服務帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="0fa15-121">**Important** Modifying the installation clears the credentials for the AGPM Service Account.</span></span> <span data-ttu-id="0fa15-122">您必須重新輸入認證，但不需要符合在原始安裝期間所使用的認證。</span><span class="sxs-lookup"><span data-stu-id="0fa15-122">You must re-enter credentials, but they are not required to match the credentials used during the original installation.</span></span>

        <span data-ttu-id="0fa15-123">AGPM 服務帳戶必須擁有對其所管理之 Gpo 的完整存取權，並將其授**與服務許可權登**入。</span><span class="sxs-lookup"><span data-stu-id="0fa15-123">The AGPM Service Account must have full access to the GPOs that it will manage and will be granted **Log On As A Service** permission.</span></span> <span data-ttu-id="0fa15-124">如果您要在單一網域上管理 Gpo，您可以將 [本機系統] 帳戶設為主要網網域控制站（AGPM 服務帳戶）。</span><span class="sxs-lookup"><span data-stu-id="0fa15-124">If you will be managing GPOs on a single domain, you can make the Local System account for the primary domain controller the AGPM Service Account.</span></span>

        <span data-ttu-id="0fa15-125">如果您要管理多個網域上的 Gpo，或如果成員伺服器將是 AGPM 服務器，您應該將另一個帳戶設定為 AGPM 服務帳戶，因為一個網網域控制站的本機系統帳戶無法存取其他網域上的 Gpo。</span><span class="sxs-lookup"><span data-stu-id="0fa15-125">If you will be managing GPOs on multiple domains or if a member server will be the AGPM Server, you should configure a different account as the AGPM Service Account because the Local System account for one domain controller cannot access GPOs on other domains.</span></span>

         

    3.  <span data-ttu-id="0fa15-126">在 [封存**擁有**者] 對話方塊中，輸入 agpm 管理員（完全控制）或 Agpm 系統管理員群組的使用者名稱，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="0fa15-126">In the **Archive Owner** dialog box, enter the user name of an AGPM Administrator (Full Control) or group of AGPM Administrators, and click **Next**.</span></span>

        <span data-ttu-id="0fa15-127">**記事** 修改安裝會清除封存擁有者的認證。</span><span class="sxs-lookup"><span data-stu-id="0fa15-127">**Note** Modifying the installation clears the credentials for the Archive Owner.</span></span> <span data-ttu-id="0fa15-128">您必須重新輸入認證，但不需要符合在原始安裝期間所使用的認證。</span><span class="sxs-lookup"><span data-stu-id="0fa15-128">You must re-enter credentials, but they are not required to match the credentials used during the original installation.</span></span>

         

    4.  <span data-ttu-id="0fa15-129">在 [**埠**設定] 對話方塊中，輸入新的埠，以便 AGPM 服務聆聽或確認目前已選取的埠，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="0fa15-129">In the **Port Configuration** dialog box, type a new port on which the AGPM Service should listen or confirm the port currently selected, and click **Next**.</span></span>

        <span data-ttu-id="0fa15-130">**記事** 根據預設，AGPM 服務會偵聽埠4600。</span><span class="sxs-lookup"><span data-stu-id="0fa15-130">**Note** By default, the AGPM Service listens on port 4600.</span></span>

        <span data-ttu-id="0fa15-131">如果您手動設定埠例外狀況，或有設定埠例外狀況的規則，您可以清除 [**將埠例外新增到防火牆**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="0fa15-131">If you manually configure port exceptions or have rules configuring port exceptions, you can clear the **Add port exception to firewall** check box.</span></span>

         

5.  <span data-ttu-id="0fa15-132">按一下 [**變更**]，完成安裝後，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="0fa15-132">Click **Change**, and when the installation is complete click **Finish**.</span></span>

6.  <span data-ttu-id="0fa15-133">如果您已經變更了 AGPM 服務偵聽的埠，請針對每個群組原則管理員，在 AGPM 服務器連線中修改埠。</span><span class="sxs-lookup"><span data-stu-id="0fa15-133">If you have changed the port on which the AGPM Service listens, modify the port in the AGPM Server connection for each Group Policy administrator.</span></span> <span data-ttu-id="0fa15-134">（如需詳細資訊，請參閱[設定 AGPM 服務器](configure-agpm-server-connections-agpm30ops.md)連線）。</span><span class="sxs-lookup"><span data-stu-id="0fa15-134">(For more information, see [Configure AGPM Server Connections](configure-agpm-server-connections-agpm30ops.md).)</span></span>

7.  <span data-ttu-id="0fa15-135">針對要套用設定變更的每個 AGPM 服務器重複上述步驟。</span><span class="sxs-lookup"><span data-stu-id="0fa15-135">Repeat for each AGPM Server to which the configuration changes should be applied.</span></span>

### <span data-ttu-id="0fa15-136">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="0fa15-136">Additional references</span></span>

-   [<span data-ttu-id="0fa15-137">管理 AGPM 服務</span><span class="sxs-lookup"><span data-stu-id="0fa15-137">Managing the AGPM Service</span></span>](managing-the-agpm-service-agpm30ops.md)

 

 





