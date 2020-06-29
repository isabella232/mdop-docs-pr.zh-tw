---
title: 如何針對 MBAM 設定網路負載平衡
description: 如何針對 MBAM 設定網路負載平衡
author: dansimp
ms.assetid: df2208c3-352b-4a48-9722-237b0c8cd6a5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a04bc74a9dab7bfe18eed8e5a3c1b6ca64d88b5b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811199"
---
# <span data-ttu-id="28ab4-103">如何針對 MBAM 設定網路負載平衡</span><span class="sxs-lookup"><span data-stu-id="28ab4-103">How to Configure Network Load Balancing for MBAM</span></span>


<span data-ttu-id="28ab4-104">若要確認您已滿足安裝管理和監視伺服器功能所需的先決條件與硬體及軟體需求，請參閱[MBAM 1.0 部署先決條件](mbam-10-deployment-prerequisites.md)和[MBAM 1.0 支援](mbam-10-supported-configurations.md)的設定。</span><span class="sxs-lookup"><span data-stu-id="28ab4-104">To verify that you have met the prerequisites and hardware and software requirements to install the Administration and Monitoring Server feature, see [MBAM 1.0 Deployment Prerequisites](mbam-10-deployment-prerequisites.md) and [MBAM 1.0 Supported Configurations](mbam-10-supported-configurations.md).</span></span>

<span data-ttu-id="28ab4-105">**記事** 若要取得安裝記錄檔，您必須使用**msiexec**套件和 **/l** Location 選項安裝 Microsoft BitLocker 管理和監控（MBAM） &lt; &gt; 。</span><span class="sxs-lookup"><span data-stu-id="28ab4-105">**Note** To obtain the setup log files, you must install Microsoft BitLocker Administration and Monitoring (MBAM) by using the **msiexec** package and the **/l** &lt;location&gt; option.</span></span> <span data-ttu-id="28ab4-106">系統會在您指定的位置建立記錄檔。</span><span class="sxs-lookup"><span data-stu-id="28ab4-106">The Log files are created in the location that you specify.</span></span>

<span data-ttu-id="28ab4-107">在安裝 MBAM 的使用者的% temp% 資料夾中，會建立其他設定記錄檔。</span><span class="sxs-lookup"><span data-stu-id="28ab4-107">Additional setup log files are created in the %temp% folder of the user who installs MBAM.</span></span>

 

<span data-ttu-id="28ab4-108">[管理及監視伺服器] 的網路負載平衡（NLB）群集可在 MBAM 中提供可縮放性，且應支援超過 55000 MBAM 個用戶端電腦。</span><span class="sxs-lookup"><span data-stu-id="28ab4-108">The Network Load Balancing (NLB) clusters for the Administration and Monitoring Server feature provides scalability in MBAM and it should support more than 55,000 MBAM client computers.</span></span>

<span data-ttu-id="28ab4-109">**記事** Windows Server 網路負載平衡會將用戶端要求分佈到一組伺服器，並設定在單一伺服器叢集中。</span><span class="sxs-lookup"><span data-stu-id="28ab4-109">**Note** Windows Server Network Load Balancing distributes client requests across a set of servers that are configured into a single server cluster.</span></span> <span data-ttu-id="28ab4-110">當網路負載平衡安裝在群集中的每個伺服器（主機）上時，群集會向用戶端要求顯示虛擬 IP 位址或完整的功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="28ab4-110">When Network Load Balancing is installed on each of the servers (hosts) in a cluster, the cluster presents a virtual IP address or fully qualified domain name (FQDN) to client requests.</span></span> <span data-ttu-id="28ab4-111">初始用戶端要求會移至群集中的所有主機，但只有一個主機接受並處理要求。</span><span class="sxs-lookup"><span data-stu-id="28ab4-111">The initial client requests go to all the hosts in the cluster, but only one host accepts and handles the request.</span></span>

<span data-ttu-id="28ab4-112">所有將組成 NLB 群集的電腦都有下列需求：</span><span class="sxs-lookup"><span data-stu-id="28ab4-112">All computers that will be part of a NLB cluster have the following requirements:</span></span>

-   <span data-ttu-id="28ab4-113">NLB 群集中的所有電腦都必須在同一個網域中。</span><span class="sxs-lookup"><span data-stu-id="28ab4-113">All computers in the NLB cluster must be in the same domain.</span></span>

-   <span data-ttu-id="28ab4-114">NLB 群集中的每個電腦都必須使用靜態 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="28ab4-114">Each computer in the NLB cluster must use a static IP address.</span></span>

-   <span data-ttu-id="28ab4-115">NLB 群集中的每個電腦都必須啟用網路負載平衡。</span><span class="sxs-lookup"><span data-stu-id="28ab4-115">Each computer in the NLB cluster must have Network Load Balancing enabled.</span></span>

