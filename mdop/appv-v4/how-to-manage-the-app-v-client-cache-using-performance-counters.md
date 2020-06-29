---
title: 如何使用效能計數器管理 App-V 用戶端快取
description: 如何使用效能計數器管理 App-V 用戶端快取
author: dansimp
ms.assetid: 49d6c3f2-68b8-4c69-befa-7598a8737d05
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 396cceaf9a3bde661200be2771a85596a512732f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801294"
---
# <span data-ttu-id="00f80-103">如何使用效能計數器管理 App-V 用戶端快取</span><span class="sxs-lookup"><span data-stu-id="00f80-103">How to Manage the App-V Client Cache Using Performance Counters</span></span>


<span data-ttu-id="00f80-104">您可以在應用程式虛擬化（App-v）用戶端快取中使用 [效能監視器] 以圖形顯示資訊來判斷有多少可用空間。</span><span class="sxs-lookup"><span data-stu-id="00f80-104">You can use the following procedure to determine how much free space is available in the Application Virtualization (App-V) client cache by using Performance Monitor to display the information graphically.</span></span> <span data-ttu-id="00f80-105">此資訊是在用戶端電腦上透過一個名為「應用程式 Virt 用戶端快取」的效能計數器來捕獲，且包含下列計數器：「快取大小（MB）」、「快取磁碟空間（MB）」和「% 可用空間」。</span><span class="sxs-lookup"><span data-stu-id="00f80-105">This information is captured on the client computer by a performance counter called “App Virt Client Cache,” and it includes the following counters: “Cache size (MB),” “Cache free space (MB),” and “% free space.”</span></span>

**<span data-ttu-id="00f80-106">判斷用戶端的快取空間使用量</span><span class="sxs-lookup"><span data-stu-id="00f80-106">To determine client cache space usage</span></span>**

1.  <span data-ttu-id="00f80-107">以系統管理員身分開啟命令提示字元，或按一下 [**開始**]、[**執行**]，輸入**perfmon.exe**，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="00f80-107">Open a command prompt as administrator, or click **Start**, **Run**, type **perfmon.exe**, and click **OK**.</span></span>

2.  <span data-ttu-id="00f80-108">根據所使用的 Windows 作業系統，在 MMC 視窗開啟後，按一下 [效能監視器] 或 [系統監視器] 工具。</span><span class="sxs-lookup"><span data-stu-id="00f80-108">Depending on the Windows operating system being used, click the Performance Monitor or System Monitor tool after the MMC window opens.</span></span>

3.  <span data-ttu-id="00f80-109">若要新增計數器，請以滑鼠右鍵按一下繪圖區域，然後選取 [**新增計數器**]。</span><span class="sxs-lookup"><span data-stu-id="00f80-109">To add counters, right-click the graph area and select **Add Counters**.</span></span>

4.  <span data-ttu-id="00f80-110">按一下下拉式清單以顯示可用計數器的清單、滾動至 [尋找**應用程式 Virt 用戶端**快取]，然後新增三個計數器。</span><span class="sxs-lookup"><span data-stu-id="00f80-110">Click the drop-down to display the list of available counters, scroll to find **App Virt Client Cache**, and then add the three counters.</span></span>

    <span data-ttu-id="00f80-111">**重要** App V 效能計數器是在32位 DLL 中實現，因此若要查看它們，您必須使用下列命令來啟動32位版本的效能監視器： **mmc/32 perfmon**。</span><span class="sxs-lookup"><span data-stu-id="00f80-111">**Important** The App-V performance counters are implemented in a 32-bit DLL, so to see them, you must use the following command to start the 32-bit version of Performance Monitor: **mmc /32 perfmon.msc**.</span></span> <span data-ttu-id="00f80-112">這個命令必須直接在受監視的電腦上執行，而且無法用來監視執行64位作業系統的遠端電腦。</span><span class="sxs-lookup"><span data-stu-id="00f80-112">This command must be run directly on the computer being monitored and cannot be used to monitor a remote computer running a 64-bit operating system.</span></span>

     

## <span data-ttu-id="00f80-113">相關主題</span><span class="sxs-lookup"><span data-stu-id="00f80-113">Related topics</span></span>


[<span data-ttu-id="00f80-114">如何使用命令列管理虛擬應用程式</span><span class="sxs-lookup"><span data-stu-id="00f80-114">How to Manage Virtual Applications by Using the Command Line</span></span>](how-to-manage-virtual-applications-by-using-the-command-line.md)

 

 





