---
title: 如何使用 DaRT 復原映像來復原本機電腦
description: 如何使用 DaRT 復原映像來復原本機電腦
author: dansimp
ms.assetid: f679d522-49ab-429c-93d0-294c3f3e5639
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1b5faa0eb9ac24b33c66f1d5262a050b92e11e52
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810478"
---
# <span data-ttu-id="c249b-103">如何使用 DaRT 復原映像來復原本機電腦</span><span class="sxs-lookup"><span data-stu-id="c249b-103">How to Recover Local Computers by Using the DaRT Recovery Image</span></span>


<span data-ttu-id="c249b-104">當您實際出現在遇到問題的使用者電腦上時，請使用下列指示來復原電腦。</span><span class="sxs-lookup"><span data-stu-id="c249b-104">Use these instructions to recover a computer when you are physically present at the end-user computer that is experiencing problems.</span></span>

**<span data-ttu-id="c249b-105">如何使用 DaRT 恢復影像來復原本機電腦</span><span class="sxs-lookup"><span data-stu-id="c249b-105">How to recover a local computer by using the DaRT recovery image</span></span>**

1.  <span data-ttu-id="c249b-106">使用 Microsoft Diagnostics 和復原工具庫（DaRT）8.0 復原影像來啟動使用者電腦。</span><span class="sxs-lookup"><span data-stu-id="c249b-106">Boot the end-user computer by using the Microsoft Diagnostics and Recovery Toolset (DaRT) 8.0 recovery image.</span></span>

    <span data-ttu-id="c249b-107">當電腦啟動至 DaRT 8.0 恢復影像時，會出現 [ **NetStart** ] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="c249b-107">As the computer is booting into the DaRT 8.0 recovery image, the **NetStart** dialog box appears.</span></span>

2.  <span data-ttu-id="c249b-108">當系統詢問您是否要初始化網路服務時，請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="c249b-108">When you are asked whether you want to initialize network services, select one of the following:</span></span>

    <span data-ttu-id="c249b-109">**是**-假設您有 DHCP 伺服器出現在網路上，且嘗試從伺服器取得 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="c249b-109">**Yes** - it is assumed that a DHCP server is present on the network, and an attempt is made to obtain an IP address from the server.</span></span> <span data-ttu-id="c249b-110">如果網路使用靜態 IP 位址而不是 DHCP，您可以稍後在 DaRT 中使用**Tcp/ip 配置**工具來指定靜態 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="c249b-110">If the network uses static IP addresses instead of DHCP, you can later use the **TCP/IP Configuration** tool in DaRT to specify a static IP address.</span></span>

    <span data-ttu-id="c249b-111">**否**-略過網路初始化程式。</span><span class="sxs-lookup"><span data-stu-id="c249b-111">**No** - skip the network initialization process.</span></span>

3.  <span data-ttu-id="c249b-112">指出您是否要重新映射磁片磁碟機盤符。</span><span class="sxs-lookup"><span data-stu-id="c249b-112">Indicate whether you want to remap the drive letters.</span></span> <span data-ttu-id="c249b-113">當您執行 Windows online 時，系統磁碟區通常會對應到磁碟機 C。不過，當您在 [WinRE] 下執行 Windows 離線時，原始的系統磁碟區可能會對應到另一個磁片磁碟機，這可能會造成混淆。</span><span class="sxs-lookup"><span data-stu-id="c249b-113">When you run Windows online, the system volume is typically mapped to drive C. However, when you run Windows offline under WinRE, the original system volume might be mapped to another drive, and this can cause confusion.</span></span> <span data-ttu-id="c249b-114">如果您決定重新映射，DaRT 會嘗試對應離線磁碟機盤符，以符合線上磁片磁碟機盤符。</span><span class="sxs-lookup"><span data-stu-id="c249b-114">If you decide to remap, DaRT tries to map the offline drive letters to match the online drive letters.</span></span> <span data-ttu-id="c249b-115">只有在後續的啟動程式中選取了離線作業系統時，才會執行重新映射。</span><span class="sxs-lookup"><span data-stu-id="c249b-115">Remapping is performed only if an offline operating system is selected later in the startup process.</span></span>

