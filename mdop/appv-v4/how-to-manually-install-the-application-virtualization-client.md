---
title: 如何手動安裝 Application Virtualization Client
description: 如何手動安裝 Application Virtualization Client
author: dansimp
ms.assetid: bb67f70b-d525-4317-b254-e4f084c717ab
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 0cb41b5e51bd33c377b17c088e97cb54f1a57685
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801274"
---
# <span data-ttu-id="12d16-103">如何手動安裝 Application Virtualization Client</span><span class="sxs-lookup"><span data-stu-id="12d16-103">How to Manually Install the Application Virtualization Client</span></span>

<span data-ttu-id="12d16-104">有兩種類型的應用程式虛擬化用戶端元件：適用于在桌上型電腦上安裝的應用程式虛擬化桌面用戶端，以及可在遠端桌面工作階段主機（RD 工作階段主機）伺服器上安裝的遠端桌面服務（舊稱終端服務）應用程式虛擬化用戶端。</span><span class="sxs-lookup"><span data-stu-id="12d16-104">There are two types of Application Virtualization Client components: the Application Virtualization Desktop Client, which is designed for installation on desktop computers, and the Application Virtualization Client for Remote Desktop Services (formerly Terminal Services), which you can install on Remote Desktop Session Host (RD Session Host) servers .</span></span> <span data-ttu-id="12d16-105">雖然兩個用戶端安裝程式不同，但您可以使用下列程式，在單一桌上型電腦上手動安裝應用程式虛擬化桌面用戶端，或在單一 RD 工作階段主機伺服器上，將遠端桌面服務的 Application Virtualization 用戶端手動安裝。</span><span class="sxs-lookup"><span data-stu-id="12d16-105">Although the two client installer programs are different, you can use the following procedure to manually install either the Application Virtualization Desktop Client on a single desktop computer or the Application Virtualization Client for Remote Desktop Services on a single RD Session Host server.</span></span> <span data-ttu-id="12d16-106">在生產環境中，您很可能會將應用程式虛擬化桌面用戶端安裝在具有自動腳本安裝程式的多台桌上型電腦上。</span><span class="sxs-lookup"><span data-stu-id="12d16-106">In a production environment, you most likely will install the Application Virtualization Desktop Client on multiple desktop computers with an automated scripted installation process.</span></span> <span data-ttu-id="12d16-107">如需如何使用腳本式安裝程式安裝多個用戶端的相關資訊，請參閱[如何使用命令列來安裝用戶端](how-to-install-the-client-by-using-the-command-line-new.md)。</span><span class="sxs-lookup"><span data-stu-id="12d16-107">For information about how to install multiple clients by using a scripted installation process, see [How to Install the Client by Using the Command Line](how-to-install-the-client-by-using-the-command-line-new.md).</span></span>

**<span data-ttu-id="12d16-108">注意</span><span class="sxs-lookup"><span data-stu-id="12d16-108">Note</span></span>**  
1. <span data-ttu-id="12d16-109">如果您要在 RD 工作階段主機伺服器上為遠端桌面服務軟體安裝 Application Virtualization 用戶端，建議有開啟的 RDP 或 ICA 用戶端會話與 RD 工作階段主機伺服器的使用者，他們必須儲存其工作並結束其會話。</span><span class="sxs-lookup"><span data-stu-id="12d16-109">If you are installing the Application Virtualization Client for Remote Desktop Services software on a RD Session Host server, advise users who have an open RDP or ICA client session with the RD Session Host server that they must save their work and close their sessions.</span></span> <span data-ttu-id="12d16-110">在遠端桌面會話中，您可以手動將用戶端安裝至用戶端。</span><span class="sxs-lookup"><span data-stu-id="12d16-110">In a Remote Desktop session, you can install the client the client manually.</span></span> <span data-ttu-id="12d16-111">如需升級用戶端的詳細資訊，請參閱[如何升級應用程式虛擬化用戶端](how-to-upgrade-the-application-virtualization-client.md)。</span><span class="sxs-lookup"><span data-stu-id="12d16-111">For more information about upgrading the client, see [How to Upgrade the Application Virtualization Client](how-to-upgrade-the-application-virtualization-client.md).</span></span>

