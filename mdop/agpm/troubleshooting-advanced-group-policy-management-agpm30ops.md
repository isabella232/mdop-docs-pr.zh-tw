---
title: 疑難排解進階群組原則管理
description: 疑難排解進階群組原則管理
author: dansimp
ms.assetid: f7ece97c-e9f8-4b18-8c7a-a615c98d5c60
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4815378a17a7c083501cfd7772e62415ec285237
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802513"
---
# <span data-ttu-id="bbeec-103">疑難排解進階群組原則管理</span><span class="sxs-lookup"><span data-stu-id="bbeec-103">Troubleshooting Advanced Group Policy Management</span></span>


<span data-ttu-id="bbeec-104">本節列出當您使用 [高級群組原則管理] （Gpo）管理群組原則物件時可能會遇到的常見問題。</span><span class="sxs-lookup"><span data-stu-id="bbeec-104">This section lists common issues that you may encounter when you use Advanced Group Policy Management (AGPM) to manage Group Policy Objects (GPOs).</span></span> <span data-ttu-id="bbeec-105">若要診斷此處未列出的問題，可能會對 AGPM 系統管理員（完全控制）有用，以使用記錄和追蹤功能。</span><span class="sxs-lookup"><span data-stu-id="bbeec-105">To diagnose issues not listed here, it may be helpful for an AGPM Administrator (Full Control) to use logging and tracing.</span></span> <span data-ttu-id="bbeec-106">如需詳細資訊，請參閱[設定記錄和追蹤](configure-logging-and-tracing-agpm30ops.md)。</span><span class="sxs-lookup"><span data-stu-id="bbeec-106">For more information, see [Configure Logging and Tracing](configure-logging-and-tracing-agpm30ops.md).</span></span>

**<span data-ttu-id="bbeec-107">注意</span><span class="sxs-lookup"><span data-stu-id="bbeec-107">Note</span></span>**  
-   <span data-ttu-id="bbeec-108">如需回退到舊版 GPO （如果有問題的話）的相關資訊，請參閱[回滾到舊版的 gpo](roll-back-to-a-previous-version-of-a-gpo-agpm30ops.md)。</span><span class="sxs-lookup"><span data-stu-id="bbeec-108">For information about rolling back to an earlier version of a GPO if there are problems, see [Roll Back to a Previous Version of a GPO](roll-back-to-a-previous-version-of-a-gpo-agpm30ops.md).</span></span>

-   <span data-ttu-id="bbeec-109">如需如何從備份還原完整封存的相關資訊，請參閱從[備份還原](restore-the-archive-from-a-backup.md)封存。</span><span class="sxs-lookup"><span data-stu-id="bbeec-109">For information about how to recover from a disaster by restoring the complete archive from a backup, see [Restore the Archive from a Backup](restore-the-archive-from-a-backup.md).</span></span>

 

## <span data-ttu-id="bbeec-110">您遇到什麼問題？</span><span class="sxs-lookup"><span data-stu-id="bbeec-110">What problems are you having?</span></span>


