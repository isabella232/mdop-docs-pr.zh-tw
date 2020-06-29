---
title: 作業疑難排解
description: 作業疑難排解
author: dansimp
ms.assetid: 948d7869-accd-44da-974f-93409234dee7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 126b5fae517c59914dcb7fb155ef4ad47278b5bd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800169"
---
# <span data-ttu-id="1c555-103">作業疑難排解</span><span class="sxs-lookup"><span data-stu-id="1c555-103">Operations Troubleshooting</span></span>


<span data-ttu-id="1c555-104">本主題包含的資訊可協助您解決 Microsoft 企業桌面虛擬化（MED-V）2.0 中的一般操作問題。</span><span class="sxs-lookup"><span data-stu-id="1c555-104">This topic includes information that you can use to help troubleshoot general operational issues in Microsoft Enterprise Desktop Virtualization (MED-V) 2.0.</span></span>

## <span data-ttu-id="1c555-105">MED-V 作業中的疑難排解問題</span><span class="sxs-lookup"><span data-stu-id="1c555-105">Troubleshooting Issues in MED-V Operations</span></span>


<span data-ttu-id="1c555-106">當使用者執行 MED-V 和解決方案來協助您排查這些問題時，可能會遇到下列問題：</span><span class="sxs-lookup"><span data-stu-id="1c555-106">The following are some issues end users might encounter when they run MED-V and solutions to help troubleshoot these issues:</span></span>

<span data-ttu-id="1c555-107">**檔重定向失敗**。</span><span class="sxs-lookup"><span data-stu-id="1c555-107">**Documentation Redirection Fails**.</span></span> <span data-ttu-id="1c555-108">當使用者的 [我的文件] 資料夾指向網路位置時，通常會發生這個問題。</span><span class="sxs-lookup"><span data-stu-id="1c555-108">This issue typically occurs when an end user’s My Documents folder points to a network location.</span></span> <span data-ttu-id="1c555-109">Windows 不支援從另一個共用資料夾建立共用。</span><span class="sxs-lookup"><span data-stu-id="1c555-109">Windows does not support creating a share from another shared folder.</span></span> <span data-ttu-id="1c555-110">當磁碟機或資料夾重新導向至來賓時，RDP\\Windows 虛擬電腦會為該資料夾建立共用。</span><span class="sxs-lookup"><span data-stu-id="1c555-110">When a drive or folder is redirected to the guest, RDP\\Windows Virtual PC creates a share for that folder.</span></span> <span data-ttu-id="1c555-111">因此，如果主機上的 [我的文件] 資料夾已經指向共用，RDP\\Windows [虛擬電腦] 無法建立共用的共用。</span><span class="sxs-lookup"><span data-stu-id="1c555-111">Therefore, if the My Documents folder on the host is already pointing to a share, RDP\\Windows Virtual PC cannot create a share of a share.</span></span>

<span data-ttu-id="1c555-112">這個問題的另一個可能原因是，連線到網路資源所需的認證可能與使用者的網域認證不同。</span><span class="sxs-lookup"><span data-stu-id="1c555-112">Another possible cause of this issue is that the credentials that are required to connect to the network resource might differ from the user’s domain credentials.</span></span> <span data-ttu-id="1c555-113">MED-V 可能會檢測到該文檔已在主機上重新導向，傳送該資訊給來賓，然後嘗試重新連線網路資源。</span><span class="sxs-lookup"><span data-stu-id="1c555-113">MED-V might be detecting that documents are redirected on the host, send that information to the guest, and then try to reconnect the network resource.</span></span> <span data-ttu-id="1c555-114">如果使用者的認證沒有驗證，MED-V 可能會停止嘗試驗證。</span><span class="sxs-lookup"><span data-stu-id="1c555-114">If the user’s credentials do not authenticate, MED-V might stop trying to authenticate.</span></span>

**<span data-ttu-id="1c555-115">解決方案</span><span class="sxs-lookup"><span data-stu-id="1c555-115">Solution</span></span>**

<span data-ttu-id="1c555-116">若要解決此問題，請嘗試下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="1c555-116">Try one of the following to resolve this issue:</span></span>