2. <span data-ttu-id="12d16-112">如果您在使用者的電腦上有任何由用戶端安裝路徑決定的設定，請注意應用程式虛擬化（App-v）4.5 用戶端使用的安裝資料夾與先前的版本不同。</span><span class="sxs-lookup"><span data-stu-id="12d16-112">If you have any configuration on the user’s computer that depends on the client install path, note that the Application Virtualization (App-V) 4.5 client uses a different install folder than previous versions.</span></span> <span data-ttu-id="12d16-113">根據預設，應用程式虛擬化（App-v）4.5 用戶端的新安裝會安裝至 \\Program Files\\Microsoft 應用程式虛擬化用戶端資料夾。</span><span class="sxs-lookup"><span data-stu-id="12d16-113">By default, a new install of the Application Virtualization (App-V) 4.5 client will install to the \\Program Files\\Microsoft Application Virtualization Client folder.</span></span> <span data-ttu-id="12d16-114">如果已安裝較舊版本的用戶端，安裝 App-v 用戶端將會執行升級至現有的安裝資料夾。</span><span class="sxs-lookup"><span data-stu-id="12d16-114">If an earlier version of the client is already installed, installing the App-V client will perform an upgrade into the existing installation folder.</span></span>

**<span data-ttu-id="12d16-115">注意</span><span class="sxs-lookup"><span data-stu-id="12d16-115">Note</span></span>**  
<span data-ttu-id="12d16-116">在 App-V 版本4.6 及更新版本中，安裝 App-v 用戶端時，SFTLDR.DLL 會安裝在 Windows\\system32 目錄中。</span><span class="sxs-lookup"><span data-stu-id="12d16-116">For App-V version 4.6 and later, when the App-V client is installed, SFTLDR.DLL is installed in the Windows\\system32 directory.</span></span> <span data-ttu-id="12d16-117">如果應用程式 V 用戶端安裝在64位系統上，SFTLDR\_WOW64.DLL 會安裝在 Windows\\SysWOW64 目錄中。</span><span class="sxs-lookup"><span data-stu-id="12d16-117">If the App-V client is installed on a 64-bit system, SFTLDR\_WOW64.DLL is installed in the Windows\\SysWOW64 directory.</span></span>

**<span data-ttu-id="12d16-118">手動安裝應用程式虛擬化桌面用戶端</span><span class="sxs-lookup"><span data-stu-id="12d16-118">To manually install Application Virtualization Desktop Client</span></span>**

1. <span data-ttu-id="12d16-119">在取得正確的安裝程式封存檔案並將其儲存到電腦之後，請確認您是以擁有電腦的系統管理員許可權的帳戶登入，然後按兩下檔案以展開封存。</span><span class="sxs-lookup"><span data-stu-id="12d16-119">After you have obtained the correct installer archive file and saved it to your computer, make sure you are logged on with an account having administrator rights on the computer and double-click the file to expand the archive.</span></span>

2. <span data-ttu-id="12d16-120">選擇要儲存檔案的資料夾，然後在檔案複製到檔案後開啟該資料夾。</span><span class="sxs-lookup"><span data-stu-id="12d16-120">Choose the folder in which to save the files, and then open the folder after the files have been copied to it.</span></span>

3. <span data-ttu-id="12d16-121">視需要查看版本資訊。</span><span class="sxs-lookup"><span data-stu-id="12d16-121">Review the Release Notes if appropriate.</span></span>

4. <span data-ttu-id="12d16-122">流覽以尋找 setup.exe 檔案，然後按兩下 setup.exe 以開始安裝。</span><span class="sxs-lookup"><span data-stu-id="12d16-122">Browse to find the setup.exe file, and double-click setup.exe to start the installation.</span></span>

