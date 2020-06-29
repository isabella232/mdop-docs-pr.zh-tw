---
title: 如何在與管理和報告服務不同的電腦上安裝管理和報告資料庫
description: 如何在與管理和報告服務不同的電腦上安裝管理和報告資料庫
author: dansimp
ms.assetid: 02afd6d6-4c33-4c0b-bd88-ae167b786fdf
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1522045fced411164ac4fd36af41d46ab61ad6f9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800490"
---
# <span data-ttu-id="bd41a-103">如何在與管理和報告服務不同的電腦上安裝管理和報告資料庫</span><span class="sxs-lookup"><span data-stu-id="bd41a-103">How to Install the Management and Reporting Databases on Separate Computers from the Management and Reporting Services</span></span>


<span data-ttu-id="bd41a-104">使用下列程式在不同的電腦上安裝資料庫伺服器與管理伺服器。</span><span class="sxs-lookup"><span data-stu-id="bd41a-104">Use the following procedure to install the database server and management server on different computers.</span></span> <span data-ttu-id="bd41a-105">您計畫在其上安裝資料庫伺服器的電腦必須執行 Microsoft SQL 支援的版本，否則安裝將會失敗。</span><span class="sxs-lookup"><span data-stu-id="bd41a-105">The computer you plan to install the database server on must be running a supported version of Microsoft SQL or the installation will fail.</span></span>

**<span data-ttu-id="bd41a-106">注意</span><span class="sxs-lookup"><span data-stu-id="bd41a-106">Note</span></span>**  
<span data-ttu-id="bd41a-107">完成部署之後，系統會要求安裝服務的**MICROSOFT SQL Server 名稱**、**實例名稱**和**資料庫名稱**，才能連線至這些資料庫。</span><span class="sxs-lookup"><span data-stu-id="bd41a-107">After you complete the deployment, the **Microsoft SQL Server name**, **instance name** and **database name** will be required by the administrator installing the service to be able to connect to these databases.</span></span>



**<span data-ttu-id="bd41a-108">在不同的電腦上安裝管理資料庫和管理伺服器</span><span class="sxs-lookup"><span data-stu-id="bd41a-108">To install the management database and the management server on separate computers</span></span>**

1.  <span data-ttu-id="bd41a-109">將 App-v 5.0 server 安裝檔案複製到您要安裝它的電腦上。</span><span class="sxs-lookup"><span data-stu-id="bd41a-109">Copy the App-V 5.0 server installation files to the computer on which you want to install it on.</span></span> <span data-ttu-id="bd41a-110">若要啟動 App-v 5.0 伺服器安裝，請以滑鼠右鍵按一下，然後以系統管理員身分執行**appv\_server\_setup.exe** 。</span><span class="sxs-lookup"><span data-stu-id="bd41a-110">To start the App-V 5.0 server installation right-click and run **appv\_server\_setup.exe** as an administrator.</span></span> <span data-ttu-id="bd41a-111">按一下 **\[安裝\]**。</span><span class="sxs-lookup"><span data-stu-id="bd41a-111">Click **Install**.</span></span>

2.  <span data-ttu-id="bd41a-112">在 [**快速入門**] 頁面上，查看並接受授權條款，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bd41a-112">On the **Getting Started** page, review and accept the license terms, and click **Next**.</span></span>

3.  <span data-ttu-id="bd41a-113">在 [**使用 Microsoft update]，協助保護您的電腦安全性且最新的**頁面，若要啟用 Microsoft 更新，請選取 **[在我檢查更新時使用 microsoft Update （建議）]。**</span><span class="sxs-lookup"><span data-stu-id="bd41a-113">On the **Use Microsoft Update to help keep your computer secure and up-to-date** page, to enable Microsoft updates, select **Use Microsoft Update when I check for updates (recommended).**</span></span> <span data-ttu-id="bd41a-114">若要停用 Microsoft 更新，請選取 [**我不想使用 Microsoft Update**]。</span><span class="sxs-lookup"><span data-stu-id="bd41a-114">To disable Microsoft updates, select **I don’t want to use Microsoft Update**.</span></span> <span data-ttu-id="bd41a-115">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="bd41a-115">Click **Next**.</span></span>

