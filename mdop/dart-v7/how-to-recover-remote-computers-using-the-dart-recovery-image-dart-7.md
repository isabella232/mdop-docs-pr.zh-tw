---
title: 如何使用 DaRT 復原映像來復原遠端電腦
description: 如何使用 DaRT 復原映像來復原遠端電腦
author: dansimp
ms.assetid: 66bc45fb-dc40-4d47-b583-5bb1ff5c97a7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 885ab1d1cf8f51dc4fd4613e41a20a2525ea7d6d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809567"
---
# <span data-ttu-id="18749-103">如何使用 DaRT 復原映像來復原遠端電腦</span><span class="sxs-lookup"><span data-stu-id="18749-103">How to Recover Remote Computers Using the DaRT Recovery Image</span></span>


<span data-ttu-id="18749-104">Microsoft Diagnostics 與復原工具組（DaRT）7中的遠端連線功能可讓 IT 系統管理員在最終使用者電腦上遠端執行 DaRT 工具。</span><span class="sxs-lookup"><span data-stu-id="18749-104">The Remote Connection feature in Microsoft Diagnostics and Recovery Toolset (DaRT) 7 lets an IT administrator run the DaRT tools remotely on an end-user computer.</span></span> <span data-ttu-id="18749-105">當使用者（或由支援使用者電腦的技術人員）提供特定資訊之後，IT 系統管理員或技術支援人員就可以控制最終使用者的電腦，並以遠端方式執行必要的 DaRT 工具。</span><span class="sxs-lookup"><span data-stu-id="18749-105">After certain information is provided by the end user (or by a helpdesk professional working on the end-user computer), the IT administrator or helpdesk agent can take control of the end user's computer and run the necessary DaRT tools remotely.</span></span>

**<span data-ttu-id="18749-106">重要</span><span class="sxs-lookup"><span data-stu-id="18749-106">Important</span></span>**  
<span data-ttu-id="18749-107">建立遠端連線的兩台電腦必須是相同網路的一部分。</span><span class="sxs-lookup"><span data-stu-id="18749-107">The two computers establishing a remote connection must be part of the same network.</span></span>



**<span data-ttu-id="18749-108">使用 DaRT 復原遠端電腦</span><span class="sxs-lookup"><span data-stu-id="18749-108">To recover a remote computer by using DaRT</span></span>**

1.  <span data-ttu-id="18749-109">使用 DaRT 復原影像啟動端使用者電腦。</span><span class="sxs-lookup"><span data-stu-id="18749-109">Boot an end-user computer by using the DaRT recovery image.</span></span>

    <span data-ttu-id="18749-110">您通常會使用下列其中一種方法來引導至 DaRT，以根據您部署 DaRT 復原影像的方式來復原遠端電腦。</span><span class="sxs-lookup"><span data-stu-id="18749-110">You will typically use one of the following methods to boot into DaRT to recover a remote computer, depending on how you deploy the DaRT recovery image.</span></span> <span data-ttu-id="18749-111">如需有關部署 DaRT 復原影像的詳細資訊，請參閱[部署 dart 7.0 恢復影像](deploying-the-dart-70-recovery-image-dart-7.md)。</span><span class="sxs-lookup"><span data-stu-id="18749-111">For more information about deploying the DaRT recovery image, see [Deploying the DaRT 7.0 Recovery Image](deploying-the-dart-70-recovery-image-dart-7.md).</span></span>

    -   <span data-ttu-id="18749-112">從問題電腦上的 [恢復] 分區引導至 DaRT。</span><span class="sxs-lookup"><span data-stu-id="18749-112">Boot into DaRT from a recovery partition on the problem computer.</span></span>

    -   <span data-ttu-id="18749-113">從網路上的遠端分區引導至 DaRT。</span><span class="sxs-lookup"><span data-stu-id="18749-113">Boot into DaRT from a remote partition on the network.</span></span>

    <span data-ttu-id="18749-114">如需每個方法的優點與缺點的詳細資訊，請參閱[規劃如何儲存和部署 DaRT 7.0 恢復影像](planning-how-to-save-and-deploy-the-dart-70-recovery-image.md)。</span><span class="sxs-lookup"><span data-stu-id="18749-114">For information about the advantages and disadvantages of each method, see [Planning How to Save and Deploy the DaRT 7.0 Recovery Image](planning-how-to-save-and-deploy-the-dart-70-recovery-image.md).</span></span>

    <span data-ttu-id="18749-115">無論您使用何種方法引導至 DaRT，您都必須在 BIOS 中啟用啟動裝置，以找到您要讓使用者使用的引導選項或選項。</span><span class="sxs-lookup"><span data-stu-id="18749-115">Whichever method that you use to boot into DaRT, you must enable the boot device in the BIOS for the boot option or options that you want to make available to the end user.</span></span>

    **<span data-ttu-id="18749-116">注意</span><span class="sxs-lookup"><span data-stu-id="18749-116">Note</span></span>**  
    <span data-ttu-id="18749-117">根據您組織中使用的硬碟、網路介面卡及其他硬體的類型，設定 BIOS 是唯一的。</span><span class="sxs-lookup"><span data-stu-id="18749-117">Configuring the BIOS is unique, depending on the kind of hard disk drive, network adapters, and other hardware that is used in your organization.</span></span>



