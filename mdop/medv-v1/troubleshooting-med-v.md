---
title: 疑難排解 MED-V
description: 疑難排解 MED-V
author: dansimp
ms.assetid: f43dae36-6485-4e06-9c66-0a646e27079d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 38d13be699a92368ff258026acd8e0d5f0e28cd6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811409"
---
# <span data-ttu-id="463bc-103">疑難排解 MED-V</span><span class="sxs-lookup"><span data-stu-id="463bc-103">Troubleshooting MED-V</span></span>


<span data-ttu-id="463bc-104">本節提供的資訊可協助針對 Microsoft 企業版桌面虛擬化（MED-V）的一般問題進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="463bc-104">This section provides information to help troubleshoot general issues with Microsoft Enterprise Desktop Virtualization (MED-V).</span></span>

## <span data-ttu-id="463bc-105">變更主機解析度，然後最大化 MED-V 工作區，使桌面看起來像是黑色</span><span class="sxs-lookup"><span data-stu-id="463bc-105">Changing the host resolution and then maximizing the MED-V workspace causes the desktop to appear black</span></span>


<span data-ttu-id="463bc-106">在完整的桌面圖案中工作時，如果您變更主機解析度，然後最大化 MED-V 工作區視窗，則桌面會出現黑色，而 MED-V 工作區可能不會回應。</span><span class="sxs-lookup"><span data-stu-id="463bc-106">When working in full desktop mode, if you change the host resolution and then maximize the MED-V workspace window, the desktop appears black and the MED-V workspace might not respond.</span></span>

### <span data-ttu-id="463bc-107">解決方案</span><span class="sxs-lookup"><span data-stu-id="463bc-107">Solution</span></span>

<span data-ttu-id="463bc-108">停止並啟動 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="463bc-108">Stop and then start the MED-V workspace.</span></span>

## <span data-ttu-id="463bc-109">在已停用網路介面卡的情況下啟動 MED-V 工作區，然後再啟用配接器並不會還原網路連線</span><span class="sxs-lookup"><span data-stu-id="463bc-109">Starting a MED-V workspace with a network adapter disabled and then later enabling the adapter does not restore network connectivity</span></span>


<span data-ttu-id="463bc-110">如果您在 bridge 模式中設定 MED-V 工作區，然後在已停用網路介面卡的情況下啟動 MED-V 工作區，則如果稍後啟用該配接器，則無法還原透過該配接器的網路連線。</span><span class="sxs-lookup"><span data-stu-id="463bc-110">If you configure a MED-V workspace in bridge mode and then start the MED-V workspace while a network adapter is disabled, if the adapter is later enabled, the network connectivity through that adapter is not restored.</span></span>

### <span data-ttu-id="463bc-111">解決方案</span><span class="sxs-lookup"><span data-stu-id="463bc-111">Solution</span></span>

<span data-ttu-id="463bc-112">停止並啟動 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="463bc-112">Stop and then start the MED-V workspace.</span></span>

## <span data-ttu-id="463bc-113">每個電腦只有一個 Windows 使用者可以使用影像</span><span class="sxs-lookup"><span data-stu-id="463bc-113">An image can be used by only one Windows user per computer</span></span>


<span data-ttu-id="463bc-114">MED-V 工作區圖像只能由下載或匯入影像的 Windows 使用者使用。</span><span class="sxs-lookup"><span data-stu-id="463bc-114">A MED-V workspace image can be used only by the Windows user who downloaded or imported the image.</span></span> <span data-ttu-id="463bc-115">只有在擁有下載的影像所在資料夾許可權的系統管理員，才可以使用此使用者。</span><span class="sxs-lookup"><span data-stu-id="463bc-115">This user is the only user aside from administrators who have permissions to the folder where the downloaded images are located.</span></span>

### <span data-ttu-id="463bc-116">解決方案</span><span class="sxs-lookup"><span data-stu-id="463bc-116">Solution</span></span>

<span data-ttu-id="463bc-117">在影像存放區上手動變更存取控制清單（ACL）。</span><span class="sxs-lookup"><span data-stu-id="463bc-117">Manually change the access control list (ACL) on the image store.</span></span>

## <span data-ttu-id="463bc-118">在已啟用使用者許可權的情況下，使用 Configuration Manager 安裝 MED-V-V 時，卸載失敗</span><span class="sxs-lookup"><span data-stu-id="463bc-118">When installing MED-V by using Configuration Manager with users rights enabled, uninstall fails</span></span>


