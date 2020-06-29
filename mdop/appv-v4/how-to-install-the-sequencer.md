---
title: 如何安裝 Sequencer
description: 如何安裝 Sequencer
author: dansimp
ms.assetid: 2cd16427-a0ba-4870-82d1-3e3c79e1959b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 75a0f987fcc76d1ed92631085a4364ae6e06c9ce
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801349"
---
# <span data-ttu-id="c3767-103">如何安裝 Sequencer</span><span class="sxs-lookup"><span data-stu-id="c3767-103">How to Install the Sequencer</span></span>


<span data-ttu-id="c3767-104">Microsoft Application Virtualization （App-v） Sequencer 會監視並記錄應用程式的安裝與設定程式，讓應用程式可以作為虛擬應用程式執行。</span><span class="sxs-lookup"><span data-stu-id="c3767-104">The Microsoft Application Virtualization (App-V) Sequencer monitors and records the installation and setup process for applications so that the application can be run as a virtual application.</span></span> <span data-ttu-id="c3767-105">您應該在只安裝作業系統的電腦上安裝 Sequencer。</span><span class="sxs-lookup"><span data-stu-id="c3767-105">You should install the Sequencer on a computer that has only the operating system installed.</span></span> <span data-ttu-id="c3767-106">或者，您也可以在執行虛擬環境的電腦（例如 Microsoft Virtual PC）上安裝 Sequencer。</span><span class="sxs-lookup"><span data-stu-id="c3767-106">Alternatively, you can install the Sequencer on a computer running a virtual environment—for example, Microsoft Virtual PC.</span></span> <span data-ttu-id="c3767-107">這個方法很實用，因為您可以更輕鬆地維護乾淨的順序環境，讓您可以使用最少的額外設定重複使用。</span><span class="sxs-lookup"><span data-stu-id="c3767-107">This method is useful because it is easier to maintain a clean sequencing environment that can be reused with minimal additional configuration.</span></span>

<span data-ttu-id="c3767-108">您必須在所用的電腦上擁有系統管理許可權，才能對應用程式進行排序，且電腦必須連線到網路。</span><span class="sxs-lookup"><span data-stu-id="c3767-108">You must have administrative rights on the computer you are using to sequence the application and the computer must be connected to the network.</span></span> <span data-ttu-id="c3767-109">電腦不能執行任何版本的 Application Virtualization （App-v）用戶端。</span><span class="sxs-lookup"><span data-stu-id="c3767-109">The computer must not be running any version of the Application Virtualization (App-V) client.</span></span> <span data-ttu-id="c3767-110">使用排序器建立虛擬應用程式會佔用大量資源，所以請務必在符合或超過建議需求的電腦上安裝 Sequencer。</span><span class="sxs-lookup"><span data-stu-id="c3767-110">Creating a virtual application using the Sequencer is very resource intensive, so it is important that you install the Sequencer on a computer that meets or exceeds the recommended requirements.</span></span> <span data-ttu-id="c3767-111">如需系統需求的詳細資訊，請參閱[Sequencer 硬體和軟體需求](sequencer-hardware-and-software-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c3767-111">For more information about the system requirements, see [Sequencer Hardware and Software Requirements](sequencer-hardware-and-software-requirements.md)..</span></span>

**<span data-ttu-id="c3767-112">若要安裝 Microsoft Application Virtualization 排序器</span><span class="sxs-lookup"><span data-stu-id="c3767-112">To install the Microsoft Application Virtualization Sequencer</span></span>**

1.  <span data-ttu-id="c3767-113">將 Microsoft Application Virtualization Sequencer 安裝檔案複製到您要安裝它的電腦上。</span><span class="sxs-lookup"><span data-stu-id="c3767-113">Copy the Microsoft Application Virtualization Sequencer installation files to the computer that you want to install it on.</span></span>

2.  <span data-ttu-id="c3767-114">若要啟動 Microsoft Application Virtualization Sequencer 安裝精靈，請選取 [ **setup.exe**]。</span><span class="sxs-lookup"><span data-stu-id="c3767-114">To start the Microsoft Application Virtualization Sequencer installation wizard, select **setup.exe**.</span></span> <span data-ttu-id="c3767-115">如果在安裝前沒有偵測到**Microsoft Visual c + + SP1 可再發行套件（x86）** ， **setup.exe**會安裝它。</span><span class="sxs-lookup"><span data-stu-id="c3767-115">If the **Microsoft Visual C++ SP1 Redistributable Package (x86)** is not detected prior to installation, **setup.exe** will install it.</span></span>

3.  <span data-ttu-id="c3767-116">在 [**歡迎**] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c3767-116">On the **Welcome** page, click **Next**.</span></span>

4.  <span data-ttu-id="c3767-117">若要接受授權合約條款，請在 [**授權協定**] 頁面上，選取 [**我接受授權合約中的條款**]。</span><span class="sxs-lookup"><span data-stu-id="c3767-117">On the **License Agreement** page, to accept the terms of the license agreement, select **I accept the terms in the license agreement**.</span></span> <span data-ttu-id="c3767-118">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="c3767-118">Click **Next**.</span></span>

5.  <span data-ttu-id="c3767-119">若要接受預設安裝資料夾，請在 [**目的地資料夾**] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c3767-119">On the **Destination Folder** page, to accept the default installation folder, click **Next**.</span></span> <span data-ttu-id="c3767-120">若要指定不同的目的地資料夾，請按一下 [**變更**]，然後指定安裝所用的安裝資料夾。</span><span class="sxs-lookup"><span data-stu-id="c3767-120">To specify a different destination folder, click **Change** and specify the installation folder that will be used for the installation.</span></span> <span data-ttu-id="c3767-121">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="c3767-121">Click **Next**.</span></span>

6.  <span data-ttu-id="c3767-122">在 [**準備好安裝程式**] 頁面上，按一下 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="c3767-122">On the **Ready to Install the Program** page, to start the installation, click **Install**.</span></span>

7.  <span data-ttu-id="c3767-123">在 [ **InstallShield 嚮導已完成]** 頁面上，若要關閉 [安裝精靈] 並開啟排序器，請按一下 **[完成**]。</span><span class="sxs-lookup"><span data-stu-id="c3767-123">On the **InstallShield Wizard Completed** page, to close the installation wizard and open the Sequencer, click **Finish**.</span></span> <span data-ttu-id="c3767-124">若要關閉 [安裝精靈] 而不開啟排序器，請取消選取 [**啟動程式**]，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="c3767-124">To close the installation wizard without opening the Sequencer, deselect **Launch the program** and click **Finish**.</span></span>

## <span data-ttu-id="c3767-125">相關主題</span><span class="sxs-lookup"><span data-stu-id="c3767-125">Related topics</span></span>


[<span data-ttu-id="c3767-126">設定 Application Virtualization Sequencer</span><span class="sxs-lookup"><span data-stu-id="c3767-126">Configuring the Application Virtualization Sequencer</span></span>](configuring-the-application-virtualization-sequencer.md)

 

 