5. <span data-ttu-id="12d16-123">此嚮導會檢查系統，以確保已安裝所有必備軟體，且如果缺少下列任何一個軟體，嚮導會自動提示您安裝它們：</span><span class="sxs-lookup"><span data-stu-id="12d16-123">The wizard checks the system to ensure that all prerequisite software is installed, and if any of the following are missing, the wizard will automatically prompt you to install them:</span></span>

    - <span data-ttu-id="12d16-124">Microsoft Visual c + + 2005 SP1 可再發行套件（x86）</span><span class="sxs-lookup"><span data-stu-id="12d16-124">Microsoft Visual C++ 2005 SP1 Redistributable Package (x86)</span></span>

    - <span data-ttu-id="12d16-125">Microsoft Core XML Services （MSXML） 6.0 SP1 （x86）</span><span class="sxs-lookup"><span data-stu-id="12d16-125">Microsoft Core XML Services (MSXML) 6.0 SP1 (x86)</span></span>

    - <span data-ttu-id="12d16-126">Microsoft 應用程式錯誤報表</span><span class="sxs-lookup"><span data-stu-id="12d16-126">Microsoft Application Error Reporting</span></span>

    **<span data-ttu-id="12d16-127">注意</span><span class="sxs-lookup"><span data-stu-id="12d16-127">Note</span></span>**  
    <span data-ttu-id="12d16-128">針對 App-v 版本4.6 及更新版本，此嚮導也會安裝 Microsoft Visual c + + 2008 SP1 可再發行套件（x86）。</span><span class="sxs-lookup"><span data-stu-id="12d16-128">For App-V version 4.6 and later, the wizard will also install Microsoft Visual C++ 2008 SP1 Redistributable Package (x86).</span></span>

    <span data-ttu-id="12d16-129">如需安裝 Microsoft Visual c + + 2008 SP1 可再發行套件（x86）的詳細資訊，請參閱 [https://go.microsoft.com/fwlink/?LinkId=150700](https://go.microsoft.com/fwlink/?LinkId=150700) 。</span><span class="sxs-lookup"><span data-stu-id="12d16-129">For more information about installing Microsoft Visual C++ 2008 SP1 Redistributable Package (x86), see [https://go.microsoft.com/fwlink/?LinkId=150700](https://go.microsoft.com/fwlink/?LinkId=150700).</span></span>

    <span data-ttu-id="12d16-130">如果出現提示，請按一下 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="12d16-130">If prompted, click **Install**.</span></span> <span data-ttu-id="12d16-131">隨即會顯示安裝進度，且狀態會從 [**擱置**] 變更為 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="12d16-131">Installation progress is displayed, and the status changes from **Pending** to **Installing**.</span></span> <span data-ttu-id="12d16-132">成功完成每個步驟時，安裝狀態會變更為 [**成功**]。</span><span class="sxs-lookup"><span data-stu-id="12d16-132">Installation status changes to **Succeeded** as each step is completed successfully.</span></span>

6. <span data-ttu-id="12d16-133">當顯示 [ **Microsoft Application Virtualization 桌面用戶端– InstallShield] 嚮導**時，請按 **[下一步**]。</span><span class="sxs-lookup"><span data-stu-id="12d16-133">When the **Microsoft Application Virtualization Desktop Client – InstallShield Wizard** is displayed, click **Next**.</span></span>

7. <span data-ttu-id="12d16-134">[**授權協定**] 畫面隨即顯示。</span><span class="sxs-lookup"><span data-stu-id="12d16-134">The **License Agreement** screen is displayed.</span></span> <span data-ttu-id="12d16-135">閱讀 [授權合約]，如果您同意，請按一下 [**我接受授權合約中的條款**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="12d16-135">Read the license agreement, and if you agree, click **I accept the terms in the license agreement** and then click **Next**.</span></span>

   <span data-ttu-id="12d16-136">您也可以按一下按鈕來朗讀隱私權聲明。</span><span class="sxs-lookup"><span data-stu-id="12d16-136">Optionally, you can click the button to read the Privacy Statement.</span></span> <span data-ttu-id="12d16-137">您必須連線至網際網路，才能存取隱私權聲明。</span><span class="sxs-lookup"><span data-stu-id="12d16-137">You must be connected to the Internet to access the Privacy Statement.</span></span>

8. <span data-ttu-id="12d16-138">在 [**安裝類型**] 畫面上，選取 [安裝類型]。</span><span class="sxs-lookup"><span data-stu-id="12d16-138">On the **Setup Type** screen, select the setup type.</span></span> <span data-ttu-id="12d16-139">按一下 [**一般**] 以使用預設的程式值，或按一下 [**自訂**] （如果您想要在安裝期間設定程式設定）。</span><span class="sxs-lookup"><span data-stu-id="12d16-139">Click **Typical** to use the default program values, or click **Custom** if you want to configure the program settings during installation.</span></span>

9. <span data-ttu-id="12d16-140">如果您選擇 [**一般**]，下一個畫面就會顯示已**準備好安裝程式**。</span><span class="sxs-lookup"><span data-stu-id="12d16-140">If you choose **Typical**, the next screen displays **Ready to Install the Program**.</span></span> <span data-ttu-id="12d16-141">按一下 [**安裝**] 以開始安裝。</span><span class="sxs-lookup"><span data-stu-id="12d16-141">Click **Install** to begin the installation.</span></span>

10. <span data-ttu-id="12d16-142">如果您選擇 [**自訂**]，就會出現 [**目的地資料夾**] 畫面。</span><span class="sxs-lookup"><span data-stu-id="12d16-142">If you choose **Custom**, the **Destination Folder** screen appears.</span></span>

11. <span data-ttu-id="12d16-143">在 [**目的地資料夾**] 畫面上，按一下 **[下一步]** 接受預設資料夾，或按一下 [**變更**] 以顯示 [**變更目前目的地資料夾**] 畫面。</span><span class="sxs-lookup"><span data-stu-id="12d16-143">On the **Destination Folder** screen, click **Next** to accept the default folder or click **Change** to display the **Change Current Destination Folder** screen.</span></span> <span data-ttu-id="12d16-144">流覽至 []，或在 [**資料夾名稱**] 欄位中，輸入目的地資料夾，按一下 **[確定]**，然後按一下 **[下一步**]。</span><span class="sxs-lookup"><span data-stu-id="12d16-144">Browse to or, in the **Folder Name** field, enter the destination folder, click **OK**, and then click **Next**.</span></span>

12. <span data-ttu-id="12d16-145">在 [**應用程式虛擬化資料位置**] 畫面上，按一下 **[下一步]** 接受預設資料位置，或完成下列動作以變更資料的儲存位置：</span><span class="sxs-lookup"><span data-stu-id="12d16-145">On the **Application Virtualization Data Location** screen, click **Next** to accept the default data locations or complete the following actions to change where the data is stored:</span></span>

    1. <span data-ttu-id="12d16-146">按一下 [**變更**]，然後流覽至 [**全域資料位置**] 欄位中，輸入全域資料位置的目的地資料夾，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="12d16-146">Click **Change**, and then browse to or, in the **Global Data Location** field, enter the destination folder for the global data location, and click **OK**.</span></span> <span data-ttu-id="12d16-147">[全域資料目錄] 是應用程式虛擬化桌面用戶端將電腦上所有使用者共用的資料，例如 OSD 檔案和 SFT 檔案資料。</span><span class="sxs-lookup"><span data-stu-id="12d16-147">The Global Data Directory is where the Application Virtualization Desktop Client caches data shared by all users on the computer, like OSD files and SFT file data.</span></span>

    2. <span data-ttu-id="12d16-148">如果您想要變更要使用的磁碟機盤符，請從下拉式清單中選取首選的磁片磁碟機字母。</span><span class="sxs-lookup"><span data-stu-id="12d16-148">If you want to change the drive letter to be used, select the preferred drive letter from the drop-down list.</span></span>

    3. <span data-ttu-id="12d16-149">如果您想要變更資料位置，請在 [**使用者專用資料位置**] 欄位中，輸入要儲存使用者特定資料的新路徑。</span><span class="sxs-lookup"><span data-stu-id="12d16-149">Enter a new path to store the user-specific data in the **User-specific Data Location** field if you want to change the data location.</span></span> <span data-ttu-id="12d16-150">[使用者資料目錄] 是應用程式虛擬化桌面用戶端儲存使用者特定資訊的位置，例如虛擬化應用程式的個人設定。</span><span class="sxs-lookup"><span data-stu-id="12d16-150">The User Data Directory is where the Application Virtualization Desktop Client stores user-specific information, like personal settings for virtualized applications.</span></span>

       **<span data-ttu-id="12d16-151">注意</span><span class="sxs-lookup"><span data-stu-id="12d16-151">Note</span></span>**  
       <span data-ttu-id="12d16-152">這個路徑對於每個使用者都必須是不同的，因此應該包含使用者特定的環境變數或對應的磁碟機，或其他將解析為每個使用者的唯一路徑的內容。</span><span class="sxs-lookup"><span data-stu-id="12d16-152">This path must be different for every user, so it should include a user-specific environment variable or a mapped drive or something else that will resolve to a unique path for each user.</span></span>

    4. <span data-ttu-id="12d16-153">完成變更後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="12d16-153">When you have finished making the changes, click **Next**.</span></span>

13. <span data-ttu-id="12d16-154">您可以在 [快取**大小設定**] 畫面上接受或變更預設的快取大小。</span><span class="sxs-lookup"><span data-stu-id="12d16-154">On the **Cache Size Settings** screen, you can accept or change the default cache size.</span></span> <span data-ttu-id="12d16-155">按一下下列其中一個選項按鈕，選擇如何管理快取空間：</span><span class="sxs-lookup"><span data-stu-id="12d16-155">Click one of the following radio buttons to choose how to manage the cache space:</span></span>

    1. <span data-ttu-id="12d16-156">**使用最大**快取大小。</span><span class="sxs-lookup"><span data-stu-id="12d16-156">**Use maximum cache size**.</span></span> <span data-ttu-id="12d16-157">在 [**最大大小（MB）** ] 欄位中，輸入介於100到1048576（1 TB）中的數值，以指定快取的大小上限。</span><span class="sxs-lookup"><span data-stu-id="12d16-157">Enter a numeric value from 100–1,048,576 (1 TB) in the **Maximum size (MB)** field to specify the maximum size of the cache.</span></span>

    2. <span data-ttu-id="12d16-158">**使用可用磁碟空間閾值**。</span><span class="sxs-lookup"><span data-stu-id="12d16-158">**Use free disk space threshold**.</span></span> <span data-ttu-id="12d16-159">輸入數值，以指定應用程式虛擬化用戶端必須留在磁片上的可用磁碟空間大小（以 MB 為單位）。</span><span class="sxs-lookup"><span data-stu-id="12d16-159">Enter a numeric value to specify the amount of free disk space, in MB, that the Application Virtualization Client must leave available on the disk.</span></span> <span data-ttu-id="12d16-160">這可讓快取增加，直到可用磁碟空間量達到這個限制為止。</span><span class="sxs-lookup"><span data-stu-id="12d16-160">This allows the cache to grow until the amount of free disk space reaches this limit.</span></span> <span data-ttu-id="12d16-161">[**剩餘可用磁碟空間**] 所顯示的值代表目前未使用的磁碟空間大小。</span><span class="sxs-lookup"><span data-stu-id="12d16-161">The value shown in **Free disk space remaining** indicates how much disk space is currently unused.</span></span>

    **<span data-ttu-id="12d16-162">重要</span><span class="sxs-lookup"><span data-stu-id="12d16-162">Important</span></span>**  
    <span data-ttu-id="12d16-163">若要確保快取已為所有已部署套件指派足夠的空間，請使用設定用戶端時使用的 [**可用磁碟空間閾值**] 設定，讓快取視需要增加。</span><span class="sxs-lookup"><span data-stu-id="12d16-163">To ensure that the cache has sufficient space allocated for all packages that might be deployed, use the **Use free disk space threshold** setting when you configure the client so that the cache can grow as needed.</span></span> <span data-ttu-id="12d16-164">或者，您可以在安裝期間預先決定需要多少磁碟空間，並在安裝時設定快取大小。</span><span class="sxs-lookup"><span data-stu-id="12d16-164">Alternatively, determine in advance how much disk space will be needed for the App-V cache, and at installation time, set the cache size accordingly.</span></span> <span data-ttu-id="12d16-165">如需有關快取空間管理功能的詳細資訊，請參閱 Microsoft Application Virtualization （App-v）操作指南中的 [使用快取**空間管理] 功能**。</span><span class="sxs-lookup"><span data-stu-id="12d16-165">For more information about the cache space management feature, in the Microsoft Application Virtualization (App-V) Operations Guide, see **How to Use the Cache Space Management Feature**.</span></span>

    <span data-ttu-id="12d16-166">按 \[**下一步**\] 繼續。</span><span class="sxs-lookup"><span data-stu-id="12d16-166">Click **Next** to continue.</span></span>

14. <span data-ttu-id="12d16-167">在 [**執行時間套件原則**設定] 畫面的下列各節中，您可以變更會影響應用程式虛擬化用戶端在執行時間期間的行為方式的參數：</span><span class="sxs-lookup"><span data-stu-id="12d16-167">In the following sections of the **Runtime Package Policy Configuration** screen, you can change the parameters that affect how the Application Virtualization client behaves during runtime:</span></span>

    1. <span data-ttu-id="12d16-168">**應用程式來源根目錄**。</span><span class="sxs-lookup"><span data-stu-id="12d16-168">**Application Source Root**.</span></span> <span data-ttu-id="12d16-169">指定 SFT 檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="12d16-169">Specifies the location of SFT files.</span></span> <span data-ttu-id="12d16-170">如果使用的話，會覆寫 OSD 檔案中基本代碼 HREF URL 的通訊協定、伺服器和埠部分。</span><span class="sxs-lookup"><span data-stu-id="12d16-170">If used, overrides the protocol, server, and port portions of the CODEBASE HREF URL in the OSD file.</span></span>

    2. <span data-ttu-id="12d16-171">**應用程式授權**。</span><span class="sxs-lookup"><span data-stu-id="12d16-171">**Application Authorization**.</span></span> <span data-ttu-id="12d16-172">即使在已選取 [快取] 時，**也需要使用者授權**，使用者還是必須先連線到伺服器並驗證其認證，才能啟動每個虛擬應用程式。</span><span class="sxs-lookup"><span data-stu-id="12d16-172">When **Require User authorization even when cached** is checked, users are required to connect to a server and validate their credentials at least once before they are allowed to start each virtual application.</span></span>

    3. <span data-ttu-id="12d16-173">**允許來自檔案的資料流程**。</span><span class="sxs-lookup"><span data-stu-id="12d16-173">**Allow streaming from file**.</span></span> <span data-ttu-id="12d16-174">指示無論**應用程式來源根**欄位的使用方式為何，是否會啟用來自檔案的串流。</span><span class="sxs-lookup"><span data-stu-id="12d16-174">Indicates whether streaming from file will be enabled, regardless of how the **Application Source Root** field is used.</span></span> <span data-ttu-id="12d16-175">如果未核取，則會停用檔案的資料流程。</span><span class="sxs-lookup"><span data-stu-id="12d16-175">If not checked, streaming from files is disabled.</span></span> <span data-ttu-id="12d16-176">如果**應用程式源根目錄**在 [表單 \\\\server\\share.] 中包含 UNC 路徑，則必須選取此選項。</span><span class="sxs-lookup"><span data-stu-id="12d16-176">This must be checked if **Application Source Root** contains a UNC path in the form \\\\server\\share.</span></span>

    4. <span data-ttu-id="12d16-177">**自動載入應用程式**。</span><span class="sxs-lookup"><span data-stu-id="12d16-177">**Automatically Load Application**.</span></span> <span data-ttu-id="12d16-178">控制應用程式自動載入背景的時機及方式。</span><span class="sxs-lookup"><span data-stu-id="12d16-178">Controls when and how automatic background loading of applications occurs.</span></span>

       **<span data-ttu-id="12d16-179">注意</span><span class="sxs-lookup"><span data-stu-id="12d16-179">Note</span></span>**  
       <span data-ttu-id="12d16-180">當您安裝 App-V 用戶端以搭配唯讀快取（例如，使用 VDI 伺服器實現）時，請設定**自動載入的應用程式**，**不要自動載入應用程式**，以免用戶端嘗試更新唯讀快取中的應用程式。</span><span class="sxs-lookup"><span data-stu-id="12d16-180">When you install the App-V client to use with a read-only cache, for example, with a VDI server implementation, set **What applications to Auto Load** to **Do not automatically load applications** to prevent the client from trying to update applications in the read-only cache.</span></span>

    <span data-ttu-id="12d16-181">按 \[**下一步**\] 繼續。</span><span class="sxs-lookup"><span data-stu-id="12d16-181">Click **Next** to continue.</span></span>

15. <span data-ttu-id="12d16-182">如果您想要定義發佈伺服器，請在 [**發佈伺服器**] 畫面上，選取 [**立即設定發佈伺服器**] 核取方塊，或按一下 **[下一步]** （如果您想要稍後完成此選項）。</span><span class="sxs-lookup"><span data-stu-id="12d16-182">On the **Publishing Server** screen, select the **Set up a Publishing Server now** check box if you want to define a publishing server, or click **Next** if you want to complete this later.</span></span> <span data-ttu-id="12d16-183">若要定義發佈伺服器，請指定下列資訊：</span><span class="sxs-lookup"><span data-stu-id="12d16-183">To define a publishing server, specify the following information:</span></span>

    1. <span data-ttu-id="12d16-184">[**顯示名稱**]-輸入您想要顯示給伺服器的名稱。</span><span class="sxs-lookup"><span data-stu-id="12d16-184">**Display Name**—Enter the name you want to display for the server.</span></span>

    2. <span data-ttu-id="12d16-185">**類型**—從伺服器類型的下拉式清單中，選取 [伺服器類型]。</span><span class="sxs-lookup"><span data-stu-id="12d16-185">**Type**—Select the server type from the drop-down list of server types.</span></span>

    3. <span data-ttu-id="12d16-186">[**主機名稱**與**埠**]-在對應的欄位中輸入主機名稱和埠。</span><span class="sxs-lookup"><span data-stu-id="12d16-186">**Host Name** and **Port**—Enter the host name and the port in the corresponding fields.</span></span> <span data-ttu-id="12d16-187">當您在下拉式清單中選取伺服器類型時，[埠] 欄位會自動填入標準埠號碼。</span><span class="sxs-lookup"><span data-stu-id="12d16-187">When you select a server type in the drop-down list, the port field will automatically fill with the standard port numbers.</span></span> <span data-ttu-id="12d16-188">若要變更埠號碼，請按一下清單中的伺服器類型，然後根據您的需求變更埠號碼。</span><span class="sxs-lookup"><span data-stu-id="12d16-188">To change a port number, click the server type in the list and change the port number according to your needs.</span></span>

    4. <span data-ttu-id="12d16-189">**路徑**：如果您已選取 [**標準 HTTP 伺服器**] 或 [**增強的安全性 HTTP 伺服器**]，則必須輸入包含此欄位中發佈資料之 XML 檔案的完整路徑。</span><span class="sxs-lookup"><span data-stu-id="12d16-189">**Path**—If you have selected either **Standard HTTP Server** or **Enhanced Security HTTP Server**, you must enter the complete path to the XML file containing publishing data in this field.</span></span> <span data-ttu-id="12d16-190">如果您選取 [**應用程式虛擬化伺服器**] 或 [**增強的安全性應用程式虛擬化伺服器**]，此欄位則無法使用。</span><span class="sxs-lookup"><span data-stu-id="12d16-190">If you select either **Application Virtualization Server** or **Enhanced Security Application Virtualization Server**, this field is not active.</span></span>

    5. <span data-ttu-id="12d16-191">**自動聯絡此伺服器以在使用者登入時更新設定**—如果您希望在使用者登入到應用程式虛擬化用戶端的帳戶時，自動查詢此伺服器，請選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="12d16-191">**Automatically contact this server to update settings when a user logs in**—Select this check box if you want this server to be queried automatically when users log in to their account on the Application Virtualization Client.</span></span>

    6. <span data-ttu-id="12d16-192">完成設定步驟後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="12d16-192">When finished with the configuration steps, click **Next**.</span></span>

16. <span data-ttu-id="12d16-193">在 [**準備好安裝程式**] 畫面中，按一下 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="12d16-193">On the **Ready to Install the Program** screen, click **Install**.</span></span> <span data-ttu-id="12d16-194">畫面隨即出現，顯示安裝進度。</span><span class="sxs-lookup"><span data-stu-id="12d16-194">A screen is displayed that shows the progress of the installation.</span></span>

17. <span data-ttu-id="12d16-195">在 [**安裝精靈完成]** 畫面上，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="12d16-195">On the **Install Wizard Completed** screen, click **Finish**.</span></span>

    **<span data-ttu-id="12d16-196">注意</span><span class="sxs-lookup"><span data-stu-id="12d16-196">Note</span></span>**  
    <span data-ttu-id="12d16-197">如果安裝由於任何原因而失敗，您可能需要重新開機電腦，才能再次嘗試安裝。</span><span class="sxs-lookup"><span data-stu-id="12d16-197">If the installation fails for any reason, you might need to restart the computer before trying the install again.</span></span>

## <span data-ttu-id="12d16-198">相關主題</span><span class="sxs-lookup"><span data-stu-id="12d16-198">Related topics</span></span>

[<span data-ttu-id="12d16-199">如何使用命令列安裝用戶端</span><span class="sxs-lookup"><span data-stu-id="12d16-199">How to Install the Client by Using the Command Line</span></span>](how-to-install-the-client-by-using-the-command-line-new.md)

[<span data-ttu-id="12d16-200">獨立傳遞案例概觀</span><span class="sxs-lookup"><span data-stu-id="12d16-200">Stand-Alone Delivery Scenario Overview</span></span>](stand-alone-delivery-scenario-overview.md)
