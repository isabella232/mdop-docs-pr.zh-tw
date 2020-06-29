---
title: 如何使用 DaRT 復原映像來復原遠端電腦
description: 如何使用 DaRT 復原映像來復原遠端電腦
author: dansimp
ms.assetid: 363ccd48-6820-4b5b-a43a-323c0b208a9d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 3b3e3155dbea8da18338b8a167d22f73b1c8e4bb
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810532"
---
# <span data-ttu-id="e7b44-103">如何使用 DaRT 復原映像來復原遠端電腦</span><span class="sxs-lookup"><span data-stu-id="e7b44-103">How to Recover Remote Computers by Using the DaRT Recovery Image</span></span>


<span data-ttu-id="e7b44-104">使用 Microsoft Diagnostics 與復原工具組（DaRT）8.0 中的 [遠端連線] 功能，在最終使用者電腦上遠端執行 DaRT 工具。</span><span class="sxs-lookup"><span data-stu-id="e7b44-104">Use the Remote Connection feature in Microsoft Diagnostics and Recovery Toolset (DaRT) 8.0 to run the DaRT tools remotely on an end-user computer.</span></span> <span data-ttu-id="e7b44-105">當使用者以特定資訊提供系統管理員或技術支援人員之後，IT 系統管理員或技術支援人員就可以控制最終使用者的電腦，並以遠端方式執行必要的 DaRT 工具。</span><span class="sxs-lookup"><span data-stu-id="e7b44-105">After the end user provides the administrator or help desk worker with certain information, the IT administrator or help desk worker can take control of the end user's computer and run the necessary DaRT tools remotely.</span></span>

<span data-ttu-id="e7b44-106">如果您在建立恢復影像時停用了 DaRT 工具，您仍然可以存取所有的工具。</span><span class="sxs-lookup"><span data-stu-id="e7b44-106">If you disabled the DaRT tools when you created the recovery image, you still have access to all of the tools.</span></span> <span data-ttu-id="e7b44-107">使用者無法使用所有工具（除了遠端連線之外）。</span><span class="sxs-lookup"><span data-stu-id="e7b44-107">All of the tools, except Remote Connection, are unavailable to end users.</span></span>

**<span data-ttu-id="e7b44-108">使用 DaRT 恢復影像來復原遠端電腦</span><span class="sxs-lookup"><span data-stu-id="e7b44-108">To recover a remote computer by using the DaRT recovery image</span></span>**

1.  <span data-ttu-id="e7b44-109">使用 DaRT 復原影像啟動端使用者電腦。</span><span class="sxs-lookup"><span data-stu-id="e7b44-109">Boot an end-user computer by using the DaRT recovery image.</span></span>

    <span data-ttu-id="e7b44-110">您通常會使用下列其中一種方法來引導至 DaRT，以根據您部署 DaRT 復原影像的方式來復原遠端電腦。</span><span class="sxs-lookup"><span data-stu-id="e7b44-110">You will typically use one of the following methods to boot into DaRT to recover a remote computer, depending on how you deploy the DaRT recovery image.</span></span> <span data-ttu-id="e7b44-111">如需有關部署 DaRT 恢復影像的詳細資訊，請參閱[部署 dart 8.0](deploying-dart-80-dart-8.md)。</span><span class="sxs-lookup"><span data-stu-id="e7b44-111">For more information about deploying the DaRT recovery image, see [Deploying DaRT 8.0](deploying-dart-80-dart-8.md).</span></span>

    -   <span data-ttu-id="e7b44-112">從問題電腦上的 [恢復] 分區引導至 DaRT。</span><span class="sxs-lookup"><span data-stu-id="e7b44-112">Boot into DaRT from a recovery partition on the problem computer.</span></span>

    -   <span data-ttu-id="e7b44-113">從網路上的遠端分區引導至 DaRT。</span><span class="sxs-lookup"><span data-stu-id="e7b44-113">Boot into DaRT from a remote partition on the network.</span></span>

    <span data-ttu-id="e7b44-114">如需每個方法的優點與缺點的詳細資訊，請參閱[規劃如何儲存和部署 DaRT 8.0 恢復影像](planning-how-to-save-and-deploy-the-dart-80-recovery-image-dart-8.md)。</span><span class="sxs-lookup"><span data-stu-id="e7b44-114">For information about the advantages and disadvantages of each method, see [Planning How to Save and Deploy the DaRT 8.0 Recovery Image](planning-how-to-save-and-deploy-the-dart-80-recovery-image-dart-8.md).</span></span>

    <span data-ttu-id="e7b44-115">無論您使用何種方法引導至 DaRT，您都必須在 BIOS 中啟用啟動裝置，以找到您要讓使用者使用的引導選項或選項。</span><span class="sxs-lookup"><span data-stu-id="e7b44-115">Whichever method that you use to boot into DaRT, you must enable the boot device in the BIOS for the boot option or options that you want to make available to the end user.</span></span>

    **<span data-ttu-id="e7b44-116">注意</span><span class="sxs-lookup"><span data-stu-id="e7b44-116">Note</span></span>**  
    <span data-ttu-id="e7b44-117">根據您組織中使用的硬碟、網路介面卡及其他硬體的類型，設定 BIOS 是唯一的。</span><span class="sxs-lookup"><span data-stu-id="e7b44-117">Configuring the BIOS is unique, depending on the kind of hard disk drive, network adapters, and other hardware that is used in your organization.</span></span>