<span data-ttu-id="463bc-119">如果 MED-V 是使用 Microsoft System Center Configuration Manager 安裝，且套件的 [執行] 模式設定為 [使用者權利]，則卸載失敗，並顯示錯誤訊息，指出只有系統管理使用者可以卸載 MED-V。</span><span class="sxs-lookup"><span data-stu-id="463bc-119">If MED-V is installed by using Microsoft System Center Configuration Manager and the run mode of the package is set to users rights, uninstall fails with an error message that says that only administrative users can uninstall MED-V.</span></span>

### <span data-ttu-id="463bc-120">解決方案</span><span class="sxs-lookup"><span data-stu-id="463bc-120">Solution</span></span>

<span data-ttu-id="463bc-121">為 MED-V 建立 Configuration Manager 套件時，請將 [執行模式] 設定為 [系統管理許可權]。</span><span class="sxs-lookup"><span data-stu-id="463bc-121">When creating a Configuration Manager package for MED-V, set the run mode to administrative rights.</span></span>

## <span data-ttu-id="463bc-122">當您使用公司部署系統安裝 MED-V-V 時，安裝會設定為在安裝之後執行用戶端，而您無法執行用戶端</span><span class="sxs-lookup"><span data-stu-id="463bc-122">When installing MED-V by using a corporate deployment system, where the installation is configured to run the client following installation, you cannot run the client</span></span>


<span data-ttu-id="463bc-123">如果 MED-V 是使用公司部署系統來安裝，且安裝套件是設定為在安裝之後執行 MED-V 用戶端，則在用戶端以 system 帳戶執行之後，您就無法看到用戶端正在執行（在通知區域中除外），而且您無法與其互動。</span><span class="sxs-lookup"><span data-stu-id="463bc-123">If MED-V is installed by using a corporate deployment system and the installation package is configured to run MED-V client following the installation, after the client is running under the system account, you cannot see that the client is running (except in the notification area), and you cannot interact with it.</span></span>

### <span data-ttu-id="463bc-124">解決方案</span><span class="sxs-lookup"><span data-stu-id="463bc-124">Solution</span></span>

<span data-ttu-id="463bc-125">當您使用公司部署系統安裝 MED-V 時，請使用*START \ _MEDV = 0* .msi 參數。</span><span class="sxs-lookup"><span data-stu-id="463bc-125">When installing MED-V by using a corporate deployment system, use the *START\_MEDV=0* .msi parameter.</span></span>

## <span data-ttu-id="463bc-126">MED-V 測試影像無法啟動</span><span class="sxs-lookup"><span data-stu-id="463bc-126">MED-V test image fails to start</span></span>


<span data-ttu-id="463bc-127">如果 MED-V 測試影像無法啟動，它將不會復原，而且所有未來的啟動都會失敗，並出現「GINA 無法載入」錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="463bc-127">If a MED-V test image fails to start, it will never recover and all future startups will fail with a “GINA fail to load” error message.</span></span>

### <span data-ttu-id="463bc-128">解決方案</span><span class="sxs-lookup"><span data-stu-id="463bc-128">Solution</span></span>

<span data-ttu-id="463bc-129">刪除現有的測試影像，然後重新建立。</span><span class="sxs-lookup"><span data-stu-id="463bc-129">Delete the existing test image and then re-create it.</span></span>

## <span data-ttu-id="463bc-130">在嘗試使用錯誤的認證加入網域之後，該影像在加入網域時永遠不會成功</span><span class="sxs-lookup"><span data-stu-id="463bc-130">After attempting to join a domain with the wrong credentials, the image never succeeds in joining the domain</span></span>


<span data-ttu-id="463bc-131">如果加入網域構造區塊（這是虛擬電腦的第一次設定腳本的一部分）發生配置錯誤，則在嘗試加入網域時，會導致 MED-V 工作區失敗。</span><span class="sxs-lookup"><span data-stu-id="463bc-131">If there is a configuration error in the join domain building block, which is part of the virtual machine first-time setup script, it causes the MED-V workspace to fail when attempting to join a domain.</span></span> <span data-ttu-id="463bc-132">修復配置錯誤之後，MED-V 工作區中包含的影像將無法加入網域。</span><span class="sxs-lookup"><span data-stu-id="463bc-132">After the configuration error is repaired, the image included in the MED-V workspace cannot join the domain.</span></span>

### <span data-ttu-id="463bc-133">解決方案</span><span class="sxs-lookup"><span data-stu-id="463bc-133">Solution</span></span>

