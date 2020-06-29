---
title: 如何安裝 Management Web Service
description: 如何安裝 Management Web Service
author: dansimp
ms.assetid: cac296f5-8ca0-4ce7-afdb-859ae207d2f1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4b8cc1b4821cb4041d75003cf7e6ff592e1c5039
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801353"
---
# <span data-ttu-id="a3de7-103">如何安裝 Management Web Service</span><span class="sxs-lookup"><span data-stu-id="a3de7-103">How to Install the Management Web Service</span></span>


<span data-ttu-id="a3de7-104">使用下列程式，在網路上的目的電腦上安裝應用程式虛擬化管理 Web 服務，並使用具有本機系統管理許可權的登入帳戶。</span><span class="sxs-lookup"><span data-stu-id="a3de7-104">Use the following procedure to install the Application Virtualization Management Web Service on a target computer on the network, with a logon account having local administrative privileges.</span></span> <span data-ttu-id="a3de7-105">我們建議您在 Web 服務器上安裝此元件，但這不是必要的。</span><span class="sxs-lookup"><span data-stu-id="a3de7-105">Although it is not required, we recommended that you install this component on your Web server.</span></span>

**<span data-ttu-id="a3de7-106">若要安裝管理 Web 服務</span><span class="sxs-lookup"><span data-stu-id="a3de7-106">To install the Management Web Service</span></span>**

1.  <span data-ttu-id="a3de7-107">確認您的目的電腦上沒有安裝舊版的 Application Virtualization Web 服務。</span><span class="sxs-lookup"><span data-stu-id="a3de7-107">Verify that no previous versions of the Application Virtualization Web Service are installed on your target computer.</span></span>

2.  <span data-ttu-id="a3de7-108">流覽至 [應用程式虛擬化系統] 設定程式在網路上的位置，請從網路執行此程式，或將其目錄複寫到目的電腦，然後按兩下 [ **Setup.exe**]。</span><span class="sxs-lookup"><span data-stu-id="a3de7-108">Navigate to the location of the Application Virtualization System setup program on the network, either run this program from the network or copy its directory to the target computer, and then double-click **Setup.exe**.</span></span>

3.  <span data-ttu-id="a3de7-109">安裝精靈開啟後，請在 [**歡迎**] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="a3de7-109">After the Installation Wizard opens, on the **Welcome** page, click **Next**.</span></span>