-   <span data-ttu-id="1c555-117">在 Active Directory 中設定使用者的根目錄。</span><span class="sxs-lookup"><span data-stu-id="1c555-117">Set the user’s root directory inside Active Directory.</span></span> <span data-ttu-id="1c555-118">來賓和主機必須接著連線到相同的網路資源。</span><span class="sxs-lookup"><span data-stu-id="1c555-118">The guest and host should then connect to the same network resource.</span></span>

-   <span data-ttu-id="1c555-119">不要將 [我的文件] 資料夾重新導向至 UNC 路徑，而是將它對應至磁片磁碟機號（在主機上，對應指向網路資源的磁片磁碟機）。</span><span class="sxs-lookup"><span data-stu-id="1c555-119">Instead of redirecting the My Documents folder to a UNC path, map it to a drive letter (on the host, map a drive that points to the network resource).</span></span> <span data-ttu-id="1c555-120">然後，您可以將 [我的文件] 資料夾設定為使用磁片磁碟機盤符，而不是 UNC 路徑。</span><span class="sxs-lookup"><span data-stu-id="1c555-120">The My Documents folder can then be set to use the drive letter instead of the UNC path.</span></span> <span data-ttu-id="1c555-121">然後，來賓就會按照預期重新導向到同一個對應的磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="1c555-121">The guest will then redirect to that same mapped drive as expected.</span></span>

-   <span data-ttu-id="1c555-122">在來賓中建立啟動腳本，以將 [我的文件] 資料夾重新導向至網路資源，並視需要提供其他認證。</span><span class="sxs-lookup"><span data-stu-id="1c555-122">Create a startup script in the guest that redirects the My Documents folder to the network resource and provides additional credentials as needed.</span></span>

<span data-ttu-id="1c555-123">**URL**重新導向失敗。</span><span class="sxs-lookup"><span data-stu-id="1c555-123">**URL Redirection Fails**.</span></span> <span data-ttu-id="1c555-124">您指定要從主機重新導向至來賓的 URL 未按照預期方式重新導向，或是傳回錯誤訊息，指出該網站不存在。</span><span class="sxs-lookup"><span data-stu-id="1c555-124">A URL that you have specified for redirection from the host to the guest is not redirecting as intended or is returning an error message that indicates that the website does not exist.</span></span>

**<span data-ttu-id="1c555-125">解決方案</span><span class="sxs-lookup"><span data-stu-id="1c555-125">Solution</span></span>**

<span data-ttu-id="1c555-126">當 URL 重新導向資訊中有拼錯或不正確的字元使用（例如星號（\ \*））時，可能會發生此錯誤。</span><span class="sxs-lookup"><span data-stu-id="1c555-126">This error can occur when there is a misspelling or incorrect use of characters, such as asterisk (\*), in the URL redirection information.</span></span> <span data-ttu-id="1c555-127">檢查 URL 重新導向的登錄值，並修正任何錯誤。</span><span class="sxs-lookup"><span data-stu-id="1c555-127">Check the registry value for URL redirection and correct any mistakes.</span></span>

<span data-ttu-id="1c555-128">登錄機碼的名稱 `RedirectUrls` 通常位於：</span><span class="sxs-lookup"><span data-stu-id="1c555-128">The registry key is called `RedirectUrls` and is typically located at:</span></span>

<span data-ttu-id="1c555-129">Computer\\HKEY\ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\MEDV\\v2\\UserExperience</span><span class="sxs-lookup"><span data-stu-id="1c555-129">Computer\\HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\MEDV\\v2\\UserExperience</span></span>

<span data-ttu-id="1c555-130">**工作列中的圖示令人誤解**。</span><span class="sxs-lookup"><span data-stu-id="1c555-130">**Icon in Taskbar Misleading**.</span></span> <span data-ttu-id="1c555-131">根據預設，在已發佈的應用程式和重新導向的 Url 中出現在最終使用者的工作列中的圖示是 Windows 虛擬電腦的圖示。</span><span class="sxs-lookup"><span data-stu-id="1c555-131">By default, the icon that appears in an end user’s taskbar for published applications and redirected URLs is the icon for Windows Virtual PC.</span></span> <span data-ttu-id="1c555-132">如果使用者不知道這個預設行為，當您查看工作列來找出其應用程式時，就會變得混亂。</span><span class="sxs-lookup"><span data-stu-id="1c555-132">If an end user is not aware of this default behavior, they can become confused when looking at the taskbar to locate their application.</span></span>