~~~
As the computer is booting into the DaRT recovery image, the **NetStart** dialog box appears.
~~~

2. <span data-ttu-id="e7b44-118">當系統詢問您是否要初始化網路服務時，請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="e7b44-118">When you are asked whether you want to initialize network services, select one of the following:</span></span>

   <span data-ttu-id="e7b44-119">**是**-假設您有 DHCP 伺服器出現在網路上，且嘗試從伺服器取得 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="e7b44-119">**Yes** - it is assumed that a DHCP server is present on the network, and an attempt is made to obtain an IP address from the server.</span></span> <span data-ttu-id="e7b44-120">如果網路使用靜態 IP 位址而不是 DHCP，您可以稍後在 DaRT 中使用**Tcp/ip 配置**工具來指定靜態 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="e7b44-120">If the network uses static IP addresses instead of DHCP, you can later use the **TCP/IP Configuration** tool in DaRT to specify a static IP address.</span></span>

   <span data-ttu-id="e7b44-121">**否**-略過網路初始化程式。</span><span class="sxs-lookup"><span data-stu-id="e7b44-121">**No** - skip the network initialization process.</span></span>

3. <span data-ttu-id="e7b44-122">指出您是否要重新映射磁片磁碟機盤符。</span><span class="sxs-lookup"><span data-stu-id="e7b44-122">Indicate whether you want to remap the drive letters.</span></span> <span data-ttu-id="e7b44-123">當您執行 Windows online 時，系統磁碟區通常會對應到磁碟機 C。不過，當您在 [WinRE] 下執行 Windows 離線時，原始的系統磁碟區可能會對應到另一個磁片磁碟機，這可能會造成混淆。</span><span class="sxs-lookup"><span data-stu-id="e7b44-123">When you run Windows online, the system volume is typically mapped to drive C. However, when you run Windows offline under WinRE, the original system volume might be mapped to another drive, and this can cause confusion.</span></span> <span data-ttu-id="e7b44-124">如果您決定重新映射，DaRT 會嘗試對應離線磁碟機盤符，以符合線上磁片磁碟機盤符。</span><span class="sxs-lookup"><span data-stu-id="e7b44-124">If you decide to remap, DaRT tries to map the offline drive letters to match the online drive letters.</span></span> <span data-ttu-id="e7b44-125">只有在後續的啟動程式中選取了離線作業系統時，才會執行重新映射。</span><span class="sxs-lookup"><span data-stu-id="e7b44-125">Remapping is performed only if an offline operating system is selected later in the startup process.</span></span>

4. <span data-ttu-id="e7b44-126">在 [**系統復原選項**] 對話方塊中，選取鍵盤配置。</span><span class="sxs-lookup"><span data-stu-id="e7b44-126">On the **System Recovery Options** dialog box, select a keyboard layout.</span></span>