4.  <span data-ttu-id="bd41a-116">在 [**功能選取**] 頁面上，選取您要安裝的元件，方法是選取 [**管理伺服器資料庫**] 核取方塊，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bd41a-116">On the **Feature Selection** page, select the components you want to install by selecting the **Management Server Database** checkbox and click **Next**.</span></span>

5.  <span data-ttu-id="bd41a-117">在 [**安裝位置**] 頁面上，接受預設位置，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bd41a-117">On the **Installation Location** page, accept the default location and click **Next**.</span></span>

6.  <span data-ttu-id="bd41a-118">在 [**建立新的管理伺服器資料庫] 頁面**上，接受預設選項（如果適用的話），然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bd41a-118">On the initial **Create New Management Server Database page**, accept the default selections if appropriate, and click **Next**.</span></span>

    <span data-ttu-id="bd41a-119">如果您使用的是自訂 SQL Server 實例，請選取 [**使用自訂實例**]，然後輸入實例的名稱。</span><span class="sxs-lookup"><span data-stu-id="bd41a-119">If you are using a custom SQL Server instance, then select **Use a custom instance** and type the name of the instance.</span></span>

    <span data-ttu-id="bd41a-120">如果您使用的是自訂資料庫名稱，請選取 [**自訂**設定]，然後輸入資料庫的名稱。</span><span class="sxs-lookup"><span data-stu-id="bd41a-120">If you are using a custom database name, then select **Custom configuration** and type the database name.</span></span>

7.  <span data-ttu-id="bd41a-121">在 [**建立新的管理伺服器資料庫**] 頁面上，選取 [**使用遠端電腦**]，然後使用下列格式輸入遠端電腦帳戶： **Domain\\MachineAccount**。</span><span class="sxs-lookup"><span data-stu-id="bd41a-121">On the next **Create New Management Server Database** page, select **Use a remote computer**, and type the remote machine account using the following format: **Domain\\MachineAccount**.</span></span>

    **<span data-ttu-id="bd41a-122">注意</span><span class="sxs-lookup"><span data-stu-id="bd41a-122">Note</span></span>**  
    <span data-ttu-id="bd41a-123">如果您打算在同一部電腦上部署管理伺服器，您必須選取 [**使用本機電腦**]。</span><span class="sxs-lookup"><span data-stu-id="bd41a-123">If you plan to deploy the management server on the same computer you must select **Use this local computer**.</span></span>



~~~
Specify the user name for the management server **Install Administrator** using the following format: **Domain\\AdministratorLoginName**. Click **Next**.
~~~

8. <span data-ttu-id="bd41a-124">若要開始安裝，請按一下 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="bd41a-124">To start the installation, click **Install**.</span></span>

**<span data-ttu-id="bd41a-125">在不同的電腦上安裝報表資料庫和報表伺服器</span><span class="sxs-lookup"><span data-stu-id="bd41a-125">To install the reporting database and the reporting server on separate computers</span></span>**

1.  <span data-ttu-id="bd41a-126">將 App-v 5.0 server 安裝檔案複製到您要安裝它的電腦上。</span><span class="sxs-lookup"><span data-stu-id="bd41a-126">Copy the App-V 5.0 server installation files to the computer on which you want to install it on.</span></span> <span data-ttu-id="bd41a-127">若要啟動 App-v 5.0 伺服器安裝，請以滑鼠右鍵按一下，然後以系統管理員身分執行**appv\_server\_setup.exe** 。</span><span class="sxs-lookup"><span data-stu-id="bd41a-127">To start the App-V 5.0 server installation right-click and run **appv\_server\_setup.exe** as an administrator.</span></span> <span data-ttu-id="bd41a-128">按一下 **\[安裝\]**。</span><span class="sxs-lookup"><span data-stu-id="bd41a-128">Click **Install**.</span></span>

2.  <span data-ttu-id="bd41a-129">在 [**快速入門**] 頁面上，查看並接受授權條款，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bd41a-129">On the **Getting Started** page, review and accept the license terms, and click **Next**.</span></span>

