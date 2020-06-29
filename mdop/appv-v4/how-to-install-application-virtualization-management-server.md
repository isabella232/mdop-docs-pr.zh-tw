---
title: 如何安裝 Application Virtualization Management Server
description: 如何安裝 Application Virtualization Management Server
author: dansimp
ms.assetid: 8184be79-8c27-4328-a3c1-183791b5556c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dfd06ee1d2448990d5a740f3d59b0e5e4b45be4d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801386"
---
# <span data-ttu-id="6c8d2-103">如何安裝 Application Virtualization Management Server</span><span class="sxs-lookup"><span data-stu-id="6c8d2-103">How to Install Application Virtualization Management Server</span></span>


<span data-ttu-id="6c8d2-104">應用程式虛擬化管理伺服器會將其應用程式發佈給用戶端。</span><span class="sxs-lookup"><span data-stu-id="6c8d2-104">The Application Virtualization Management Server publishes its applications to clients.</span></span> <span data-ttu-id="6c8d2-105">在負載平衡環境（通常是大型部署）中，伺服器群組中的所有伺服器應該串流相同的應用程式。</span><span class="sxs-lookup"><span data-stu-id="6c8d2-105">In a load-balanced environment, which is typical of large deployments, all servers in a server group should stream the same applications.</span></span> <span data-ttu-id="6c8d2-106">如果應用程式虛擬化管理伺服器要發佈不同的應用程式，請將伺服器指派給不同的伺服器群組。</span><span class="sxs-lookup"><span data-stu-id="6c8d2-106">If Application Virtualization Management Servers are to publish different applications, assign the servers to different server groups.</span></span> <span data-ttu-id="6c8d2-107">在這種情況下，您也可能需要增加伺服器群組的容量。</span><span class="sxs-lookup"><span data-stu-id="6c8d2-107">In this case, you also might need to increase a server group's capacity.</span></span>

<span data-ttu-id="6c8d2-108">如果您已在網路上指定目的電腦，且有具有本機系統管理員許可權的登入帳戶，您可以使用下列程式來安裝應用程式虛擬化管理伺服器，並將它指派給適當的伺服器群組。</span><span class="sxs-lookup"><span data-stu-id="6c8d2-108">If you have designated a target computer on the network, with a login account having local Administrator privileges, you can use the following procedure to install the Application Virtualization Management Server and assign it to the appropriate server group.</span></span>

**<span data-ttu-id="6c8d2-109">注意</span><span class="sxs-lookup"><span data-stu-id="6c8d2-109">Note</span></span>**  
<span data-ttu-id="6c8d2-110">安裝精靈可以建立一個伺服器群組記錄（如果沒有的話），以及應用程式虛擬化管理伺服器在此群組中的成員資格記錄。</span><span class="sxs-lookup"><span data-stu-id="6c8d2-110">The Installation Wizard can create a server group record, if one does not exist, as well as a record of the Application Virtualization Management Server's membership in this group.</span></span>



<span data-ttu-id="6c8d2-111">完成安裝程式後，請重新開機伺服器。</span><span class="sxs-lookup"><span data-stu-id="6c8d2-111">After you complete the installation process, reboot the server.</span></span>

**<span data-ttu-id="6c8d2-112">安裝應用程式虛擬化管理伺服器</span><span class="sxs-lookup"><span data-stu-id="6c8d2-112">To install an Application Virtualization Management Server</span></span>**

1.  <span data-ttu-id="6c8d2-113">驗證並視需要卸載已安裝在目的電腦上的舊版應用程式虛擬化管理伺服器。</span><span class="sxs-lookup"><span data-stu-id="6c8d2-113">Verify and, if necessary, uninstall previous versions of the Application Virtualization Management Server that are installed on the target computer.</span></span>

