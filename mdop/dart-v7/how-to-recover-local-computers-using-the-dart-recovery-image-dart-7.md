---
title: 如何使用 DaRT 復原映像來復原本機電腦
description: 如何使用 DaRT 復原映像來復原本機電腦
author: dansimp
ms.assetid: be29b5a8-be08-4cf2-822e-77a51d3f3b65
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4c605db895b5ea812d90db51d3c2de9653e2dd2d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810149"
---
# <span data-ttu-id="477db-103">如何使用 DaRT 復原映像來復原本機電腦</span><span class="sxs-lookup"><span data-stu-id="477db-103">How to Recover Local Computers Using the DaRT Recovery Image</span></span>


<span data-ttu-id="477db-104">若要使用 Microsoft Diagnostics 和恢復工具組（DaRT）7來復原本機電腦，您必須在遇到需要 DaRT 之問題的使用者電腦上實際出現。</span><span class="sxs-lookup"><span data-stu-id="477db-104">To recover a local computer by using Microsoft Diagnostics and Recovery Toolset (DaRT) 7, you must be physically present at the end-user computer that is experiencing problems that require DaRT.</span></span> <span data-ttu-id="477db-105">您也可以依照[如何使用 Dart 復原影像復原遠端電腦](how-to-recover-remote-computers-using-the-dart-recovery-image-dart-7.md)的指示，遠端執行 DaRT。</span><span class="sxs-lookup"><span data-stu-id="477db-105">You can also run DaRT remotely by following the instructions at [How to Recover Remote Computers Using the DaRT Recovery Image](how-to-recover-remote-computers-using-the-dart-recovery-image-dart-7.md).</span></span>

**<span data-ttu-id="477db-106">使用 DaRT 復原本機電腦</span><span class="sxs-lookup"><span data-stu-id="477db-106">To recover a local computer by using DaRT</span></span>**

1.  <span data-ttu-id="477db-107">當電腦啟動至 DaRT 復原影像時，會出現 [ **NetStart** ] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="477db-107">As the computer is booting into the DaRT recovery image, the **NetStart** dialog box appears.</span></span> <span data-ttu-id="477db-108">系統會詢問您是否要初始化網路服務。</span><span class="sxs-lookup"><span data-stu-id="477db-108">You are asked whether you want to initialize network services.</span></span> <span data-ttu-id="477db-109">如果您按一下 **[是]**，系統會假設 DHCP 伺服器出現在網路上，且嘗試從伺服器取得 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="477db-109">If you click **Yes**, it is assumed that a DHCP server is present on the network and an attempt is made to obtain an IP address from the server.</span></span> <span data-ttu-id="477db-110">如果網路使用靜態 IP 位址而不是 DHCP，您可以稍後在 DaRT 中使用**Tcp/ip 配置**工具來指定靜態 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="477db-110">If the network uses static IP addresses instead of DHCP, you can later use the **TCP/IP Configuration** tool in DaRT to specify a static IP address.</span></span>

    <span data-ttu-id="477db-111">若要略過網路初始化程式，請按一下 [**否**]。</span><span class="sxs-lookup"><span data-stu-id="477db-111">To skip the network initialization process, click **No**.</span></span>

2.  <span data-ttu-id="477db-112">在 [網路初始化] 對話方塊中，系統會詢問您是否要重新映射磁片磁碟機盤符。</span><span class="sxs-lookup"><span data-stu-id="477db-112">Following the network initialization dialog box, you are asked whether you want to remap the drive letters.</span></span> <span data-ttu-id="477db-113">當您執行 Windows online 時，系統磁碟區通常會對應到磁碟機 C。不過，當您在 [WinRE] 下執行 Windows 離線時，原始的系統磁碟區可能會對應到另一個磁片磁碟機，這可能會造成混淆。</span><span class="sxs-lookup"><span data-stu-id="477db-113">When you run Windows online, the system volume is typically mapped to drive C. However, when you run Windows offline under WinRE, the original system volume might be mapped to another drive, and this can cause confusion.</span></span> <span data-ttu-id="477db-114">如果您決定重新映射，DaRT 會嘗試對應離線磁碟機盤符，以符合線上磁片磁碟機盤符。</span><span class="sxs-lookup"><span data-stu-id="477db-114">If you decide to remap, DaRT tries to map the offline drive letters to match the online drive letters.</span></span> <span data-ttu-id="477db-115">只有在後續的啟動程式中選取了離線作業系統時，才會執行重新映射。</span><span class="sxs-lookup"><span data-stu-id="477db-115">Remapping is performed only if an offline operating system is selected later in the startup process.</span></span>

