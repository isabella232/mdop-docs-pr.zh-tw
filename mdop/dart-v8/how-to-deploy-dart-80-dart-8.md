---
title: 如何部署 DaRT 8.0
description: 如何部署 DaRT 8.0
author: dansimp
ms.assetid: ab772e7a-c02f-4847-acdf-8bd362769a77
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: e7d64297f7687ebc0a23add3aa749ee4719beee4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810472"
---
# <span data-ttu-id="aa8ea-103">如何部署 DaRT 8.0</span><span class="sxs-lookup"><span data-stu-id="aa8ea-103">How to Deploy DaRT 8.0</span></span>


<span data-ttu-id="aa8ea-104">下列指示說明如何在您的環境中部署 Microsoft Diagnostics 和恢復工具集（DaRT）8.0。</span><span class="sxs-lookup"><span data-stu-id="aa8ea-104">The following instructions explain how to deploy Microsoft Diagnostics and Recovery Toolset (DaRT) 8.0 in your environment.</span></span> <span data-ttu-id="aa8ea-105">若要取得 DaRT 軟體，請參閱[如何取得 MDOP](https://go.microsoft.com/fwlink/?LinkId=322049)。</span><span class="sxs-lookup"><span data-stu-id="aa8ea-105">To get the DaRT software, see [How to Get MDOP](https://go.microsoft.com/fwlink/?LinkId=322049).</span></span> <span data-ttu-id="aa8ea-106">假設您要在一部系統管理員電腦上安裝所有功能。</span><span class="sxs-lookup"><span data-stu-id="aa8ea-106">It is assumed that you are installing all functionality on one administrator computer.</span></span> <span data-ttu-id="aa8ea-107">如果您需要在多部電腦上部署或卸載 DaRT 8.0 （例如，使用電子軟體發佈系統），可能會比較容易使用命令列安裝選項。</span><span class="sxs-lookup"><span data-stu-id="aa8ea-107">If you need to deploy or uninstall DaRT 8.0 on multiple computers, using an electronic software distribution system, for example, it might be easier to use command line installation options.</span></span> <span data-ttu-id="aa8ea-108">此區段提供可用命令列選項的描述及範例。</span><span class="sxs-lookup"><span data-stu-id="aa8ea-108">Descriptions and examples of the available command line options are provided in this section.</span></span>

<span data-ttu-id="aa8ea-109">**重要** 安裝 DaRT 之前，請參閱[DaRT 8.0 支援](dart-80-supported-configurations-dart-8.md)的設定，以確保您已安裝所有必備軟體，且電腦符合最低系統需求。</span><span class="sxs-lookup"><span data-stu-id="aa8ea-109">**Important** Before you install DaRT, see [DaRT 8.0 Supported Configurations](dart-80-supported-configurations-dart-8.md) to ensure that you have installed all of the prerequisite software and that the computer meets the minimum system requirements.</span></span> <span data-ttu-id="aa8ea-110">您在其上安裝 DaRT 的電腦必須執行 Windows 8 或 Windows Server 2012。</span><span class="sxs-lookup"><span data-stu-id="aa8ea-110">The computer onto which you install DaRT must be running Windows 8 or Windows Server 2012.</span></span>

 

<span data-ttu-id="aa8ea-111">您可以使用以下兩種不同的設定之一來安裝 DaRT：</span><span class="sxs-lookup"><span data-stu-id="aa8ea-111">You can install DaRT using one of two different configurations:</span></span>

-   <span data-ttu-id="aa8ea-112">在系統管理員電腦上安裝 DaRT 和所有的 DaRT 工具。</span><span class="sxs-lookup"><span data-stu-id="aa8ea-112">Install DaRT and all of the DaRT tools on the administrator computer.</span></span>

-   <span data-ttu-id="aa8ea-113">在系統管理員電腦上，只安裝您要建立 DaRT 復原影像所需的工具，然後再安裝**遠端連線檢視器**，以及在技術支援部電腦上的**故障分析**程式（選擇性）。</span><span class="sxs-lookup"><span data-stu-id="aa8ea-113">Install on the administrator computer only the tools that you need to create the DaRT recovery image, and then install the **Remote Connection Viewer** and, optionally, **Crash Analyzer** on a help desk computer.</span></span>

<span data-ttu-id="aa8ea-114">您可以在32位和64位版本中使用 DaRT 安裝檔。</span><span class="sxs-lookup"><span data-stu-id="aa8ea-114">The DaRT installation file is available in both 32-bit and 64-bit versions.</span></span> <span data-ttu-id="aa8ea-115">安裝符合您執行 DaRT 復原映射嚮導之電腦之體系結構的版本，而不是您所建立之復原影像的電腦架構。</span><span class="sxs-lookup"><span data-stu-id="aa8ea-115">Install the version that matches the architecture of the computer on which you are running the DaRT Recovery Image wizard, not the computer architecture of the recovery image that you are creating.</span></span>

<span data-ttu-id="aa8ea-116">您可以使用任一版本的 DaRT 安裝檔來建立32位或64位電腦的復原影像，但是您無法為兩個32位電腦和64電腦版建立一個復原影像。</span><span class="sxs-lookup"><span data-stu-id="aa8ea-116">You can use either version of the DaRT installation file to create a recovery image for either 32-bit or 64-bit computers, but you cannot create one recovery image for both 32-bit and 64-bit computers.</span></span>

**<span data-ttu-id="aa8ea-117">在系統管理員電腦上安裝 DaRT 和所有 DaRT 工具</span><span class="sxs-lookup"><span data-stu-id="aa8ea-117">To install DaRT and all DaRT tools on an administrator computer</span></span>**

1.  <span data-ttu-id="aa8ea-118">下載32位或64位版本的 DaRT 8.0 安裝程式檔案。</span><span class="sxs-lookup"><span data-stu-id="aa8ea-118">Download the 32-bit or 64-bit version of the DaRT 8.0 installer file.</span></span> <span data-ttu-id="aa8ea-119">選擇與您要安裝 DaRT 的電腦相符的架構，並執行 DaRT 復原影像嚮導。</span><span class="sxs-lookup"><span data-stu-id="aa8ea-119">Choose the architecture that matches the computer on which you are installing DaRT and running the DaRT Recovery Image wizard.</span></span>

2.  <span data-ttu-id="aa8ea-120">從您下載 DaRT 8.0 的資料夾中，執行與您的系統需求相對應的**MSDaRT80.msi**安裝檔。</span><span class="sxs-lookup"><span data-stu-id="aa8ea-120">From the folder into which you downloaded DaRT 8.0, run the **MSDaRT80.msi** installation file that corresponds to your system requirements.</span></span>

3.  <span data-ttu-id="aa8ea-121">在 [**歡迎使用 Microsoft DaRT 8.0 安裝精靈]** 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="aa8ea-121">On the **Welcome to the Microsoft DaRT 8.0 Setup Wizard** page, click **Next**.</span></span>

4.  <span data-ttu-id="aa8ea-122">接受 Microsoft 軟體授權條款，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="aa8ea-122">Accept the Microsoft Software License Terms, and then click **Next**.</span></span>

5.  <span data-ttu-id="aa8ea-123">在 [ **Microsoft update** ] 頁面上，選取 [**當我檢查更新時使用 Microsoft Update**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="aa8ea-123">On the **Microsoft Update** page, select **Use Microsoft Update when I check for updates**, and then click **Next**.</span></span>

6.  <span data-ttu-id="aa8ea-124">在 [**選取安裝資料夾**] 頁面上，選取一個資料夾，或按一下 **[下一步]** ，以在預設安裝位置安裝 DaRT。</span><span class="sxs-lookup"><span data-stu-id="aa8ea-124">On the **Select Installation Folder** page, select a folder, or click **Next** to install DaRT in the default installation location.</span></span>

7.  <span data-ttu-id="aa8ea-125">在 [**安裝選項**] 頁面上，選取您要安裝的 dart 功能，或按一下 **[下一步]** 以安裝 dart 與所有功能。</span><span class="sxs-lookup"><span data-stu-id="aa8ea-125">On the **Setup Options** page, select the DaRT features that you want to install, or click **Next** to install DaRT with all of the features.</span></span>

8.  <span data-ttu-id="aa8ea-126">若要開始安裝，請按一下 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="aa8ea-126">To start the installation, click **Install**.</span></span>

9.  <span data-ttu-id="aa8ea-127">成功完成安裝後，請按一下 **[完成**] 結束嚮導。</span><span class="sxs-lookup"><span data-stu-id="aa8ea-127">After the installation has completed successfully, click **Finish** to exit the wizard.</span></span>

## <span data-ttu-id="aa8ea-128">使用命令提示字元在系統管理員電腦上安裝 DaRT 和所有 DaRT 工具</span><span class="sxs-lookup"><span data-stu-id="aa8ea-128">To install DaRT and all DaRT tools on an administrator computer by using a command prompt</span></span>


<span data-ttu-id="aa8ea-129">當您安裝或卸載 DaRT 時，您可以選擇在命令提示字元執行安裝檔。</span><span class="sxs-lookup"><span data-stu-id="aa8ea-129">When you install or uninstall DaRT, you have the option of running the installation files at the command prompt.</span></span> <span data-ttu-id="aa8ea-130">本節說明您可以在命令提示字元中安裝或卸載 DaRT 時指定的幾個不同選項範例。</span><span class="sxs-lookup"><span data-stu-id="aa8ea-130">This section describes some examples of different options that you can specify when you install or uninstall DaRT at the command prompt.</span></span>

<span data-ttu-id="aa8ea-131">下列範例顯示如何安裝所有的 DaRT 功能。</span><span class="sxs-lookup"><span data-stu-id="aa8ea-131">The following example shows how to install all DaRT functionality.</span></span>

``` syntax
msiexec /i MSDaRT80.msi ADDLOCAL=CommonFiles, DaRTRecoveryImage,CrashAnalyzer,RemoteViewer 
```

<span data-ttu-id="aa8ea-132">下列範例顯示如何只安裝 DaRT 復原影像嚮導。</span><span class="sxs-lookup"><span data-stu-id="aa8ea-132">The following example shows how to install only the DaRT Recovery Image wizard.</span></span>

``` syntax
msiexec /i MSDaRT80.msi ADDLOCAL=CommonFiles, ,DaRTRecoveryImage
```

<span data-ttu-id="aa8ea-133">下列範例顯示如何只安裝 [損毀分析器] 和 [DaRT 遠端連線檢視器]。</span><span class="sxs-lookup"><span data-stu-id="aa8ea-133">The following example shows how to install only the Crash Analyzer and the DaRT Remote Connection Viewer.</span></span>

``` syntax
msiexec /i MSDaRT80.msi ADDLOCAL=CommonFiles,CrashAnalyzer,RemoteViewer 
```

<span data-ttu-id="aa8ea-134">下列範例會建立 Windows 安裝程式的安裝記錄。</span><span class="sxs-lookup"><span data-stu-id="aa8ea-134">The following example creates a setup log for the Windows Installer.</span></span> <span data-ttu-id="aa8ea-135">這對於調試很有用。</span><span class="sxs-lookup"><span data-stu-id="aa8ea-135">This is valuable for debugging.</span></span>

``` syntax
msiexec.exe /i MSDaRT80.msi /l*v log.txt 
```

<span data-ttu-id="aa8ea-136">**記事** 您可以新增/qn 或/qb 來執行緘默安裝。</span><span class="sxs-lookup"><span data-stu-id="aa8ea-136">**Note** You can add /qn or /qb to perform a silent installation.</span></span>

 

**<span data-ttu-id="aa8ea-137">驗證 DaRT 安裝</span><span class="sxs-lookup"><span data-stu-id="aa8ea-137">To validate the DaRT installation</span></span>**

1.  <span data-ttu-id="aa8ea-138">按一下 [**開始**]，然後選取 [**診斷及損毀修復工具**組]。</span><span class="sxs-lookup"><span data-stu-id="aa8ea-138">Click **Start**, and select **Diagnostics and Recovery Toolset**.</span></span>

    <span data-ttu-id="aa8ea-139">隨即會開啟 [**診斷與修復工具集**] 視窗。</span><span class="sxs-lookup"><span data-stu-id="aa8ea-139">The **Diagnostics and Recovery Toolset** window opens.</span></span>

2.  <span data-ttu-id="aa8ea-140">檢查您已成功安裝您所選取的所有 DaRT 工具。</span><span class="sxs-lookup"><span data-stu-id="aa8ea-140">Check that all of the DaRT tools that you selected for installation were successfully installed.</span></span>

## <span data-ttu-id="aa8ea-141">相關主題</span><span class="sxs-lookup"><span data-stu-id="aa8ea-141">Related topics</span></span>


[<span data-ttu-id="aa8ea-142">部署 DaRT 8.0 到系統管理員電腦</span><span class="sxs-lookup"><span data-stu-id="aa8ea-142">Deploying DaRT 8.0 to Administrator Computers</span></span>](deploying-dart-80-to-administrator-computers-dart-8.md)

 

 