-   <span data-ttu-id="28ab4-116">NLB 群集需要靜態 IP 位址，而且必須在網功能變數名稱稱系統（DNS）中手動建立主機記錄。</span><span class="sxs-lookup"><span data-stu-id="28ab4-116">The NLB cluster requires a static IP address, and a host record must be manually created in the domain name system (DNS).</span></span>

 

## <span data-ttu-id="28ab4-117">針對 MBAM 管理和監視伺服器設定網路負載平衡</span><span class="sxs-lookup"><span data-stu-id="28ab4-117">Configuring Network Load Balancing for MBAM Administration and Monitoring Servers</span></span>


<span data-ttu-id="28ab4-118">下列步驟說明如何針對兩個 MBAM 管理和監視伺服器設定 NLB 群集虛擬名稱和 IP 位址，以及如何將 MBAM 用戶端設定為使用 NLB 群集。</span><span class="sxs-lookup"><span data-stu-id="28ab4-118">The following steps describe how to configure an NLB cluster virtual name and IP address for two MBAM Administration and Monitoring servers, and how to configure MBAM Clients to use the NLB Cluster.</span></span>

<span data-ttu-id="28ab4-119">開始本主題中所述的程式之前，您必須在兩部不同的伺服器電腦上使用相同的 IIS 埠系結來成功安裝 MBAM 管理和監視伺服器功能，以符合 MBAM 伺服器功能安裝與 NLB 群集設定的先決條件。</span><span class="sxs-lookup"><span data-stu-id="28ab4-119">Before you begin the procedures described in this topic, you must have the MBAM Administration and Monitoring Server feature successfully installed by using the same IIS port binding on two separate server computers that meet the prerequisites for both MBAM Server feature installation and NLB Cluster configuration.</span></span>

