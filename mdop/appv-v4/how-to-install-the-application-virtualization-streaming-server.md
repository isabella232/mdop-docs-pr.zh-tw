---
title: 如何安裝 Application Virtualization Streaming Server
description: 如何安裝 Application Virtualization Streaming Server
author: dansimp
ms.assetid: a3065257-fb5a-4d92-98f8-7ef996c61db9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c4e4f8421ef1c0e60a7df92d41be98a5d2bc0132
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801373"
---
# <span data-ttu-id="5a737-103">如何安裝 Application Virtualization Streaming Server</span><span class="sxs-lookup"><span data-stu-id="5a737-103">How to Install the Application Virtualization Streaming Server</span></span>


<span data-ttu-id="5a737-104">應用程式虛擬化資料流程伺服器會將其應用程式發佈給用戶端。</span><span class="sxs-lookup"><span data-stu-id="5a737-104">The Application Virtualization Streaming Server publishes its applications to clients.</span></span> <span data-ttu-id="5a737-105">在負載平衡環境（通常是大型部署）中，伺服器群組中的所有伺服器應該串流相同的應用程式。</span><span class="sxs-lookup"><span data-stu-id="5a737-105">In a load-balanced environment, which is typical of large deployments, all servers in a server group should stream the same applications.</span></span> <span data-ttu-id="5a737-106">如果應用程式虛擬化資料流程伺服器要傳輸不同的應用程式，請將伺服器指派給不同的伺服器群組。</span><span class="sxs-lookup"><span data-stu-id="5a737-106">If Application Virtualization Streaming Servers are to stream different applications, assign the servers to different server groups.</span></span> <span data-ttu-id="5a737-107">在這種情況下，您可能也需要增加伺服器群組的容量。</span><span class="sxs-lookup"><span data-stu-id="5a737-107">In this case, you might also have to increase a server group's capacity.</span></span>

<span data-ttu-id="5a737-108">如果您已指定網路上的目的電腦，且具有本機系統管理許可權的登入帳戶，您可以使用下列程式來安裝應用程式虛擬化資料流程伺服器，並將它指派給適當的伺服器群組。</span><span class="sxs-lookup"><span data-stu-id="5a737-108">If you have designated a target computer on the network, with a logon account having local administrative privileges, you can use the following procedure to install the Application Virtualization Streaming Server and assign it to the appropriate server group.</span></span>

<span data-ttu-id="5a737-109">**記事** 安裝精靈可以建立一個伺服器群組記錄（如果不存在的話），以及此群組中應用程式虛擬化資料流程伺服器成員資格的記錄。</span><span class="sxs-lookup"><span data-stu-id="5a737-109">**Note** The Installation Wizard can create a server group record, if one does not exist, and a record of the Application Virtualization Streaming Server membership in this group.</span></span>

 

<span data-ttu-id="5a737-110">完成安裝程式後，請重新開機伺服器。</span><span class="sxs-lookup"><span data-stu-id="5a737-110">After you complete the installation process, restart the server.</span></span>

**<span data-ttu-id="5a737-111">若要安裝應用程式虛擬化資料流程伺服器</span><span class="sxs-lookup"><span data-stu-id="5a737-111">To install an Application Virtualization Streaming Server</span></span>**

1.  <span data-ttu-id="5a737-112">確認您的目的電腦上沒有安裝舊版的應用程式虛擬化資料流程伺服器。</span><span class="sxs-lookup"><span data-stu-id="5a737-112">Verify that no earlier versions of the Application Virtualization Streaming Server are installed on your target computer.</span></span>

    <span data-ttu-id="5a737-113">**重要** 確定此電腦上未安裝 App-v 管理伺服器。</span><span class="sxs-lookup"><span data-stu-id="5a737-113">**Important** Make sure that the App-V Management Server is not installed on this computer.</span></span> <span data-ttu-id="5a737-114">這兩個產品無法安裝在同一部電腦上。</span><span class="sxs-lookup"><span data-stu-id="5a737-114">The two products cannot be installed on the same computer.</span></span>

     

2.  <span data-ttu-id="5a737-115">流覽至 [應用程式虛擬化系統] 設定程式在網路上的位置，請從網路執行此程式，或將它的目錄複寫到目的電腦，然後按兩下**Setup.exe**的檔案。</span><span class="sxs-lookup"><span data-stu-id="5a737-115">Navigate to the location of the Application Virtualization System Setup program on the network, either run this program from the network or copy its directory to the target computer, and then double-click the **Setup.exe** file.</span></span>

