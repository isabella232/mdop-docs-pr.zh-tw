---
title: 如何安裝排序器（App-v 4.6 SP1）
description: 如何安裝排序器（App-v 4.6 SP1）
author: dansimp
ms.assetid: fe8eb876-28fb-46ae-b592-da055107e639
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 611564e861d65dcd357c58732fb60dab21c05abe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801350"
---
# <span data-ttu-id="1db1d-103">如何安裝排序器（App-v 4.6 SP1）</span><span class="sxs-lookup"><span data-stu-id="1db1d-103">How to Install the Sequencer (App-V 4.6 SP1)</span></span>


<span data-ttu-id="1db1d-104">Microsoft Application Virtualization （App-v） Sequencer 會監視並記錄應用程式的安裝與設定程式，讓應用程式可以作為虛擬應用程式執行。</span><span class="sxs-lookup"><span data-stu-id="1db1d-104">The Microsoft Application Virtualization (App-V) Sequencer monitors and records the installation and setup process for applications so that the application can be run as a virtual application.</span></span> <span data-ttu-id="1db1d-105">您應該在只安裝作業系統的電腦上安裝 App-v 排序器。</span><span class="sxs-lookup"><span data-stu-id="1db1d-105">You should install the App-V Sequencer on a computer that has only the operating system installed.</span></span> <span data-ttu-id="1db1d-106">或者，您也可以在虛擬環境中執行的電腦上安裝 Sequencer （例如虛擬電腦）。</span><span class="sxs-lookup"><span data-stu-id="1db1d-106">Alternatively, you can install the Sequencer on a computer running in a virtual environment, for example, a virtual computer.</span></span> <span data-ttu-id="1db1d-107">這個方法很實用，因為您可以更輕鬆地維護乾淨的順序環境，讓您可以使用最低的額外設定重複使用。</span><span class="sxs-lookup"><span data-stu-id="1db1d-107">This method is useful because it is easier to maintain a clean sequencing environment that you can reuse with minimal additional configuration.</span></span>

<span data-ttu-id="1db1d-108">您必須在所用的電腦上擁有系統管理認證，才能對應用程式進行排序，且電腦不得執行任何版本的 App-v 用戶端。</span><span class="sxs-lookup"><span data-stu-id="1db1d-108">You must have administrative credentials on the computer you are using to sequence the application, and the computer must not be running any version of App-V client.</span></span> <span data-ttu-id="1db1d-109">使用 App-v 排序器建立虛擬應用程式需要多個作業，所以請務必在符合或超過[應用程式虛擬化排序器硬體和軟體需求](application-virtualization-sequencer-hardware-and-software-requirements.md)的電腦上安裝 Sequencer。</span><span class="sxs-lookup"><span data-stu-id="1db1d-109">Creating a virtual application by using the App-V Sequencer requires multiple operations, so it is important that you install the Sequencer on a computer that meets or exceeds the [Application Virtualization Sequencer Hardware and Software Requirements](application-virtualization-sequencer-hardware-and-software-requirements.md).</span></span>

**<span data-ttu-id="1db1d-110">注意</span><span class="sxs-lookup"><span data-stu-id="1db1d-110">Note</span></span>**  
<span data-ttu-id="1db1d-111">在安全模式中執行 App-v 排序器不受支援。</span><span class="sxs-lookup"><span data-stu-id="1db1d-111">Running the App-V sequencer in Safe Mode is not supported.</span></span>



**<span data-ttu-id="1db1d-112">若要安裝 Microsoft Application Virtualization 排序器</span><span class="sxs-lookup"><span data-stu-id="1db1d-112">To install the Microsoft Application Virtualization Sequencer</span></span>**

1.  <span data-ttu-id="1db1d-113">將 Microsoft Application Virtualization Sequencer 安裝檔案複製到您要安裝它的電腦上。</span><span class="sxs-lookup"><span data-stu-id="1db1d-113">Copy the Microsoft Application Virtualization Sequencer installation files to the computer on which you want to install it.</span></span>

2.  <span data-ttu-id="1db1d-114">若要啟動 Microsoft Application Virtualization Sequencer 安裝精靈，請按兩下 [ **Setup.exe**]。</span><span class="sxs-lookup"><span data-stu-id="1db1d-114">To start the Microsoft Application Virtualization Sequencer installation wizard, double-click **Setup.exe**.</span></span> <span data-ttu-id="1db1d-115">如果在安裝前沒有偵測到**Microsoft Visual c + + SP1 可再發行套件（x86）** ，請按一下 [**安裝**] 以安裝必要的先決條件。</span><span class="sxs-lookup"><span data-stu-id="1db1d-115">If the **Microsoft Visual C++ SP1 Redistributable Package (x86)** is not detected prior to installation, click **Install** to install the required prerequisite.</span></span>

3.  <span data-ttu-id="1db1d-116">若要繼續安裝，請在 [**歡迎**] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="1db1d-116">To continue the installation, on the **Welcome** page, click **Next**.</span></span>