<span data-ttu-id="28ab4-120">**記事** 本主題描述使用網路負載平衡管理員建立 NLB 群集的基本程式。</span><span class="sxs-lookup"><span data-stu-id="28ab4-120">**Note** This topic describes the basic process of using Network Load Balancing Manager to create an NLB Cluster.</span></span> <span data-ttu-id="28ab4-121">將 Windows Server 設定為 NLB 群集一部分的確切步驟，取決於使用中的 Windows Server 版本。</span><span class="sxs-lookup"><span data-stu-id="28ab4-121">The exact steps to configure a Windows Server as part of an NLB cluster depend on the Windows Server version in use..</span></span> <span data-ttu-id="28ab4-122">如需如何在 WindowsServer2008 上建立 NLBs 的詳細資訊，請參閱在 Windows Server2008 TechNet 文件庫中[建立網路負載平衡群集](https://go.microsoft.com/fwlink/?LinkId=197176)。</span><span class="sxs-lookup"><span data-stu-id="28ab4-122">For more information about how to create NLBs on WindowsServer2008, see [Creating Network Load Balancing Clusters](https://go.microsoft.com/fwlink/?LinkId=197176) in the Windows Server2008 TechNet library.</span></span>

 

**<span data-ttu-id="28ab4-123">針對兩個 MBAM 管理和監視伺服器設定 NLB 群集虛擬名稱和 IP 位址</span><span class="sxs-lookup"><span data-stu-id="28ab4-123">To configure an NLB Cluster Virtual Name and IP address for two MBAM Administration and Monitoring Servers</span></span>**

1.  <span data-ttu-id="28ab4-124">按一下 [**開始**]，按一下 [**所有程式**]，按一下 [系統**管理工具**]，然後按一下 [**網路負載平衡管理員**]。</span><span class="sxs-lookup"><span data-stu-id="28ab4-124">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Network Load Balancing Manager**.</span></span>

    <span data-ttu-id="28ab4-125">**記事** 如果 NLB 管理員不存在，您可以將它安裝為 WindowsServer 功能。</span><span class="sxs-lookup"><span data-stu-id="28ab4-125">**Note** If the NLB Manager is not present, you can install it as a WindowsServer feature.</span></span> <span data-ttu-id="28ab4-126">如果您想要將此功能設定在 NLB 群集中，您必須在 MBAM 管理和監視伺服器上安裝此功能。</span><span class="sxs-lookup"><span data-stu-id="28ab4-126">You must install this feature on both MBAM Administration and Monitoring servers if you want to configure it into the NLB cluster.</span></span>

     

2.  <span data-ttu-id="28ab4-127">在功能表列上，按一下 [**群集**]，然後按一下 [**新增**] 以開啟 [**群集參數**] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="28ab4-127">On the menu bar, click **Cluster**, and then click **New** to open the **Cluster Parameters** dialog box.</span></span>

3.  <span data-ttu-id="28ab4-128">在 [**群集參數**] 對話方塊中，輸入 NLB 群集 IP 配置的資訊：</span><span class="sxs-lookup"><span data-stu-id="28ab4-128">In the **Cluster Parameters** dialog box, enter the information for the NLB cluster IP configuration:</span></span>

    -   <span data-ttu-id="28ab4-129">**IP 位址：** 已在 DNS 中註冊的 NLB 群集 IP 位址</span><span class="sxs-lookup"><span data-stu-id="28ab4-129">**IP address:** NLB cluster IP address registered in DNS</span></span>

    -   <span data-ttu-id="28ab4-130">**子網路遮罩：** 已在 DNS 中註冊 NLB 群集 IP 位址子網路遮罩</span><span class="sxs-lookup"><span data-stu-id="28ab4-130">**Subnet mask:** NLB cluster IP address subnet mask registered in DNS</span></span>

    -   <span data-ttu-id="28ab4-131">**完整的網際網路名稱：** 在 DNS 中註冊 NLB 群集名稱的 FQDN</span><span class="sxs-lookup"><span data-stu-id="28ab4-131">**Full Internet name:** FQDN of NLB cluster name registered in DNS</span></span>

4.  <span data-ttu-id="28ab4-132">確定 [**群集作業模式]** 中已選取 [**單播**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="28ab4-132">Ensure that **Unicast** is selected in **Cluster operation mode**, and then click **Next**.</span></span>

5.  <span data-ttu-id="28ab4-133">在 [**群集 IP 位址**] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="28ab4-133">On the **Cluster IP Addresses** page, click **Next**.</span></span>

6.  <span data-ttu-id="28ab4-134">在 [**連接埠規則**] 頁面上，按一下 [**編輯**] 以定義 NLB 群集將回應的埠，並設定用於用戶端到網站系統通訊的埠，就像為網站定義的埠一樣，或按一下 **[下一步]** ，讓 NLB 群集 IP 位址回應所有 tcp/ip 埠。</span><span class="sxs-lookup"><span data-stu-id="28ab4-134">On the **Port Rules** page, click **Edit** to define the ports that the NLB cluster will respond to and configure the ports that are used for client-to-site system communication as they are defined for the site, or click **Next** to enable the NLB cluster IP address to respond to all TCP/IP ports.</span></span>

    <span data-ttu-id="28ab4-135">**記事** 確定 [**關聯性**] 已設定為 [**單一**]。</span><span class="sxs-lookup"><span data-stu-id="28ab4-135">**Note** Ensure that **Affinity** is set to **Single**.</span></span>

     

7.  <span data-ttu-id="28ab4-136">在 [ **Connect]** （連線）頁面上，輸入 MBAM 管理和監視伺服器實例主機名稱，該名稱會成為**主機**中的 NLB 群集的一部分，然後按一下 **[連線]**。</span><span class="sxs-lookup"><span data-stu-id="28ab4-136">On the **Connect** page, enter an MBAM Administration and Monitoring server instance host name that will be part of the NLB cluster in **Host**, and then click **Connect**.</span></span>

8.  <span data-ttu-id="28ab4-137">在 [**可用於設定新群集的介面**] 中，選取將設定為回應 NLB 群集通訊的網路介面，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="28ab4-137">In **Interfaces available for configuring a new cluster**, select the networking interface that will be configured to respond to NLB cluster communication, and then click **Next**.</span></span>

9.  <span data-ttu-id="28ab4-138">在 [**主機參數**] 頁面上，查看顯示的資訊，以**確保專用的 IP**設定設定會針對正確的 NLB 群集主機顯示專用的主機 IP 設定，請檢查初始正本狀態**預設狀態：** 已**啟動**，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="28ab4-138">On the **Host Parameters** page, review the information displayed to ensure that the **Dedicated IP configuration** settings display the dedicated host IP configuration for the correct NLB cluster host, check that the Initial host state **Default state:** is **Started**, and then click **Finish**.</span></span>

    <span data-ttu-id="28ab4-139">**記事** [**主機參數**] 頁面也會顯示 [NLB 群集主機優先順序]，也就是1到32。</span><span class="sxs-lookup"><span data-stu-id="28ab4-139">**Note** The **Host Parameters** page also displays the NLB cluster host priority, which is 1 through 32.</span></span> <span data-ttu-id="28ab4-140">在 NLB 群集中新增主機時，主機優先順序必須與先前新增的主機有所不同。</span><span class="sxs-lookup"><span data-stu-id="28ab4-140">As new hosts are added to the NLB cluster, the host priority must differ from the previously added hosts.</span></span> <span data-ttu-id="28ab4-141">當您使用網路負載平衡管理員時，會自動增加優先順序。</span><span class="sxs-lookup"><span data-stu-id="28ab4-141">The priority is automatically incremented when you use the Network Load Balancing Manager.</span></span>

     

10. <span data-ttu-id="28ab4-142">按一下 [ \*\* &lt; nlb 群集 &gt; 名稱**]，並確保 NLB 主機介面**狀態**會在您繼續之前先進行**集中\*\*顯示。</span><span class="sxs-lookup"><span data-stu-id="28ab4-142">Click **&lt;NLB cluster name&gt;** and ensure that the NLB host interface **Status** displays **Converged** before you continue.</span></span> <span data-ttu-id="28ab4-143">此步驟可能會要求您將 NLB 群集顯示重新整理為 NLB 管理員要修改的主機 TCP/IP 設定。</span><span class="sxs-lookup"><span data-stu-id="28ab4-143">This step might require that you refresh the NLB cluster display as the host TCP/IP configuration that is being modified by the NLB Manager.</span></span>

11. <span data-ttu-id="28ab4-144">若要在 NLB 群集中新增其他主機，請以滑鼠右鍵按一下 [ \*\* &lt; nlb 群集名稱 &gt; **]，按一下 [**新增主機至群集]，\*\* 然後針對將是 NLB 群集一部分的每個網站系統重複步驟7到10。</span><span class="sxs-lookup"><span data-stu-id="28ab4-144">To add additional hosts to the NLB cluster, right-click **&lt;NLB cluster name&gt;**, click **Add Host to Cluster,** and then repeat steps 7 through 10 for each site system that will be part of the NLB cluster.</span></span>

12. <span data-ttu-id="28ab4-145">在已安裝 MBAM 群組原則範本的電腦上，修改 MBAM 群組原則設定，將 MBAM 服務端點設定為使用 NLB 群集名稱和適當的 IIS 埠系結，以存取已安裝在 NLB 群集電腦上的 MBAM 管理和監視伺服器功能。</span><span class="sxs-lookup"><span data-stu-id="28ab4-145">On a computer that has MBAM Group Policy template installed, modify the MBAM Group Policy settings to configure the MBAM services endpoints to use the NLB Cluster name and the appropriate IIS port binding to access the MBAM Administration and Monitoring Server features that are installed on the NLB Cluster computers.</span></span> <span data-ttu-id="28ab4-146">如需如何編輯 MBAM GPO 設定的詳細資訊，請參閱[如何編輯 MBAM 1.0 Gpo 設定](how-to-edit-mbam-10-gpo-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="28ab4-146">For more information about how to edit MBAM GPO settings, see [How to Edit MBAM 1.0 GPO Settings](how-to-edit-mbam-10-gpo-settings.md).</span></span> <span data-ttu-id="28ab4-147">如果 MBAM 管理和監視伺服器對您的環境而言是新的，請確定已正確設定必要的本地安全性群組成員資格。</span><span class="sxs-lookup"><span data-stu-id="28ab4-147">If the MBAM Administration and Monitoring servers are new to your environment, ensure that the required local security group memberships have been properly configured.</span></span> <span data-ttu-id="28ab4-148">如需安全群組需求的詳細資訊，請參閱[規劃 MBAM 1.0 系統管理員角色](planning-for-mbam-10-administrator-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="28ab4-148">For more information about security group requirements, see [Planning for MBAM 1.0 Administrator Roles](planning-for-mbam-10-administrator-roles.md).</span></span>

13. <span data-ttu-id="28ab4-149">當 NLB 群集設定完成時，建議您驗證 MBAM 管理和監視 NLB 群集是否正常運作。</span><span class="sxs-lookup"><span data-stu-id="28ab4-149">When the NLB Cluster configuration is complete, we recommend that you validate that the MBAM Administration and Monitoring NLB Cluster is functional.</span></span> <span data-ttu-id="28ab4-150">若要這樣做，請在您的電腦上開啟網頁瀏覽器，而不是在 NLB 中設定的伺服器，並確保您可以使用 NLB FQDN 存取 MBAM 管理和監控網站。</span><span class="sxs-lookup"><span data-stu-id="28ab4-150">To do this, open a web browser on a computer other than the servers that are configured in the NLB, and ensure that you can access the MBAM Administration and Monitoring web site by using the NLB FQDN.</span></span>

## <span data-ttu-id="28ab4-151">相關主題</span><span class="sxs-lookup"><span data-stu-id="28ab4-151">Related topics</span></span>


[<span data-ttu-id="28ab4-152">部署 MBAM 1.0 伺服器基礎結構</span><span class="sxs-lookup"><span data-stu-id="28ab4-152">Deploying the MBAM 1.0 Server Infrastructure</span></span>](deploying-the-mbam-10-server-infrastructure.md)

 

 