2.  <span data-ttu-id="6c8d2-114">若要開啟**Microsoft Application Virtualization 管理伺服器安裝**嚮導，請流覽至網路上應用程式虛擬化系統**setup.exe**程式的位置，或者從網路執行此程式，或將其目錄複寫到目的電腦，然後按兩下**Setup.exe**檔案。</span><span class="sxs-lookup"><span data-stu-id="6c8d2-114">To open the **Microsoft Application Virtualization Management Server installation** wizard, navigate to the location of the Application Virtualization System **setup.exe** program on the network, either run this program from the network or copy its directory to the target computer, and then double-click the **Setup.exe** file.</span></span>

3.  <span data-ttu-id="6c8d2-115">在 [**歡迎**] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="6c8d2-115">On the **Welcome** page, click **Next**.</span></span>

4.  <span data-ttu-id="6c8d2-116">在 [**授權協定**] 頁面上，閱讀 [授權協定]，然後選取 [接受授權合約]，選取 **[我接受授權條款及條件**]。</span><span class="sxs-lookup"><span data-stu-id="6c8d2-116">On the **License Agreement** page, read the license agreement and, to accept the license agreement, select **I accept the license terms and conditions**.</span></span> <span data-ttu-id="6c8d2-117">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="6c8d2-117">Click **Next**.</span></span>

5.  <span data-ttu-id="6c8d2-118">在 [**註冊資訊**] 頁面上，您必須輸入使用者名稱和**組織**。</span><span class="sxs-lookup"><span data-stu-id="6c8d2-118">On the **Registering Information** page, you must enter the user name and the **Organization**.</span></span> <span data-ttu-id="6c8d2-119">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="6c8d2-119">Click **Next**.</span></span>