3.  <span data-ttu-id="bd41a-130">在 [**使用 Microsoft update]，協助保護您的電腦安全性且最新的**頁面，若要啟用 Microsoft 更新，請選取 **[在我檢查更新時使用 microsoft Update （建議）]。**</span><span class="sxs-lookup"><span data-stu-id="bd41a-130">On the **Use Microsoft Update to help keep your computer secure and up-to-date** page, to enable Microsoft updates, select **Use Microsoft Update when I check for updates (recommended).**</span></span> <span data-ttu-id="bd41a-131">若要停用 Microsoft 更新，請選取 [**我不想使用 Microsoft Update**]。</span><span class="sxs-lookup"><span data-stu-id="bd41a-131">To disable Microsoft updates, select **I don’t want to use Microsoft Update**.</span></span> <span data-ttu-id="bd41a-132">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="bd41a-132">Click **Next**.</span></span>

4.  <span data-ttu-id="bd41a-133">在 [**功能選取**] 頁面上，選取您要安裝的元件，方法是選取 [**報表伺服器資料庫**] 核取方塊，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bd41a-133">On the **Feature Selection** page, select the components you want to install by selecting the **Reporting Server Database** checkbox and click **Next**.</span></span>

5.  <span data-ttu-id="bd41a-134">在 [**安裝位置**] 頁面上，接受預設位置，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bd41a-134">On the **Installation Location** page, accept the default location and click **Next**.</span></span>

6.  <span data-ttu-id="bd41a-135">在 [**建立新的報表伺服器資料庫**] 頁面上，接受預設選項（如果適用的話），然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bd41a-135">On the initial **Create New Reporting Server Database** page, accept the default selections if appropriate, and click **Next**.</span></span>

    <span data-ttu-id="bd41a-136">如果您使用的是自訂 SQL Server 實例，請選取 [**使用自訂實例**]，然後輸入實例的名稱。</span><span class="sxs-lookup"><span data-stu-id="bd41a-136">If you are using a custom SQL Server instance, then select **Use a custom instance** and type the name of the instance.</span></span>

    <span data-ttu-id="bd41a-137">如果您使用的是自訂資料庫名稱，請選取 [**自訂**設定]，然後輸入資料庫的名稱。</span><span class="sxs-lookup"><span data-stu-id="bd41a-137">If you are using a custom database name, then select **Custom configuration** and type the database name.</span></span>

7.  <span data-ttu-id="bd41a-138">在 [下一次**建立新報表伺服器資料庫**] 頁面上，選取 [**使用遠端電腦**]，然後使用下列格式輸入遠端電腦帳戶： **Domain\\MachineAccount**。</span><span class="sxs-lookup"><span data-stu-id="bd41a-138">On the next **Create New Reporting Server Database** page, select **Use a remote computer**, and type the remote machine account using the following format: **Domain\\MachineAccount**.</span></span>

    **<span data-ttu-id="bd41a-139">注意</span><span class="sxs-lookup"><span data-stu-id="bd41a-139">Note</span></span>**  
    <span data-ttu-id="bd41a-140">如果您打算在同一部電腦上部署報表伺服器，您必須選取 [**使用本機電腦**]。</span><span class="sxs-lookup"><span data-stu-id="bd41a-140">If you plan to deploy the reporting server on the same computer you must select **Use this local computer**.</span></span>



~~~
Specify the user name for the reporting server **Install Administrator** using the following format: **Domain\\AdministratorLoginName**. Click **Next**.
~~~

8. <span data-ttu-id="bd41a-141">若要開始安裝，請按一下 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="bd41a-141">To start the installation, click **Install**.</span></span>

**<span data-ttu-id="bd41a-142">使用 App-v 5.0 資料庫腳本安裝管理和報告資料庫</span><span class="sxs-lookup"><span data-stu-id="bd41a-142">To install the management and reporting databases using App-V 5.0 database scripts</span></span>**

1.  <span data-ttu-id="bd41a-143">將 App-v 5.0 server 安裝檔案複製到您要安裝它的電腦上。</span><span class="sxs-lookup"><span data-stu-id="bd41a-143">Copy the App-V 5.0 server installation files to the computer on which you want to install it on.</span></span>