2.  <span data-ttu-id="18749-118">當電腦啟動至 DaRT 復原影像時，會出現 [ **NetStart** ] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="18749-118">As the computer is booting into the DaRT recovery image, the **NetStart** dialog box appears.</span></span> <span data-ttu-id="18749-119">系統會詢問您是否要初始化網路服務。</span><span class="sxs-lookup"><span data-stu-id="18749-119">You are asked whether you want to initialize network services.</span></span> <span data-ttu-id="18749-120">如果您按一下 **[是]**，系統會假設 DHCP 伺服器出現在網路上，且嘗試從伺服器取得 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="18749-120">If you click **Yes**, it is assumed that a DHCP server is present on the network and an attempt is made to obtain an IP address from the server.</span></span> <span data-ttu-id="18749-121">如果網路使用靜態 IP 位址而不是 DHCP，您可以稍後在 DaRT 中使用**Tcp/ip 配置**工具來指定靜態 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="18749-121">If the network uses static IP addresses instead of DHCP, you can later use the **TCP/IP Configuration** tool in DaRT to specify a static IP address.</span></span>

    <span data-ttu-id="18749-122">若要略過網路初始化程式，請按一下 [**否**]。</span><span class="sxs-lookup"><span data-stu-id="18749-122">To skip the network initialization process, click **No**.</span></span>

3.  <span data-ttu-id="18749-123">在 [網路初始化] 對話方塊中，系統會詢問您是否要重新映射磁片磁碟機盤符。</span><span class="sxs-lookup"><span data-stu-id="18749-123">Following the network initialization dialog box, you are asked whether you want to remap the drive letters.</span></span> <span data-ttu-id="18749-124">當您執行 Windows online 時，系統磁碟區通常會對應到磁碟機 C。不過，當您在 [WinRE] 下執行 Windows 離線時，原始的系統磁碟區可能會對應到另一個磁片磁碟機，這可能會造成混淆。</span><span class="sxs-lookup"><span data-stu-id="18749-124">When you run Windows online, the system volume is typically mapped to drive C. However, when you run Windows offline under WinRE, the original system volume might be mapped to another drive, and this can cause confusion.</span></span> <span data-ttu-id="18749-125">如果您決定重新映射，DaRT 會嘗試對應離線磁碟機盤符，以符合線上磁片磁碟機盤符。</span><span class="sxs-lookup"><span data-stu-id="18749-125">If you decide to remap, DaRT tries to map the offline drive letters to match the online drive letters.</span></span> <span data-ttu-id="18749-126">只有在後續的啟動程式中選取了離線作業系統時，才會執行重新映射。</span><span class="sxs-lookup"><span data-stu-id="18749-126">Remapping is performed only if an offline operating system is selected later in the startup process.</span></span>

