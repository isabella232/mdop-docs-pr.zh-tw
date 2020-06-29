---
title: 疑難排解進階群組原則管理
description: 疑難排解進階群組原則管理
author: dansimp
ms.assetid: f58849cf-6c5b-44d8-b356-0ed7a5b24cee
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c22b9a0983b26252ee0d9c8d99b63cd4ab5dc2b6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801742"
---
# <span data-ttu-id="d5147-103">疑難排解進階群組原則管理</span><span class="sxs-lookup"><span data-stu-id="d5147-103">Troubleshooting Advanced Group Policy Management</span></span>


<span data-ttu-id="d5147-104">本節列出在使用高級群組原則管理（Gpo）管理群組原則物件時可能會遇到的一些常見問題。</span><span class="sxs-lookup"><span data-stu-id="d5147-104">This section lists a few common issues you may encounter when using Advanced Group Policy Management (AGPM) to manage Group Policy objects (GPOs).</span></span>

## <span data-ttu-id="d5147-105">您遇到什麼問題？</span><span class="sxs-lookup"><span data-stu-id="d5147-105">What problems are you having?</span></span>


-   [<span data-ttu-id="d5147-106">我無法存取封存</span><span class="sxs-lookup"><span data-stu-id="d5147-106">I am unable to access an archive</span></span>](#bkmk-access-an-archive)

-   [<span data-ttu-id="d5147-107">不同群組原則管理員的 GPO 狀態會有所不同</span><span class="sxs-lookup"><span data-stu-id="d5147-107">The GPO state varies for different Group Policy administrators</span></span>](#bkmk-state-varies)

-   [<span data-ttu-id="d5147-108">我無法修改 AGPM 服務器連線</span><span class="sxs-lookup"><span data-stu-id="d5147-108">I am unable to modify the AGPM Server connection</span></span>](#bkmk-modify-archive-location)

-   [<span data-ttu-id="d5147-109">我無法變更預設範本或查看、建立、編輯、重新命名、部署或刪除 Gpo</span><span class="sxs-lookup"><span data-stu-id="d5147-109">I am unable to change the default template or view, create, edit, rename, deploy, or delete GPOs</span></span>](#bkmk-perform-task)

-   [<span data-ttu-id="d5147-110">我無法使用特定的 GPO 名稱</span><span class="sxs-lookup"><span data-stu-id="d5147-110">I am unable to use a particular GPO name</span></span>](#bkmk-use-particular-name)

-   [<span data-ttu-id="d5147-111">我沒有收到 AGPM 電子郵件通知</span><span class="sxs-lookup"><span data-stu-id="d5147-111">I am not receiving AGPM e-mail notifications</span></span>](#bkmk-email)

-   [<span data-ttu-id="d5147-112">我無法將埠4600用於 AGPM 服務</span><span class="sxs-lookup"><span data-stu-id="d5147-112">I cannot use port 4600 for the AGPM Service</span></span>](#bkmk-port)

-   [<span data-ttu-id="d5147-113">AGPM 服務將無法啟動</span><span class="sxs-lookup"><span data-stu-id="d5147-113">The AGPM Service will not start</span></span>](#bkmk-not-start)

-   [<span data-ttu-id="d5147-114">[群組原則軟體安裝] 無法安裝軟體</span><span class="sxs-lookup"><span data-stu-id="d5147-114">Group Policy Software Installation fails to install software</span></span>](#bkmk-software-installation)

### <a href="" id="bkmk-access-an-archive"></a><span data-ttu-id="d5147-115">我無法存取封存</span><span class="sxs-lookup"><span data-stu-id="d5147-115">I am unable to access an archive</span></span>

-   <span data-ttu-id="d5147-116">**原因**：您沒有選取正確的伺服器和埠來進行封存。</span><span class="sxs-lookup"><span data-stu-id="d5147-116">**Cause**: You have not selected the correct server and port for the archive.</span></span>

-   <span data-ttu-id="d5147-117">**解決方案**：</span><span class="sxs-lookup"><span data-stu-id="d5147-117">**Solution**:</span></span>

    -   <span data-ttu-id="d5147-118">如果您是 AGPM 系統管理員：請參閱[設定 AGPM 服務器](configure-the-agpm-server-connection.md)連線。</span><span class="sxs-lookup"><span data-stu-id="d5147-118">If you are an AGPM Administrator: See [Configure the AGPM Server Connection](configure-the-agpm-server-connection.md).</span></span>

    -   <span data-ttu-id="d5147-119">如果您不是 AGPM 系統管理員：從 AGPM 系統管理員要求 AGPM 服務器的連線詳細資料。</span><span class="sxs-lookup"><span data-stu-id="d5147-119">If you are not an AGPM Administrator: Request connection details for the AGPM Server from an AGPM Administrator.</span></span> <span data-ttu-id="d5147-120">請參閱[設定 AGPM 服務器](configure-the-agpm-server-connection-reviewer.md)連線。</span><span class="sxs-lookup"><span data-stu-id="d5147-120">See [Configure the AGPM Server Connection](configure-the-agpm-server-connection-reviewer.md).</span></span>

-   <span data-ttu-id="d5147-121">**原因**： [高級] 群組原則管理服務未執行。</span><span class="sxs-lookup"><span data-stu-id="d5147-121">**Cause**: The Advanced Group Policy Management Service is not running.</span></span>

-   <span data-ttu-id="d5147-122">**解決方案**：</span><span class="sxs-lookup"><span data-stu-id="d5147-122">**Solution**:</span></span>

    -   <span data-ttu-id="d5147-123">如果您是 AGPM 系統管理員：啟動 AGPM 服務。</span><span class="sxs-lookup"><span data-stu-id="d5147-123">If you are an AGPM Administrator: Start the AGPM Service.</span></span> <span data-ttu-id="d5147-124">如需詳細資訊，請參閱[啟動和停止 AGPM 服務](start-and-stop-the-agpm-service.md)。</span><span class="sxs-lookup"><span data-stu-id="d5147-124">For more information, see [Start and Stop the AGPM Service](start-and-stop-the-agpm-service.md).</span></span>

    -   <span data-ttu-id="d5147-125">如果您不是 AGPM 系統管理員：請與 AGPM 系統管理員聯繫以取得協助。</span><span class="sxs-lookup"><span data-stu-id="d5147-125">If you are not an AGPM Administrator: Contact an AGPM Administrator for assistance.</span></span>

### <a href="" id="bkmk-state-varies"></a><span data-ttu-id="d5147-126">不同群組原則管理員的 GPO 狀態會有所不同</span><span class="sxs-lookup"><span data-stu-id="d5147-126">The GPO state varies for different Group Policy administrators</span></span>

-   <span data-ttu-id="d5147-127">**原因**：不同的群組原則管理員針對相同的封存選取了不同的 AGPM 服務器。</span><span class="sxs-lookup"><span data-stu-id="d5147-127">**Cause**: Different Group Policy administrators have selected different AGPM Servers for the same archive.</span></span>

-   <span data-ttu-id="d5147-128">**解決方案**：</span><span class="sxs-lookup"><span data-stu-id="d5147-128">**Solution**:</span></span>

    -   <span data-ttu-id="d5147-129">如果您是 AGPM 系統管理員：請參閱[設定 AGPM 服務器](configure-the-agpm-server-connection.md)連線。</span><span class="sxs-lookup"><span data-stu-id="d5147-129">If you are an AGPM Administrator: See [Configure the AGPM Server Connection](configure-the-agpm-server-connection.md).</span></span>

    -   <span data-ttu-id="d5147-130">如果您不是 AGPM 系統管理員：從 AGPM 系統管理員要求 AGPM 服務器的連線詳細資料。</span><span class="sxs-lookup"><span data-stu-id="d5147-130">If you are not an AGPM Administrator: Request connection details for the AGPM Server from an AGPM Administrator.</span></span> <span data-ttu-id="d5147-131">請參閱[設定 AGPM 服務器](configure-the-agpm-server-connection-reviewer.md)連線。</span><span class="sxs-lookup"><span data-stu-id="d5147-131">See [Configure the AGPM Server Connection](configure-the-agpm-server-connection-reviewer.md).</span></span>

### <a href="" id="bkmk-modify-archive-location"></a><span data-ttu-id="d5147-132">我無法修改 AGPM 服務器連線</span><span class="sxs-lookup"><span data-stu-id="d5147-132">I am unable to modify the AGPM Server connection</span></span>

-   <span data-ttu-id="d5147-133">**原因**：如果 [ **agpm 伺服器**] 索引標籤上的 [設定] 無法使用，則 Agpm 伺服器已使用管理樣板集中進行集中設定。</span><span class="sxs-lookup"><span data-stu-id="d5147-133">**Cause**: If the settings on the **AGPM Server** tab are unavailable, the AGPM Server has been centrally configured using an Administrative template.</span></span>

-   <span data-ttu-id="d5147-134">**解決方案**：</span><span class="sxs-lookup"><span data-stu-id="d5147-134">**Solution**:</span></span>

    -   <span data-ttu-id="d5147-135">如果您是 AGPM 系統管理員：如果 [ **Agpm 伺服器**] 索引標籤上的 [設定] 無法使用，請參閱[設定 agpm 伺服器](configure-the-agpm-server-connection.md)連線。</span><span class="sxs-lookup"><span data-stu-id="d5147-135">If you are an AGPM Administrator: If the settings on the **AGPM Server** tab are unavailable, see [Configure the AGPM Server Connection](configure-the-agpm-server-connection.md).</span></span>

    -   <span data-ttu-id="d5147-136">如果您不是 AGPM 系統管理員：如果 [ **Agpm 伺服器**] 索引標籤上的 [設定] 無法使用，您就不需要修改 agpm 伺服器。</span><span class="sxs-lookup"><span data-stu-id="d5147-136">If you are not an AGPM Administrator: If the settings on the **AGPM Server** tab are unavailable, you do not need to modify the AGPM Server.</span></span>

### <a href="" id="bkmk-perform-task"></a><span data-ttu-id="d5147-137">我無法變更預設範本或查看、建立、編輯、重新命名、部署或刪除 Gpo</span><span class="sxs-lookup"><span data-stu-id="d5147-137">I am unable to change the default template or view, create, edit, rename, deploy, or delete GPOs</span></span>

-   <span data-ttu-id="d5147-138">**原因**：您沒有獲指派角色，且擁有執行任務所需的許可權。</span><span class="sxs-lookup"><span data-stu-id="d5147-138">**Cause**: You have not been assigned a role with the permissions required to perform the task or tasks.</span></span>

-   <span data-ttu-id="d5147-139">**解決方案**：</span><span class="sxs-lookup"><span data-stu-id="d5147-139">**Solution**:</span></span>

    -   <span data-ttu-id="d5147-140">如果您是 AGPM 系統管理員：請參閱[委派網域層級存取](delegate-domain-level-access.md)權和[委派對個別 GPO 的存取權](delegate-access-to-an-individual-gpo.md)。</span><span class="sxs-lookup"><span data-stu-id="d5147-140">If you are an AGPM Administrator: See [Delegate Domain-Level Access](delegate-domain-level-access.md) and [Delegate Access to an Individual GPO](delegate-access-to-an-individual-gpo.md).</span></span> <span data-ttu-id="d5147-141">AGPM 許可權會從網域級聯到目前封存中的所有 Gpo。</span><span class="sxs-lookup"><span data-stu-id="d5147-141">AGPM permissions will cascade from the domain to all GPOs currently in the archive.</span></span> <span data-ttu-id="d5147-142">隨著新的群組原則系統管理員新增在網域層級，他們的許可權必須設定為適用于**這個物件和嵌套物件**。</span><span class="sxs-lookup"><span data-stu-id="d5147-142">As new Group Policy administrators are added at the domain level, their permissions must be set to apply to **This object and nested objects**.</span></span> <span data-ttu-id="d5147-143">如需哪些角色可以執行工作的詳細資料，以及執行工作所需的許可權，請參閱該工作的說明。</span><span class="sxs-lookup"><span data-stu-id="d5147-143">For details about which roles can perform a task and what permissions are necessary to perform a task, refer to the help for that task.</span></span>

    -   <span data-ttu-id="d5147-144">如果您不是 AGPM 系統管理員，且需要其他角色或許可權：請與 AGPM 系統管理員聯繫以取得協助。</span><span class="sxs-lookup"><span data-stu-id="d5147-144">If you are not an AGPM Administrator and you require additional roles or permissions: Contact an AGPM Administrator for assistance.</span></span> <span data-ttu-id="d5147-145">請注意，如果您是「編輯」，您可以開始建立 GPO、部署 GPO 或從生產環境刪除 GPO 的程式，但核准者或 AGPM 管理員必須核准您的要求。</span><span class="sxs-lookup"><span data-stu-id="d5147-145">Note that if you are an Editor, you can begin the process of creating a GPO, deploying a GPO, or deleting a GPO from the production environment, but an Approver or AGPM Administrator must approve your request.</span></span>

### <a href="" id="bkmk-use-particular-name"></a><span data-ttu-id="d5147-146">我無法使用特定的 GPO 名稱</span><span class="sxs-lookup"><span data-stu-id="d5147-146">I am unable to use a particular GPO name</span></span>

-   <span data-ttu-id="d5147-147">**原因**：此 gpo 名稱已在使用中，或您無權列出該 gpo。</span><span class="sxs-lookup"><span data-stu-id="d5147-147">**Cause**: Either the GPO name is already in use or you lack permission to list the GPO.</span></span>

-   <span data-ttu-id="d5147-148">**解決方案**：</span><span class="sxs-lookup"><span data-stu-id="d5147-148">**Solution**:</span></span>

    -   <span data-ttu-id="d5147-149">如果 GPO 名稱出現在 [**受控**]、[無法**控制**] 或 [**擱置**] 索引標籤上，請選擇其他名稱。</span><span class="sxs-lookup"><span data-stu-id="d5147-149">If the GPO name appears on the **Controlled**, **Uncontrolled**, or **Pending** tab, choose another name.</span></span> <span data-ttu-id="d5147-150">如果已部署的 GPO 已重新命名但尚未重新部署，則會顯示在生產環境中其舊名稱下方，因此舊名稱仍在使用中。</span><span class="sxs-lookup"><span data-stu-id="d5147-150">If a GPO that has been deployed is renamed but not yet redeployed, it will be displayed under its old name in the production environment—therefore, the old name is still in use.</span></span> <span data-ttu-id="d5147-151">重新部署 GPO 以在生產環境中更新其名稱，然後發行該名稱以供另一個 GPO 使用。</span><span class="sxs-lookup"><span data-stu-id="d5147-151">Redeploy the GPO to update its name in the production environment and release that name for use by another GPO.</span></span>

    -   <span data-ttu-id="d5147-152">如果 GPO 名稱未出現在 [**受控**]、[無法**控制**] 或 [**擱置**中] 索引標籤上，您可能就無權列出該 gpo。</span><span class="sxs-lookup"><span data-stu-id="d5147-152">If the GPO name does not appear on the **Controlled**, **Uncontrolled**, or **Pending** tab, you may lack permission to list the GPO.</span></span> <span data-ttu-id="d5147-153">若要要求許可權，請聯絡 AGPM 系統管理員。</span><span class="sxs-lookup"><span data-stu-id="d5147-153">To request permission, contact an AGPM Administrator.</span></span>

### <a href="" id="bkmk-email"></a><span data-ttu-id="d5147-154">我沒有收到 AGPM 電子郵件通知</span><span class="sxs-lookup"><span data-stu-id="d5147-154">I am not receiving AGPM e-mail notifications</span></span>

-   <span data-ttu-id="d5147-155">**原因**：尚未提供有效的 SMTP 電子郵件伺服器和電子郵件地址，或未採取任何產生電子郵件通知的動作。</span><span class="sxs-lookup"><span data-stu-id="d5147-155">**Cause**: A valid SMTP e-mail server and e-mail address has not been provided, or no action has been taken that generates an e-mail notification.</span></span>

-   <span data-ttu-id="d5147-156">**解決方案**：</span><span class="sxs-lookup"><span data-stu-id="d5147-156">**Solution**:</span></span>

    -   <span data-ttu-id="d5147-157">如果您是 AGPM 系統管理員：針對供 agpm 傳送之待執行動作的電子郵件通知，AGPM 管理員必須在 [**網域委派**] 索引標籤上為核准者提供有效的 SMTP 電子郵件伺服器和電子郵件地址。如需詳細資訊，請參閱[設定電子郵件通知](configure-e-mail-notification.md)。</span><span class="sxs-lookup"><span data-stu-id="d5147-157">If you are an AGPM Administrator: For e-mail notifications about pending actions to be sent by AGPM, an AGPM Administrator must provide a valid SMTP e-mail server and e-mail addresses for Approvers on the **Domain Delegation** tab. For more information, see [Configure E-Mail Notification](configure-e-mail-notification.md).</span></span>

    -   <span data-ttu-id="d5147-158">電子郵件通知只會在缺少建立、部署或刪除 GPO 所需許可權的編輯者、檢閱者或其他群組原則管理員處產生，以提交其中一個動作的要求。</span><span class="sxs-lookup"><span data-stu-id="d5147-158">E-mail notifications are generated only when an Editor, Reviewer, or other Group Policy administrator who lacks the permission necessary to create, deploy, or delete a GPO submits a request for one of those actions to occur.</span></span> <span data-ttu-id="d5147-159">不會自動通知核准或拒絕要求。</span><span class="sxs-lookup"><span data-stu-id="d5147-159">There is no automatic notification of approval or rejection of a request.</span></span>

### <a href="" id="bkmk-port"></a><span data-ttu-id="d5147-160">我無法將埠4600用於 AGPM 服務</span><span class="sxs-lookup"><span data-stu-id="d5147-160">I cannot use port 4600 for the AGPM Service</span></span>

-   <span data-ttu-id="d5147-161">**原因**：根據預設，AGPM 服務偵聽的埠是埠4600。</span><span class="sxs-lookup"><span data-stu-id="d5147-161">**Cause**: By default, the port on which the AGPM Service listens is port 4600.</span></span>

-   <span data-ttu-id="d5147-162">**解決方案**：如果 AGPM 服務無法使用埠4600，請修改每個封存索引檔案，以使用另一個埠，然後為所有群組原則管理員更新 AGPM 服務器。</span><span class="sxs-lookup"><span data-stu-id="d5147-162">**Solution**: If port 4600 is not available for the AGPM Service, modify each archive index file to use another port and then update the AGPM Server for all Group Policy administrators.</span></span> <span data-ttu-id="d5147-163">如需詳細資訊，請參閱[修改 AGPM 服務偵聽的埠](modify-the-port-on-which-the-agpm-service-listens.md)。</span><span class="sxs-lookup"><span data-stu-id="d5147-163">For more information, see [Modify the Port on Which the AGPM Service Listens](modify-the-port-on-which-the-agpm-service-listens.md).</span></span>

### <a href="" id="bkmk-not-start"></a><span data-ttu-id="d5147-164">AGPM 服務將無法啟動</span><span class="sxs-lookup"><span data-stu-id="d5147-164">The AGPM Service will not start</span></span>

-   <span data-ttu-id="d5147-165">**原因**：您在 [**管理工具**及**服務**] 底下的作業系統中修改了 AGPM 服務的設定。</span><span class="sxs-lookup"><span data-stu-id="d5147-165">**Cause**: You have modified settings for the AGPM Service in the operating system under **Administrative Tools** and **Services**.</span></span>

-   <span data-ttu-id="d5147-166">**解決方案**：修改**Microsoft 高級群組原則管理的設定-伺服器（** 在 [**新增或移除程式**] 底下）。</span><span class="sxs-lookup"><span data-stu-id="d5147-166">**Solution**: Modify the settings for **Microsoft Advanced Group Policy Management - Server** under **Add or Remove Programs**.</span></span> <span data-ttu-id="d5147-167">如需詳細資訊，請參閱[修改 AGPM 服務帳戶](modify-the-agpm-service-account.md)。</span><span class="sxs-lookup"><span data-stu-id="d5147-167">For more information, see [Modify the AGPM Service Account](modify-the-agpm-service-account.md).</span></span>

### <a href="" id="bkmk-software-installation"></a><span data-ttu-id="d5147-168">[群組原則軟體安裝] 無法安裝軟體</span><span class="sxs-lookup"><span data-stu-id="d5147-168">Group Policy Software Installation fails to install software</span></span>

-   <span data-ttu-id="d5147-169">**原因**： AGPM 會保留群組原則軟體安裝套件的完整性。</span><span class="sxs-lookup"><span data-stu-id="d5147-169">**Cause**: AGPM preserves the integrity of Group Policy Software Installation packages.</span></span> <span data-ttu-id="d5147-170">雖然 Gpo 是以離線方式編輯，但會保留套件之間的連結，以及緩存的用戶端資訊。</span><span class="sxs-lookup"><span data-stu-id="d5147-170">Although GPOs are edited offline, links between packages as well as cached client information are preserved.</span></span> <span data-ttu-id="d5147-171">這是原本設計的做法。</span><span class="sxs-lookup"><span data-stu-id="d5147-171">This is by design.</span></span>

-   <span data-ttu-id="d5147-172">**解決方案**：使用 AGPM 離線編輯 GPO 時，請將另一個 gpo 中的任何群群組原則軟體安裝升級為參考已部署的 gpo，而不是取出的複本。</span><span class="sxs-lookup"><span data-stu-id="d5147-172">**Solution**: When editing a GPO offline with AGPM, configure any Group Policy Software Installation upgrade of a package in another GPO to reference the deployed GPO, not the checked-out copy.</span></span> <span data-ttu-id="d5147-173">編輯器必須擁有已部署 GPO 的**讀取**許可權。</span><span class="sxs-lookup"><span data-stu-id="d5147-173">The Editor must have **Read** permission for the deployed GPO.</span></span>

 

 