**<span data-ttu-id="1c555-133">解決方案</span><span class="sxs-lookup"><span data-stu-id="1c555-133">Solution</span></span>**

<span data-ttu-id="1c555-134">避免此預設行為的唯一方法，就是變更工作列屬性的使用者設定，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1c555-134">The only way to avoid this default behavior is to change the user settings for the taskbar properties as follows:</span></span>

1.  <span data-ttu-id="1c555-135">以滑鼠右鍵按一下工作列，然後按一下 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="1c555-135">Right-click the taskbar and then click **Properties**.</span></span>

2.  <span data-ttu-id="1c555-136">在 [**工作列和開始功能表屬性**] 對話方塊中，按一下 [**工作列**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="1c555-136">In the **Taskbar and Start Menu Properties** dialog box, click the **Taskbar** tab.</span></span>

3.  <span data-ttu-id="1c555-137">在 [**工作列按鈕**] 方塊的下拉式列中，選取 [**不要合併**]。</span><span class="sxs-lookup"><span data-stu-id="1c555-137">In the drop-down bar for the **Taskbar buttons** box, select **Never combine**.</span></span>

4.  <span data-ttu-id="1c555-138">按一下 \[確定\] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1c555-138">Click **OK**.</span></span>

<span data-ttu-id="1c555-139">隨即會顯示已發佈應用程式和重定向 Url 的預期圖示。</span><span class="sxs-lookup"><span data-stu-id="1c555-139">The expected icons for published applications and redirected URLs are displayed.</span></span>

<span data-ttu-id="1c555-140">**如果第二位使用者嘗試登入，或虛擬機器正在使用中，則發出警告**。</span><span class="sxs-lookup"><span data-stu-id="1c555-140">**Warning Issued if Second User Attempts Log on or if Virtual Machine is in Use**.</span></span> <span data-ttu-id="1c555-141">第二個使用者登入 MED-V 工作區時，第一個使用者仍在執行 MED-V，就會發出警告訊息。</span><span class="sxs-lookup"><span data-stu-id="1c555-141">A warning message is issued when a second user logs on to a MED-V workspace while a first user is still running MED-V.</span></span> <span data-ttu-id="1c555-142">如果在使用虛擬機器時啟動 MED-V，例如，如果虛擬機器是透過 [**開始**] 功能表上的 WINDOWS virtual PC 啟動，則也會發出此警告。</span><span class="sxs-lookup"><span data-stu-id="1c555-142">The warning is also issued if MED-V is started while the virtual machine is being used, for example, if the virtual machine was started through Windows Virtual PC on the **Start** menu.</span></span> <span data-ttu-id="1c555-143">當使用者接受警告訊息時，MED-V 會關閉。</span><span class="sxs-lookup"><span data-stu-id="1c555-143">When the end user accepts the warning message, MED-V shuts down.</span></span>

**<span data-ttu-id="1c555-144">解決方案</span><span class="sxs-lookup"><span data-stu-id="1c555-144">Solution</span></span>**

<span data-ttu-id="1c555-145">最終使用者必須先確認所有其他使用者都已登入 MED-V，然後再嘗試登入。</span><span class="sxs-lookup"><span data-stu-id="1c555-145">An end user must verify that all other users are logged off MED-V before they try to log on.</span></span> <span data-ttu-id="1c555-146">這可確保沒有執行 MED-V 中的任何其他實例，且 Windows 虛擬電腦不是由虛擬機器控制。</span><span class="sxs-lookup"><span data-stu-id="1c555-146">This ensures that no other instance of MED-V is running and that Windows Virtual PC is not in control of the virtual machine.</span></span>

<span data-ttu-id="1c555-147">**第一次設定時聽到蜂鳴音**。</span><span class="sxs-lookup"><span data-stu-id="1c555-147">**Beeps Heard During First Time Setup**.</span></span> <span data-ttu-id="1c555-148">有時候，當 MED-V 在第一次執行時，會聽到嘟嘟聲。</span><span class="sxs-lookup"><span data-stu-id="1c555-148">Occasionally, beeps are heard while MED-V is running first time setup.</span></span> <span data-ttu-id="1c555-149">這可能會讓使用者感到困惑。</span><span class="sxs-lookup"><span data-stu-id="1c555-149">This can be confusing to an end user.</span></span> <span data-ttu-id="1c555-150">當您執行特定動作（例如關閉）時，會從虛擬機器發出嗶聲。</span><span class="sxs-lookup"><span data-stu-id="1c555-150">The beeps are originating from the virtual machine when it performs certain actions, such as shutting down.</span></span>

**<span data-ttu-id="1c555-151">解決方案</span><span class="sxs-lookup"><span data-stu-id="1c555-151">Solution</span></span>**

<span data-ttu-id="1c555-152">您可以在每個虛擬機器的開始順序中，指定「net stop 聲響」命令，以停止蜂鳴服務。</span><span class="sxs-lookup"><span data-stu-id="1c555-152">You can stop the beep service by specifying the "net stop beep" command at the beginning of each virtual machine start sequence.</span></span> <span data-ttu-id="1c555-153">或者，您也可以指定「sc config 開始 = 停用」命令來停用蜂鳴服務。</span><span class="sxs-lookup"><span data-stu-id="1c555-153">Or you can disable the beep service by specifying the “sc config beep start= disabled" command.</span></span> <span data-ttu-id="1c555-154">您可以在將影像密封或作為 Sysprep 的一部分之前，指定這些命令。</span><span class="sxs-lookup"><span data-stu-id="1c555-154">You can specify these commands either before you seal the image or as part of Sysprep.</span></span>

<span data-ttu-id="1c555-155">**在已橋接模式中，為 med-v-V 工作區建立多個網路**連線。</span><span class="sxs-lookup"><span data-stu-id="1c555-155">**Multiple Network Connections Created for MED-V Workspaces in BRIDGED Mode**.</span></span> <span data-ttu-id="1c555-156">如果您第一次安裝程式建立的 MED-V 工作區已設定為 NAT 模式，它只會在 Windows 虛擬電腦中建立單一網路連線。</span><span class="sxs-lookup"><span data-stu-id="1c555-156">If first time setup is creating a MED-V workspace that is configured for NAT mode, it only creates a single network connection in Windows Virtual PC.</span></span> <span data-ttu-id="1c555-157">不過，如果您第一次安裝所建立的 MED-V 工作區是針對橋接模式設定的，則它會針對電腦中安裝的每個網路介面卡建立一個獨立的網路連線，因為 MED-V 無法判斷哪個網路介面卡處於作用中狀態。</span><span class="sxs-lookup"><span data-stu-id="1c555-157">However, if first time setup is creating a MED-V workspace that is configured for BRIDGED mode, it creates a separate network connection for each network adapter that is installed in the computer, because MED-V cannot determine which network adapter is active.</span></span> <span data-ttu-id="1c555-158">這也確保漫遊使用者永遠都能使用網路介面卡來進行有線和無線連線。</span><span class="sxs-lookup"><span data-stu-id="1c555-158">This also ensures that roaming users always have a network adapter available for wired and wireless connections.</span></span>

**<span data-ttu-id="1c555-159">解決方案</span><span class="sxs-lookup"><span data-stu-id="1c555-159">Solution</span></span>**

<span data-ttu-id="1c555-160">無。</span><span class="sxs-lookup"><span data-stu-id="1c555-160">None.</span></span>

<span data-ttu-id="1c555-161">**在關閉時，Med-v 應用程式沒有回應太長時間**。</span><span class="sxs-lookup"><span data-stu-id="1c555-161">**MED-V Application is Unresponsive for Too Long when Closing**.</span></span> <span data-ttu-id="1c555-162">在某些情況下，MED-V 應用程式在嘗試關閉時會停止回應。</span><span class="sxs-lookup"><span data-stu-id="1c555-162">In some instances, a MED-V application stops responding when it is trying to close.</span></span>

**<span data-ttu-id="1c555-163">解決方案</span><span class="sxs-lookup"><span data-stu-id="1c555-163">Solution</span></span>**

<span data-ttu-id="1c555-164">您可以在來賓虛擬機器中設定 WaitToKillAppTimeout 登錄機碼，以指定 MED-V 停止回應應用程式的時間長度。</span><span class="sxs-lookup"><span data-stu-id="1c555-164">You can specify the length of time that MED-V waits to close unresponsive applications by setting the WaitToKillAppTimeout registry key in the guest virtual machine.</span></span> <span data-ttu-id="1c555-165">如需詳細資訊，請參閱[如何增加關閉時間，讓程式在 WINDOWS XP 中能正常](https://go.microsoft.com/fwlink/?LinkId=206819)結束（ https://go.microsoft.com/fwlink/?LinkId=206819) 。</span><span class="sxs-lookup"><span data-stu-id="1c555-165">For more information, see [How To Increase Shutdown Time So That Processes Can Quit Properly in Windows XP](https://go.microsoft.com/fwlink/?LinkId=206819) (https://go.microsoft.com/fwlink/?LinkId=206819).</span></span>

<span data-ttu-id="1c555-166">**在來賓虛擬機器中重新命名已發佈的應用程式快捷方式並不會變更主機中發佈的名稱**。</span><span class="sxs-lookup"><span data-stu-id="1c555-166">**Renaming a Published Application Shortcut in the Guest Virtual Machine does not Change the Published Name in the Host**.</span></span> <span data-ttu-id="1c555-167">當您透過建立快捷方式並重新命名來賓虛擬機器中的快捷方式來發佈應用程式時，原始應用程式名稱會保留在主機 [**開始**] 功能表中。</span><span class="sxs-lookup"><span data-stu-id="1c555-167">When you publish an application by creating a shortcut and then rename the shortcut in the guest virtual machine, the original application name remains in the host **Start** menu.</span></span> <span data-ttu-id="1c555-168">程式會依預期繼續執行，但程式將永遠保留原始名稱。</span><span class="sxs-lookup"><span data-stu-id="1c555-168">The program continues to run as expected, however the program will always retain the original name.</span></span>

**<span data-ttu-id="1c555-169">解決方案</span><span class="sxs-lookup"><span data-stu-id="1c555-169">Solution</span></span>**

<span data-ttu-id="1c555-170">無。</span><span class="sxs-lookup"><span data-stu-id="1c555-170">None.</span></span> <span data-ttu-id="1c555-171">這是 Windows 虛擬電腦的已知行為。</span><span class="sxs-lookup"><span data-stu-id="1c555-171">This is a known behavior of Windows Virtual PC.</span></span>

<span data-ttu-id="1c555-172">**移動來賓虛擬機器中的快捷方式不會更新主機電腦 [開始] 功能表上的位置**。</span><span class="sxs-lookup"><span data-stu-id="1c555-172">**Moving a Shortcut in the Guest Virtual Machine does not Update the Location on the Host Computer Start Menu**.</span></span> <span data-ttu-id="1c555-173">發佈到主機電腦 [**開始**] 功能表的 [med-v] 應用程式快捷方式會在註冊表中編目。</span><span class="sxs-lookup"><span data-stu-id="1c555-173">MED-V application shortcuts that are published to the host computer **Start** menu are cataloged in the registry.</span></span> <span data-ttu-id="1c555-174">如果您將應用程式快捷方式移至子資料夾中，則不會更新登錄以反映所做的變更。</span><span class="sxs-lookup"><span data-stu-id="1c555-174">If you move an application shortcut into a subfolder, the registry is not updated to reflect the change.</span></span>

**<span data-ttu-id="1c555-175">解決方案</span><span class="sxs-lookup"><span data-stu-id="1c555-175">Solution</span></span>**

<span data-ttu-id="1c555-176">請依照下列步驟變更 MED-V 應用程式快捷方式的位置：</span><span class="sxs-lookup"><span data-stu-id="1c555-176">Follow these steps to change the location of a MED-V application shortcut:</span></span>

1.  <span data-ttu-id="1c555-177">當 MED-V 執行時，請開啟 MED-V 來賓虛擬機器上的 Windows 資源管理器。</span><span class="sxs-lookup"><span data-stu-id="1c555-177">When MED-V is running, open up Windows Explorer on the MED-V guest virtual machine.</span></span>

2.  <span data-ttu-id="1c555-178">流覽至 [%ALLUSERSPROFILE%\\Start Menu\\Programs] 目錄。</span><span class="sxs-lookup"><span data-stu-id="1c555-178">Browse to the "%ALLUSERSPROFILE%\\Start Menu\\Programs" directory.</span></span>

3.  <span data-ttu-id="1c555-179">將應用程式快捷方式移出 [startmenu] 或 [程式] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="1c555-179">Move the application shortcuts out of the startmenu or programs folders.</span></span>

4.  <span data-ttu-id="1c555-180">大約30秒之後，請確認已從主機電腦的 [**開始**] 功能表中移除快速鍵。</span><span class="sxs-lookup"><span data-stu-id="1c555-180">After about 30 seconds, validate that the shortcuts are removed from the host computer **Start** menu.</span></span>

5.  <span data-ttu-id="1c555-181">將應用程式快捷方式移回到 [開始] Menu\\Programs 目錄下的新程式資料夾中。</span><span class="sxs-lookup"><span data-stu-id="1c555-181">Move the application shortcuts back in to the new program folders under the Start Menu\\Programs directory.</span></span>

6.  <span data-ttu-id="1c555-182">大約30秒之後，確認主機電腦的 [**開始**] 功能表中的快速鍵已更新。</span><span class="sxs-lookup"><span data-stu-id="1c555-182">After about 30 seconds, validate that the shortcuts are updated in the host computer **Start** Menu.</span></span>

<span data-ttu-id="1c555-183">**已發佈的應用程式在處於閒置狀態後，可能會超時**。</span><span class="sxs-lookup"><span data-stu-id="1c555-183">**Published Applications can Time Out after Sitting Idle**.</span></span> <span data-ttu-id="1c555-184">在某些情況下，如果已發佈的應用程式有一段時間沒有週六空閒，就會超時。</span><span class="sxs-lookup"><span data-stu-id="1c555-184">In some cases, published applications will time out if they have sat idle for some time.</span></span> <span data-ttu-id="1c555-185">只有在啟用 IPsec 且為 NAT 模式設定 MED-V 工作區時，才會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="1c555-185">This situation only occurs if IPsec is enabled and the MED-V workspace is configured for NAT mode.</span></span> <span data-ttu-id="1c555-186">如果以橋接模式執行，就不會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="1c555-186">This situation does not occur if running in BRIDGED mode.</span></span>

**<span data-ttu-id="1c555-187">解決方案</span><span class="sxs-lookup"><span data-stu-id="1c555-187">Solution</span></span>**

<span data-ttu-id="1c555-188">當您在 NAT 模式中執行 MED-V 工作區時，請停用 IPsec。</span><span class="sxs-lookup"><span data-stu-id="1c555-188">Disable IPsec when you are running the MED-V workspace in NAT mode.</span></span>

<span data-ttu-id="1c555-189">**將已發佈的應用程式釘選到工作列，會繞過 med-v**。</span><span class="sxs-lookup"><span data-stu-id="1c555-189">**Pinning a Published Application to the Taskbar Bypasses MED-V**.</span></span> <span data-ttu-id="1c555-190">如果使用者將已發佈的應用程式釘選到工作列，然後關閉應用程式，則下次從工作列圖示開啟應用程式時，就會略過 MED-V。</span><span class="sxs-lookup"><span data-stu-id="1c555-190">If an end user pins a published application to the taskbar and then closes the application, MED-V is bypassed the next time that the application is opened from the taskbar icon.</span></span> <span data-ttu-id="1c555-191">相反地，應用程式會直接在 VMSAL 視窗中開啟。</span><span class="sxs-lookup"><span data-stu-id="1c555-191">Instead, the application opens directly in a VMSAL window.</span></span>

**<span data-ttu-id="1c555-192">解決方案</span><span class="sxs-lookup"><span data-stu-id="1c555-192">Solution</span></span>**

<span data-ttu-id="1c555-193">請勿將在 MED-V 中發佈的應用程式釘選到工作列。</span><span class="sxs-lookup"><span data-stu-id="1c555-193">Do not pin the applications published in MED-V to the taskbar.</span></span>

## <span data-ttu-id="1c555-194">相關主題</span><span class="sxs-lookup"><span data-stu-id="1c555-194">Related topics</span></span>


[<span data-ttu-id="1c555-195">MED-V 作業的安全性最佳做法</span><span class="sxs-lookup"><span data-stu-id="1c555-195">Security Best Practices for MED-V Operations</span></span>](security-best-practices-for-med-v-operations.md)

[<span data-ttu-id="1c555-196">部署疑難排解</span><span class="sxs-lookup"><span data-stu-id="1c555-196">Deployment Troubleshooting</span></span>](deployment-troubleshooting.md)

 

 