4.  <span data-ttu-id="18749-127">在重新變換對話方塊之後，會出現 [**系統復原選項**] 對話方塊，要求您選取鍵盤配置。</span><span class="sxs-lookup"><span data-stu-id="18749-127">Following the remapping dialog box, a **System Recovery Options** dialog box appears and asks you to select a keyboard layout.</span></span> <span data-ttu-id="18749-128">接著，它會顯示系統根目錄、所安裝的作業系統類型，以及分區大小。</span><span class="sxs-lookup"><span data-stu-id="18749-128">Then it displays the system root directory, the kind of operating system installed, and the partition size.</span></span> <span data-ttu-id="18749-129">如果您沒有看到您的作業系統，且懷疑驅動程式缺乏可能造成失敗，請按一下 [**載入驅動**程式] 載入可疑的驅動程式。</span><span class="sxs-lookup"><span data-stu-id="18749-129">If you do not see your operating system listed, and suspect that the lack of drivers is a possible cause of the failure, click **Load Drivers** to load the suspect drivers.</span></span> <span data-ttu-id="18749-130">這會提示您插入裝置的安裝媒體及選取驅動程式。</span><span class="sxs-lookup"><span data-stu-id="18749-130">This prompts you to insert the installation media for the device and to select the driver.</span></span> <span data-ttu-id="18749-131">選取您要修復或診斷的安裝，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="18749-131">Select the installation that you want to repair or diagnose, and then click **Next**.</span></span>

    **<span data-ttu-id="18749-132">注意</span><span class="sxs-lookup"><span data-stu-id="18749-132">Note</span></span>**  
    <span data-ttu-id="18749-133">如果 Windows 修復環境（WinRE）偵測到或懷疑 Windows 7 在上次嘗試時無法正常啟動，**啟動修復**可能會開始自動執行。</span><span class="sxs-lookup"><span data-stu-id="18749-133">If the Windows Recovery Environment (WinRE) detects or suspects that Windows 7 did not start correctly the last time that it was tried, **Startup Repair** might start to run automatically.</span></span> <span data-ttu-id="18749-134">如需此情況的相關資訊（包括如何解決），請參閱[DaRT 7.0 疑難排解](troubleshooting-dart-70-new-ia.md)。</span><span class="sxs-lookup"><span data-stu-id="18749-134">For information about this situation including how to resolve it, see [Troubleshooting DaRT 7.0](troubleshooting-dart-70-new-ia.md).</span></span>



~~~
If any of the registry hives are corrupted or missing, Registry Editor, and several other DaRT utilities, will have limited functionality. If no operating system is selected, some tools will not be available.

The **System Recovery Options** window appears and lists various recovery tools.
~~~

5. <span data-ttu-id="18749-135">在 [**系統復原選項**] 視窗中，選取 [ **Microsoft 診斷與修復工具集**] 以開啟 [**診斷及修復工具集**] 視窗。</span><span class="sxs-lookup"><span data-stu-id="18749-135">On the **System Recovery Options** window, select **Microsoft Diagnostics and Recovery Toolset** to open the **Diagnostics and Recovery Toolset** window.</span></span>

6. <span data-ttu-id="18749-136">在 [**診斷及修復工具**] 視窗中，按一下 [**遠端**連線] 以開啟 [ **DaRT 遠端**連線] 視窗。</span><span class="sxs-lookup"><span data-stu-id="18749-136">On the **Diagnostics and Recovery Toolset** window, click **Remote Connection** to open the **DaRT Remote Connection** window.</span></span> <span data-ttu-id="18749-137">如果系統提示您提供支援中心的遠端存取，請按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="18749-137">If you are prompted to give the help desk remote access, click **OK**.</span></span>

   <span data-ttu-id="18749-138">隨即會開啟 [DaRT 遠端連線] 視窗，並顯示票證號碼、IP 位址和埠資訊。</span><span class="sxs-lookup"><span data-stu-id="18749-138">The DaRT Remote Connection window opens and displays a ticket number, IP address, and port information.</span></span>

7. <span data-ttu-id="18749-139">在 [服務台] 代理電腦上，開啟 [ **DaRT 遠端連線檢視器]**。</span><span class="sxs-lookup"><span data-stu-id="18749-139">On the helpdesk agent computer, open the **DaRT Remote Connection Viewer**.</span></span>

   <span data-ttu-id="18749-140">按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft DaRT 7**]，然後按一下 [ **DaRT 遠端連線檢視器]**。</span><span class="sxs-lookup"><span data-stu-id="18749-140">Click **Start**, click **All Programs**, click **Microsoft DaRT 7**, and then click **DaRT Remote Connection Viewer**.</span></span>

8. <span data-ttu-id="18749-141">在 [ **DaRT 遠端**連線] 視窗中，輸入所需的票證、IP 位址和埠資訊。</span><span class="sxs-lookup"><span data-stu-id="18749-141">In the **DaRT Remote Connection** window, enter the required ticket, IP address, and port information.</span></span>

   **<span data-ttu-id="18749-142">注意</span><span class="sxs-lookup"><span data-stu-id="18749-142">Note</span></span>**  
   <span data-ttu-id="18749-143">此資訊是在使用者電腦上建立，且必須由最終使用者提供。</span><span class="sxs-lookup"><span data-stu-id="18749-143">This information is created on the end-user computer and must be provided by the end user.</span></span> <span data-ttu-id="18749-144">可能有多個 IP 位址可供選擇，視最終使用者電腦上可用的數目而定。</span><span class="sxs-lookup"><span data-stu-id="18749-144">There might be multiple IP addresses to choose from, depending on how many are available on the end-user computer.</span></span>