4.  <span data-ttu-id="c249b-116">在 [**系統復原選項**] 對話方塊中，選取鍵盤配置。</span><span class="sxs-lookup"><span data-stu-id="c249b-116">On the **System Recovery Options** dialog box, select a keyboard layout.</span></span>

5.  <span data-ttu-id="c249b-117">檢查顯示的系統根目錄、所安裝的作業系統類型，以及分區大小。</span><span class="sxs-lookup"><span data-stu-id="c249b-117">Check the displayed system root directory, the kind of operating system installed, and the partition size.</span></span> <span data-ttu-id="c249b-118">如果您沒有看到您的作業系統，且懷疑驅動程式缺乏可能造成失敗的原因，請按一下 [**載入驅動**程式] 載入可疑的驅動程式，然後選取驅動程式的安裝媒體。</span><span class="sxs-lookup"><span data-stu-id="c249b-118">If you do not see your operating system listed, and suspect that the lack of drivers is a possible cause of the failure, click **Load Drivers** to load the suspect drivers, and then insert the installation media for the device and select the driver.</span></span>

6.  <span data-ttu-id="c249b-119">選取您要修復或診斷的安裝，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c249b-119">Select the installation that you want to repair or diagnose, and then click **Next**.</span></span>

    **<span data-ttu-id="c249b-120">注意</span><span class="sxs-lookup"><span data-stu-id="c249b-120">Note</span></span>**  
    <span data-ttu-id="c249b-121">如果 Windows 修復環境（WinRE）檢測到或懷疑 Windows 8 無法正常啟動，則**啟動修復**可能會開始自動執行。</span><span class="sxs-lookup"><span data-stu-id="c249b-121">If the Windows Recovery Environment (WinRE) detects or suspects that Windows 8 did not start correctly the last time that it was tried, **Startup Repair** might start to run automatically.</span></span>



~~~
If any of the registry hives are corrupted or missing, Registry Editor and several other DaRT utilities will have limited functionality. If no operating system is selected, some tools will not be available.

The **System Recovery Options** window appears and lists various recovery tools.
~~~

7. <span data-ttu-id="c249b-122">在 [**系統復原選項**] 視窗中，按一下 [ **Microsoft 診斷與修復工具**組]。</span><span class="sxs-lookup"><span data-stu-id="c249b-122">On the **System Recovery Options** window, click **Microsoft Diagnostics and Recovery Toolset**.</span></span>

   <span data-ttu-id="c249b-123">隨即會開啟 [**診斷與修復工具集**] 視窗。</span><span class="sxs-lookup"><span data-stu-id="c249b-123">The **Diagnostics and Recovery Toolset** window opens.</span></span> <span data-ttu-id="c249b-124">您現在可以執行在建立 DaRT 復原影像時所包含的任何個別工具或嚮導。</span><span class="sxs-lookup"><span data-stu-id="c249b-124">You can now run any of the individual tools or wizards that were included when the DaRT recovery image was created.</span></span>

<span data-ttu-id="c249b-125">您可以按一下 [**診斷及修復工具集**] 視窗**上的 [** 說明]，開啟用戶端說明檔案，提供執行個別 DaRT 工具所需的詳細指示和資訊。</span><span class="sxs-lookup"><span data-stu-id="c249b-125">You can click **Help** on the **Diagnostics and Recovery Toolset** window to open the client Help file that provides detailed instruction and information needed to run the individual DaRT tools.</span></span> <span data-ttu-id="c249b-126">您也可以按一下 [**診斷及復原工具集**] 視窗上的 [**方案嚮導**]，根據嚮導所提供的簡短訪談，選擇適合情況的最佳工具。</span><span class="sxs-lookup"><span data-stu-id="c249b-126">You can also click the **Solution Wizard** on the **Diagnostics and Recovery Toolset** window to choose the best tool for the situation, based on a brief interview that the wizard provides.</span></span>

