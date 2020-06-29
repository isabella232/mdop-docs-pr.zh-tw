---
title: 如何在獨立電腦上安裝 Management Server 並將它連線到資料庫
description: 如何在獨立電腦上安裝 Management Server 並將它連線到資料庫
author: dansimp
ms.assetid: 3f83c335-d976-4abd-b8f8-d7f5e50b4318
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f2cce96f914f65e7432b5ed9e7c5ecb1a6306990
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800487"
---
# <span data-ttu-id="06357-103">如何在獨立電腦上安裝 Management Server 並將它連線到資料庫</span><span class="sxs-lookup"><span data-stu-id="06357-103">How to install the Management Server on a Standalone Computer and Connect it to the Database</span></span>


<span data-ttu-id="06357-104">使用下列程式在獨立電腦上安裝管理伺服器，並將它連線至資料庫。</span><span class="sxs-lookup"><span data-stu-id="06357-104">Use the following procedure to install the management server on a standalone computer and connect it to the database.</span></span>

**<span data-ttu-id="06357-105">在獨立電腦上安裝管理伺服器並將它連線至資料庫</span><span class="sxs-lookup"><span data-stu-id="06357-105">To install the management server on a standalone computer and connect it to the database</span></span>**

1.  <span data-ttu-id="06357-106">將 App-v 5.1 server 安裝檔案複製到您要安裝它的電腦上。</span><span class="sxs-lookup"><span data-stu-id="06357-106">Copy the App-V 5.1 server installation files to the computer on which you want to install it on.</span></span> <span data-ttu-id="06357-107">若要啟動 App-v 5.1 伺服器安裝，請以滑鼠右鍵按一下，然後以系統管理員身分執行**appv\_server\_setup.exe** 。</span><span class="sxs-lookup"><span data-stu-id="06357-107">To start the App-V 5.1 server installation right-click and run **appv\_server\_setup.exe** as an administrator.</span></span> <span data-ttu-id="06357-108">按一下 **\[安裝\]**。</span><span class="sxs-lookup"><span data-stu-id="06357-108">Click **Install**.</span></span>

2.  <span data-ttu-id="06357-109">在 [**快速入門**] 頁面上，查看並接受授權條款，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="06357-109">On the **Getting Started** page, review and accept the license terms, and click **Next**.</span></span>

3.  <span data-ttu-id="06357-110">在 [**使用 Microsoft update]，協助保護您的電腦安全性且最新的**頁面，若要啟用 Microsoft 更新，請選取 **[在我檢查更新時使用 microsoft Update （建議）]。**</span><span class="sxs-lookup"><span data-stu-id="06357-110">On the **Use Microsoft Update to help keep your computer secure and up-to-date** page, to enable Microsoft updates, select **Use Microsoft Update when I check for updates (recommended).**</span></span> <span data-ttu-id="06357-111">若要停用 Microsoft 更新，請選取 [**我不想使用 Microsoft Update**]。</span><span class="sxs-lookup"><span data-stu-id="06357-111">To disable Microsoft updates, select **I don’t want to use Microsoft Update**.</span></span> <span data-ttu-id="06357-112">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="06357-112">Click **Next**.</span></span>

4.  <span data-ttu-id="06357-113">在**功能選取**頁面上，選取 [**管理伺服器**] 核取方塊，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="06357-113">On the **Feature Selection** page, select the **Management Server** checkbox and click **Next**.</span></span>

5.  <span data-ttu-id="06357-114">在 [**安裝位置**] 頁面上，接受預設位置，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="06357-114">On the **Installation Location** page, accept the default location and click **Next**.</span></span>

6.  <span data-ttu-id="06357-115">在 [**設定現有的管理資料庫**] 頁面上，選取 [**使用遠端 SQL Server**]，然後輸入執行 Microsoft sql sql 的電腦的電腦名稱稱（例如**SqlServerMachine**）。</span><span class="sxs-lookup"><span data-stu-id="06357-115">On the **Configure Existing Management Database** page, select **Use a remote SQL Server**, and type the machine name of the computer running Microsoft SQL SQL, for example **SqlServerMachine**.</span></span>

    **<span data-ttu-id="06357-116">注意</span><span class="sxs-lookup"><span data-stu-id="06357-116">Note</span></span>**  
    <span data-ttu-id="06357-117">如果 Microsoft SQL Server 部署在同一台伺服器上，請選取 [**使用本機 SQL server**]。</span><span class="sxs-lookup"><span data-stu-id="06357-117">If the Microsoft SQL Server is deployed on the same server, select **Use local SQL Server**.</span></span>