9. <span data-ttu-id="18749-145">按一下 **\[連線\]**。</span><span class="sxs-lookup"><span data-stu-id="18749-145">Click **Connect**.</span></span>

<span data-ttu-id="18749-146">IT 系統管理員現在假設您可以控制最終使用者電腦，並可遠端執行 DaRT 工具。</span><span class="sxs-lookup"><span data-stu-id="18749-146">The IT administrator now assumes control of the end-user computer and can run the DaRT tools remotely.</span></span>

**<span data-ttu-id="18749-147">注意</span><span class="sxs-lookup"><span data-stu-id="18749-147">Note</span></span>**  
<span data-ttu-id="18749-148">已提供名為 inv32.xml 的檔案，其中包含遠端連線資訊，例如埠號碼和 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="18749-148">A file is provided that is named inv32.xml and contains remote connection information, such as the port number and IP address.</span></span> <span data-ttu-id="18749-149">根據預設，檔案通常位於%windir%\\system32。</span><span class="sxs-lookup"><span data-stu-id="18749-149">By default, the file is typically located at %windir%\\system32.</span></span>



**<span data-ttu-id="18749-150">自訂遠端連線進程</span><span class="sxs-lookup"><span data-stu-id="18749-150">To customize the Remote Connection process</span></span>**