<span data-ttu-id="c249b-127">如需任何 DaRT 工具的一般資訊，請參閱[DaRT 8.0 中的工具概覽](overview-of-the-tools-in-dart-80-dart-8.md)。</span><span class="sxs-lookup"><span data-stu-id="c249b-127">For general information about any of the DaRT tools, see [Overview of the Tools in DaRT 8.0](overview-of-the-tools-in-dart-80-dart-8.md).</span></span>

**<span data-ttu-id="c249b-128">如何在命令提示字元中執行 DaRT</span><span class="sxs-lookup"><span data-stu-id="c249b-128">How to run DaRT at the command prompt</span></span>**

- <span data-ttu-id="c249b-129">若要在命令提示字元執行 DaRT，請指定**netstart.exe**命令，然後使用下列任何一個參數：</span><span class="sxs-lookup"><span data-stu-id="c249b-129">To run DaRT at the command prompt, specify the **netstart.exe** command then use any of the following parameters:</span></span>

  <table>
  <colgroup>
  <col width="50%" />
  <col width="50%" />
  </colgroup>
  <tbody>
  <tr class="odd">
  <td align="left"><p><strong><span data-ttu-id="c249b-130">參數</span><span class="sxs-lookup"><span data-stu-id="c249b-130">Parameter</span></span></strong></p></td>
  <td align="left"><p><strong><span data-ttu-id="c249b-131">描述</span><span class="sxs-lookup"><span data-stu-id="c249b-131">Description</span></span></strong></p></td>
  </tr>
  <tr class="even">
  <td align="left"><p><span data-ttu-id="c249b-132">-網路</span><span class="sxs-lookup"><span data-stu-id="c249b-132">-network</span></span></p></td>
  <td align="left"><p><span data-ttu-id="c249b-133">初始化網路服務。</span><span class="sxs-lookup"><span data-stu-id="c249b-133">Initializes the network services.</span></span></p></td>
  </tr>
  <tr class="odd">
  <td align="left"><p><span data-ttu-id="c249b-134">重新裝載</span><span class="sxs-lookup"><span data-stu-id="c249b-134">-remount</span></span></p></td>
  <td align="left"><p><span data-ttu-id="c249b-135">重新映射磁片磁碟機盤符。</span><span class="sxs-lookup"><span data-stu-id="c249b-135">Remaps the drive letters.</span></span></p></td>
  </tr>
  <tr class="even">
  <td align="left"><p><span data-ttu-id="c249b-136">-提示</span><span class="sxs-lookup"><span data-stu-id="c249b-136">-prompt</span></span></p></td>
  <td align="left"><p><span data-ttu-id="c249b-137">顯示訊息，要求使用者指定是否要初始化網路並重新映射磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="c249b-137">Displays messages that ask the end user to specify whether to initialize the network and remap the drives.</span></span></p>
  <div class="alert">
  <strong><span data-ttu-id="c249b-138">警告</span><span class="sxs-lookup"><span data-stu-id="c249b-138">Warning</span></span></strong><br/><p><span data-ttu-id="c249b-139">最終使用者對提示的回應會覆寫 [網路] 和 [重新裝載] 交換器。</span><span class="sxs-lookup"><span data-stu-id="c249b-139">The end user’s response to the prompt overrides the –network and –remount switches.</span></span></p>
  </div>
  <div>

  </div></td>
  </tr>
  </tbody>
  </table>



## <span data-ttu-id="c249b-140">相關主題</span><span class="sxs-lookup"><span data-stu-id="c249b-140">Related topics</span></span>


[<span data-ttu-id="c249b-141">適用於 DaRT 8.0 的操作</span><span class="sxs-lookup"><span data-stu-id="c249b-141">Operations for DaRT 8.0</span></span>](operations-for-dart-80-dart-8.md)

[<span data-ttu-id="c249b-142">使用 DaRT 8.0 復原電腦</span><span class="sxs-lookup"><span data-stu-id="c249b-142">Recovering Computers Using DaRT 8.0</span></span>](recovering-computers-using-dart-80-dart-8.md)