5. <span data-ttu-id="e7b44-127">檢查顯示的系統根目錄、所安裝的作業系統類型，以及分區大小。</span><span class="sxs-lookup"><span data-stu-id="e7b44-127">Check the displayed system root directory, the kind of operating system installed, and the partition size.</span></span> <span data-ttu-id="e7b44-128">如果您沒有看到您的作業系統，且懷疑驅動程式缺乏可能造成失敗的原因，請按一下 [**載入驅動**程式] 載入可疑的驅動程式，然後選取驅動程式的安裝媒體。</span><span class="sxs-lookup"><span data-stu-id="e7b44-128">If you do not see your operating system listed, and suspect that the lack of drivers is a possible cause of the failure, click **Load Drivers** to load the suspect drivers, and then insert the installation media for the device and select the driver.</span></span>

6. <span data-ttu-id="e7b44-129">選取您要修復或診斷的安裝，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e7b44-129">Select the installation that you want to repair or diagnose, and then click **Next**.</span></span>

   **<span data-ttu-id="e7b44-130">注意</span><span class="sxs-lookup"><span data-stu-id="e7b44-130">Note</span></span>**  
   <span data-ttu-id="e7b44-131">如果 Windows 修復環境（WinRE）檢測到或懷疑 Windows 8 無法正常啟動，則**啟動修復**可能會開始自動執行。</span><span class="sxs-lookup"><span data-stu-id="e7b44-131">If the Windows Recovery Environment (WinRE) detects or suspects that Windows 8 did not start correctly the last time that it was tried, **Startup Repair** might start to run automatically.</span></span> <span data-ttu-id="e7b44-132">如需如何解決此問題的相關資訊，請參閱[DaRT 8.0 的疑難排解](troubleshooting-dart-80-dart-8.md)。</span><span class="sxs-lookup"><span data-stu-id="e7b44-132">For information about how to resolve this issue, see [Troubleshooting DaRT 8.0](troubleshooting-dart-80-dart-8.md).</span></span>



~~~
If any of the registry hives are corrupted or missing, Registry Editor and several other DaRT utilities will have limited functionality. If no operating system is selected, some tools will not be available.

The **System Recovery Options** window appears and lists various recovery tools.
~~~

7. <span data-ttu-id="e7b44-133">在 [**系統復原選項**] 視窗中，按一下 [ **Microsoft 診斷與修復工具集**]，開啟 [**診斷與修復工具**]。</span><span class="sxs-lookup"><span data-stu-id="e7b44-133">On the **System Recovery Options** window, click **Microsoft Diagnostics and Recovery Toolset** to open the **Diagnostics and Recovery Toolset**.</span></span>

8. <span data-ttu-id="e7b44-134">在 [**診斷及修復工具**] 視窗中，按一下 [**遠端**連線] 以開啟 [ **DaRT 遠端**連線] 視窗。</span><span class="sxs-lookup"><span data-stu-id="e7b44-134">On the **Diagnostics and Recovery Toolset** window, click **Remote Connection** to open the **DaRT Remote Connection** window.</span></span> <span data-ttu-id="e7b44-135">如果系統提示您提供支援中心的遠端存取，請按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="e7b44-135">If you are prompted to give the help desk remote access, click **OK**.</span></span>

   <span data-ttu-id="e7b44-136">隨即會開啟 [DaRT 遠端連線] 視窗，並顯示票證號碼、IP 位址和埠資訊。</span><span class="sxs-lookup"><span data-stu-id="e7b44-136">The DaRT Remote Connection window opens and displays a ticket number, IP address, and port information.</span></span>

9. <span data-ttu-id="e7b44-137">在技術支援部電腦上，開啟 [ **DaRT 遠端連線檢視器]**。</span><span class="sxs-lookup"><span data-stu-id="e7b44-137">On the help desk computer, open the **DaRT Remote Connection Viewer**.</span></span>