6.  <span data-ttu-id="6c8d2-120">在 [**安裝類型**] 頁面上，選取 [**自訂**]。</span><span class="sxs-lookup"><span data-stu-id="6c8d2-120">On the **Setup Type** page, select **Custom**.</span></span> <span data-ttu-id="6c8d2-121">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="6c8d2-121">Click **Next**.</span></span> <span data-ttu-id="6c8d2-122">在 [**自訂安裝**] 頁面上，取消選取 [除了**應用程式虛擬化伺服器**以外的所有應用程式虛擬化系統元件]，然後按一下 **[**</span><span class="sxs-lookup"><span data-stu-id="6c8d2-122">On the **Custom Setup** page, deselect all Application Virtualization System components except **Application Virtualization Server**, and then click **Next**.</span></span>

    **<span data-ttu-id="6c8d2-123">警告</span><span class="sxs-lookup"><span data-stu-id="6c8d2-123">Caution</span></span>**  
    <span data-ttu-id="6c8d2-124">如果電腦上已安裝元件，當您在 [**自訂設定**] 視窗中取消選取該元件時，系統會自動卸載該元件。</span><span class="sxs-lookup"><span data-stu-id="6c8d2-124">If a component is already installed on the computer, when you deselect it in the **Custom Setup** window, the component is automatically uninstalled.</span></span>



7.  <span data-ttu-id="6c8d2-125">在 [設定**資料庫**] 頁面上，從可用伺服器清單中選取資料庫伺服器，或選取 [**使用下列主機名稱**] 並指定**伺服器名稱**和**埠號碼**資料來新增伺服器。</span><span class="sxs-lookup"><span data-stu-id="6c8d2-125">On the **Configuration Database** page, select a database server from the list of available servers or add a server by selecting **Use the following host name** and specifying the **Server Name** and **Port Number** data.</span></span> <span data-ttu-id="6c8d2-126">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="6c8d2-126">Click **Next**.</span></span>

    **<span data-ttu-id="6c8d2-127">注意</span><span class="sxs-lookup"><span data-stu-id="6c8d2-127">Note</span></span>**  
    <span data-ttu-id="6c8d2-128">應用程式虛擬化管理伺服器不支援區分大小寫的 SQL。</span><span class="sxs-lookup"><span data-stu-id="6c8d2-128">The Application Virtualization Management Server does not support case sensitive SQL.</span></span>



~~~
If a database is available, click the radio button, select the database from the list, and then click **Next**. Setup will upgrade it to this newer version. If the name does not appear in the list, enter the name in the space provided.

**Note**  
When naming a server, do not use the backslash character (/) in the server name.

If you need to install a database, see [How to Install a Database](how-to-install-a-database.md). If you would like to create a new database for this version, select **Create a new database** and specify the name that will be assigned to the new database. You can also specify a new location for the database by selecting the check box and entering the path.
~~~



8. <span data-ttu-id="6c8d2-129">在 [連線**安全模式]** 頁面上，從下拉式清單中選取所要的憑證。</span><span class="sxs-lookup"><span data-stu-id="6c8d2-129">On the **Connection Security Mode** page, select the desired certificate from the drop-down list.</span></span> <span data-ttu-id="6c8d2-130">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="6c8d2-130">Click **Next**.</span></span>

   **<span data-ttu-id="6c8d2-131">注意</span><span class="sxs-lookup"><span data-stu-id="6c8d2-131">Note</span></span>**  
   <span data-ttu-id="6c8d2-132">[**安全連線模式]** 設定需要伺服器從公開金鑰基礎結構將伺服器憑證提供給它。</span><span class="sxs-lookup"><span data-stu-id="6c8d2-132">The **Secure Connection Mode** setting requires the server to have a server certificate provisioned to it from a public key infrastructure.</span></span> <span data-ttu-id="6c8d2-133">如果伺服器上沒有安裝伺服器憑證，則此選項無法使用且無法選取。</span><span class="sxs-lookup"><span data-stu-id="6c8d2-133">If a server certificate is not installed on the server, this option is unavailable and cannot be selected.</span></span> <span data-ttu-id="6c8d2-134">您必須授與網路服務帳戶對正在使用之憑證的讀取存取權。</span><span class="sxs-lookup"><span data-stu-id="6c8d2-134">You must grant the Network Service account read access to the certificate being used.</span></span>



9. <span data-ttu-id="6c8d2-135">在 [ **TCP 埠**設定] 頁面上，若要使用預設埠（554），請選取 [**使用預設埠（554）**]。</span><span class="sxs-lookup"><span data-stu-id="6c8d2-135">On the **TCP Port Configuration** page, to use the default port (554), select **Use default port (554)**.</span></span> <span data-ttu-id="6c8d2-136">若要指定自訂埠，請選取 [**使用自訂埠**]，然後指定將使用的埠號碼。</span><span class="sxs-lookup"><span data-stu-id="6c8d2-136">To specify a custom port, select **Use custom port** and specify the port number that will be used.</span></span> <span data-ttu-id="6c8d2-137">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="6c8d2-137">Click **Next**.</span></span>

   **<span data-ttu-id="6c8d2-138">注意</span><span class="sxs-lookup"><span data-stu-id="6c8d2-138">Note</span></span>**  
   <span data-ttu-id="6c8d2-139">當您在非安全的環境中安裝伺服器時，您可以使用預設埠（554），或者您可以定義自訂埠。</span><span class="sxs-lookup"><span data-stu-id="6c8d2-139">When you install the server in a nonsecure environment, you can use the default port (554) or you can define a custom port.</span></span>



10. <span data-ttu-id="6c8d2-140">在 [**管理員群組**] 頁面上，指定在 [**組名**] 中授權管理此伺服器的安全性群組名稱。</span><span class="sxs-lookup"><span data-stu-id="6c8d2-140">On the **Administrator Group** page, specify the name of the security group authorized to manage this server in **Group Name**.</span></span> <span data-ttu-id="6c8d2-141">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="6c8d2-141">Click **Next**.</span></span> <span data-ttu-id="6c8d2-142">確認指定的群組，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="6c8d2-142">Confirm the group specified and click **Next**.</span></span>

11. <span data-ttu-id="6c8d2-143">在 [**預設提供者群組**] 頁面上，指定預設提供者群組的名稱，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="6c8d2-143">On the **Default Provider Group** page, specify the name of the default provider group, and then click **Next**.</span></span>

12. <span data-ttu-id="6c8d2-144">在 [**內容路徑**] 頁面上，指定要儲存 SFT 檔案之目的電腦上的位置，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="6c8d2-144">On the **Content Path** page, specify the location on the target computer where SFT files will be saved, and then click **Next**.</span></span>

   **<span data-ttu-id="6c8d2-145">注意</span><span class="sxs-lookup"><span data-stu-id="6c8d2-145">Note</span></span>**  
   <span data-ttu-id="6c8d2-146">如果管理伺服器的 HTTP 或 RTSP 埠已被指派，系統會提示您選擇新的埠。</span><span class="sxs-lookup"><span data-stu-id="6c8d2-146">If the HTTP or RTSP port for the Management Server is already allocated, you will be prompted to choose a new port.</span></span> <span data-ttu-id="6c8d2-147">選取想要的埠，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="6c8d2-147">Select the desired port, and then click **Next**.</span></span>



13. <span data-ttu-id="6c8d2-148">在 [**準備好安裝程式**] 頁面上，若要安裝應用程式虛擬化管理伺服器，請按一下 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="6c8d2-148">On the **Ready to Install the Program** page, to install the Application Virtualization Management Server, click **Install**.</span></span>

   **<span data-ttu-id="6c8d2-149">注意</span><span class="sxs-lookup"><span data-stu-id="6c8d2-149">Note</span></span>**  
   <span data-ttu-id="6c8d2-150">如果您在嘗試完成此步驟時顯示錯誤25120，您必須啟用 IIS**管理腳本和工具**。</span><span class="sxs-lookup"><span data-stu-id="6c8d2-150">If error 25120 is displayed when you try to complete this step, you need to enable IIS **Management Scripts and Tools**.</span></span> <span data-ttu-id="6c8d2-151">若要啟用此 Windows 功能，請開啟 [**程式和功能**] 控制台，選取 [**開啟或關閉 Windows 功能**]，然後流覽至 [**網際網路資訊服務]。**</span><span class="sxs-lookup"><span data-stu-id="6c8d2-151">To enable this Windows feature, open the **Programs and Features** control panel, select **Turn Windows features on or off**, and navigate to **Internet Information Services.**</span></span>

   <span data-ttu-id="6c8d2-152">在 [ **Web 管理工具**] 底下，啟用 [ **IIS 管理腳本與工具**]。</span><span class="sxs-lookup"><span data-stu-id="6c8d2-152">Under **Web Management Tools**, enable **IIS Management Scripts and Tools**.</span></span>



14. <span data-ttu-id="6c8d2-153">在 [**安裝精靈完成]** 畫面上，若要關閉嚮導，請按一下 **[完成**]。</span><span class="sxs-lookup"><span data-stu-id="6c8d2-153">On the **Installation Wizard Completed** screen, to close the wizard, click **Finish**.</span></span>

   **<span data-ttu-id="6c8d2-154">重要</span><span class="sxs-lookup"><span data-stu-id="6c8d2-154">Important</span></span>**  
   <span data-ttu-id="6c8d2-155">安裝可能需要幾分鐘的時間才能完成。</span><span class="sxs-lookup"><span data-stu-id="6c8d2-155">The installation can take a few minutes to finish.</span></span> <span data-ttu-id="6c8d2-156">狀態訊息會在 Windows 桌面通知區域上方閃爍，指出安裝已成功完成。</span><span class="sxs-lookup"><span data-stu-id="6c8d2-156">A status message will flash above the Windows desktop notification area, indicating that the installation succeeded.</span></span>

   <span data-ttu-id="6c8d2-157">出現提示時，不需要重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="6c8d2-157">It is not necessary to reboot the computer when prompted.</span></span> <span data-ttu-id="6c8d2-158">不過，若要優化系統效能，建議您重新開機。</span><span class="sxs-lookup"><span data-stu-id="6c8d2-158">However, to optimize system performance, a reboot is recommended.</span></span>



## <span data-ttu-id="6c8d2-159">相關主題</span><span class="sxs-lookup"><span data-stu-id="6c8d2-159">Related topics</span></span>


[<span data-ttu-id="6c8d2-160">如何安裝伺服器和系統元件</span><span class="sxs-lookup"><span data-stu-id="6c8d2-160">How to Install the Servers and System Components</span></span>](how-to-install-the-servers-and-system-components.md)









