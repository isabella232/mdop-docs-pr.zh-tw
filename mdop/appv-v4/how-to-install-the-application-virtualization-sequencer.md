---
title: 如何安裝 Application Virtualization Sequencer
description: 如何安裝 Application Virtualization Sequencer
author: dansimp
ms.assetid: 89cdf60d-18b0-4204-aa9f-b402610f8f0e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 56a6fe03f2149504b6c34c70b2b82ce2ba0b55ad
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801365"
---
# <span data-ttu-id="a0653-103">如何安裝 Application Virtualization Sequencer</span><span class="sxs-lookup"><span data-stu-id="a0653-103">How to Install the Application Virtualization Sequencer</span></span>


<span data-ttu-id="a0653-104">Microsoft Application Virtualization 排序器會監視並記錄應用程式的安裝與設定程式，讓應用程式可以作為虛擬應用程式執行。</span><span class="sxs-lookup"><span data-stu-id="a0653-104">The Microsoft Application Virtualization Sequencer monitors and records the installation and setup process for applications so that the application can be run as a virtual application.</span></span> <span data-ttu-id="a0653-105">您應該在只安裝作業系統的電腦上安裝 Sequencer。</span><span class="sxs-lookup"><span data-stu-id="a0653-105">You should install the Sequencer on a computer that has only the operating system installed.</span></span> <span data-ttu-id="a0653-106">或者，您也可以在執行虛擬環境的電腦（例如 Microsoft Virtual PC）上安裝 Sequencer。</span><span class="sxs-lookup"><span data-stu-id="a0653-106">Alternatively, you can install the Sequencer on a computer running a virtual environment—for example, Microsoft Virtual PC.</span></span> <span data-ttu-id="a0653-107">這個方法很實用，因為您可以更輕鬆地維護乾淨的順序環境，讓您可以使用最少的額外設定重複使用。</span><span class="sxs-lookup"><span data-stu-id="a0653-107">This method is useful because it is easier to maintain a clean sequencing environment that can be reused with minimal additional configuration.</span></span>