10. <span data-ttu-id="e7b44-138">按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft DaRT 8.0**]，然後按一下 [ **DaRT 遠端連線檢視器]**。</span><span class="sxs-lookup"><span data-stu-id="e7b44-138">Click **Start**, click **All Programs**, click **Microsoft DaRT 8.0**, and then click **DaRT Remote Connection Viewer**.</span></span>

11. <span data-ttu-id="e7b44-139">在 [ **DaRT 遠端**連線] 視窗中，輸入所需的票證、IP 位址和埠資訊。</span><span class="sxs-lookup"><span data-stu-id="e7b44-139">In the **DaRT Remote Connection** window, enter the required ticket, IP address, and port information.</span></span>

   **<span data-ttu-id="e7b44-140">注意</span><span class="sxs-lookup"><span data-stu-id="e7b44-140">Note</span></span>**  
   <span data-ttu-id="e7b44-141">此資訊是在使用者電腦上建立，且必須由最終使用者提供。</span><span class="sxs-lookup"><span data-stu-id="e7b44-141">This information is created on the end-user computer and must be provided by the end user.</span></span> <span data-ttu-id="e7b44-142">可能有多個 IP 位址可供選擇，視最終使用者電腦上可用的數目而定。</span><span class="sxs-lookup"><span data-stu-id="e7b44-142">There might be multiple IP addresses to choose from, depending on how many are available on the end-user computer.</span></span>



12. <span data-ttu-id="e7b44-143">按一下 **\[連線\]**。</span><span class="sxs-lookup"><span data-stu-id="e7b44-143">Click **Connect**.</span></span>

<span data-ttu-id="e7b44-144">IT 系統管理員現在假設您可以控制最終使用者電腦，並可遠端執行 DaRT 工具。</span><span class="sxs-lookup"><span data-stu-id="e7b44-144">The IT administrator now assumes control of the end-user computer and can run the DaRT tools remotely.</span></span>

**<span data-ttu-id="e7b44-145">注意</span><span class="sxs-lookup"><span data-stu-id="e7b44-145">Note</span></span>**  
<span data-ttu-id="e7b44-146">已提供名為 inv32.xml 的檔案，其中包含遠端連線資訊，例如埠號碼和 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="e7b44-146">A file is provided that is named inv32.xml and contains remote connection information, such as the port number and IP address.</span></span> <span data-ttu-id="e7b44-147">根據預設，檔案通常位於%windir%\\system32。</span><span class="sxs-lookup"><span data-stu-id="e7b44-147">By default, the file is typically located at %windir%\\system32.</span></span>



**<span data-ttu-id="e7b44-148">自訂遠端連線進程</span><span class="sxs-lookup"><span data-stu-id="e7b44-148">To customize the Remote Connection process</span></span>**

