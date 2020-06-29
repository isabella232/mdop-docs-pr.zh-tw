---
title: 如何使用 PowerShell 來建立封裝加速器
description: 如何使用 PowerShell 來建立封裝加速器
author: dansimp
ms.assetid: 0cb98394-4477-4193-8c5f-1c1773c7263a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 347572343cff058a7494574035464d66c4d61be4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800554"
---
# <span data-ttu-id="f7a85-103">如何使用 PowerShell 來建立封裝加速器</span><span class="sxs-lookup"><span data-stu-id="f7a85-103">How to Create a Package Accelerator by Using PowerShell</span></span>


<span data-ttu-id="f7a85-104">App-v 5.1 套件加速器會自動序列化大型、複雜的應用程式。</span><span class="sxs-lookup"><span data-stu-id="f7a85-104">App-V 5.1 package accelerators automatically sequence large, complex applications.</span></span> <span data-ttu-id="f7a85-105">此外，當您套用 app-v 5.1 套件加速器時，您不一定必須手動安裝應用程式，才能建立虛擬化套件。</span><span class="sxs-lookup"><span data-stu-id="f7a85-105">Additionally, when you apply an App-V 5.1 package accelerator, you are not always required to manually install an application to create the virtualized package.</span></span>

**<span data-ttu-id="f7a85-106">建立套件加速器</span><span class="sxs-lookup"><span data-stu-id="f7a85-106">To create a package accelerator</span></span>**

1.  <span data-ttu-id="f7a85-107">安裝 App-v 5.1 排序器。</span><span class="sxs-lookup"><span data-stu-id="f7a85-107">Install the App-V 5.1 sequencer.</span></span> <span data-ttu-id="f7a85-108">如需有關安裝排序器的詳細資訊，請參閱[如何安裝排序](how-to-install-the-sequencer-51beta-gb18030.md)器。</span><span class="sxs-lookup"><span data-stu-id="f7a85-108">For more information about installing the sequencer see [How to Install the Sequencer](how-to-install-the-sequencer-51beta-gb18030.md).</span></span>

2.  <span data-ttu-id="f7a85-109">若要開啟 PowerShell 主控台，請按一下 [**開始**]，然後輸入**powershell**。</span><span class="sxs-lookup"><span data-stu-id="f7a85-109">To open a PowerShell console click **Start** and type **PowerShell**.</span></span> <span data-ttu-id="f7a85-110">以滑鼠右鍵按一下 **Windows PowerShell**，並選取 **\[以系統管理員身分執行\]**。</span><span class="sxs-lookup"><span data-stu-id="f7a85-110">Right-click **Windows PowerShell** and select **Run as Administrator**.</span></span> <span data-ttu-id="f7a85-111">使用**AppvPackageAccelerator** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f7a85-111">Use the **New-AppvPackageAccelerator** cmdlet.</span></span>

3.  <span data-ttu-id="f7a85-112">若要建立套件加速器，請確定您有要從中建立加速器的 appv 套件、安裝媒體或安裝檔案，以及可供加速器使用的使用者選擇 [讀我檔案]。</span><span class="sxs-lookup"><span data-stu-id="f7a85-112">To create a package accelerator, make sure that you have the .appv package to create an accelerator from, the installation media or installation files, and optionally a read me file for consumers of the accelerator to use.</span></span> <span data-ttu-id="f7a85-113">下列參數是使用封裝快速鍵 Cmdlet 所需的：</span><span class="sxs-lookup"><span data-stu-id="f7a85-113">The following parameters are required to use the package accelerator cmdlet:</span></span>

    -   <span data-ttu-id="f7a85-114">**InstalledFilesPath** -指定應用程式的安裝路徑。</span><span class="sxs-lookup"><span data-stu-id="f7a85-114">**InstalledFilesPath** - specifies the application installation path.</span></span>

    -   <span data-ttu-id="f7a85-115">**安裝**程式–指定應用程式安裝程式媒體的路徑</span><span class="sxs-lookup"><span data-stu-id="f7a85-115">**Installer** – specifies the path to the application installer media</span></span>

    -   <span data-ttu-id="f7a85-116">**InputPackagePath** –指定 appv 包的路徑</span><span class="sxs-lookup"><span data-stu-id="f7a85-116">**InputPackagePath** – specifies the path to the .appv package</span></span>

    -   <span data-ttu-id="f7a85-117">**Path** -指定套件的輸出目錄。</span><span class="sxs-lookup"><span data-stu-id="f7a85-117">**Path** – specifies the output directory for the package.</span></span>

    <span data-ttu-id="f7a85-118">下列範例顯示如何使用 appv 封裝與安裝媒體來建立套件加速器：</span><span class="sxs-lookup"><span data-stu-id="f7a85-118">The following example displays how you can create a package accelerator with an .appv package and the installation media:</span></span>

    **<span data-ttu-id="f7a85-119">AppvPackageAccelerator-InputPackagePath &lt; 路徑，到 &gt; 安裝程式可執行檔的 appv 檔案安裝程式 &lt; 路徑（ &gt; &lt; 輸出路徑的路徑目錄）&gt;</span><span class="sxs-lookup"><span data-stu-id="f7a85-119">New-AppvPackageAccelerator -InputPackagePath &lt;path to the .appv file&gt; -Installer &lt;path to the installer executable&gt; -Path &lt;directory of the output path&gt;</span></span>**

    <span data-ttu-id="f7a85-120">您可以在下列清單中顯示可搭配使用**AppvPackageAccelerator** Cmdlet 的其他可選參數：</span><span class="sxs-lookup"><span data-stu-id="f7a85-120">Additional optional parameters that can be used with the **New-AppvPackageAccelerator** cmdlet are displayed in the following list:</span></span>

    -   <span data-ttu-id="f7a85-121">**AcceleratorDescriptionFile** -指定使用者建立的套件快速鍵指示路徑。</span><span class="sxs-lookup"><span data-stu-id="f7a85-121">**AcceleratorDescriptionFile** - specifies the path to user created package accelerator instructions.</span></span> <span data-ttu-id="f7a85-122">封裝快速鍵指示是使用 [套件加速器] 建立的套件所封裝的 **.txt**或 **.rtf**描述檔。</span><span class="sxs-lookup"><span data-stu-id="f7a85-122">The package accelerator instructions are **.txt** or **.rtf** description files that will be packaged with the package created using the package accelerator.</span></span>

    <span data-ttu-id="f7a85-123">您**有應用程式-V 的建議**嗎？</span><span class="sxs-lookup"><span data-stu-id="f7a85-123">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="f7a85-124">在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="f7a85-124">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="f7a85-125">有應用程式-V 問題嗎？</span><span class="sxs-lookup"><span data-stu-id="f7a85-125">Got an App-V issue?</span></span>** <span data-ttu-id="f7a85-126">使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="f7a85-126">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="f7a85-127">相關主題</span><span class="sxs-lookup"><span data-stu-id="f7a85-127">Related topics</span></span>


[<span data-ttu-id="f7a85-128">使用 PowerShell 管理 App-V 5.1</span><span class="sxs-lookup"><span data-stu-id="f7a85-128">Administering App-V 5.1 by Using PowerShell</span></span>](administering-app-v-51-by-using-powershell.md)

 

 





