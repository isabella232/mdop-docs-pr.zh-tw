---
title: 如何安裝資料庫
description: 如何安裝資料庫
author: dansimp
ms.assetid: 52e3a19d-b7cf-4f2c-8268-0f8361cc9766
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: c5f42673c08744d17e1d2e0ef955ebed2848de18
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801393"
---
# <span data-ttu-id="8b65d-103">如何安裝資料庫</span><span class="sxs-lookup"><span data-stu-id="8b65d-103">How to Install a Database</span></span>


<span data-ttu-id="8b65d-104">如果資料庫尚未提供，您可以使用下列程式來安裝應用程式虛擬化部署的資料庫。</span><span class="sxs-lookup"><span data-stu-id="8b65d-104">You can use the following procedure to install a database for your server-based deployment of Application Virtualization if a database is not already available.</span></span> <span data-ttu-id="8b65d-105">通常，在生產環境中，您會連線至現有的資料庫。</span><span class="sxs-lookup"><span data-stu-id="8b65d-105">Typically, in a production environment, you will connect to an existing database.</span></span>

<span data-ttu-id="8b65d-106">**重要** 若要安裝資料庫，您必須使用具有適當許可權的網路帳戶。</span><span class="sxs-lookup"><span data-stu-id="8b65d-106">**Important** To install the database, you must use a network account with the appropriate permissions.</span></span> <span data-ttu-id="8b65d-107">如果您的組織要求只有資料庫管理員才能建立並執行資料庫升級，就可以使用腳本來執行這項工作。</span><span class="sxs-lookup"><span data-stu-id="8b65d-107">If your organization requires that only database administrators are allowed to create and conduct database upgrades, scripts are available that allow this task to be performed.</span></span>

 

**<span data-ttu-id="8b65d-108">若要安裝資料庫</span><span class="sxs-lookup"><span data-stu-id="8b65d-108">To install a database</span></span>**

1.  <span data-ttu-id="8b65d-109">流覽至 [應用程式虛擬化系統] 設定程式在網路上的位置，請從網路執行此程式，或將其目錄複寫到目的電腦，然後按兩下 [ **Setup.exe**]。</span><span class="sxs-lookup"><span data-stu-id="8b65d-109">Navigate to the location of the Application Virtualization System setup program on the network, either run this program from the network or copy its directory to the target computer, and then double-click **Setup.exe**.</span></span>

2.  <span data-ttu-id="8b65d-110">在 [**歡迎] 頁面**上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8b65d-110">On the **Welcome Page**, click **Next**.</span></span>