3.  <span data-ttu-id="477db-116">在重新變換對話方塊之後，會出現 [**系統復原選項**] 對話方塊，要求您選取鍵盤配置。</span><span class="sxs-lookup"><span data-stu-id="477db-116">Following the remapping dialog box, a **System Recovery Options** dialog box appears and asks you to select a keyboard layout.</span></span> <span data-ttu-id="477db-117">接著，它會顯示系統根目錄、所安裝的作業系統類型，以及分區大小。</span><span class="sxs-lookup"><span data-stu-id="477db-117">Then it displays the system root directory, the kind of operating system installed, and the partition size.</span></span> <span data-ttu-id="477db-118">如果您沒有看到您的作業系統，且懷疑驅動程式缺乏可能造成失敗，請按一下 [**載入驅動**程式] 載入可疑的驅動程式。</span><span class="sxs-lookup"><span data-stu-id="477db-118">If you do not see your operating system listed, and suspect that the lack of drivers is a possible cause of the failure, click **Load Drivers** to load the suspect drivers.</span></span> <span data-ttu-id="477db-119">這會提示您插入裝置的安裝媒體及選取驅動程式。</span><span class="sxs-lookup"><span data-stu-id="477db-119">This prompts you to insert the installation media for the device and to select the driver.</span></span> <span data-ttu-id="477db-120">選取您要修復或診斷的安裝，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="477db-120">Select the installation that you want to repair or diagnose, and then click **Next**.</span></span>

    **<span data-ttu-id="477db-121">注意</span><span class="sxs-lookup"><span data-stu-id="477db-121">Note</span></span>**  
    <span data-ttu-id="477db-122">如果 Windows 修復環境（WinRE）偵測到或懷疑 Windows 7 在上次嘗試時無法正常啟動，**啟動修復**可能會開始自動執行。</span><span class="sxs-lookup"><span data-stu-id="477db-122">If the Windows Recovery Environment (WinRE) detects or suspects that Windows 7 did not start correctly the last time that it was tried, **Startup Repair** might start to run automatically.</span></span>



~~~
If any of the registry hives are corrupted or missing, Registry Editor, and several other DaRT utilities, will have limited functionality. If no operating system is selected, some tools will not be available.

The **System Recovery Options** window appears and lists various recovery tools.
~~~

4. <span data-ttu-id="477db-123">在 [**系統復原選項**] 視窗中，按一下 [ **Microsoft 診斷與修復工具**組]。</span><span class="sxs-lookup"><span data-stu-id="477db-123">On the **System Recovery Options** window, click **Microsoft Diagnostics and Recovery Toolset**.</span></span>

   <span data-ttu-id="477db-124">隨即會開啟 [**診斷與修復工具集**] 視窗。</span><span class="sxs-lookup"><span data-stu-id="477db-124">The **Diagnostics and Recovery Toolset** window opens.</span></span> <span data-ttu-id="477db-125">您現在可以執行在建立 DaRT 復原影像時所包含的任何個別工具或嚮導。</span><span class="sxs-lookup"><span data-stu-id="477db-125">You can now run any of the individual tools or wizards that were included when the DaRT recovery image was created.</span></span>