<span data-ttu-id="463bc-134">如果已部署影像，請重新發佈影像。</span><span class="sxs-lookup"><span data-stu-id="463bc-134">If the image was deployed, redistribute the image.</span></span> <span data-ttu-id="463bc-135">如果影像是測試影像，請重新建立影像。</span><span class="sxs-lookup"><span data-stu-id="463bc-135">If the image was a test image, re-create the image.</span></span>

## <span data-ttu-id="463bc-136">MED-V 不支援多個監視器</span><span class="sxs-lookup"><span data-stu-id="463bc-136">MED-V does not support multiple monitors</span></span>


<span data-ttu-id="463bc-137">MED-V 不支援在多台監視器上顯示已發佈的應用程式。</span><span class="sxs-lookup"><span data-stu-id="463bc-137">MED-V does not support displaying published applications across multiple monitors.</span></span> <span data-ttu-id="463bc-138">已發佈的應用程式和其他用戶端視窗可能會顯示在錯誤的螢幕上，有時在畫面斷開連接之後，MED-V 會嘗試將畫面移至顯示器，讓連接的顯示器顯示為空白。</span><span class="sxs-lookup"><span data-stu-id="463bc-138">Published applications and other client windows may be displayed in the wrong screen, and sometimes after a screen is disconnected, MED-V attempts to send the screen to the monitor so that the connected monitor appears blank.</span></span>

### <span data-ttu-id="463bc-139">解決方案</span><span class="sxs-lookup"><span data-stu-id="463bc-139">Solution</span></span>

<span data-ttu-id="463bc-140">中斷其他螢幕，然後重新開機用戶端。</span><span class="sxs-lookup"><span data-stu-id="463bc-140">Disconnect the additional screen, and restart the client.</span></span>

## <span data-ttu-id="463bc-141">如果主機在 MED-V 工作區啟動期間當機當機，則 MED-V 工作區可能無法啟動</span><span class="sxs-lookup"><span data-stu-id="463bc-141">MED-V workspace might fail to start if the host crashes during MED-V workspace startup</span></span>


<span data-ttu-id="463bc-142">如果主機在 MED-V 工作區啟動程式中當機，且出現錯誤訊息，指出「根項目遺失」，則 MED-V 工作區可能會將資料新增至空白的虛擬機器設定（VMC）檔案，這會導致啟動程式失敗。</span><span class="sxs-lookup"><span data-stu-id="463bc-142">If the host crashes during the MED-V workspace startup process and an error message appears that says “Root element is missing,” the MED-V workspace might add data to an empty virtual machine configuration (VMC) file, which will cause the startup process to fail.</span></span>

### <span data-ttu-id="463bc-143">解決方案</span><span class="sxs-lookup"><span data-stu-id="463bc-143">Solution</span></span>

<span data-ttu-id="463bc-144">使用基底影像的 VMC 檔案取代空白的 VMC 檔案。</span><span class="sxs-lookup"><span data-stu-id="463bc-144">Replace the empty VMC file with a VMC file from the base image.</span></span>

## <span data-ttu-id="463bc-145">鍵盤在已發佈的應用程式視窗中沒有回應</span><span class="sxs-lookup"><span data-stu-id="463bc-145">The keyboard does not respond in published application windows</span></span>


<span data-ttu-id="463bc-146">在 MED-V 工作區中，如果您在已發佈的應用程式成為焦點時按下 Windows 標誌鍵，就不會再在已發佈的應用程式視窗中回應鍵盤。</span><span class="sxs-lookup"><span data-stu-id="463bc-146">In a MED-V workspace, if you press the Windows logo key when a published application is in focus, the keyboard no longer responds in published application windows.</span></span>

### <span data-ttu-id="463bc-147">解決方案</span><span class="sxs-lookup"><span data-stu-id="463bc-147">Solution</span></span>

<span data-ttu-id="463bc-148">在已發佈的應用程式成為焦點時，按下 Windows 標誌鍵。</span><span class="sxs-lookup"><span data-stu-id="463bc-148">Press the Windows logo key while a published application is in focus.</span></span>

## <span data-ttu-id="463bc-149">網域 MED-V-V 工作區無法更新網域認證</span><span class="sxs-lookup"><span data-stu-id="463bc-149">A domain MED-V workspace does not update domain credentials</span></span>