2.  <span data-ttu-id="bd41a-144">若要解壓縮 App-v 5.0 資料庫腳本，請開啟命令提示字元，並指定儲存安裝盤案的位置，然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="bd41a-144">To extract the App-V 5.0 database scripts, open a command prompt and specify the location where the installation files are saved and run the following command:</span></span>

    <span data-ttu-id="bd41a-145">**appv\_server\_setup.exe** **/LAYOUT** **/LAYOUTDIR = "InstallationExtractionLocation"**。</span><span class="sxs-lookup"><span data-stu-id="bd41a-145">**appv\_server\_setup.exe** **/LAYOUT** **/LAYOUTDIR=”InstallationExtractionLocation”**.</span></span>

3.  <span data-ttu-id="bd41a-146">解壓縮完成後，若要存取 App-v 5.0 資料庫腳本與指示讀我檔案，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="bd41a-146">After the extraction has been completed, to access the App-V 5.0 database scripts and instructions readme file:</span></span>

    -   <span data-ttu-id="bd41a-147">App-V 5.0 管理資料庫腳本與指示讀我檔案位於下列資料夾： **InstallationExtractionLocation**  \\  **資料庫腳本**  \\  **管理資料庫**。</span><span class="sxs-lookup"><span data-stu-id="bd41a-147">The App-V 5.0 Management Database scripts and instructions readme are located in the following folder: **InstallationExtractionLocation** \\ **Database Scripts** \\ **Management Database**.</span></span>

    -   <span data-ttu-id="bd41a-148">App-v 5.0 報告資料庫腳本與指示讀我檔案位於下列資料夾： **InstallationExtractionLocation**  \\  **資料庫腳本**  \\  **報告資料庫**。</span><span class="sxs-lookup"><span data-stu-id="bd41a-148">The App-V 5.0 Reporting Database scripts and instructions readme are located in the following folder: **InstallationExtractionLocation** \\ **Database Scripts** \\ **Reporting Database**.</span></span>

4.  <span data-ttu-id="bd41a-149">針對每個資料庫，將腳本複製到共用，然後依照讀我檔案中的指示進行修改。</span><span class="sxs-lookup"><span data-stu-id="bd41a-149">For each database, copy the scripts to a share and modify them following the instructions in the readme file.</span></span>

    **<span data-ttu-id="bd41a-150">注意</span><span class="sxs-lookup"><span data-stu-id="bd41a-150">Note</span></span>**  
    <span data-ttu-id="bd41a-151">如需修改腳本中所需的 Sid 的詳細資訊，請參閱[如何安裝 App-v 資料庫，以及如何使用 PowerShell 轉換關聯的安全性識別碼](how-to-install-the-app-v-databases-and-convert-the-associated-security-identifiers--by-using-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="bd41a-151">For more information about modifying the required SIDs contained in the scripts see, [How to Install the App-V Databases and Convert the Associated Security Identifiers by Using PowerShell](how-to-install-the-app-v-databases-and-convert-the-associated-security-identifiers--by-using-powershell.md).</span></span>



5.  <span data-ttu-id="bd41a-152">在執行 Microsoft SQL Server 的電腦上執行腳本。</span><span class="sxs-lookup"><span data-stu-id="bd41a-152">Run the scripts on the computer running Microsoft SQL Server.</span></span>

    <span data-ttu-id="bd41a-153">您**有應用程式-V 的建議**嗎？</span><span class="sxs-lookup"><span data-stu-id="bd41a-153">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="bd41a-154">在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="bd41a-154">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="bd41a-155">有應用程式-V 問題嗎？</span><span class="sxs-lookup"><span data-stu-id="bd41a-155">Got an App-V issue?</span></span>** <span data-ttu-id="bd41a-156">使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="bd41a-156">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="bd41a-157">相關主題</span><span class="sxs-lookup"><span data-stu-id="bd41a-157">Related topics</span></span>


[<span data-ttu-id="bd41a-158">部署 App-V 5.0</span><span class="sxs-lookup"><span data-stu-id="bd41a-158">Deploying App-V 5.0</span></span>](deploying-app-v-50.md)









