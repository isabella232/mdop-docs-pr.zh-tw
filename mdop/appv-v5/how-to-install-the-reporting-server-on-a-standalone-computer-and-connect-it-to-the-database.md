---
title: 如何在獨立電腦上安裝 Reporting Server 並將它連線到資料庫
description: 如何在獨立電腦上安裝 Reporting Server 並將它連線到資料庫
author: dansimp
ms.assetid: d186bdb7-e522-4124-bc6d-7d5a41ba8266
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f20f1ce16c3f0168d1c797efd816d4125c0f1f53
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800480"
---
# <span data-ttu-id="89738-103">如何在獨立電腦上安裝 Reporting Server 並將它連線到資料庫</span><span class="sxs-lookup"><span data-stu-id="89738-103">How to install the Reporting Server on a Standalone Computer and Connect it to the Database</span></span>


<span data-ttu-id="89738-104">使用下列程式在獨立電腦上安裝報表伺服器，並將它連線至資料庫。</span><span class="sxs-lookup"><span data-stu-id="89738-104">Use the following procedure to install the reporting server on a standalone computer and connect it to the database.</span></span>

**<span data-ttu-id="89738-105">重要</span><span class="sxs-lookup"><span data-stu-id="89738-105">Important</span></span>**  
<span data-ttu-id="89738-106">在執行下列程式之前，您應該閱讀並瞭解[app-v 5.0 報告](about-app-v-50-reporting.md)。</span><span class="sxs-lookup"><span data-stu-id="89738-106">Before performing the following procedure you should read and understand [About App-V 5.0 Reporting](about-app-v-50-reporting.md).</span></span>



**<span data-ttu-id="89738-107">在獨立電腦上安裝報表伺服器並將它連線至資料庫</span><span class="sxs-lookup"><span data-stu-id="89738-107">To install the reporting server on a standalone computer and connect it to the database</span></span>**

1.  <span data-ttu-id="89738-108">將 App-v 5.0 server 安裝檔案複製到您要安裝它的電腦上。</span><span class="sxs-lookup"><span data-stu-id="89738-108">Copy the App-V 5.0 server installation files to the computer on which you want to install it on.</span></span> <span data-ttu-id="89738-109">若要啟動 App-v 5.0 伺服器安裝，請以滑鼠右鍵按一下，然後以系統管理員身分執行**appv\_server\_setup.exe** 。</span><span class="sxs-lookup"><span data-stu-id="89738-109">To start the App-V 5.0 server installation right-click and run **appv\_server\_setup.exe** as an administrator.</span></span> <span data-ttu-id="89738-110">按一下 **\[安裝\]**。</span><span class="sxs-lookup"><span data-stu-id="89738-110">Click **Install**.</span></span>

2.  <span data-ttu-id="89738-111">在 [**快速入門**] 頁面上，查看並接受授權條款，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="89738-111">On the **Getting Started** page, review and accept the license terms, and click **Next**.</span></span>

3.  <span data-ttu-id="89738-112">在 [**使用 Microsoft update]，協助保護您的電腦安全性且最新的**頁面，若要啟用 Microsoft 更新，請選取 **[在我檢查更新時使用 microsoft Update （建議）]。**</span><span class="sxs-lookup"><span data-stu-id="89738-112">On the **Use Microsoft Update to help keep your computer secure and up-to-date** page, to enable Microsoft updates, select **Use Microsoft Update when I check for updates (recommended).**</span></span> <span data-ttu-id="89738-113">若要停用 Microsoft 更新，請選取 [**我不想使用 Microsoft Update**]。</span><span class="sxs-lookup"><span data-stu-id="89738-113">To disable Microsoft updates, select **I don’t want to use Microsoft Update**.</span></span> <span data-ttu-id="89738-114">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="89738-114">Click **Next**.</span></span>

4.  <span data-ttu-id="89738-115">在**功能選取**頁面上，選取 [**報表伺服器**] 核取方塊，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="89738-115">On the **Feature Selection** page, select the **Reporting Server** checkbox and click **Next**.</span></span>