<span data-ttu-id="a0653-108">您必須在所用的電腦上擁有系統管理許可權，才能對應用程式進行排序，且電腦必須不執行任何版本的 Application Virtualization （App-v）用戶端。</span><span class="sxs-lookup"><span data-stu-id="a0653-108">You must have administrative rights on the computer you are using to sequence the application and the computer must not be running any version of the Application Virtualization (App-V) client.</span></span> <span data-ttu-id="a0653-109">使用排序器建立虛擬應用程式是佔用大量資源，所以請務必在符合或超過建議需求的電腦上安裝 Sequencer。</span><span class="sxs-lookup"><span data-stu-id="a0653-109">Creating a virtual application by using the Sequencer is very resource intensive, so it is important that you install the Sequencer on a computer that meets or exceeds the recommended requirements.</span></span> <span data-ttu-id="a0653-110">在安全模式中執行 App-v 排序器不受支援。</span><span class="sxs-lookup"><span data-stu-id="a0653-110">Running the App-V sequencer in Safe Mode is not supported.</span></span> <span data-ttu-id="a0653-111">如需系統需求的詳細資訊，請參閱[應用程式虛擬化系統需求](application-virtualization-system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a0653-111">For more information about the system requirements, see [Application Virtualization System Requirements](application-virtualization-system-requirements.md).</span></span>

<span data-ttu-id="a0653-112">**重要** 當您將應用程式排序之後，您必須在您用來序列化應用程式的電腦上重新安裝作業系統和 Sequencer，才能正確地順序新的應用程式。</span><span class="sxs-lookup"><span data-stu-id="a0653-112">**Important** After you have sequenced an application, before you can properly sequence a new application you must reinstall the operating system and the Sequencer on the computer you are using to sequence applications.</span></span>

 

**<span data-ttu-id="a0653-113">若要安裝 Microsoft Application Virtualization 排序器</span><span class="sxs-lookup"><span data-stu-id="a0653-113">To install the Microsoft Application Virtualization Sequencer</span></span>**

1.  <span data-ttu-id="a0653-114">將 Microsoft Application Virtualization Sequencer 安裝檔案複製到您要安裝它的電腦上。</span><span class="sxs-lookup"><span data-stu-id="a0653-114">Copy the Microsoft Application Virtualization Sequencer installation files to the computer that you want to install it on.</span></span>

2.  <span data-ttu-id="a0653-115">若要啟動 Microsoft Application Virtualization Sequencer 安裝精靈，請選取 [ **setup.exe**]。</span><span class="sxs-lookup"><span data-stu-id="a0653-115">To start the Microsoft Application Virtualization Sequencer installation wizard, select **setup.exe**.</span></span> <span data-ttu-id="a0653-116">如果在安裝前沒有偵測到**Microsoft Visual c + + SP1 可再發行套件（x86）** ， **setup.exe**會安裝它。</span><span class="sxs-lookup"><span data-stu-id="a0653-116">If the **Microsoft Visual C++ SP1 Redistributable Package (x86)** is not detected prior to installation, **setup.exe** will install it.</span></span>

3.  <span data-ttu-id="a0653-117">在 [**歡迎**] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="a0653-117">On the **Welcome** page, click **Next**.</span></span>

4.  <span data-ttu-id="a0653-118">若要接受授權合約條款，請在 [**授權協定**] 頁面上，選取 [**我接受授權合約中的條款**]。</span><span class="sxs-lookup"><span data-stu-id="a0653-118">On the **License Agreement** page, to accept the terms of the license agreement, select **I accept the terms in the license agreement**.</span></span> <span data-ttu-id="a0653-119">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="a0653-119">Click **Next**.</span></span>

5.  <span data-ttu-id="a0653-120">若要接受預設安裝資料夾，請在 [**目的地資料夾**] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="a0653-120">On the **Destination Folder** page, to accept the default installation folder, click **Next**.</span></span> <span data-ttu-id="a0653-121">若要指定不同的目的地資料夾，請按一下 [**變更**]，然後指定安裝所用的安裝資料夾。</span><span class="sxs-lookup"><span data-stu-id="a0653-121">To specify a different destination folder, click **Change** and specify the installation folder that will be used for the installation.</span></span> <span data-ttu-id="a0653-122">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="a0653-122">Click **Next**.</span></span>

6.  <span data-ttu-id="a0653-123">在 [**準備好安裝程式**] 頁面上，按一下 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="a0653-123">On the **Ready to Install the Program** page, to start the installation, click **Install**.</span></span>

7.  <span data-ttu-id="a0653-124">在 [ **InstallShield 嚮導已完成]** 頁面上，若要關閉 [安裝精靈] 並開啟排序器，請按一下 **[完成**]。</span><span class="sxs-lookup"><span data-stu-id="a0653-124">On the **InstallShield Wizard Completed** page, to close the installation wizard and open the Sequencer, click **Finish**.</span></span> <span data-ttu-id="a0653-125">若要關閉 [安裝精靈] 而不開啟排序器，請取消選取 [**啟動程式**]，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="a0653-125">To close the installation wizard without opening the Sequencer, deselect **Launch the program** and click **Finish**.</span></span>

## <span data-ttu-id="a0653-126">相關主題</span><span class="sxs-lookup"><span data-stu-id="a0653-126">Related topics</span></span>


[<span data-ttu-id="a0653-127">如何升級 Application Virtualization Sequencer</span><span class="sxs-lookup"><span data-stu-id="a0653-127">How to Upgrade the Application Virtualization Sequencer</span></span>](how-to-upgrade-the-application-virtualization-sequencer.md)

[<span data-ttu-id="a0653-128">Application Virtualization 部署需求</span><span class="sxs-lookup"><span data-stu-id="a0653-128">Application Virtualization Deployment Requirements</span></span>](application-virtualization-deployment-requirements.md)

 

 





