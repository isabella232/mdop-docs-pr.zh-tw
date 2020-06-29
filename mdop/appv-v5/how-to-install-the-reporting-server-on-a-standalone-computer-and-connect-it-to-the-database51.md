---
title: 如何在獨立電腦上安裝 Reporting Server 並將它連線到資料庫
description: 如何在獨立電腦上安裝 Reporting Server 並將它連線到資料庫
author: dansimp
ms.assetid: 11f07750-4045-4c8d-a583-7d70c9e9aa7b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 67866714ff6ae60097d9b368fd0eaf361b08eec6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800477"
---
# <span data-ttu-id="82d65-103">如何在獨立電腦上安裝 Reporting Server 並將它連線到資料庫</span><span class="sxs-lookup"><span data-stu-id="82d65-103">How to install the Reporting Server on a Standalone Computer and Connect it to the Database</span></span>

<span data-ttu-id="82d65-104">使用下列程式在獨立電腦上安裝報表伺服器，並將它連線至資料庫。</span><span class="sxs-lookup"><span data-stu-id="82d65-104">Use the following procedure to install the reporting server on a standalone computer and connect it to the database.</span></span>

<span data-ttu-id="82d65-105">**重要**在執行下列程式之前，您應該閱讀並瞭解[app-v 5.1 報告](about-app-v-51-reporting.md)。</span><span class="sxs-lookup"><span data-stu-id="82d65-105">**Important** Before performing the following procedure you should read and understand [About App-V 5.1 Reporting](about-app-v-51-reporting.md).</span></span>

## <span data-ttu-id="82d65-106">在獨立電腦上安裝報表伺服器並將它連線至資料庫</span><span class="sxs-lookup"><span data-stu-id="82d65-106">To install the reporting server on a standalone computer and connect it to the database</span></span>

1. <span data-ttu-id="82d65-107">將 App-v 5.1 server 安裝檔案複製到您要安裝它的電腦上。</span><span class="sxs-lookup"><span data-stu-id="82d65-107">Copy the App-V 5.1 server installation files to the computer on which you want to install it on.</span></span> <span data-ttu-id="82d65-108">若要啟動 App-v 5.1 伺服器安裝，請以滑鼠右鍵按一下，然後以系統管理員身分執行**appv\_server\_setup.exe** 。</span><span class="sxs-lookup"><span data-stu-id="82d65-108">To start the App-V 5.1 server installation right-click and run **appv\_server\_setup.exe** as an administrator.</span></span> <span data-ttu-id="82d65-109">按一下 **\[安裝\]**。</span><span class="sxs-lookup"><span data-stu-id="82d65-109">Click **Install**.</span></span>

2. <span data-ttu-id="82d65-110">在 [**快速入門**] 頁面上，查看並接受授權條款，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="82d65-110">On the **Getting Started** page, review and accept the license terms, and click **Next**.</span></span>

3. <span data-ttu-id="82d65-111">在 [**使用 Microsoft update]，協助保護您的電腦安全性且最新的**頁面，若要啟用 Microsoft 更新，請選取 **[在我檢查更新時使用 microsoft Update （建議）]。**</span><span class="sxs-lookup"><span data-stu-id="82d65-111">On the **Use Microsoft Update to help keep your computer secure and up-to-date** page, to enable Microsoft updates, select **Use Microsoft Update when I check for updates (recommended).**</span></span> <span data-ttu-id="82d65-112">若要停用 Microsoft 更新，請選取 [**我不想使用 Microsoft Update**]。</span><span class="sxs-lookup"><span data-stu-id="82d65-112">To disable Microsoft updates, select **I don't want to use Microsoft Update**.</span></span> <span data-ttu-id="82d65-113">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="82d65-113">Click **Next**.</span></span>

4. <span data-ttu-id="82d65-114">在**功能選取**頁面上，選取 [**報表伺服器**] 核取方塊，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="82d65-114">On the **Feature Selection** page, select the **Reporting Server** checkbox and click **Next**.</span></span>

5. <span data-ttu-id="82d65-115">在 [**安裝位置**] 頁面上，接受預設位置，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="82d65-115">On the **Installation Location** page, accept the default location and click **Next**.</span></span>

