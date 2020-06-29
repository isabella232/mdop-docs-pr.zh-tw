---
title: 如何在與管理和報告服務不同的電腦上安裝管理和報告資料庫
description: 如何在與管理和報告服務不同的電腦上安裝管理和報告資料庫
author: dansimp
ms.assetid: 2a67402e-3119-40ea-a247-24d166af1ced
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2332f674f10a9b60aa1cee814c6eac4ddbe4f5af
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800492"
---
# <span data-ttu-id="c2160-103">如何在與管理和報告服務不同的電腦上安裝管理和報告資料庫</span><span class="sxs-lookup"><span data-stu-id="c2160-103">How to Install the Management and Reporting Databases on Separate Computers from the Management and Reporting Services</span></span>

<span data-ttu-id="c2160-104">使用下列程式在不同的電腦上安裝資料庫伺服器與管理伺服器。</span><span class="sxs-lookup"><span data-stu-id="c2160-104">Use the following procedure to install the database server and management server on different computers.</span></span> <span data-ttu-id="c2160-105">您計畫在其上安裝資料庫伺服器的電腦必須執行 Microsoft SQL 支援的版本，否則安裝將會失敗。</span><span class="sxs-lookup"><span data-stu-id="c2160-105">The computer you plan to install the database server on must be running a supported version of Microsoft SQL or the installation will fail.</span></span>

> [!NOTE]
> <span data-ttu-id="c2160-106">完成部署之後，系統會要求安裝服務的**MICROSOFT SQL Server 名稱**、**實例名稱**和**資料庫名稱**，才能連線至這些資料庫。</span><span class="sxs-lookup"><span data-stu-id="c2160-106">After you complete the deployment, the **Microsoft SQL Server name**, **instance name** and **database name** will be required by the administrator installing the service to be able to connect to these databases.</span></span>

## <span data-ttu-id="c2160-107">在不同的電腦上安裝管理資料庫和管理伺服器</span><span class="sxs-lookup"><span data-stu-id="c2160-107">To install the management database and the management server on separate computers</span></span>

1. <span data-ttu-id="c2160-108">將 App-v 5.1 server 安裝檔案複製到您要安裝它的電腦上。</span><span class="sxs-lookup"><span data-stu-id="c2160-108">Copy the App-V 5.1 server installation files to the computer on which you want to install it on.</span></span> <span data-ttu-id="c2160-109">若要啟動 App-v 5.1 伺服器安裝，請以滑鼠右鍵按一下，然後以系統管理員身分執行**appv\_server\_setup.exe** 。</span><span class="sxs-lookup"><span data-stu-id="c2160-109">To start the App-V 5.1 server installation right-click and run **appv\_server\_setup.exe** as an administrator.</span></span> <span data-ttu-id="c2160-110">按一下 **\[安裝\]**。</span><span class="sxs-lookup"><span data-stu-id="c2160-110">Click **Install**.</span></span>
1. <span data-ttu-id="c2160-111">在 [**快速入門**] 頁面上，查看並接受授權條款，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c2160-111">On the **Getting Started** page, review and accept the license terms, and click **Next**.</span></span>
1. <span data-ttu-id="c2160-112">在 [**使用 Microsoft update]，協助保護您的電腦安全性且最新的**頁面，若要啟用 Microsoft 更新，請選取 **[在我檢查更新時使用 microsoft Update （建議）]。**</span><span class="sxs-lookup"><span data-stu-id="c2160-112">On the **Use Microsoft Update to help keep your computer secure and up-to-date** page, to enable Microsoft updates, select **Use Microsoft Update when I check for updates (recommended).**</span></span> <span data-ttu-id="c2160-113">若要停用 Microsoft 更新，請選取 [**我不想使用 Microsoft Update**]。</span><span class="sxs-lookup"><span data-stu-id="c2160-113">To disable Microsoft updates, select **I don't want to use Microsoft Update**.</span></span> <span data-ttu-id="c2160-114">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="c2160-114">Click **Next**.</span></span>
1. <span data-ttu-id="c2160-115">在 [**功能選取**] 頁面上，選取您要安裝的元件，方法是選取 [**管理伺服器資料庫**] 核取方塊，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c2160-115">On the **Feature Selection** page, select the components you want to install by selecting the **Management Server Database** checkbox and click **Next**.</span></span>
1. <span data-ttu-id="c2160-116">在 [**安裝位置**] 頁面上，接受預設位置，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c2160-116">On the **Installation Location** page, accept the default location and click **Next**.</span></span>
1. <span data-ttu-id="c2160-117">在 [**建立新的管理伺服器資料庫] 頁面**上，接受預設選項（如果適用的話），然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c2160-117">On the initial **Create New Management Server Database page**, accept the default selections if appropriate, and click **Next**.</span></span>

    <span data-ttu-id="c2160-118">如果您使用的是自訂 SQL Server 實例，請選取 [**使用自訂實例**]，然後輸入實例的名稱。</span><span class="sxs-lookup"><span data-stu-id="c2160-118">If you are using a custom SQL Server instance, then select **Use a custom instance** and type the name of the instance.\</span></span>
    <span data-ttu-id="c2160-119">如果您使用的是自訂資料庫名稱，請選取 [**自訂**設定]，然後輸入資料庫的名稱。</span><span class="sxs-lookup"><span data-stu-id="c2160-119">If you are using a custom database name, then select **Custom configuration** and type the database name.</span></span>