-   [<span data-ttu-id="bbeec-111">我無法存取封存</span><span class="sxs-lookup"><span data-stu-id="bbeec-111">I am unable to access an archive</span></span>](#bkmk-access-an-archive)

-   [<span data-ttu-id="bbeec-112">不同群組原則管理員的 GPO 狀態會有所不同</span><span class="sxs-lookup"><span data-stu-id="bbeec-112">The GPO state varies for different Group Policy administrators</span></span>](#bkmk-state-varies)

-   [<span data-ttu-id="bbeec-113">我無法修改 AGPM 服務器連線</span><span class="sxs-lookup"><span data-stu-id="bbeec-113">I am unable to modify the AGPM Server connection</span></span>](#bkmk-modify-archive-location)

-   [<span data-ttu-id="bbeec-114">我無法變更預設範本或查看、建立、編輯、重新命名、部署或刪除 Gpo</span><span class="sxs-lookup"><span data-stu-id="bbeec-114">I am unable to change the default template or view, create, edit, rename, deploy, or delete GPOs</span></span>](#bkmk-perform-task)

-   [<span data-ttu-id="bbeec-115">我無法使用特定的 GPO 名稱</span><span class="sxs-lookup"><span data-stu-id="bbeec-115">I am unable to use a particular GPO name</span></span>](#bkmk-use-particular-name)

-   [<span data-ttu-id="bbeec-116">我沒有收到 AGPM 電子郵件通知</span><span class="sxs-lookup"><span data-stu-id="bbeec-116">I am not receiving AGPM e-mail notifications</span></span>](#bkmk-email)

-   [<span data-ttu-id="bbeec-117">我無法將埠4600用於 AGPM 服務</span><span class="sxs-lookup"><span data-stu-id="bbeec-117">I cannot use port 4600 for the AGPM Service</span></span>](#bkmk-port)

-   [<span data-ttu-id="bbeec-118">AGPM 服務將無法啟動</span><span class="sxs-lookup"><span data-stu-id="bbeec-118">The AGPM Service will not start</span></span>](#bkmk-not-start)

-   [<span data-ttu-id="bbeec-119">[群組原則軟體安裝] 無法安裝軟體</span><span class="sxs-lookup"><span data-stu-id="bbeec-119">Group Policy Software Installation fails to install software</span></span>](#bkmk-software-installation)

-   [<span data-ttu-id="bbeec-120">將封存還原到新的 AGPM 服務器時，發生錯誤</span><span class="sxs-lookup"><span data-stu-id="bbeec-120">An error occurred when I restored the archive to a new AGPM Server</span></span>](#bkmk-error-on-restore)

### <a href="" id="bkmk-access-an-archive"></a><span data-ttu-id="bbeec-121">我無法存取封存</span><span class="sxs-lookup"><span data-stu-id="bbeec-121">I am unable to access an archive</span></span>

-   <span data-ttu-id="bbeec-122">**原因**：您沒有選取正確的伺服器和埠來進行封存。</span><span class="sxs-lookup"><span data-stu-id="bbeec-122">**Cause**: You have not selected the correct server and port for the archive.</span></span>

-   <span data-ttu-id="bbeec-123">**解決方案**：</span><span class="sxs-lookup"><span data-stu-id="bbeec-123">**Solution**:</span></span>

    -   <span data-ttu-id="bbeec-124">如果您是 AGPM 系統管理員：請參閱[設定 Agpm 伺服器](configure-agpm-server-connections-agpm30ops.md)連線。</span><span class="sxs-lookup"><span data-stu-id="bbeec-124">If you are an AGPM Administrator: See [Configure AGPM Server Connections](configure-agpm-server-connections-agpm30ops.md).</span></span>

    -   <span data-ttu-id="bbeec-125">如果您不是 AGPM 系統管理員：從 AGPM 系統管理員要求 AGPM 服務器的連線詳細資料。</span><span class="sxs-lookup"><span data-stu-id="bbeec-125">If you are not an AGPM Administrator: Request connection details for the AGPM Server from an AGPM Administrator.</span></span> <span data-ttu-id="bbeec-126">請參閱[設定 AGPM 服務器](configure-an-agpm-server-connection-reviewer-agpm30ops.md)連線。</span><span class="sxs-lookup"><span data-stu-id="bbeec-126">See [Configure an AGPM Server Connection](configure-an-agpm-server-connection-reviewer-agpm30ops.md).</span></span>

-   <span data-ttu-id="bbeec-127">**原因**： AGPM 服務未執行。</span><span class="sxs-lookup"><span data-stu-id="bbeec-127">**Cause**: The AGPM Service is not running.</span></span>

-   <span data-ttu-id="bbeec-128">**解決方案**：</span><span class="sxs-lookup"><span data-stu-id="bbeec-128">**Solution**:</span></span>

    -   <span data-ttu-id="bbeec-129">如果您是 AGPM 系統管理員：啟動 AGPM 服務。</span><span class="sxs-lookup"><span data-stu-id="bbeec-129">If you are an AGPM Administrator: Start the AGPM Service.</span></span> <span data-ttu-id="bbeec-130">如需詳細資訊，請參閱[啟動和停止 AGPM 服務](start-and-stop-the-agpm-service-agpm30ops.md)。</span><span class="sxs-lookup"><span data-stu-id="bbeec-130">For more information, see [Start and Stop the AGPM Service](start-and-stop-the-agpm-service-agpm30ops.md).</span></span>

    -   <span data-ttu-id="bbeec-131">如果您不是 AGPM 系統管理員：請與 AGPM 系統管理員聯繫以取得協助。</span><span class="sxs-lookup"><span data-stu-id="bbeec-131">If you are not an AGPM Administrator: Contact an AGPM Administrator for assistance.</span></span>

### <a href="" id="bkmk-state-varies"></a><span data-ttu-id="bbeec-132">不同群組原則管理員的 GPO 狀態會有所不同</span><span class="sxs-lookup"><span data-stu-id="bbeec-132">The GPO state varies for different Group Policy administrators</span></span>

-   <span data-ttu-id="bbeec-133">**原因**：不同的群組原則管理員針對相同的封存選取了不同的 AGPM 服務器。</span><span class="sxs-lookup"><span data-stu-id="bbeec-133">**Cause**: Different Group Policy administrators have selected different AGPM Servers for the same archive.</span></span>

-   <span data-ttu-id="bbeec-134">**解決方案**：</span><span class="sxs-lookup"><span data-stu-id="bbeec-134">**Solution**:</span></span>

    -   <span data-ttu-id="bbeec-135">如果您是 AGPM 系統管理員：請參閱[設定 Agpm 伺服器](configure-agpm-server-connections-agpm30ops.md)連線。</span><span class="sxs-lookup"><span data-stu-id="bbeec-135">If you are an AGPM Administrator: See [Configure AGPM Server Connections](configure-agpm-server-connections-agpm30ops.md).</span></span>

    -   <span data-ttu-id="bbeec-136">如果您不是 AGPM 系統管理員：從 AGPM 系統管理員要求 AGPM 服務器的連線詳細資料。</span><span class="sxs-lookup"><span data-stu-id="bbeec-136">If you are not an AGPM Administrator: Request connection details for the AGPM Server from an AGPM Administrator.</span></span> <span data-ttu-id="bbeec-137">請參閱[設定 AGPM 服務器](configure-an-agpm-server-connection-reviewer-agpm30ops.md)連線。</span><span class="sxs-lookup"><span data-stu-id="bbeec-137">See [Configure an AGPM Server Connection](configure-an-agpm-server-connection-reviewer-agpm30ops.md).</span></span>

### <a href="" id="bkmk-modify-archive-location"></a><span data-ttu-id="bbeec-138">我無法修改 AGPM 服務器連線</span><span class="sxs-lookup"><span data-stu-id="bbeec-138">I am unable to modify the AGPM Server connection</span></span>

-   <span data-ttu-id="bbeec-139">**原因**：如果 [ **agpm 伺服器**] 索引標籤上的 [設定] 無法使用，則 Agpm 伺服器已使用管理樣板集中進行集中設定。</span><span class="sxs-lookup"><span data-stu-id="bbeec-139">**Cause**: If the settings on the **AGPM Server** tab are unavailable, the AGPM Server has been centrally configured using an Administrative template.</span></span>

-   <span data-ttu-id="bbeec-140">**解決方案**：</span><span class="sxs-lookup"><span data-stu-id="bbeec-140">**Solution**:</span></span>

    -   <span data-ttu-id="bbeec-141">如果您是 AGPM 系統管理員：如果 [ **Agpm 伺服器**] 索引標籤上的 [設定] 無法使用，請參閱[設定 agpm 伺服器](configure-agpm-server-connections-agpm30ops.md)連線。</span><span class="sxs-lookup"><span data-stu-id="bbeec-141">If you are an AGPM Administrator: If the settings on the **AGPM Server** tab are unavailable, see [Configure AGPM Server Connections](configure-agpm-server-connections-agpm30ops.md).</span></span>

    -   <span data-ttu-id="bbeec-142">如果您不是 AGPM 系統管理員：如果 [ **Agpm 伺服器**] 索引標籤上的 [設定] 無法使用，您就不需要修改 agpm 伺服器。</span><span class="sxs-lookup"><span data-stu-id="bbeec-142">If you are not an AGPM Administrator: If the settings on the **AGPM Server** tab are unavailable, you do not need to modify the AGPM Server.</span></span>

### <a href="" id="bkmk-perform-task"></a><span data-ttu-id="bbeec-143">我無法變更預設範本或查看、建立、編輯、重新命名、部署或刪除 Gpo</span><span class="sxs-lookup"><span data-stu-id="bbeec-143">I am unable to change the default template or view, create, edit, rename, deploy, or delete GPOs</span></span>

-   <span data-ttu-id="bbeec-144">**原因**：您沒有獲指派角色，且擁有執行任務所需的許可權。</span><span class="sxs-lookup"><span data-stu-id="bbeec-144">**Cause**: You have not been assigned a role with the permissions required to perform the task or tasks.</span></span>

-   <span data-ttu-id="bbeec-145">**解決方案**：</span><span class="sxs-lookup"><span data-stu-id="bbeec-145">**Solution**:</span></span>

    -   <span data-ttu-id="bbeec-146">如果您是 AGPM 系統管理員：請參閱[委派網域層級的存取權](delegate-domain-level-access-to-the-archive-agpm30ops.md)，並委派對封存[中個別 GPO 的存取權](delegate-access-to-an-individual-gpo-in-the-archive-agpm30ops.md)。</span><span class="sxs-lookup"><span data-stu-id="bbeec-146">If you are an AGPM Administrator: See [Delegate Domain-Level Access to the Archive](delegate-domain-level-access-to-the-archive-agpm30ops.md) and [Delegate Access to an Individual GPO in the Archive](delegate-access-to-an-individual-gpo-in-the-archive-agpm30ops.md).</span></span> <span data-ttu-id="bbeec-147">AGPM 許可權會從網域級聯到目前封存中的所有 Gpo。</span><span class="sxs-lookup"><span data-stu-id="bbeec-147">AGPM permissions will cascade from the domain to all GPOs currently in the archive.</span></span> <span data-ttu-id="bbeec-148">如需哪些角色可以執行工作的詳細資料，以及執行工作所需的許可權，請參閱該工作的說明。</span><span class="sxs-lookup"><span data-stu-id="bbeec-148">For details about which roles can perform a task and which permissions are necessary to perform a task, refer to the help for that task.</span></span>

    -   <span data-ttu-id="bbeec-149">如果您不是 AGPM 系統管理員，且需要其他角色或許可權：請與 AGPM 系統管理員聯繫以取得協助。</span><span class="sxs-lookup"><span data-stu-id="bbeec-149">If you are not an AGPM Administrator and you require additional roles or permissions: Contact an AGPM Administrator for assistance.</span></span> <span data-ttu-id="bbeec-150">請注意，如果您是「編輯」，您可以開始建立 GPO、部署 GPO 或從生產環境刪除 GPO 的程式，但核准者或 AGPM 管理員必須核准您的要求。</span><span class="sxs-lookup"><span data-stu-id="bbeec-150">Be aware that if you are an Editor, you can begin the process of creating a GPO, deploying a GPO, or deleting a GPO from the production environment, but an Approver or AGPM Administrator must approve your request.</span></span>

### <a href="" id="bkmk-use-particular-name"></a><span data-ttu-id="bbeec-151">我無法使用特定的 GPO 名稱</span><span class="sxs-lookup"><span data-stu-id="bbeec-151">I am unable to use a particular GPO name</span></span>

-   <span data-ttu-id="bbeec-152">**原因**：此 gpo 名稱已在使用中，或您無權列出該 gpo。</span><span class="sxs-lookup"><span data-stu-id="bbeec-152">**Cause**: Either the GPO name is already in use or you lack permission to list the GPO.</span></span>

-   <span data-ttu-id="bbeec-153">**解決方案**：</span><span class="sxs-lookup"><span data-stu-id="bbeec-153">**Solution**:</span></span>

    -   <span data-ttu-id="bbeec-154">如果 GPO 名稱出現在 [**受控**]、[無法**控制**] 或 [**擱置**] 索引標籤上，請選擇其他名稱。</span><span class="sxs-lookup"><span data-stu-id="bbeec-154">If the GPO name appears on the **Controlled**, **Uncontrolled**, or **Pending** tab, choose another name.</span></span> <span data-ttu-id="bbeec-155">如果部署的 GPO 已重新命名但尚未重新部署，則會顯示在生產環境中其舊名稱下方。</span><span class="sxs-lookup"><span data-stu-id="bbeec-155">If a GPO that was deployed is renamed but not yet redeployed, it will be displayed under its old name in the production environment.</span></span> <span data-ttu-id="bbeec-156">因此，仍在使用舊名稱。</span><span class="sxs-lookup"><span data-stu-id="bbeec-156">Therefore, the old name is still being used.</span></span> <span data-ttu-id="bbeec-157">重新部署 GPO 以在生產環境中更新其名稱，然後發行該名稱以供另一個 GPO 使用。</span><span class="sxs-lookup"><span data-stu-id="bbeec-157">Redeploy the GPO to update its name in the production environment and release that name for use by another GPO.</span></span>

    -   <span data-ttu-id="bbeec-158">如果 GPO 名稱未出現在 [**受控**]、[無法**控制**] 或 [**擱置**中] 索引標籤上，您可能就無權列出該 gpo。</span><span class="sxs-lookup"><span data-stu-id="bbeec-158">If the GPO name does not appear on the **Controlled**, **Uncontrolled**, or **Pending** tab, you may lack permission to list the GPO.</span></span> <span data-ttu-id="bbeec-159">若要要求許可權，請聯絡 AGPM 系統管理員。</span><span class="sxs-lookup"><span data-stu-id="bbeec-159">To request permission, contact an AGPM Administrator.</span></span>

### <a href="" id="bkmk-email"></a><span data-ttu-id="bbeec-160">我沒有收到 AGPM 電子郵件通知</span><span class="sxs-lookup"><span data-stu-id="bbeec-160">I am not receiving AGPM e-mail notifications</span></span>

-   <span data-ttu-id="bbeec-161">**原因**：尚未提供有效的 SMTP 電子郵件伺服器和電子郵件地址，或未採取任何產生電子郵件通知的動作。</span><span class="sxs-lookup"><span data-stu-id="bbeec-161">**Cause**: A valid SMTP e-mail server and e-mail address has not been provided, or no action has been taken that generates an e-mail notification.</span></span>

-   <span data-ttu-id="bbeec-162">**解決方案**：</span><span class="sxs-lookup"><span data-stu-id="bbeec-162">**Solution**:</span></span>

    -   <span data-ttu-id="bbeec-163">如果您是 AGPM 系統管理員：針對供 agpm 傳送之待執行動作的電子郵件通知，AGPM 管理員必須在 [**網域委派**] 索引標籤上為核准者提供有效的 SMTP 電子郵件伺服器和電子郵件地址。如需詳細資訊，請參閱[設定電子郵件通知](configure-e-mail-notification-agpm30ops.md)。</span><span class="sxs-lookup"><span data-stu-id="bbeec-163">If you are an AGPM Administrator: For e-mail notifications about pending actions to be sent by AGPM, an AGPM Administrator must provide a valid SMTP e-mail server and e-mail addresses for Approvers on the **Domain Delegation** tab. For more information, see [Configure E-Mail Notification](configure-e-mail-notification-agpm30ops.md).</span></span>

    -   <span data-ttu-id="bbeec-164">電子郵件通知只會在缺少建立、部署或刪除 GPO 所需許可權的編輯者、檢閱者或其他群組原則管理員處產生，以提交其中一個動作的要求。</span><span class="sxs-lookup"><span data-stu-id="bbeec-164">E-mail notifications are generated only when an Editor, Reviewer, or other Group Policy administrator who lacks the permission necessary to create, deploy, or delete a GPO submits a request for one of those actions to occur.</span></span> <span data-ttu-id="bbeec-165">不會自動通知核准或拒絕要求。</span><span class="sxs-lookup"><span data-stu-id="bbeec-165">There is no automatic notification of approval or rejection of a request.</span></span>

### <a href="" id="bkmk-port"></a><span data-ttu-id="bbeec-166">我無法將埠4600用於 AGPM 服務</span><span class="sxs-lookup"><span data-stu-id="bbeec-166">I cannot use port 4600 for the AGPM Service</span></span>

-   <span data-ttu-id="bbeec-167">**原因**：根據預設，AGPM 服務偵聽的埠是埠4600。</span><span class="sxs-lookup"><span data-stu-id="bbeec-167">**Cause**: By default, the port on which the AGPM Service listens is port 4600.</span></span>

-   <span data-ttu-id="bbeec-168">**解決方案**：如果 agpm 服務無法使用埠4600，請在 agpm 伺服器上修改埠設定，以使用另一個埠，然後在 Agpm 用戶端的 agpm 伺服器連線中更新埠。</span><span class="sxs-lookup"><span data-stu-id="bbeec-168">**Solution**: If port 4600 is not available for the AGPM Service, modify the port configuration on the AGPM Server to use another port and then update the port in the AGPM Server connection for AGPM Clients.</span></span> <span data-ttu-id="bbeec-169">如需詳細資訊，請參閱[修改 AGPM 服務](modify-the-agpm-service-agpm30ops.md)。</span><span class="sxs-lookup"><span data-stu-id="bbeec-169">For more information, see [Modify the AGPM Service](modify-the-agpm-service-agpm30ops.md).</span></span>

### <a href="" id="bkmk-not-start"></a><span data-ttu-id="bbeec-170">AGPM 服務將無法啟動</span><span class="sxs-lookup"><span data-stu-id="bbeec-170">The AGPM Service will not start</span></span>

-   <span data-ttu-id="bbeec-171">**原因**：您在 [**管理工具**及**服務**] 底下的作業系統中修改了 AGPM 服務的設定。</span><span class="sxs-lookup"><span data-stu-id="bbeec-171">**Cause**: You have modified settings for the AGPM Service in the operating system under **Administrative Tools** and **Services**.</span></span>

-   <span data-ttu-id="bbeec-172">**解決方案**：修改**Microsoft 高級群組原則管理的設定-伺服器**[控制台] 中的 [**程式和功能**]。</span><span class="sxs-lookup"><span data-stu-id="bbeec-172">**Solution**: Modify the settings for **Microsoft Advanced Group Policy Management - Server** under **Programs and Features** in Control Panel.</span></span> <span data-ttu-id="bbeec-173">如需詳細資訊，請參閱[修改 AGPM 服務](modify-the-agpm-service-agpm30ops.md)。</span><span class="sxs-lookup"><span data-stu-id="bbeec-173">For more information, see [Modify the AGPM Service](modify-the-agpm-service-agpm30ops.md).</span></span>

### <a href="" id="bkmk-software-installation"></a><span data-ttu-id="bbeec-174">[群組原則軟體安裝] 無法安裝軟體</span><span class="sxs-lookup"><span data-stu-id="bbeec-174">Group Policy Software Installation fails to install software</span></span>

-   <span data-ttu-id="bbeec-175">**原因**： AGPM 會保留群組原則軟體安裝套件的完整性。</span><span class="sxs-lookup"><span data-stu-id="bbeec-175">**Cause**: AGPM preserves the integrity of Group Policy Software Installation packages.</span></span> <span data-ttu-id="bbeec-176">雖然 Gpo 是以離線方式編輯，但會保留封裝用戶端資訊以外的套件之間的連結。</span><span class="sxs-lookup"><span data-stu-id="bbeec-176">Although GPOs are edited offline, links between packages in addition to cached client information are preserved.</span></span> <span data-ttu-id="bbeec-177">這是原本設計的做法。</span><span class="sxs-lookup"><span data-stu-id="bbeec-177">This is by design.</span></span>

-   <span data-ttu-id="bbeec-178">**解決方案**：當您使用 AGPM 離線編輯 GPO 時，請將另一個 gpo 中的任何群群組原則軟體安裝升級為參考已部署的 gpo，而非已取出的複本。</span><span class="sxs-lookup"><span data-stu-id="bbeec-178">**Solution**: When you edit a GPO offline with AGPM, configure any Group Policy Software Installation upgrade of a package in another GPO to reference the deployed GPO, not the checked-out copy.</span></span> <span data-ttu-id="bbeec-179">編輯器必須擁有已部署 GPO 的**讀取**許可權。</span><span class="sxs-lookup"><span data-stu-id="bbeec-179">The Editor must have **Read** permission for the deployed GPO.</span></span>

### <a href="" id="bkmk-error-on-restore"></a><span data-ttu-id="bbeec-180">將封存還原到新的 AGPM 服務器時，發生錯誤</span><span class="sxs-lookup"><span data-stu-id="bbeec-180">An error occurred when I restored the archive to a new AGPM Server</span></span>

-   <span data-ttu-id="bbeec-181">**原因**：出於安全性考慮，保護在 [**網域委派**] 索引標籤上輸入之密碼的加密，如果將封存移到另一部電腦，就會導致密碼失敗。</span><span class="sxs-lookup"><span data-stu-id="bbeec-181">**Cause**: For security reasons, the encryption protecting the password entered on the **Domain Delegation** tab causes the password to fail if the archive is moved to another computer.</span></span>

-   <span data-ttu-id="bbeec-182">**解決方案**：重新輸入並確認 [**網域委派**] 索引標籤上的密碼。如需詳細資訊，請參閱[設定電子郵件通知](configure-e-mail-notification-agpm30ops.md)。</span><span class="sxs-lookup"><span data-stu-id="bbeec-182">**Solution**: Re-enter and confirm the password on the **Domain Delegation** tab. For more information, see [Configure E-Mail Notification](configure-e-mail-notification-agpm30ops.md).</span></span>

 

 





