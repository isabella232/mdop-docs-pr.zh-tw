---
title: 如何在遠端電腦上安裝發佈伺服器
description: 如何在遠端電腦上安裝發佈伺服器
author: dansimp
ms.assetid: 1c903f78-0558-458d-a149-d5f6fb55aefb
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1a085d68305057538228599e35dd9500957342ba
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800479"
---
# <span data-ttu-id="ce4ca-103">如何在遠端電腦上安裝發佈伺服器</span><span class="sxs-lookup"><span data-stu-id="ce4ca-103">How to Install the Publishing Server on a Remote Computer</span></span>


<span data-ttu-id="ce4ca-104">使用下列程式在不同的電腦上安裝發佈伺服器。</span><span class="sxs-lookup"><span data-stu-id="ce4ca-104">Use the following procedure to install the publishing server on a separate computer.</span></span> <span data-ttu-id="ce4ca-105">在執行下列程式之前，請先確定資料庫和管理伺服器可供使用。</span><span class="sxs-lookup"><span data-stu-id="ce4ca-105">Before you perform the following procedure, ensure the database and management server are available.</span></span>

**<span data-ttu-id="ce4ca-106">在不同的電腦上安裝發佈伺服器</span><span class="sxs-lookup"><span data-stu-id="ce4ca-106">To install the publishing server on a separate computer</span></span>**

1. <span data-ttu-id="ce4ca-107">將 App-v 5.1 server 安裝檔案複製到您要安裝它的電腦上。</span><span class="sxs-lookup"><span data-stu-id="ce4ca-107">Copy the App-V 5.1 server installation files to the computer on which you want to install it on.</span></span> <span data-ttu-id="ce4ca-108">若要啟動 App-v 5.1 伺服器安裝，請以滑鼠右鍵按一下，然後以系統管理員身分執行**appv\_server\_setup.exe** 。</span><span class="sxs-lookup"><span data-stu-id="ce4ca-108">To start the App-V 5.1 server installation right-click and run **appv\_server\_setup.exe** as an administrator.</span></span> <span data-ttu-id="ce4ca-109">按一下 **\[安裝\]**。</span><span class="sxs-lookup"><span data-stu-id="ce4ca-109">Click **Install**.</span></span>

2. <span data-ttu-id="ce4ca-110">在 [**快速入門**] 頁面上，查看並接受授權條款，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="ce4ca-110">On the **Getting Started** page, review and accept the license terms, and click **Next**.</span></span>

3. <span data-ttu-id="ce4ca-111">在 [**使用 Microsoft update]，協助保護您的電腦安全性且最新的**頁面，若要啟用 Microsoft 更新，請選取 **[在我檢查更新時使用 microsoft Update （建議）]。**</span><span class="sxs-lookup"><span data-stu-id="ce4ca-111">On the **Use Microsoft Update to help keep your computer secure and up-to-date** page, to enable Microsoft updates, select **Use Microsoft Update when I check for updates (recommended).**</span></span> <span data-ttu-id="ce4ca-112">若要停用 Microsoft 更新，請選取 [**我不想使用 Microsoft Update**]。</span><span class="sxs-lookup"><span data-stu-id="ce4ca-112">To disable Microsoft updates, select **I don’t want to use Microsoft Update**.</span></span> <span data-ttu-id="ce4ca-113">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="ce4ca-113">Click **Next**.</span></span>

4. <span data-ttu-id="ce4ca-114">在**功能選取**頁面上，選取 [**發佈伺服器**] 核取方塊，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="ce4ca-114">On the **Feature Selection** page, select the **Publishing Server** checkbox and click **Next**.</span></span>

5. <span data-ttu-id="ce4ca-115">在 [**安裝位置**] 頁面上，接受預設位置，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="ce4ca-115">On the **Installation Location** page, accept the default location and click **Next**.</span></span>