1. <span data-ttu-id="c2160-120">在 [**建立新的管理伺服器資料庫**] 頁面上，選取 [**使用遠端電腦**]，然後使用下列格式輸入遠端電腦帳戶： **Domain\\MachineAccount**。</span><span class="sxs-lookup"><span data-stu-id="c2160-120">On the next **Create New Management Server Database** page, select **Use a remote computer**, and type the remote machine account using the following format: **Domain\\MachineAccount**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c2160-121">如果您打算在同一部電腦上部署管理伺服器，您必須選取 [**使用本機電腦**]。</span><span class="sxs-lookup"><span data-stu-id="c2160-121">If you plan to deploy the management server on the same computer you must select **Use this local computer**.</span></span>

1. <span data-ttu-id="c2160-122">使用下列格式指定管理伺服器的使用者名稱**安裝系統管理員**： **Domain\\AdministratorLoginName**。</span><span class="sxs-lookup"><span data-stu-id="c2160-122">Specify the user name for the management server **Install Administrator** using the following format: **Domain\\AdministratorLoginName**.</span></span> <span data-ttu-id="c2160-123">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="c2160-123">Click **Next**.</span></span>
1. <span data-ttu-id="c2160-124">若要開始安裝，請按一下 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="c2160-124">To start the installation, click **Install**.</span></span>

## <span data-ttu-id="c2160-125">在不同的電腦上安裝報表資料庫和報表伺服器</span><span class="sxs-lookup"><span data-stu-id="c2160-125">To install the reporting database and the reporting server on separate computers</span></span>