~~~
For the SQL Server Instance, select **Use the default instance**. If you are using a custom Microsoft SQL Server instance, you must select **Use a custom instance** and then type the name of the instance.

Specify the **SQL Server Database name** that this management server will use, for example **AppvManagement**.
~~~

7. <span data-ttu-id="06357-118">在 [**設定管理伺服器設定**] 頁面上，指定將會連線至管理主控台以進行管理的 AD 群組或帳戶（例如**MyDomain\\MyUser**或**MyDomain\\AdminGroup**）。</span><span class="sxs-lookup"><span data-stu-id="06357-118">On the **Configure Management Server Configuration** page, specify the AD group or account that will connect to the management console for administrative purposes for example **MyDomain\\MyUser** or **MyDomain\\AdminGroup**.</span></span> <span data-ttu-id="06357-119">您指定的帳號或 AD 群組將會透過管理主控台啟用以管理伺服器。</span><span class="sxs-lookup"><span data-stu-id="06357-119">The account or AD group you specify will be enabled to manage the server through the management console.</span></span> <span data-ttu-id="06357-120">您可以在安裝後使用管理主控台新增其他使用者或群組</span><span class="sxs-lookup"><span data-stu-id="06357-120">You can add additional users or groups using the management console after installation</span></span>

   <span data-ttu-id="06357-121">指定您要用於管理服務的**網站名稱**。</span><span class="sxs-lookup"><span data-stu-id="06357-121">Specify the **Website Name** that you want to use for the management service.</span></span> <span data-ttu-id="06357-122">如果您沒有自訂名稱，請接受預設值。</span><span class="sxs-lookup"><span data-stu-id="06357-122">Accept the default if you do not have a custom name.</span></span> <span data-ttu-id="06357-123">針對**埠**系結，請指定要使用的唯一端口號碼（例如**12345**）。</span><span class="sxs-lookup"><span data-stu-id="06357-123">For the **Port Binding**, specify a unique port number to be used, for example **12345**.</span></span>

8. <span data-ttu-id="06357-124">按一下 **\[安裝\]**。</span><span class="sxs-lookup"><span data-stu-id="06357-124">Click **Install**.</span></span>

9. <span data-ttu-id="06357-125">若要確認安裝程式已順利完成，請開啟網頁瀏覽器，然後輸入下列 URL： http://managementserver:portnumber/Console 。</span><span class="sxs-lookup"><span data-stu-id="06357-125">To confirm that the setup has completed successfully, open a web browser, and type the following URL: http://managementserver:portnumber/Console.</span></span> <span data-ttu-id="06357-126">如果安裝成功，您應該會看到 [**管理主控台**] 出現，但不會顯示任何錯誤訊息或警告。</span><span class="sxs-lookup"><span data-stu-id="06357-126">If the installation was successful, you should see the **Management Console** appear without any error messages or warnings being displayed.</span></span>

   <span data-ttu-id="06357-127">您**有應用程式-V 的建議**嗎？</span><span class="sxs-lookup"><span data-stu-id="06357-127">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="06357-128">在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="06357-128">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="06357-129">有應用程式-V 問題嗎？</span><span class="sxs-lookup"><span data-stu-id="06357-129">Got an App-V issue?</span></span>** <span data-ttu-id="06357-130">使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="06357-130">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="06357-131">相關主題</span><span class="sxs-lookup"><span data-stu-id="06357-131">Related topics</span></span>


[<span data-ttu-id="06357-132">部署 App-V 5.1</span><span class="sxs-lookup"><span data-stu-id="06357-132">Deploying App-V 5.1</span></span>](deploying-app-v-51.md)









