---
title: 如何升級 Application Virtualization Client
description: 如何升級 Application Virtualization Client
author: dansimp
ms.assetid: 2a75d8b5-da88-456c-85bb-f5bd3d470f7f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b9748fbdba7c8d2777a06c93295e4582be784dd1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801022"
---
# <span data-ttu-id="b5f6f-103">如何升級 Application Virtualization Client</span><span class="sxs-lookup"><span data-stu-id="b5f6f-103">How to Upgrade the Application Virtualization Client</span></span>


<span data-ttu-id="b5f6f-104">您可以使用下列程式來升級應用程式虛擬化（app-v）桌面用戶端或適用于遠端桌面服務的 App-v 用戶端（以前稱為 [終端服務]）。</span><span class="sxs-lookup"><span data-stu-id="b5f6f-104">You can use the following procedures to upgrade the Application Virtualization (App-V) Desktop Client or the App-V Client for Remote Desktop Services (formerly Terminal Services).</span></span> <span data-ttu-id="b5f6f-105">您可以透過在先前安裝較舊版本的新版本來升級用戶端。</span><span class="sxs-lookup"><span data-stu-id="b5f6f-105">You upgrade the client by installing a new version over the previously installed older version.</span></span> <span data-ttu-id="b5f6f-106">當您升級用戶端時，安裝程式軟體會自動保留及遷移使用者的虛擬應用程式設定。</span><span class="sxs-lookup"><span data-stu-id="b5f6f-106">When you upgrade the clients, the installer software automatically preserves and migrates the user’s settings for virtual applications.</span></span> <span data-ttu-id="b5f6f-107">需要系統管理許可權才能執行安裝程式。</span><span class="sxs-lookup"><span data-stu-id="b5f6f-107">Administrative rights are required to run the setup program.</span></span>

<span data-ttu-id="b5f6f-108">**記事** 在升級到應用程式虛擬化（App-v）4.5 或更新版本期間，會變更 HKCU 登錄機碼的許可權。</span><span class="sxs-lookup"><span data-stu-id="b5f6f-108">**Note** During the upgrade to Application Virtualization (App-V)4.5 or later versions, the permissions to the HKCU registry key are changed.</span></span> <span data-ttu-id="b5f6f-109">如此一來，使用者就會遺失先前設定的使用者設定，例如使用者設定的中斷式模式設定。</span><span class="sxs-lookup"><span data-stu-id="b5f6f-109">Because of this, users will lose user configurations that were set previously, such as user-configured Disconnected Mode settings.</span></span> <span data-ttu-id="b5f6f-110">如果使用者未受到限制許可權鎖定的用戶端使用者介面行為，使用者就可以在發佈重新整理後重設這些喜好設定。</span><span class="sxs-lookup"><span data-stu-id="b5f6f-110">If the user is not actively restricted from configuring client user interface behavior through a permission lockdown, the user can reset these preferences after a publishing refresh.</span></span>

 

<span data-ttu-id="b5f6f-111">**重要** 當您升級至4.6 或更新版本的 App-V 用戶端時，您必須針對電腦的作業系統、32位或64位使用正確的安裝程式。</span><span class="sxs-lookup"><span data-stu-id="b5f6f-111">**Important** When upgrading to version4.6 or a later version of the App-V Client, you must use the correct installer for the computer’s operating system, 32-bit or 64-bit.</span></span> <span data-ttu-id="b5f6f-112">如果您使用的是錯誤的安裝程式，安裝將會失敗，並會顯示錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="b5f6f-112">The installation will fail and an error message will be displayed if you use the wrong installer.</span></span>

 

**<span data-ttu-id="b5f6f-113">升級應用程式虛擬化桌面用戶端</span><span class="sxs-lookup"><span data-stu-id="b5f6f-113">To upgrade the Application Virtualization Desktop Client</span></span>**

1.  <span data-ttu-id="b5f6f-114">關閉所有虛擬應用程式，以滑鼠右鍵按一下顯示在 Windows 桌面通知區域中的 app-v 桌面用戶端圖示，**然後選取 [** 結束] 以關閉現有的用戶端。</span><span class="sxs-lookup"><span data-stu-id="b5f6f-114">Shut down all virtual applications, right-click the App-V Desktop Client icon displayed in the Windows desktop notification area, and select **Exit** to shut down the existing client.</span></span>