<span data-ttu-id="477db-126">您可以按一下 [**診斷及修復工具集**] 視窗**上的 [** 說明]，開啟用戶端說明檔案，提供執行個別 DaRT 工具所需的詳細指示和資訊。</span><span class="sxs-lookup"><span data-stu-id="477db-126">You can click **Help** on the **Diagnostics and Recovery Toolset** window to open the client Help file that provides detailed instruction and information needed to run the individual DaRT tools.</span></span> <span data-ttu-id="477db-127">您也可以按一下 [**診斷及復原工具集**] 視窗上的 [**方案嚮導**]，根據嚮導所提供的簡短訪談，選擇適合情況的最佳工具。</span><span class="sxs-lookup"><span data-stu-id="477db-127">You can also click the **Solution Wizard** on the **Diagnostics and Recovery Toolset** window to choose the best tool for the situation, based on a brief interview that the wizard provides.</span></span>

<span data-ttu-id="477db-128">如需任何 DaRT 工具的一般資訊，請參閱[DaRT 7.0 中的工具概覽](overview-of-the-tools-in-dart-70-new-ia.md)。</span><span class="sxs-lookup"><span data-stu-id="477db-128">For general information about any of the DaRT tools, see [Overview of the Tools in DaRT 7.0](overview-of-the-tools-in-dart-70-new-ia.md).</span></span>

**<span data-ttu-id="477db-129">在命令提示字元執行 DaRT</span><span class="sxs-lookup"><span data-stu-id="477db-129">To run DaRT at the command prompt</span></span>**

1. <span data-ttu-id="477db-130">您可以在命令提示字元中，使用下列任何一個參數指定**netstart.exe**命令，以執行 DaRT：</span><span class="sxs-lookup"><span data-stu-id="477db-130">You can run DaRT at the command prompt by specifying the **netstart.exe** command and by using any of the following parameters:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="477db-131">參數</span><span class="sxs-lookup"><span data-stu-id="477db-131">Parameter</span></span></th>
   <th align="left"><span data-ttu-id="477db-132">描述</span><span class="sxs-lookup"><span data-stu-id="477db-132">Description</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="477db-133">-網路</span><span class="sxs-lookup"><span data-stu-id="477db-133">-network</span></span></p></td>
   <td align="left"><p><span data-ttu-id="477db-134">初始化網路服務。</span><span class="sxs-lookup"><span data-stu-id="477db-134">Initializes the network services.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="477db-135">重新裝載</span><span class="sxs-lookup"><span data-stu-id="477db-135">-remount</span></span></p></td>
   <td align="left"><p><span data-ttu-id="477db-136">重新映射磁片磁碟機盤符。</span><span class="sxs-lookup"><span data-stu-id="477db-136">Remaps the drive letters.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="477db-137">-提示</span><span class="sxs-lookup"><span data-stu-id="477db-137">-prompt</span></span></p></td>
   <td align="left"><p><span data-ttu-id="477db-138">顯示訊息，要求使用者指定是否要初始化網路並重新映射磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="477db-138">Displays messages asking the end user to specify whether to initialize the network and remap the drives.</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="477db-139">重要</span><span class="sxs-lookup"><span data-stu-id="477db-139">Important</span></span></strong><br/><p><span data-ttu-id="477db-140">使用者對提示的回應會覆寫網路和重新裝載開關。</span><span class="sxs-lookup"><span data-stu-id="477db-140">The end user’s response to the prompts overrides the -network and -remount switches.</span></span></p>
   </div>
   <div>

   </div></td>
   </tr>
   </tbody>
   </table>



2. <span data-ttu-id="477db-141">您可以自訂 DaRT，讓啟動至 DaRT 的電腦自動開啟用來建立與技術支援人員的遠端連線的**遠端連線**工具。</span><span class="sxs-lookup"><span data-stu-id="477db-141">You can customize DaRT so that a computer that boots into DaRT automatically opens the **Remote Connection** tool that is used to establish a remote connection with the help desk.</span></span>

## <span data-ttu-id="477db-142">相關主題</span><span class="sxs-lookup"><span data-stu-id="477db-142">Related topics</span></span>


[<span data-ttu-id="477db-143">使用 DaRT 7.0 復原電腦</span><span class="sxs-lookup"><span data-stu-id="477db-143">Recovering Computers Using DaRT 7.0</span></span>](recovering-computers-using-dart-70-dart-7.md)