1. <span data-ttu-id="c2160-126">將 App-v 5.1 server 安裝檔案複製到您要安裝它的電腦上。</span><span class="sxs-lookup"><span data-stu-id="c2160-126">Copy the App-V 5.1 server installation files to the computer on which you want to install it on.</span></span> <span data-ttu-id="c2160-127">若要啟動 App-v 5.1 伺服器安裝，請以滑鼠右鍵按一下，然後以系統管理員身分執行**appv\_server\_setup.exe** 。</span><span class="sxs-lookup"><span data-stu-id="c2160-127">To start the App-V 5.1 server installation right-click and run **appv\_server\_setup.exe** as an administrator.</span></span> <span data-ttu-id="c2160-128">按一下 **\[安裝\]**。</span><span class="sxs-lookup"><span data-stu-id="c2160-128">Click **Install**.</span></span>
1. <span data-ttu-id="c2160-129">在 [**快速入門**] 頁面上，查看並接受授權條款，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c2160-129">On the **Getting Started** page, review and accept the license terms, and click **Next**.</span></span>
1. <span data-ttu-id="c2160-130">在 [**使用 Microsoft update]，協助保護您的電腦安全性且最新的**頁面，若要啟用 Microsoft 更新，請選取 **[在我檢查更新時使用 microsoft Update （建議）]。**</span><span class="sxs-lookup"><span data-stu-id="c2160-130">On the **Use Microsoft Update to help keep your computer secure and up-to-date** page, to enable Microsoft updates, select **Use Microsoft Update when I check for updates (recommended).**</span></span> <span data-ttu-id="c2160-131">若要停用 Microsoft 更新，請選取 [**我不想使用 Microsoft Update**]。</span><span class="sxs-lookup"><span data-stu-id="c2160-131">To disable Microsoft updates, select **I don't want to use Microsoft Update**.</span></span> <span data-ttu-id="c2160-132">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="c2160-132">Click **Next**.</span></span>
1. <span data-ttu-id="c2160-133">在 [**功能選取**] 頁面上，選取您要安裝的元件，方法是選取 [**報表伺服器資料庫**] 核取方塊，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c2160-133">On the **Feature Selection** page, select the components you want to install by selecting the **Reporting Server Database** checkbox and click **Next**.</span></span>
1. <span data-ttu-id="c2160-134">在 [**安裝位置**] 頁面上，接受預設位置，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c2160-134">On the **Installation Location** page, accept the default location and click **Next**.</span></span>
1. <span data-ttu-id="c2160-135">在 [**建立新的報表伺服器資料庫**] 頁面上，接受預設選項（如果適用的話），然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c2160-135">On the initial **Create New Reporting Server Database** page, accept the default selections if appropriate, and click **Next**.</span></span>

    <span data-ttu-id="c2160-136">如果您使用的是自訂 SQL Server 實例，請選取 [**使用自訂實例**]，然後輸入實例的名稱。</span><span class="sxs-lookup"><span data-stu-id="c2160-136">If you are using a custom SQL Server instance, then select **Use a custom instance** and type the name of the instance.</span></span>
    <span data-ttu-id="c2160-137">如果您使用的是自訂資料庫名稱，請選取 [**自訂**設定]，然後輸入資料庫的名稱。</span><span class="sxs-lookup"><span data-stu-id="c2160-137">If you are using a custom database name, then select **Custom configuration** and type the database name.</span></span>

1. <span data-ttu-id="c2160-138">在 [下一次**建立新報表伺服器資料庫**] 頁面上，選取 [**使用遠端電腦**]，然後使用下列格式輸入遠端電腦帳戶： **Domain\\MachineAccount**。</span><span class="sxs-lookup"><span data-stu-id="c2160-138">On the next **Create New Reporting Server Database** page, select **Use a remote computer**, and type the remote machine account using the following format: **Domain\\MachineAccount**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c2160-139">如果您打算在同一部電腦上部署報表伺服器，您必須選取 [**使用本機電腦**]。</span><span class="sxs-lookup"><span data-stu-id="c2160-139">If you plan to deploy the reporting server on the same computer you must select **Use this local computer**.</span></span>

1. <span data-ttu-id="c2160-140">使用下列格式指定 reporting server**安裝系統管理員**的使用者名稱： **Domain\\AdministratorLoginName**。</span><span class="sxs-lookup"><span data-stu-id="c2160-140">Specify the user name for the reporting server **Install Administrator** using the following format: **Domain\\AdministratorLoginName**.</span></span> <span data-ttu-id="c2160-141">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="c2160-141">Click **Next**.</span></span>
1. <span data-ttu-id="c2160-142">若要開始安裝，請按一下 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="c2160-142">To start the installation, click **Install**.</span></span>

## <span data-ttu-id="c2160-143">使用 App-v 5.1 資料庫腳本安裝管理和報告資料庫</span><span class="sxs-lookup"><span data-stu-id="c2160-143">To install the management and reporting databases using App-V 5.1 database scripts</span></span>