2.  <span data-ttu-id="b5f6f-115">在取得正確的安裝程式封存檔案並將它儲存到您的電腦之後，請按兩下它以展開封存。</span><span class="sxs-lookup"><span data-stu-id="b5f6f-115">After you have obtained the correct installer archive file and saved it to your computer, double-click it to expand the archive.</span></span>

3.  <span data-ttu-id="b5f6f-116">流覽以尋找 setup.exe 檔案，然後按兩下 setup.exe 以開始安裝。</span><span class="sxs-lookup"><span data-stu-id="b5f6f-116">Browse to find the setup.exe file, and double-click setup.exe to start the installation.</span></span>

4.  <span data-ttu-id="b5f6f-117">此嚮導會檢查系統，以確保已安裝所有必備軟體，並會提示您安裝下列任何一項（如果遺失的話）：</span><span class="sxs-lookup"><span data-stu-id="b5f6f-117">The wizard checks the system to ensure that all prerequisite software is installed and will prompt you to install any of the following, if missing:</span></span>

    -   <span data-ttu-id="b5f6f-118">Microsoft VisualC + + 2005SP1 可再發行套件（x86）</span><span class="sxs-lookup"><span data-stu-id="b5f6f-118">Microsoft VisualC++2005SP1 Redistributable Package (x86)</span></span>

    -   <span data-ttu-id="b5f6f-119">Microsoft Core XML Services （MSXML） 6.0 SP1 （x86）</span><span class="sxs-lookup"><span data-stu-id="b5f6f-119">Microsoft Core XML Services (MSXML)6.0SP1 (x86)</span></span>

    -   <span data-ttu-id="b5f6f-120">Microsoft 應用程式錯誤報表</span><span class="sxs-lookup"><span data-stu-id="b5f6f-120">Microsoft Application Error Reporting</span></span>

    <span data-ttu-id="b5f6f-121">**記事** 針對版本4.6 及更高版本，此嚮導也會安裝下列軟體必備元件：</span><span class="sxs-lookup"><span data-stu-id="b5f6f-121">**Note** For version4.6 and higher, the wizard will also install the following software prerequisite:</span></span>

    -   <span data-ttu-id="b5f6f-122">Microsoft VisualC + + 2008SP1 可再發行套件（x86）</span><span class="sxs-lookup"><span data-stu-id="b5f6f-122">Microsoft VisualC++2008SP1 Redistributable Package (x86)</span></span>

     

5.  <span data-ttu-id="b5f6f-123">按一下 **\[安裝\]**。</span><span class="sxs-lookup"><span data-stu-id="b5f6f-123">Click **Install**.</span></span> <span data-ttu-id="b5f6f-124">隨即會顯示安裝進度，且狀態會從 [**擱置**] 變更為 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="b5f6f-124">Installation progress is displayed, and the status changes from **Pending** to **Installing**.</span></span> <span data-ttu-id="b5f6f-125">成功完成每個步驟時，安裝狀態會變更為 [**成功**]。</span><span class="sxs-lookup"><span data-stu-id="b5f6f-125">Installation status changes to **Succeeded** as each step is completed successfully.</span></span>

6.  <span data-ttu-id="b5f6f-126">當**應用程式虛擬化桌面用戶端**對話方塊出現並顯示一則訊息，指出電腦上已找到較舊版本的用戶端時，請按一下 **[下一步]** 以升級至新版本。</span><span class="sxs-lookup"><span data-stu-id="b5f6f-126">When the **Application Virtualization Desktop Client** dialog appears and displays a message stating that an older version of the client has been found on the computer, click **Next** to upgrade to the new version.</span></span>