3.  <span data-ttu-id="8b65d-111">若要接受授權協定，請在 [**授權協定**] 頁面上，選取 [**我接受授權條款及條件**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8b65d-111">On the **License Agreement** page, to accept the license agreement, select **I accept the license terms and conditions**, and click **Next**.</span></span>

4.  <span data-ttu-id="8b65d-112">在 [**註冊資訊**] 頁面上，指定**使用者名稱**和**組織**資訊，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8b65d-112">On the **Registering Information** page, specify the **User Name** and **Organization** information, and then click **Next**.</span></span>

5.  <span data-ttu-id="8b65d-113">在 [**安裝類型**] 頁面上選取 [**自訂**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8b65d-113">On the **Setup Type** page, select **Custom** and then click **Next**.</span></span>

6.  <span data-ttu-id="8b65d-114">在 [**自訂安裝**] 頁面上，取消選取 [除了**應用程式虛擬化伺服器**以外的所有應用程式虛擬化系統元件]，然後按一下 **[**</span><span class="sxs-lookup"><span data-stu-id="8b65d-114">On the **Custom Setup** page, deselect all Application Virtualization System components except **Application Virtualization Server**, and then click **Next**.</span></span>

    <span data-ttu-id="8b65d-115">**記事** 如果電腦上已安裝元件，請在 [**自訂設定**] 畫面上取消選擇該元件，系統會自動將它卸載。</span><span class="sxs-lookup"><span data-stu-id="8b65d-115">**Note** If a component is already installed on the computer, by deselecting it on the **Custom Setup** screen it will automatically be uninstalled.</span></span>

     

7.  <span data-ttu-id="8b65d-116">在 [**資料庫伺服器**] 頁面上，輸入密碼、指派安裝路徑、儲存資訊，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8b65d-116">On the **Database Server** page, type the passwords, assign an installation path, save the information, and click **Next**.</span></span>

8.  <span data-ttu-id="8b65d-117">選取資料庫的名稱，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8b65d-117">Select a name for the database, and then click **Next**.</span></span>

    <span data-ttu-id="8b65d-118">**記事** 如果在您嘗試完成此步驟時顯示錯誤25109，就是您無法正確設定安裝資料庫所需的許可權。</span><span class="sxs-lookup"><span data-stu-id="8b65d-118">**Note** If error 25109 is displayed when you try to complete this step, you have incorrectly set up the permissions necessary to install the database.</span></span> <span data-ttu-id="8b65d-119">如需有關設定必要 SQL 許可權的詳細資料，請參閱 <https://go.microsoft.com/fwlink/?LinkId=132144> 。</span><span class="sxs-lookup"><span data-stu-id="8b65d-119">For details on setting up the necessary SQL permissions, please see <https://go.microsoft.com/fwlink/?LinkId=132144>.</span></span>

     

9.  <span data-ttu-id="8b65d-120">在 [**目錄伺服器**] 畫面上，輸入應用程式虛擬化伺服器與管理 Web 服務將用來存取您的網網域控制站的功能變數名稱和認證，儲存此資訊，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8b65d-120">On the **Directory Server** screen, enter a domain name and credentials that Application Virtualization Servers and the Management Web Service will use to access your domain controller, save this information, and then click **Next**.</span></span>

    <span data-ttu-id="8b65d-121">**記事** 安裝將預設為目前電腦的網域。</span><span class="sxs-lookup"><span data-stu-id="8b65d-121">**Note** The installation will default to the domain of the current computer.</span></span>

     

10. <span data-ttu-id="8b65d-122">在 [**管理員] 群組**頁面上，輸入將擁有系統管理員許可權的群組名稱，儲存此資訊，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8b65d-122">On the **Administrator Group** page, enter the name of a group that will have Administrator privileges, save this information, and then click **Next**.</span></span>

    <span data-ttu-id="8b65d-123">**記事** 您也可以輸入將擁有管理許可權之群組之名稱的前幾個字元，按一下 **[下一步]**，然後在 [**選取管理員群組**] 畫面上，從產生的清單中選取群組。</span><span class="sxs-lookup"><span data-stu-id="8b65d-123">**Note** You can also enter the first few characters of the name of a group that will have Administration privileges, click **Next**, and on the **Select Administrator Group** screen, select the group from the resulting list.</span></span> <span data-ttu-id="8b65d-124">然後，儲存此資訊，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8b65d-124">Then save this information and click **Next**.</span></span>

     

11. <span data-ttu-id="8b65d-125">在 [**預設提供者群組**] 頁面上，輸入將控制對應用程式存取權的群組的完整名稱，儲存此資訊，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8b65d-125">On the **Default Provider Group** page, enter the complete name of a group that will control access to applications, save this information, and then click **Next**.</span></span>

    <span data-ttu-id="8b65d-126">**記事** 您也可以輸入將會控制應用程式存取權之群組名稱的前幾個字元，請按 **[下一步]**，然後在 [**選取預設提供者群組**] 畫面上，選取清單中的群組。</span><span class="sxs-lookup"><span data-stu-id="8b65d-126">**Note** You can also enter the first few characters of the name of a group that will control access to applications, click **Next**, and on the **Select Default Provider Group** screen, select the group in the list.</span></span> <span data-ttu-id="8b65d-127">然後，儲存此資訊，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8b65d-127">Then save this information and click **Next**.</span></span>

     

12. <span data-ttu-id="8b65d-128">在 [**安裝精靈已完成]** 頁面上，若要關閉嚮導，請按一下 **[完成**]。</span><span class="sxs-lookup"><span data-stu-id="8b65d-128">On the **Installation Wizard Completed** page, to close the wizard, click **Finish**.</span></span>

    <span data-ttu-id="8b65d-129">**重要** 安裝可能需要幾分鐘的時間才能完成。</span><span class="sxs-lookup"><span data-stu-id="8b65d-129">**Important** The installation can take a few minutes to finish.</span></span> <span data-ttu-id="8b65d-130">狀態訊息會在 Windows 桌面通知區域上方閃爍，指出安裝是否已成功完成。</span><span class="sxs-lookup"><span data-stu-id="8b65d-130">A status message will flash above the Windows desktop notification area, indicating whether the installation succeeded.</span></span>

     

## <span data-ttu-id="8b65d-131">相關主題</span><span class="sxs-lookup"><span data-stu-id="8b65d-131">Related topics</span></span>


[<span data-ttu-id="8b65d-132">如何安裝伺服器和系統元件</span><span class="sxs-lookup"><span data-stu-id="8b65d-132">How to Install the Servers and System Components</span></span>](how-to-install-the-servers-and-system-components.md)

 

 