6. <span data-ttu-id="ce4ca-116">在 [**設定發佈伺服器設定**] 頁面上，指定下列專案：</span><span class="sxs-lookup"><span data-stu-id="ce4ca-116">On the **Configure Publishing Server Configuration** page, specify the following items:</span></span>

   -   <span data-ttu-id="ce4ca-117">發佈伺服器將連接至之管理服務的 URL。</span><span class="sxs-lookup"><span data-stu-id="ce4ca-117">The URL for the management service that the publishing server will connect to.</span></span> <span data-ttu-id="ce4ca-118">例如， **http://ManagementServerName:12345** 。</span><span class="sxs-lookup"><span data-stu-id="ce4ca-118">For example, **http://ManagementServerName:12345**.</span></span>

   -   <span data-ttu-id="ce4ca-119">指定要用於發佈服務的網站名稱。</span><span class="sxs-lookup"><span data-stu-id="ce4ca-119">Specify the website name that you want to use for the publishing service.</span></span> <span data-ttu-id="ce4ca-120">如果您沒有自訂名稱，請接受預設值。</span><span class="sxs-lookup"><span data-stu-id="ce4ca-120">Accept the default if you do not have a custom name.</span></span>

   -   <span data-ttu-id="ce4ca-121">針對**埠**系結，請指定將由 app-v 5.1 使用的唯一端口號碼（例如**54321**）。</span><span class="sxs-lookup"><span data-stu-id="ce4ca-121">For the **Port Binding**, specify a unique port number that will be used by App-V 5.1, for example **54321**.</span></span>

7. <span data-ttu-id="ce4ca-122">在 [**準備安裝**] 頁面上，按一下 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="ce4ca-122">On the **Ready to Install** page, click **Install**.</span></span>

8. <span data-ttu-id="ce4ca-123">安裝完成後，發佈伺服器必須在管理伺服器上註冊。</span><span class="sxs-lookup"><span data-stu-id="ce4ca-123">After the installation is complete, the publishing server must be registered with the management server.</span></span> <span data-ttu-id="ce4ca-124">在 App-V 5.1 管理主控台中，請使用下列步驟來註冊伺服器：</span><span class="sxs-lookup"><span data-stu-id="ce4ca-124">In the App-V 5.1 management console, use the following steps to register the server:</span></span>

   1.  <span data-ttu-id="ce4ca-125">開啟 App-V 5.1 管理伺服器主控台。</span><span class="sxs-lookup"><span data-stu-id="ce4ca-125">Open the App-V 5.1 management server console.</span></span>

   2.  <span data-ttu-id="ce4ca-126">在左窗格中，選取 [**伺服器**]，然後選取 [**註冊新的伺服器**]。</span><span class="sxs-lookup"><span data-stu-id="ce4ca-126">In the left pane, select **Servers**, and then select **Register New Server**.</span></span>

   3.  <span data-ttu-id="ce4ca-127">輸入此伺服器的名稱和描述（如果需要的話），然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="ce4ca-127">Type the name of this server and a description (if required) and click **Add**.</span></span>

9. <span data-ttu-id="ce4ca-128">若要驗證發佈伺服器是否正常運作，您應該將套件匯入管理伺服器、將套件 entitle 到 AD 群組，然後發佈套件。</span><span class="sxs-lookup"><span data-stu-id="ce4ca-128">To verify if the publishing server is running correctly, you should import a package to the management server, entitle the package to an AD group, and publish the package.</span></span> <span data-ttu-id="ce4ca-129">使用網際網路瀏覽器，開啟下列 URL： <strong> http://publishingserver:pubport </strong> 。</span><span class="sxs-lookup"><span data-stu-id="ce4ca-129">Using an internet browser, open the following URL: <strong>http://publishingserver:pubport</strong>.</span></span> <span data-ttu-id="ce4ca-130">如果伺服器執行的是正確的資訊，則會顯示類似以下內容：</span><span class="sxs-lookup"><span data-stu-id="ce4ca-130">If the server is running correctly information similar to the following will be displayed:</span></span>

   ```xml
   <Publishing Protocol="1.0">
     <Packages>
       <Package PackageId="28115343-06e2-44dc-a327-3a0b9b868bda" VersionId="5d03c08f-51dc-4026-8cf9-15ebe3d65a72" PackageUrl="\\server\share\file.appv" />
     </Packages>
     <NoGroup>
       <Package PackageId="28115343-06e2-44dc-a327-3a0b9b868bda" />
     </NoGroup>
   </Publishing>
   ```

   <span data-ttu-id="ce4ca-131">您**有應用程式-V 的建議**嗎？</span><span class="sxs-lookup"><span data-stu-id="ce4ca-131">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="ce4ca-132">在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="ce4ca-132">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="ce4ca-133">有應用程式-V 問題嗎？</span><span class="sxs-lookup"><span data-stu-id="ce4ca-133">Got an App-V issue?</span></span>** <span data-ttu-id="ce4ca-134">使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="ce4ca-134">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="ce4ca-135">相關主題</span><span class="sxs-lookup"><span data-stu-id="ce4ca-135">Related topics</span></span>


[<span data-ttu-id="ce4ca-136">部署 App-V 5.1</span><span class="sxs-lookup"><span data-stu-id="ce4ca-136">Deploying App-V 5.1</span></span>](deploying-app-v-51.md)

 

 