1. <span data-ttu-id="18749-151">您可以編輯 winpeshl.ini 檔案，自訂遠端連線進程。</span><span class="sxs-lookup"><span data-stu-id="18749-151">You can customize the Remote Connection process by editing the winpeshl.ini file.</span></span> <span data-ttu-id="18749-152">如需如何編輯 winpeshl.ini 檔案的詳細資訊，請參閱[Winpeshl.ini](https://go.microsoft.com/fwlink/?LinkId=219413)檔案。</span><span class="sxs-lookup"><span data-stu-id="18749-152">For more information about how to edit the winpeshl.ini file, see [Winpeshl.ini Files](https://go.microsoft.com/fwlink/?LinkId=219413).</span></span>

   <span data-ttu-id="18749-153">指定下列命令和參數，來自訂如何與終端使用者電腦建立遠端連線：</span><span class="sxs-lookup"><span data-stu-id="18749-153">Specify the following commands and parameters to customize how a remote connection is established with an end-user computer:</span></span>

   <table>
   <colgroup>
   <col width="33%" />
   <col width="33%" />
   <col width="33%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="18749-154">命令</span><span class="sxs-lookup"><span data-stu-id="18749-154">Command</span></span></th>
   <th align="left"><span data-ttu-id="18749-155">參數</span><span class="sxs-lookup"><span data-stu-id="18749-155">Parameter</span></span></th>
   <th align="left"><span data-ttu-id="18749-156">描述</span><span class="sxs-lookup"><span data-stu-id="18749-156">Description</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="18749-157">RemoteRecovery.exe</span><span class="sxs-lookup"><span data-stu-id="18749-157">RemoteRecovery.exe</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="18749-158">-nomessage</span><span class="sxs-lookup"><span data-stu-id="18749-158">-nomessage</span></span></p></td>
   <td align="left"><p><span data-ttu-id="18749-159">指定不會顯示確認提示。</span><span class="sxs-lookup"><span data-stu-id="18749-159">Specifies that the confirmation prompt is not displayed.</span></span> <strong><span data-ttu-id="18749-160">[遠端連線] </strong> 繼續執行，就像最終使用者 &quot; &quot; 對確認提示作出回應時一樣。</span><span class="sxs-lookup"><span data-stu-id="18749-160">Remote Connection</strong> continues just as if the end user had responded &quot;Yes&quot; to the confirmation prompt.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="18749-161">WaitForConnection.exe</span><span class="sxs-lookup"><span data-stu-id="18749-161">WaitForConnection.exe</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="18749-162">無 (none)</span><span class="sxs-lookup"><span data-stu-id="18749-162">none</span></span></p></td>
   <td align="left"><p><span data-ttu-id="18749-163">防止自訂腳本繼續進行，直到 <strong> 沒有執行任何遠端連線 </strong> ，或是與使用者電腦建立有效的連線。</span><span class="sxs-lookup"><span data-stu-id="18749-163">Prevents a custom script from continuing until either <strong>Remote Connection</strong> is not running or a valid connection is established with the end-user computer.</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="18749-164">重要</span><span class="sxs-lookup"><span data-stu-id="18749-164">Important</span></span></strong><br/><p><span data-ttu-id="18749-165">這個命令不會提供任何函數（如果它是獨立指定的）。</span><span class="sxs-lookup"><span data-stu-id="18749-165">This command serves no function if it is specified independently.</span></span> <span data-ttu-id="18749-166">必須在腳本中指定它才能正常運作。</span><span class="sxs-lookup"><span data-stu-id="18749-166">It must be specified in a script to function correctly.</span></span></p>
   </div>
   <div>

   </div></td>
   </tr>
   </tbody>
   </table>



2. <span data-ttu-id="18749-167">下列是自訂的 winpeshl.ini 檔案範例，只要嘗試啟動到 DaRT，就可以開啟**遠端**連線工具：</span><span class="sxs-lookup"><span data-stu-id="18749-167">The following is an example of a winpeshl.ini file that is customized to open the **Remote Connection** tool as soon as an attempt is made to boot into DaRT:</span></span>

   ```ini
   [LaunchApps]
   "%windir%\system32\netstart.exe -network -remount"
   "cmd /C start %windir%\system32\RemoteRecovery.exe -nomessage"
   "%windir%\system32\WaitForConnection.exe"
   "%SYSTEMDRIVE%\sources\recovery\recenv.exe"
   ```

**<span data-ttu-id="18749-168">在命令提示字元執行遠端連線檢視器</span><span class="sxs-lookup"><span data-stu-id="18749-168">To run the Remote Connection Viewer at the command prompt</span></span>**

1.  <span data-ttu-id="18749-169">您可以在命令提示字元上執行**DaRT 遠端連線檢視器**，方法是指定**DartRemoteViewer.exe**命令，並使用下列參數：</span><span class="sxs-lookup"><span data-stu-id="18749-169">You can run the **DaRT Remote Connection Viewer** at the command prompt by specifying the **DartRemoteViewer.exe** command and by using the following parameters:</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="18749-170">參數</span><span class="sxs-lookup"><span data-stu-id="18749-170">Parameter</span></span></th>
    <th align="left"><span data-ttu-id="18749-171">描述</span><span class="sxs-lookup"><span data-stu-id="18749-171">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="18749-172">-ticket = &lt; <em> ticketnumber</em>&gt;</span><span class="sxs-lookup"><span data-stu-id="18749-172">-ticket=&lt;<em>ticketnumber</em>&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="18749-173">其中 &lt; <em> ticketnumber </em> &gt; 是由遠端連線產生的票證編號，包括虛線。</span><span class="sxs-lookup"><span data-stu-id="18749-173">Where &lt;<em>ticketnumber</em>&gt; is the ticket number, including the dashes, that is generated by Remote Connection.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="18749-174">-ipaddress = &lt; <em> ipaddress</em>&gt;</span><span class="sxs-lookup"><span data-stu-id="18749-174">-ipaddress=&lt;<em>ipaddress</em>&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="18749-175">其中， &lt; <em> Ipaddress </em> &gt; 是遠端連線所產生的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="18749-175">Where &lt;<em>ipaddress</em>&gt; is the IP address that is generated by Remote Connection.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="18749-176">-port = &lt; <em> 埠</em>&gt;</span><span class="sxs-lookup"><span data-stu-id="18749-176">-port=&lt;<em>port</em>&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="18749-177">其中 &lt; <em> port </em> &gt; 是對應至指定 IP 位址的埠。</span><span class="sxs-lookup"><span data-stu-id="18749-177">Where &lt;<em>port</em>&gt; is the port that corresponds to the specified IP address.</span></span></p></td>
    </tr>
    </tbody>
    </table>



~~~
**Note**  
The variables for these parameters are created on the end-user computer and must be provided by the end user.
~~~



2. <span data-ttu-id="18749-178">如果所有三個參數都已指定，且資料有效，則會在程式啟動時立即嘗試連接。</span><span class="sxs-lookup"><span data-stu-id="18749-178">If all three parameters are specified and the data is valid, a connection is immediately tried when the program starts.</span></span> <span data-ttu-id="18749-179">如果有任何參數無效，程式就會啟動，就好像沒有指定參數一樣。</span><span class="sxs-lookup"><span data-stu-id="18749-179">If any parameter is not valid, the program starts as if there were no parameters specified.</span></span>

## <span data-ttu-id="18749-180">相關主題</span><span class="sxs-lookup"><span data-stu-id="18749-180">Related topics</span></span>


[<span data-ttu-id="18749-181">使用 DaRT 7.0 復原電腦</span><span class="sxs-lookup"><span data-stu-id="18749-181">Recovering Computers Using DaRT 7.0</span></span>](recovering-computers-using-dart-70-dart-7.md)