4.  <span data-ttu-id="1db1d-117">若要接受授權合約條款，請在 [**授權協定**] 頁面上，按一下 **[我接受授權合約中的條款**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="1db1d-117">On the **License Agreement** page, to accept the terms of the license agreement, click **I accept the terms in the license agreement**, and then click **Next**.</span></span>

5.  <span data-ttu-id="1db1d-118">若要接受預設安裝資料夾，請在 [**目的地資料夾**] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="1db1d-118">On the **Destination Folder** page, to accept the default installation folder, click **Next**.</span></span> <span data-ttu-id="1db1d-119">若要指定不同的目的地資料夾，請按一下 [**變更**]，然後指定安裝所用的安裝資料夾。</span><span class="sxs-lookup"><span data-stu-id="1db1d-119">To specify a different destination folder, click **Change** and specify the installation folder that will be used for the installation.</span></span> <span data-ttu-id="1db1d-120">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="1db1d-120">Click **Next**.</span></span>

6.  <span data-ttu-id="1db1d-121">在**虛擬磁片磁碟機**頁面上，若要將應用程式虛擬化預設磁片磁碟機**Q:\\** （預設）設定為所有順序應用程式將從哪個磁碟機執行，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="1db1d-121">On the **Virtual Drive** page, to configure the Application Virtualization default drive **Q:\\** (default) as the drive that all sequenced applications will run from, click **Next**.</span></span> <span data-ttu-id="1db1d-122">如果您想要指定不同的磁片磁碟機盤符，請使用清單並選取您要使用的磁片磁碟機盤符，方法是選取適當的磁片磁碟機盤符，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="1db1d-122">If you want to specify a different drive letter, use the list and select the drive letter that you want to use by selecting the appropriate drive letter, and then click **Next**.</span></span>

    **<span data-ttu-id="1db1d-123">重要</span><span class="sxs-lookup"><span data-stu-id="1db1d-123">Important</span></span>**  
    <span data-ttu-id="1db1d-124">在這個步驟中指定的應用程式虛擬化磁片磁碟機盤符就是虛擬應用程式將從目的電腦上執行的磁片磁碟機字母。</span><span class="sxs-lookup"><span data-stu-id="1db1d-124">The Application Virtualization drive letter specified with this step is the drive letter that virtual applications will be run from on target computers.</span></span> <span data-ttu-id="1db1d-125">指定的磁碟機盤符必須提供，且目前未在執行 App-v 用戶端的電腦上使用。</span><span class="sxs-lookup"><span data-stu-id="1db1d-125">The drive letter specified must be available, and not currently in use on the computers running the App-V client.</span></span> <span data-ttu-id="1db1d-126">如果指定的磁碟機已在使用中，虛擬應用程式會在目的電腦上失敗。</span><span class="sxs-lookup"><span data-stu-id="1db1d-126">If the specified drive is already in use, the virtual application fails on the target computer.</span></span>



7.  <span data-ttu-id="1db1d-127">在 [**準備好安裝程式**] 頁面上，按一下 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="1db1d-127">On the **Ready to Install the Program** page, to start the installation, click **Install**.</span></span>

8.  <span data-ttu-id="1db1d-128">在 [ **InstallShield 嚮導已完成]** 頁面上，若要關閉安裝精靈並開啟 app-v 排序器，請按一下 **[完成**]。</span><span class="sxs-lookup"><span data-stu-id="1db1d-128">On the **InstallShield Wizard Completed** page, to close the installation wizard and open the App-V Sequencer, click **Finish**.</span></span> <span data-ttu-id="1db1d-129">若要關閉 [安裝精靈] 而不開啟排序器，請清除 [**啟動程式**]，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="1db1d-129">To close the installation wizard without opening the Sequencer, clear **Launch the program**, and then click **Finish**.</span></span>

    **<span data-ttu-id="1db1d-130">注意</span><span class="sxs-lookup"><span data-stu-id="1db1d-130">Note</span></span>**  
    <span data-ttu-id="1db1d-131">如果您在執行虛擬環境的電腦（例如虛擬電腦）上安裝 App-v 排序器，您現在必須拍攝快照。</span><span class="sxs-lookup"><span data-stu-id="1db1d-131">If you installed the App-V Sequencer on a computer running a virtual environment, for example a virtual machine, you must now take a snapshot.</span></span> <span data-ttu-id="1db1d-132">當您將應用程式排序之後，您可以還原到這個影像，因此您可以將下一個應用程式序列化。</span><span class="sxs-lookup"><span data-stu-id="1db1d-132">After you sequence an application, you can revert to this image, so you can sequence the next application.</span></span>



~~~
When you uninstall the Sequencer, the following registry keys are not removed from the computer that the Sequencer was installed on. Additionally, you must restart the computer after you have uninstalled the Sequencer so that all associated drivers can be stopped and the operation can be completed.

-   **HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid**

-   **HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5**

-   **HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\SystemGuard**

-   **HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\SystemGuard\\SecKey**
~~~

## <span data-ttu-id="1db1d-133">相關主題</span><span class="sxs-lookup"><span data-stu-id="1db1d-133">Related topics</span></span>


[<span data-ttu-id="1db1d-134">設定 Application Virtualization Sequencer (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="1db1d-134">Configuring the Application Virtualization Sequencer (App-V 4.6 SP1)</span></span>](configuring-the-application-virtualization-sequencer--app-v-46-sp1-.md)