<span data-ttu-id="463bc-150">在網域環境中使用持久的 MED-V 工作區時，如果您變更網域密碼，MED-V 用戶端就不會更新 MED-V 工作區網域認證。</span><span class="sxs-lookup"><span data-stu-id="463bc-150">When using a persistent MED-V workspace in a domain environment, if you change your domain password, the MED-V client does not update the MED-V workspace domain credentials.</span></span> <span data-ttu-id="463bc-151">當已發佈的應用程式嘗試存取網路資源時，您會收到錯誤訊息，通知您認證已過期。</span><span class="sxs-lookup"><span data-stu-id="463bc-151">When a published application attempts to access a network resource, you will receive an error message notifying you that your credentials expired.</span></span>

### <span data-ttu-id="463bc-152">解決方案</span><span class="sxs-lookup"><span data-stu-id="463bc-152">Solution</span></span>

<span data-ttu-id="463bc-153">重新開機 MED-V 工作區作業系統。</span><span class="sxs-lookup"><span data-stu-id="463bc-153">Restart the MED-V workspace operating system.</span></span>

## <span data-ttu-id="463bc-154">最大化已發佈的應用程式視窗封面主機工作列</span><span class="sxs-lookup"><span data-stu-id="463bc-154">Maximized published application windows cover the host taskbar</span></span>


<span data-ttu-id="463bc-155">如果您將已發佈的應用程式視窗最大化至全螢幕，可能會覆蓋主機工作列。</span><span class="sxs-lookup"><span data-stu-id="463bc-155">If you maximize a published application window to full screen, it might cover the host taskbar.</span></span>

### <span data-ttu-id="463bc-156">解決方案</span><span class="sxs-lookup"><span data-stu-id="463bc-156">Solution</span></span>

<span data-ttu-id="463bc-157">執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="463bc-157">Do one of the following:</span></span>

<span data-ttu-id="463bc-158">最小化已發佈的應用程式視窗，以取得通知區域的存取權，並重新啟動 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="463bc-158">Minimize the published application window to gain access to the notification area, and restart the MED-V workspace.</span></span>

<span data-ttu-id="463bc-159">將已發佈的應用程式視窗最小化，然後將視窗還原至它的最大化狀態。</span><span class="sxs-lookup"><span data-stu-id="463bc-159">Minimize the published application window, and then restore the window to its maximized state.</span></span>

## <span data-ttu-id="463bc-160">在 MED-V Server Configuration Manager 中新增使用者或群組無法運作</span><span class="sxs-lookup"><span data-stu-id="463bc-160">Adding users or groups in the MED-V Server Configuration Manager does not work</span></span>


<span data-ttu-id="463bc-161">當您在 [**選取使用者或群組**] 對話方塊中新增使用者或群組時，選取的使用者或群組不會新增至 med-v Server 設定管理員的存取控制清單中。</span><span class="sxs-lookup"><span data-stu-id="463bc-161">When adding users or groups in the **Select Users or Groups** dialog box, the selected users or groups are not added to the access control list in the MED-V Server Configuration Manager.</span></span>

### <span data-ttu-id="463bc-162">解決方案</span><span class="sxs-lookup"><span data-stu-id="463bc-162">Solution</span></span>