7.  <span data-ttu-id="b5f6f-127">在顯示 [**授權協定**] 畫面時，請閱讀授權協定，如果您同意，請按一下 [**我接受授權合約中的條款**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b5f6f-127">When the **License Agreement** screen is displayed, read the license agreement, and if you agree, click **I accept the terms in the license agreement**, and then click **Next**.</span></span>

8.  <span data-ttu-id="b5f6f-128">當 [InstallShield] 嚮導顯示 [**準備好升級程式**] 對話方塊畫面時，請按一下 [**升級**] 開始升級。</span><span class="sxs-lookup"><span data-stu-id="b5f6f-128">When the InstallShield Wizard displays the **Ready to Upgrade the Program** dialog screen, click **Upgrade** to begin the upgrade.</span></span> <span data-ttu-id="b5f6f-129">下一個畫面會顯示用戶端已安裝。</span><span class="sxs-lookup"><span data-stu-id="b5f6f-129">The next screen indicates that the client is being installed.</span></span>

    <span data-ttu-id="b5f6f-130">**警告** 如果您沒有在步驟1中關閉用戶端程式，您可能會在 [**使用中**的警告] 畫面上看到一個檔案。</span><span class="sxs-lookup"><span data-stu-id="b5f6f-130">**Warning** If you did not shut down the client program in step 1, you might see a **Files In Use** warning displayed.</span></span> <span data-ttu-id="b5f6f-131">如果發生這種情況，請以滑鼠右鍵按一下顯示在桌面通知區域中的 app-v 用戶端圖示，**然後選取 [** 結束] 以關閉現有的用戶端。</span><span class="sxs-lookup"><span data-stu-id="b5f6f-131">If this happens, right-click the App-V Client icon displayed in the desktop notification area and select **Exit** to shut down the existing client.</span></span> <span data-ttu-id="b5f6f-132">然後按一下 [**重試**] 繼續。</span><span class="sxs-lookup"><span data-stu-id="b5f6f-132">Then click **Retry** to continue.</span></span>

     

9.  <span data-ttu-id="b5f6f-133">當安裝順利完成時，系統會提示您重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="b5f6f-133">When the installation completes successfully, you will be prompted to restart the computer.</span></span> <span data-ttu-id="b5f6f-134">您必須重新開機電腦才能完成安裝。</span><span class="sxs-lookup"><span data-stu-id="b5f6f-134">You need to restart the computer to complete the installation.</span></span>

    <span data-ttu-id="b5f6f-135">**小心** 如果升級由於任何原因而失敗，您必須重新開機電腦，才能再次嘗試升級。</span><span class="sxs-lookup"><span data-stu-id="b5f6f-135">**Caution** If the upgrade fails for any reason, you will need to restart the computer before attempting the upgrade again.</span></span>

     

**<span data-ttu-id="b5f6f-136">使用命令列升級應用程式虛擬化用戶端</span><span class="sxs-lookup"><span data-stu-id="b5f6f-136">To upgrade the Application Virtualization Client by Using the Command Line</span></span>**

1.  <span data-ttu-id="b5f6f-137">如果您使用 setup.msi 程式升級 App-v 用戶端，請確定已安裝任何必要的必備軟體。</span><span class="sxs-lookup"><span data-stu-id="b5f6f-137">If upgrading the App-V client using the setup.msi program, ensure that any necessary prerequisite software has been installed.</span></span>

    **<span data-ttu-id="b5f6f-138">重要</span><span class="sxs-lookup"><span data-stu-id="b5f6f-138">Important</span></span>**  
    -   <span data-ttu-id="b5f6f-139">針對應用程式-V 用戶端的4.6 及更新版本，setup.msi 程式會檢查系統並失敗，並顯示錯誤訊息，指出安裝程式無法在未安裝必備軟體時繼續執行。</span><span class="sxs-lookup"><span data-stu-id="b5f6f-139">For version4.6 and later of the App-V client, the setup.msi program checks the system and will fail with an error message indicating that installation cannot continue if prerequisite software is not installed.</span></span>

    -   <span data-ttu-id="b5f6f-140">在應用程式-V 版本4.6 中，在升級期間無法使用命令列參數，將會被忽略。</span><span class="sxs-lookup"><span data-stu-id="b5f6f-140">For App-V version4.6, command-line parameters cannot be used during an upgrade and will be ignored.</span></span>

     

2.  <span data-ttu-id="b5f6f-141">下列命令列範例使用 setup.msi 檔案來升級 App-v 用戶端。</span><span class="sxs-lookup"><span data-stu-id="b5f6f-141">The following command-line example uses the setup.msi file to upgrade the App-V Client.</span></span> <span data-ttu-id="b5f6f-142">您必須使用正確的用戶端安裝程式，視您是要升級 App-v Desktop 用戶端或適用于遠端桌面服務的 App-v 用戶端（以前稱為 [終端服務]）。</span><span class="sxs-lookup"><span data-stu-id="b5f6f-142">You will need to use the correct client installer program depending on whether you are upgrading the App-V Desktop Client or the App-V Client for Remote Desktop Services (formerly Terminal Services).</span></span>

    **<span data-ttu-id="b5f6f-143">msiexec.exe/i "setup.msi"</span><span class="sxs-lookup"><span data-stu-id="b5f6f-143">msiexec.exe /i "setup.msi"</span></span>**

    <span data-ttu-id="b5f6f-144">**重要** 只有在值包含空格時，才需要使用引號。</span><span class="sxs-lookup"><span data-stu-id="b5f6f-144">**Important** The quotation marks are required only when the value contains a space.</span></span> <span data-ttu-id="b5f6f-145">為了保持一致性，前一個範例中的所有實例都會顯示為引號。</span><span class="sxs-lookup"><span data-stu-id="b5f6f-145">For consistency, all instances in the preceding example are shown as having quotation marks.</span></span>

     

**<span data-ttu-id="b5f6f-146">若要為遠端桌面服務升級應用程式虛擬化用戶端</span><span class="sxs-lookup"><span data-stu-id="b5f6f-146">To upgrade the Application Virtualization Client for Remote Desktop Services</span></span>**

1.  <span data-ttu-id="b5f6f-147">遵循貴組織的標準原則，在遠端桌面工作階段主機（RDSession 主機）伺服器上安裝或升級應用程式。</span><span class="sxs-lookup"><span data-stu-id="b5f6f-147">Follow your organization’s standard policies for installing or upgrading applications on the Remote Desktop Session Host (RDSession Host) server.</span></span> <span data-ttu-id="b5f6f-148">如果系統是伺服器陣列的一部分，請從伺服器伺服器陣列中移除 RDSession 主機。</span><span class="sxs-lookup"><span data-stu-id="b5f6f-148">If the system is part of a farm, remove the RDSession Host from the server farm.</span></span>

2.  <span data-ttu-id="b5f6f-149">若要升級遠端桌面服務（舊稱終端服務）的 app-v 用戶端，您必須使用命令列，因為您無法在 RDSession 主機上手動升級用戶端。</span><span class="sxs-lookup"><span data-stu-id="b5f6f-149">To upgrade the App-V Client for Remote Desktop Services (formerly Terminal Services), you must use the command line because you cannot upgrade the client manually on the RDSession Host.</span></span>

    <span data-ttu-id="b5f6f-150">**記事** 在 App-v 版本4.6 及更新版本中，除了使用命令列升級用戶端之外，您還可以使用遠端桌面會話。</span><span class="sxs-lookup"><span data-stu-id="b5f6f-150">**Note** In App-V version 4.6 and later, in addition to using the command line to upgrade the client, you can also use a Remote Desktop session.</span></span> <span data-ttu-id="b5f6f-151">啟動遠端桌面會話時，不需要特殊的參數。</span><span class="sxs-lookup"><span data-stu-id="b5f6f-151">No special parameters are required to start the Remote Desktop session.</span></span>

     

3.  <span data-ttu-id="b5f6f-152">在遠端桌面服務升級的用戶端完成後，請重新開機並登入 RDSession 主機。</span><span class="sxs-lookup"><span data-stu-id="b5f6f-152">After the Client for Remote Desktop Services upgrade is complete, restart and log in to the RDSession Host.</span></span>

4.  <span data-ttu-id="b5f6f-153">重新開機系統之後，請將伺服器新增到伺服器伺服器陣列中。</span><span class="sxs-lookup"><span data-stu-id="b5f6f-153">After the system is restarted, add the server to the server farm.</span></span>

    <span data-ttu-id="b5f6f-154">**小心** 如果升級由於任何原因而失敗，您必須重新開機電腦，才能再次嘗試升級。</span><span class="sxs-lookup"><span data-stu-id="b5f6f-154">**Caution** If the upgrade fails for any reason, you will need to restart the computer before attempting the upgrade again.</span></span>

     

## <span data-ttu-id="b5f6f-155">相關主題</span><span class="sxs-lookup"><span data-stu-id="b5f6f-155">Related topics</span></span>


[<span data-ttu-id="b5f6f-156">Application Virtualization 部署與升級考量</span><span class="sxs-lookup"><span data-stu-id="b5f6f-156">Application Virtualization Deployment and Upgrade Considerations</span></span>](application-virtualization-deployment-and-upgrade-considerations.md)

 

 