3.  <span data-ttu-id="5a737-116">在 [**歡迎**] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="5a737-116">On the **Welcome** page, click **Next**.</span></span>

4.  <span data-ttu-id="5a737-117">若要接受授權條款，請在 [**授權協定**] 頁面上，選取 **[我接受授權條款及條件**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="5a737-117">On the **License Agreement** page, to accept the license terms, select **I accept the licensing terms and conditions**, and then click **Next**.</span></span>

5.  <span data-ttu-id="5a737-118">在 [**客戶資訊**] 頁面上，指定**使用者名稱**和組織，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="5a737-118">On the **Customer Information** page, specify the **User name** and the organization, and then click **Next**.</span></span>

6.  <span data-ttu-id="5a737-119">在 [**安裝路徑**] 頁面上，按一下 **[流覽]**，指定您要安裝流式伺服器的位置，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="5a737-119">On the **Installation Path** page, click **Browse**, specify the location where you want to install the Streaming Server, and then click **Next**.</span></span>

7.  <span data-ttu-id="5a737-120">在 [連線**安全模式]** 頁面上，從下拉式清單中選取想要的憑證，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="5a737-120">On the **Connection Security Mode** page, select the desired certificate from the drop-down list, and then click **Next**.</span></span>

    <span data-ttu-id="5a737-121">**記事** [**安全連線模式]** 設定需要伺服器從公開金鑰基礎結構將伺服器憑證提供給它。</span><span class="sxs-lookup"><span data-stu-id="5a737-121">**Note** The **Secure Connection Mode** setting requires the server to have a server certificate provisioned to it from a public key infrastructure.</span></span> <span data-ttu-id="5a737-122">如果伺服器上沒有安裝伺服器憑證，則此選項無法使用且無法選取。</span><span class="sxs-lookup"><span data-stu-id="5a737-122">If a server certificate is not installed on the server, this option is unavailable and cannot be selected.</span></span> <span data-ttu-id="5a737-123">您必須授與網路服務帳戶對正在使用之憑證的讀取存取權。</span><span class="sxs-lookup"><span data-stu-id="5a737-123">You must grant the Network Service account read access to the certificate being used.</span></span>

     

8.  <span data-ttu-id="5a737-124">在 [ **TCP 埠**設定] 頁面上，若要使用標準埠（554），請選取 [**使用預設埠（554）**]。</span><span class="sxs-lookup"><span data-stu-id="5a737-124">On the **TCP Port Configuration** page, to use the standard port (554), select **Use default port (554)**.</span></span> <span data-ttu-id="5a737-125">若要指定自訂埠，請選取 [**使用自訂埠**]，在提供的欄位中指定埠號碼，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="5a737-125">To specify a custom port, select **Use custom port**, specify the port number in the field provided, and then click **Next**.</span></span>

    <span data-ttu-id="5a737-126">**記事** 當您在不安全的情況下安裝伺服器時，您可以使用預設埠（554），也可以定義自訂埠。</span><span class="sxs-lookup"><span data-stu-id="5a737-126">**Note** When you install the server in a nonsecure scenario, you can use the default port (554), or you can define a custom port.</span></span>

     

9.  <span data-ttu-id="5a737-127">在 [**內容根目錄**] 頁面上，指定要儲存 SFT 檔案之目的電腦上的位置，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="5a737-127">On the **Content Root** page, specify the location on the target computer where SFT files will be saved, and then click **Next**.</span></span>

    <span data-ttu-id="5a737-128">**記事** 如果虛擬應用程式流式處理伺服器的 HTTP 或 RTSP 埠已被指派，系統會提示您選取新的埠。</span><span class="sxs-lookup"><span data-stu-id="5a737-128">**Note** If the HTTP or RTSP port for the Virtual Application Streaming Server is already allocated, you will be prompted to select a new port.</span></span> <span data-ttu-id="5a737-129">指定想要的埠，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="5a737-129">Specify the desired port, and then click **Next**.</span></span>

     

10. <span data-ttu-id="5a737-130">在 [**高級設定**] 畫面上，輸入下列資訊：</span><span class="sxs-lookup"><span data-stu-id="5a737-130">On the **Advanced Setting** screen, enter the following information:</span></span>

    1.  **<span data-ttu-id="5a737-131">最大用戶端連線數</span><span class="sxs-lookup"><span data-stu-id="5a737-131">Max client connections</span></span>**

    2.  **<span data-ttu-id="5a737-132">連接逾時（秒）</span><span class="sxs-lookup"><span data-stu-id="5a737-132">Connection timeout (sec)</span></span>**

    3.  **<span data-ttu-id="5a737-133">RTSP 執行緒泳池大小</span><span class="sxs-lookup"><span data-stu-id="5a737-133">RTSP thread pool size</span></span>**

    4.  **<span data-ttu-id="5a737-134">RTSP 超時（秒）</span><span class="sxs-lookup"><span data-stu-id="5a737-134">RTSP timeout (sec)</span></span>**

    5.  **<span data-ttu-id="5a737-135">核心進程數</span><span class="sxs-lookup"><span data-stu-id="5a737-135">Number of core processes</span></span>**

    6.  **<span data-ttu-id="5a737-136">核心超時（秒）</span><span class="sxs-lookup"><span data-stu-id="5a737-136">Core timeout (sec)</span></span>**

    7.  **<span data-ttu-id="5a737-137">啟用使用者驗證</span><span class="sxs-lookup"><span data-stu-id="5a737-137">Enable User authentication</span></span>**

    8.  **<span data-ttu-id="5a737-138">啟用使用者授權</span><span class="sxs-lookup"><span data-stu-id="5a737-138">Enable User authorization</span></span>**

    9.  **<span data-ttu-id="5a737-139">緩衝區塊大小（KB）</span><span class="sxs-lookup"><span data-stu-id="5a737-139">Cache block size (KB)</span></span>**

    10. **<span data-ttu-id="5a737-140">最大快取大小（MB）</span><span class="sxs-lookup"><span data-stu-id="5a737-140">Maximum cache size (MB)</span></span>**

    <span data-ttu-id="5a737-141">**記事** App-v 流式處理伺服器使用 NTFS 檔案系統許可權來控制內容共用下的應用程式存取權。</span><span class="sxs-lookup"><span data-stu-id="5a737-141">**Note** The App-V Streaming Server uses NTFS file system permissions to control access to the applications under the Content share.</span></span> <span data-ttu-id="5a737-142">使用 [**啟用使用者驗證**] 並**啟用使用者授權**，以控制伺服器是否要檢查並強制執行這些存取控制清單（acl）。</span><span class="sxs-lookup"><span data-stu-id="5a737-142">Use **Enable User authentication** and **Enable User authorization** to control whether the server checks and enforces those access control lists (ACLs) or not.</span></span>

     

11. <span data-ttu-id="5a737-143">在 [**準備好安裝程式**] 頁面上，按一下 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="5a737-143">On the **Ready to Install the Program** page, to start the installation, click **Install**.</span></span>

12. <span data-ttu-id="5a737-144">在 [**安裝精靈完成]** 畫面上，若要關閉嚮導，請按一下 **[完成**]。</span><span class="sxs-lookup"><span data-stu-id="5a737-144">On the **Installation Wizard Completed** screen, to close the wizard, click **Finish**.</span></span>

    <span data-ttu-id="5a737-145">**重要** 安裝可能需要幾分鐘的時間才能完成。</span><span class="sxs-lookup"><span data-stu-id="5a737-145">**Important** The installation can take several minutes to finish.</span></span> <span data-ttu-id="5a737-146">狀態訊息會在 Windows 桌面通知區域上方閃爍，指出安裝已成功完成。</span><span class="sxs-lookup"><span data-stu-id="5a737-146">A status message will flash above the Windows desktop notification area, indicating that the installation succeeded.</span></span>

    <span data-ttu-id="5a737-147">出現提示時，不需要重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="5a737-147">It is not required to restart the computer when you are prompted.</span></span> <span data-ttu-id="5a737-148">不過，為了優化系統效能，我們建議您重新開機。</span><span class="sxs-lookup"><span data-stu-id="5a737-148">However, to optimize system performance, we recommend a restart.</span></span>

     

13. <span data-ttu-id="5a737-149">針對您必須安裝的每個虛擬應用程式伺服器，重複步驟1到12。</span><span class="sxs-lookup"><span data-stu-id="5a737-149">Repeat Steps 1–12 for each Virtual Application Server that you have to install.</span></span>

## <span data-ttu-id="5a737-150">相關主題</span><span class="sxs-lookup"><span data-stu-id="5a737-150">Related topics</span></span>


[<span data-ttu-id="5a737-151">如何安裝伺服器和系統元件</span><span class="sxs-lookup"><span data-stu-id="5a737-151">How to Install the Servers and System Components</span></span>](how-to-install-the-servers-and-system-components.md)

 

 