1. <span data-ttu-id="e7b44-149">您可以編輯 winpeshl.ini 檔案，自訂遠端連線進程。</span><span class="sxs-lookup"><span data-stu-id="e7b44-149">You can customize the Remote Connection process by editing the winpeshl.ini file.</span></span> <span data-ttu-id="e7b44-150">如需如何編輯 winpeshl.ini 檔案的詳細資訊，請參閱[Winpeshl.ini](https://go.microsoft.com/fwlink/?LinkId=219413)檔案。</span><span class="sxs-lookup"><span data-stu-id="e7b44-150">For more information about how to edit the winpeshl.ini file, see [Winpeshl.ini Files](https://go.microsoft.com/fwlink/?LinkId=219413).</span></span>

   <span data-ttu-id="e7b44-151">指定下列命令和參數，來自訂如何與終端使用者電腦建立遠端連線：</span><span class="sxs-lookup"><span data-stu-id="e7b44-151">Specify the following commands and parameters to customize how a remote connection is established with an end-user computer:</span></span>

   <table>
   <colgroup>
   <col width="33%" />
   <col width="33%" />
   <col width="33%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="e7b44-152">命令</span><span class="sxs-lookup"><span data-stu-id="e7b44-152">Command</span></span></th>
   <th align="left"><span data-ttu-id="e7b44-153">參數</span><span class="sxs-lookup"><span data-stu-id="e7b44-153">Parameter</span></span></th>
   <th align="left"><span data-ttu-id="e7b44-154">描述</span><span class="sxs-lookup"><span data-stu-id="e7b44-154">Description</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="e7b44-155">RemoteRecovery.exe</span><span class="sxs-lookup"><span data-stu-id="e7b44-155">RemoteRecovery.exe</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="e7b44-156">-nomessage</span><span class="sxs-lookup"><span data-stu-id="e7b44-156">-nomessage</span></span></p></td>
   <td align="left"><p><span data-ttu-id="e7b44-157">指定不會顯示確認提示。</span><span class="sxs-lookup"><span data-stu-id="e7b44-157">Specifies that the confirmation prompt is not displayed.</span></span> <strong><span data-ttu-id="e7b44-158">[遠端連線] </strong> 繼續執行，就像最終使用者 &quot; &quot; 對確認提示作出回應時一樣。</span><span class="sxs-lookup"><span data-stu-id="e7b44-158">Remote Connection</strong> continues just as if the end user had responded &quot;Yes&quot; to the confirmation prompt.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="e7b44-159">WaitForConnection.exe</span><span class="sxs-lookup"><span data-stu-id="e7b44-159">WaitForConnection.exe</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="e7b44-160">無 (none)</span><span class="sxs-lookup"><span data-stu-id="e7b44-160">none</span></span></p></td>
   <td align="left"><p><span data-ttu-id="e7b44-161">防止自訂腳本繼續進行，直到 <strong> 沒有執行任何遠端連線 </strong> ，或是與使用者電腦建立有效的連線。</span><span class="sxs-lookup"><span data-stu-id="e7b44-161">Prevents a custom script from continuing until either <strong>Remote Connection</strong> is not running or a valid connection is established with the end-user computer.</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="e7b44-162">重要</span><span class="sxs-lookup"><span data-stu-id="e7b44-162">Important</span></span></strong><br/><p><span data-ttu-id="e7b44-163">這個命令不會提供任何函數（如果它是獨立指定的）。</span><span class="sxs-lookup"><span data-stu-id="e7b44-163">This command serves no function if it is specified independently.</span></span> <span data-ttu-id="e7b44-164">必須在腳本中指定它才能正常運作。</span><span class="sxs-lookup"><span data-stu-id="e7b44-164">It must be specified in a script to function correctly.</span></span></p>
   </div>
   <div>

   </div></td>
   </tr>
   </tbody>
   </table>



2. <span data-ttu-id="e7b44-165">下列是自訂的 winpeshl.ini 檔案範例，只要嘗試啟動到 DaRT，就可以開啟**遠端**連線工具：</span><span class="sxs-lookup"><span data-stu-id="e7b44-165">The following is an example of a winpeshl.ini file that is customized to open the **Remote Connection** tool as soon as an attempt is made to boot into DaRT:</span></span>

   ```ini
   [LaunchApps]
   "%windir%\system32\netstart.exe -network -remount"
   "cmd /C start %windir%\system32\RemoteRecovery.exe -nomessage"
   "%windir%\system32\WaitForConnection.exe"
   "%SYSTEMDRIVE%\sources\recovery\recenv.exe"
   ```

<span data-ttu-id="e7b44-166">當 DaRT 啟動時，會在 RAM 磁碟上的 \\Windows\\System32\\ 中建立檔案 inv32.xml。</span><span class="sxs-lookup"><span data-stu-id="e7b44-166">When DaRT starts, it creates the file inv32.xml in \\Windows\\System32\\ on the RAM disk.</span></span> <span data-ttu-id="e7b44-167">此檔案包含連線資訊： IP 位址、埠和票證號碼。</span><span class="sxs-lookup"><span data-stu-id="e7b44-167">This file contains connection information: IP address, port, and ticket number.</span></span> <span data-ttu-id="e7b44-168">您可以將此檔案複製到網路共用，以觸發問訊台工作流程。</span><span class="sxs-lookup"><span data-stu-id="e7b44-168">You can copy this file to a network share to trigger a Help desk workflow.</span></span> <span data-ttu-id="e7b44-169">例如，自訂程式可以檢查網路共用中的連線檔案，然後建立支援票證或傳送電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="e7b44-169">For example, a custom program can check the network share for connection files, and then create a support ticket or send email notifications.</span></span>

**<span data-ttu-id="e7b44-170">在命令提示字元執行遠端連線檢視器</span><span class="sxs-lookup"><span data-stu-id="e7b44-170">To run the Remote Connection Viewer at the command prompt</span></span>**

1.  <span data-ttu-id="e7b44-171">若要在命令提示字元執行**DaRT 遠端連線檢視器**，請指定**DartRemoteViewer.exe**命令，並使用下列參數：</span><span class="sxs-lookup"><span data-stu-id="e7b44-171">To run the **DaRT Remote Connection Viewer** at the command prompt, specify the **DartRemoteViewer.exe** command and use the following parameters:</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="e7b44-172">參數</span><span class="sxs-lookup"><span data-stu-id="e7b44-172">Parameter</span></span></th>
    <th align="left"><span data-ttu-id="e7b44-173">描述</span><span class="sxs-lookup"><span data-stu-id="e7b44-173">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="e7b44-174">-ticket = &lt; <em> ticketnumber</em>&gt;</span><span class="sxs-lookup"><span data-stu-id="e7b44-174">-ticket=&lt;<em>ticketnumber</em>&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e7b44-175">其中 &lt; <em> ticketnumber </em> &gt; 是由遠端連線產生的票證編號，包括虛線。</span><span class="sxs-lookup"><span data-stu-id="e7b44-175">Where &lt;<em>ticketnumber</em>&gt; is the ticket number, including the dashes, that is generated by Remote Connection.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="e7b44-176">-ipaddress = &lt; <em> ipaddress</em>&gt;</span><span class="sxs-lookup"><span data-stu-id="e7b44-176">-ipaddress=&lt;<em>ipaddress</em>&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e7b44-177">其中， &lt; <em> Ipaddress </em> &gt; 是遠端連線所產生的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="e7b44-177">Where &lt;<em>ipaddress</em>&gt; is the IP address that is generated by Remote Connection.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="e7b44-178">-port = &lt; <em> 埠</em>&gt;</span><span class="sxs-lookup"><span data-stu-id="e7b44-178">-port=&lt;<em>port</em>&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e7b44-179">其中 &lt; <em> port </em> &gt; 是對應至指定 IP 位址的埠。</span><span class="sxs-lookup"><span data-stu-id="e7b44-179">Where &lt;<em>port</em>&gt; is the port that corresponds to the specified IP address.</span></span></p></td>
    </tr>
    </tbody>
    </table>



~~~
**Note**  
The variables for these parameters are created on the end-user computer and must be provided by the end user.
~~~



2. <span data-ttu-id="e7b44-180">如果所有三個參數都已指定，且資料有效，則會在程式啟動時立即嘗試連接。</span><span class="sxs-lookup"><span data-stu-id="e7b44-180">If all three parameters are specified and the data is valid, a connection is immediately tried when the program starts.</span></span> <span data-ttu-id="e7b44-181">如果有任何參數無效，程式就會啟動，就好像沒有指定參數一樣。</span><span class="sxs-lookup"><span data-stu-id="e7b44-181">If any parameter is not valid, the program starts as if there were no parameters specified.</span></span>

## <span data-ttu-id="e7b44-182">相關主題</span><span class="sxs-lookup"><span data-stu-id="e7b44-182">Related topics</span></span>


[<span data-ttu-id="e7b44-183">適用於 DaRT 8.0 的操作</span><span class="sxs-lookup"><span data-stu-id="e7b44-183">Operations for DaRT 8.0</span></span>](operations-for-dart-80-dart-8.md)

[<span data-ttu-id="e7b44-184">使用 DaRT 8.0 復原電腦</span><span class="sxs-lookup"><span data-stu-id="e7b44-184">Recovering Computers Using DaRT 8.0</span></span>](recovering-computers-using-dart-80-dart-8.md)