<span data-ttu-id="463bc-163">使用 [**輸入使用者或組名**] 對話方塊新增使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="463bc-163">Add users or groups using the **Enter User or Group names** dialog box.</span></span> <span data-ttu-id="463bc-164">如需詳細資訊，請參閱[如何安裝和設定 Med-v 伺服器元件](how-to-install-and-configure-the-med-v-server-component.md#bkmk-configuringpermissions)。</span><span class="sxs-lookup"><span data-stu-id="463bc-164">For detailed information, see [How to Install and Configure the MED-V Server Component](how-to-install-and-configure-the-med-v-server-component.md#bkmk-configuringpermissions).</span></span>

## <span data-ttu-id="463bc-165">在已安裝 Windows 7 版 Windows Virtual PC 的電腦上，MED-V 無法運作</span><span class="sxs-lookup"><span data-stu-id="463bc-165">MED-V does not work on computers with Windows Virtual PC for Windows 7 installed</span></span>


<span data-ttu-id="463bc-166">MED-V 需要 Windows Virtual PC2007。</span><span class="sxs-lookup"><span data-stu-id="463bc-166">MED-V requires Windows Virtual PC2007.</span></span> <span data-ttu-id="463bc-167">Windows 虛擬電腦的 Windows7 和 Virtual PC2007 SP1 無法安裝在同一部電腦上。</span><span class="sxs-lookup"><span data-stu-id="463bc-167">Windows Virtual PC for Windows7 and Virtual PC2007 SP1 cannot be installed on the same computer.</span></span>

### <span data-ttu-id="463bc-168">解決方案</span><span class="sxs-lookup"><span data-stu-id="463bc-168">Solution</span></span>

<span data-ttu-id="463bc-169">在安裝 Virtual PC2007 SP1 和 MED-V 之前，請先卸載 Windows7 的虛擬電腦。</span><span class="sxs-lookup"><span data-stu-id="463bc-169">Uninstall Virtual PC for Windows7 before installing Virtual PC2007 SP1 and MED-V.</span></span>

## <a href="" id="med-v-does-not-support-virtual-pc-and-windows-xp-mode-images-"></a><span data-ttu-id="463bc-170">MED-V 不支援虛擬電腦和 WindowsXP 模式影像</span><span class="sxs-lookup"><span data-stu-id="463bc-170">MED-V does not support Virtual PC and WindowsXP Mode images</span></span>


<span data-ttu-id="463bc-171">MED-V 1.0 SP1 不支援由 Windows Virtual PC 為 Windows7 建立的影像。</span><span class="sxs-lookup"><span data-stu-id="463bc-171">MED-V1.0 SP1 does not support images created by Windows Virtual PC for Windows7.</span></span> <span data-ttu-id="463bc-172">如果使用 Windows7 影像的虛擬 PC，則在啟動期間用戶端將會失敗。</span><span class="sxs-lookup"><span data-stu-id="463bc-172">If a Virtual PC for Windows7 image is used, the client will fail during startup.</span></span>

### <span data-ttu-id="463bc-173">解決方案</span><span class="sxs-lookup"><span data-stu-id="463bc-173">Solution</span></span>

<span data-ttu-id="463bc-174">使用 Virtual PC2007 SP1 建立 MED-V 影像。</span><span class="sxs-lookup"><span data-stu-id="463bc-174">Create MED-V images by using Virtual PC2007 SP1.</span></span>

## <span data-ttu-id="463bc-175">Windows 防火牆會封鎖 Virtual PC2007 SP1 網路活動</span><span class="sxs-lookup"><span data-stu-id="463bc-175">Windows firewall blocks Virtual PC2007 SP1 network activity</span></span>


<span data-ttu-id="463bc-176">根據預設，Windows 防火牆會封鎖 Virtual PC2007 SP1 網路活動，當 Virtual PC2007 SP1 在用戶端電腦上啟動時，會出現防火牆訊息，攔截其啟動順序及所有網路存取。</span><span class="sxs-lookup"><span data-stu-id="463bc-176">By default, Windows firewall blocks Virtual PC2007 SP1 network activity, and when Virtual PC2007 SP1 initiates on the client computer, there is a firewall message that blocks its startup sequence and all network access.</span></span>

### <span data-ttu-id="463bc-177">解決方案</span><span class="sxs-lookup"><span data-stu-id="463bc-177">Solution</span></span>

<span data-ttu-id="463bc-178">在最終使用者使用 MED-V 之前，先使用 [群組原則] 來更新防火牆例外狀況。</span><span class="sxs-lookup"><span data-stu-id="463bc-178">Update the firewall exception by using Group Policy before MED-V is used by the end user.</span></span>

## <span data-ttu-id="463bc-179">當您升級用戶端時，會出現錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="463bc-179">When upgrading the client an error message appears</span></span>


<span data-ttu-id="463bc-180">當您將用戶端從 MED-V 1.0 升級到 MED-V 1.0 SP1 時，可能會出現一則訊息，通知您沒有定義 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="463bc-180">When upgrading the client from MED-V1.0 to MED-V1.0 SP1, a message may appear notifying you that no MED-V workspace is defined.</span></span>

### <span data-ttu-id="463bc-181">解決方案</span><span class="sxs-lookup"><span data-stu-id="463bc-181">Solution</span></span>

<span data-ttu-id="463bc-182">關閉用戶端並重新啟動。</span><span class="sxs-lookup"><span data-stu-id="463bc-182">Close the client and restart it.</span></span>

## <span data-ttu-id="463bc-183">相關主題</span><span class="sxs-lookup"><span data-stu-id="463bc-183">Related topics</span></span>


[<span data-ttu-id="463bc-184">MED-V 1.0 版本資訊</span><span class="sxs-lookup"><span data-stu-id="463bc-184">MED-V 1.0 Release Notes</span></span>](med-v-10-release-notesmedv-10.md)

[<span data-ttu-id="463bc-185">MED-V 1.0 SP1 和 SP2 版本資訊</span><span class="sxs-lookup"><span data-stu-id="463bc-185">MED-V 1.0 SP1 and SP2 Release Notes</span></span>](med-v-10-sp1-and-sp2-release-notesmedv-10-sp1.md)

 

 