4.  <span data-ttu-id="a3de7-110">若要接受授權協定，請在 [**授權協定**] 頁面上，選取 [**我接受授權條款及條件**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="a3de7-110">On the **License Agreement** page, to accept the license agreement, select **I accept the license terms and conditions**, and then click **Next**.</span></span>

5.  <span data-ttu-id="a3de7-111">在 [**註冊資訊**] 頁面上，指定**使用者名稱**和組織資訊，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="a3de7-111">On the **Registration Information** page, specify the **User Name** and organization information, and then click **Next**.</span></span>

6.  <span data-ttu-id="a3de7-112">在 [**安裝類型**] 頁面上，按一下 [**自訂**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="a3de7-112">On the **Setup Type** page, click **Custom**, and then click **Next**.</span></span>

    <span data-ttu-id="a3de7-113">**記事** 如果這不是您在電腦上安裝的第一個元件，就會顯示 [**程式維護**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="a3de7-113">**Note** If this is not the first component you installed on this computer, the **Program Maintenance** page is displayed.</span></span> <span data-ttu-id="a3de7-114">在 [**程式維護**] 頁面上，按一下 [**修改**]。</span><span class="sxs-lookup"><span data-stu-id="a3de7-114">On the **Program Maintenance** page, click **Modify**.</span></span>

     

7.  <span data-ttu-id="a3de7-115">在 [**自訂設定**] 頁面上，清除 [應用程式**Virt 管理服務**] 以外的所有 Application Virtualization System 元件，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="a3de7-115">On the **Custom Setup** page, clear all Application Virtualization System components except **App Virt Management Service**, and then click **Next**.</span></span>

    <span data-ttu-id="a3de7-116">**記事** 如果電腦上已安裝元件，請在 [**自訂設定**] 頁面上清除該元件，即可自動將它卸載。</span><span class="sxs-lookup"><span data-stu-id="a3de7-116">**Note** If a component is already installed on the computer, by clearing it on the **Custom Setup** page, you will automatically uninstall it.</span></span>

     

8.  <span data-ttu-id="a3de7-117">在 [**資料庫伺服器**] 頁面上，按一下 **[連線至可用資料庫]**，然後按一下 **[下一步**]。</span><span class="sxs-lookup"><span data-stu-id="a3de7-117">On the **Database Server** page, click **Connect to available database**, and then click **Next**.</span></span>

    <span data-ttu-id="a3de7-118">**記事** 在生產環境中，Microsoft 假設您要連接至現有的資料庫。</span><span class="sxs-lookup"><span data-stu-id="a3de7-118">**Note** In a production environment, Microsoft assumes that you will connect to an existing database.</span></span> <span data-ttu-id="a3de7-119">如果您想要安裝資料庫，請參閱[如何安裝資料庫](how-to-install-a-database.md)。</span><span class="sxs-lookup"><span data-stu-id="a3de7-119">If you want to install a database, see [How to Install a Database](how-to-install-a-database.md).</span></span> <span data-ttu-id="a3de7-120">安裝資料庫之後，請繼續執行步驟13。</span><span class="sxs-lookup"><span data-stu-id="a3de7-120">After installing the database, continue with step 13.</span></span>

     

9.  <span data-ttu-id="a3de7-121">在 [**資料庫伺服器類型**] 頁面上，從清單中選取資料庫類型，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="a3de7-121">On the **Database Server Type** page, select a database type from the list, and then click **Next**.</span></span>

10. <span data-ttu-id="a3de7-122">在 [**資料庫伺服器位置**] 頁面上，從可用伺服器清單中選取資料庫伺服器，或選取 [**使用下列主機名稱**] 核取方塊，然後在 [**伺服器名稱**] 和 [**埠號碼**] 方塊中輸入資訊，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="a3de7-122">On the **Database Server Location** page, select a database server from the list of available servers or add a server by selecting the **Use the following host name** check box and entering information in the **Server Name** and **Port Number** boxes, and then click **Next**.</span></span>

11. <span data-ttu-id="a3de7-123">在 [**選取資料庫**] 頁面上，選取您要的資料庫，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="a3de7-123">On the **Select Database** page, select the database you want, and then click **Next**.</span></span>

12. <span data-ttu-id="a3de7-124">在 [**資料庫使用者**設定] 頁面上，輸入管理 Web 服務將用來存取資料存儲區的認證，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="a3de7-124">On the **Database User Configuration** page, enter the credentials that the Management Web Service will use to access the data store, and then click **Next**.</span></span>

13. <span data-ttu-id="a3de7-125">在 [**準備修改程式**] 頁面上，按一下 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="a3de7-125">On the **Ready to Modify the Program** page, click **Install**.</span></span>

    <span data-ttu-id="a3de7-126">**記事** 如果這是您安裝的第一個元件，就會顯示 [已**準備好安裝程式**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="a3de7-126">**Note** If this is the first component you install, the **Ready to Install the Program** page is displayed.</span></span> <span data-ttu-id="a3de7-127">在頁面上，按一下 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="a3de7-127">On the page, click **Install**.</span></span>

     

14. <span data-ttu-id="a3de7-128">在 [**安裝精靈已完成]** 頁面上，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="a3de7-128">On the **Installation Wizard Completed** page, click **Finish**.</span></span>

## <span data-ttu-id="a3de7-129">相關主題</span><span class="sxs-lookup"><span data-stu-id="a3de7-129">Related topics</span></span>


[<span data-ttu-id="a3de7-130">如何安裝伺服器和系統元件</span><span class="sxs-lookup"><span data-stu-id="a3de7-130">How to Install the Servers and System Components</span></span>](how-to-install-the-servers-and-system-components.md)

 

 