5.  <span data-ttu-id="89738-116">在 [**安裝位置**] 頁面上，接受預設位置，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="89738-116">On the **Installation Location** page, accept the default location and click **Next**.</span></span>

6.  <span data-ttu-id="89738-117">在 [**設定現有的報表資料庫**] 頁面上，選取 [**使用遠端 SQL server**]，然後輸入執行 Microsoft SQL server 之電腦的電腦名稱稱，例如**SqlServerMachine**。</span><span class="sxs-lookup"><span data-stu-id="89738-117">On the **Configure Existing Reporting Database** page, select **Use a remote SQL Server**, and type the machine name of the computer running Microsoft SQL Server, for example **SqlServerMachine**.</span></span>

    **<span data-ttu-id="89738-118">注意</span><span class="sxs-lookup"><span data-stu-id="89738-118">Note</span></span>**  
    <span data-ttu-id="89738-119">如果 Microsoft SQL Server 部署在同一台伺服器上，請選取 [**使用本機 SQL server**]。</span><span class="sxs-lookup"><span data-stu-id="89738-119">If the Microsoft SQL Server is deployed on the same server, select **Use local SQL Server**.</span></span>



~~~
For the SQL Server Instance, select **Use the default instance**. If you are using a custom Microsoft SQL Server instance, you must select **Use a custom instance** and then type the name of the instance.

Specify the **SQL Server Database name** that this reporting server will use, for example **AppvReporting**.
~~~

7. <span data-ttu-id="89738-120">在 [**設定報表伺服器設定**] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="89738-120">On the **Configure Reporting Server Configuration** page.</span></span>

   -   <span data-ttu-id="89738-121">指定您要用於報表服務的網站名稱。</span><span class="sxs-lookup"><span data-stu-id="89738-121">Specify the Website Name that you want to use for the Reporting Service.</span></span> <span data-ttu-id="89738-122">如果您沒有自訂名稱，請將預設值保持不變。</span><span class="sxs-lookup"><span data-stu-id="89738-122">Leave the default unchanged if you do not have a custom name.</span></span>

   -   <span data-ttu-id="89738-123">針對**埠**系結，請指定將由 app-v 5.0 使用的唯一端口號碼（例如**55555**）。</span><span class="sxs-lookup"><span data-stu-id="89738-123">For the **Port binding**, specify a unique port number that will be used by App-V 5.0, for example **55555**.</span></span> <span data-ttu-id="89738-124">您也應該確保指定的埠未由其他網站使用。</span><span class="sxs-lookup"><span data-stu-id="89738-124">You should also ensure that the port specified is not being used by another website.</span></span>

8. <span data-ttu-id="89738-125">按一下 **\[安裝\]**。</span><span class="sxs-lookup"><span data-stu-id="89738-125">Click **Install**.</span></span>

   <span data-ttu-id="89738-126">您**有應用程式-V 的建議**嗎？</span><span class="sxs-lookup"><span data-stu-id="89738-126">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="89738-127">在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="89738-127">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="89738-128">有應用程式-V 問題嗎？</span><span class="sxs-lookup"><span data-stu-id="89738-128">Got an App-V issue?</span></span>** <span data-ttu-id="89738-129">使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="89738-129">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="89738-130">相關主題</span><span class="sxs-lookup"><span data-stu-id="89738-130">Related topics</span></span>


[<span data-ttu-id="89738-131">關於 App-V 5.0 報表</span><span class="sxs-lookup"><span data-stu-id="89738-131">About App-V 5.0 Reporting</span></span>](about-app-v-50-reporting.md)

[<span data-ttu-id="89738-132">部署 App-V 5.0</span><span class="sxs-lookup"><span data-stu-id="89738-132">Deploying App-V 5.0</span></span>](deploying-app-v-50.md)

[<span data-ttu-id="89738-133">如何使用 PowerShell 在 App-V 5.0 用戶端上啟用報表</span><span class="sxs-lookup"><span data-stu-id="89738-133">How to Enable Reporting on the App-V 5.0 Client by Using PowerShell</span></span>](how-to-enable-reporting-on-the-app-v-50-client-by-using-powershell.md)