6. <span data-ttu-id="82d65-116">在 [**設定現有的報表資料庫**] 頁面上，選取 [**使用遠端 SQL server**]，然後輸入執行 Microsoft SQL server 之電腦的電腦名稱稱，例如**SqlServerMachine**。</span><span class="sxs-lookup"><span data-stu-id="82d65-116">On the **Configure Existing Reporting Database** page, select **Use a remote SQL Server**, and type the machine name of the computer running Microsoft SQL Server, for example **SqlServerMachine**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="82d65-117">如果 Microsoft SQL Server 部署在同一台伺服器上，請選取 [**使用本機 SQL server**]。</span><span class="sxs-lookup"><span data-stu-id="82d65-117">If the Microsoft SQL Server is deployed on the same server, select **Use local SQL Server**.</span></span>

    <span data-ttu-id="82d65-118">針對 SQL Server 實例，請選取 [**使用預設實例**]。</span><span class="sxs-lookup"><span data-stu-id="82d65-118">For the SQL Server Instance, select **Use the default instance**.</span></span> <span data-ttu-id="82d65-119">如果您使用的是自訂的 Microsoft SQL Server 實例，您必須選取 [**使用自訂實例**]，然後輸入實例的名稱。</span><span class="sxs-lookup"><span data-stu-id="82d65-119">If you are using a custom Microsoft SQL Server instance, you must select **Use a custom instance** and then type the name of the instance.</span></span>

    <span data-ttu-id="82d65-120">指定此報表服務器將使用的**SQL Server 資料庫名稱**，例如**AppvReporting**。</span><span class="sxs-lookup"><span data-stu-id="82d65-120">Specify the **SQL Server Database name** that this reporting server will use, for example **AppvReporting**.</span></span>

7. <span data-ttu-id="82d65-121">在 [**設定報表伺服器設定**] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="82d65-121">On the **Configure Reporting Server Configuration** page.</span></span>

   - <span data-ttu-id="82d65-122">指定您要用於報表服務的網站名稱。</span><span class="sxs-lookup"><span data-stu-id="82d65-122">Specify the Website Name that you want to use for the Reporting Service.</span></span> <span data-ttu-id="82d65-123">如果您沒有自訂名稱，請將預設值保持不變。</span><span class="sxs-lookup"><span data-stu-id="82d65-123">Leave the default unchanged if you do not have a custom name.</span></span>

   - <span data-ttu-id="82d65-124">針對**埠**系結，請指定將由 app-v 5.1 使用的唯一端口號碼（例如**55555**）。</span><span class="sxs-lookup"><span data-stu-id="82d65-124">For the **Port binding**, specify a unique port number that will be used by App-V 5.1, for example **55555**.</span></span> <span data-ttu-id="82d65-125">您也應該確保指定的埠未由其他網站使用。</span><span class="sxs-lookup"><span data-stu-id="82d65-125">You should also ensure that the port specified is not being used by another website.</span></span>

8. <span data-ttu-id="82d65-126">按一下 **\[安裝\]**。</span><span class="sxs-lookup"><span data-stu-id="82d65-126">Click **Install**.</span></span>

**<span data-ttu-id="82d65-127">有應用程式-V 問題嗎？</span><span class="sxs-lookup"><span data-stu-id="82d65-127">Got an App-V issue?</span></span>** <span data-ttu-id="82d65-128">使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="82d65-128">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="82d65-129">相關主題</span><span class="sxs-lookup"><span data-stu-id="82d65-129">Related topics</span></span>

[<span data-ttu-id="82d65-130">關於 App-V 5.1 報表</span><span class="sxs-lookup"><span data-stu-id="82d65-130">About App-V 5.1 Reporting</span></span>](about-app-v-51-reporting.md)

[<span data-ttu-id="82d65-131">部署 App-V 5.1</span><span class="sxs-lookup"><span data-stu-id="82d65-131">Deploying App-V 5.1</span></span>](deploying-app-v-51.md)

[<span data-ttu-id="82d65-132">如何使用 PowerShell 在 App-V 5.1 用戶端上啟用報表</span><span class="sxs-lookup"><span data-stu-id="82d65-132">How to Enable Reporting on the App-V 5.1 Client by Using PowerShell</span></span>](how-to-enable-reporting-on-the-app-v-51-client-by-using-powershell.md)