1. <span data-ttu-id="c2160-144">將 App-v 5.1 server 安裝檔案複製到您要安裝它的電腦上。</span><span class="sxs-lookup"><span data-stu-id="c2160-144">Copy the App-V 5.1 server installation files to the computer on which you want to install it on.</span></span>
1. <span data-ttu-id="c2160-145">若要解壓縮 App-v 5.1 資料庫腳本，請開啟命令提示字元，並指定儲存安裝盤案的位置，然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="c2160-145">To extract the App-V 5.1 database scripts, open a command prompt and specify the location where the installation files are saved and run the following command:</span></span>

    <span data-ttu-id="c2160-146">**appv\_server\_setup.exe** **/LAYOUT** **/LAYOUTDIR = "InstallationExtractionLocation"**。</span><span class="sxs-lookup"><span data-stu-id="c2160-146">**appv\_server\_setup.exe** **/LAYOUT** **/LAYOUTDIR="InstallationExtractionLocation"**.</span></span>

1. <span data-ttu-id="c2160-147">解壓縮完成後，若要存取 App-v 5.1 資料庫腳本與指示讀我檔案，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="c2160-147">After the extraction has been completed, to access the App-V 5.1 database scripts and instructions readme file:</span></span>

    - <span data-ttu-id="c2160-148">App-V 5.1 管理資料庫腳本與指示讀我檔案位於下列資料夾： **InstallationExtractionLocation**  \\  **資料庫腳本**  \\  **管理資料庫**。</span><span class="sxs-lookup"><span data-stu-id="c2160-148">The App-V 5.1 Management Database scripts and instructions readme are located in the following folder: **InstallationExtractionLocation** \\ **Database Scripts** \\ **Management Database**.</span></span>
    - <span data-ttu-id="c2160-149">App-v 5.1 報告資料庫腳本與指示讀我檔案位於下列資料夾： **InstallationExtractionLocation**  \\  **資料庫腳本**  \\  **報告資料庫**。</span><span class="sxs-lookup"><span data-stu-id="c2160-149">The App-V 5.1 Reporting Database scripts and instructions readme are located in the following folder: **InstallationExtractionLocation** \\ **Database Scripts** \\ **Reporting Database**.</span></span>

1. <span data-ttu-id="c2160-150">針對每個資料庫，將腳本複製到共用，然後依照讀我檔案中的指示進行修改。</span><span class="sxs-lookup"><span data-stu-id="c2160-150">For each database, copy the scripts to a share and modify them following the instructions in the readme file.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c2160-151">如需修改腳本中所需的 Sid 的詳細資訊，請參閱[如何安裝 App-v 資料庫，以及如何使用 PowerShell 轉換關聯的安全性識別碼](how-to-install-the-app-v-databases-and-convert-the-associated-security-identifiers--by-using-powershell51.md)。</span><span class="sxs-lookup"><span data-stu-id="c2160-151">For more information about modifying the required SIDs contained in the scripts, see [How to Install the App-V Databases and Convert the Associated Security Identifiers by Using PowerShell](how-to-install-the-app-v-databases-and-convert-the-associated-security-identifiers--by-using-powershell51.md).</span></span>

1. <span data-ttu-id="c2160-152">在執行 Microsoft SQL Server 的電腦上執行腳本。</span><span class="sxs-lookup"><span data-stu-id="c2160-152">Run the scripts on the computer running Microsoft SQL Server.</span></span>

**<span data-ttu-id="c2160-153">有應用程式-V 問題嗎？</span><span class="sxs-lookup"><span data-stu-id="c2160-153">Got an App-V issue?</span></span>** <span data-ttu-id="c2160-154">使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="c2160-154">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="c2160-155">相關主題</span><span class="sxs-lookup"><span data-stu-id="c2160-155">Related topics</span></span>

[<span data-ttu-id="c2160-156">部署 App-V 5.1</span><span class="sxs-lookup"><span data-stu-id="c2160-156">Deploying App-V 5.1</span></span>](deploying-app-v-51.md)
