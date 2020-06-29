---
title: 如何解除安裝 MED-V 元件
description: 如何解除安裝 MED-V 元件
author: dansimp
ms.assetid: c121dd27-6b2f-4d41-a21a-c6e8608c5c41
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 514ec8227b858b34289ca2330f7cfb038bc4f00e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800241"
---
# <span data-ttu-id="8cec8-103">如何解除安裝 MED-V 元件</span><span class="sxs-lookup"><span data-stu-id="8cec8-103">How to Uninstall the MED-V Components</span></span>


<span data-ttu-id="8cec8-104">在某些情況下，您可能會想要從您的企業卸載全部或部分的 Microsoft 企業版桌面虛擬化（MED-V）2.0 元件。</span><span class="sxs-lookup"><span data-stu-id="8cec8-104">Under certain circumstances, you might want to uninstall all or part of the Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 components from your enterprise.</span></span> <span data-ttu-id="8cec8-105">例如，您已解決所有應用程式作業系統相容性問題，或您想要在企業中部署不同的 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="8cec8-105">For example, you have resolved all application operating system compatibility issues, or you want to deploy a different MED-V workspace in your enterprise.</span></span>

<span data-ttu-id="8cec8-106">通常，您可以使用 Windows 的安裝程式，將您的電子軟體發佈（ESD）系統設定為卸載 MED-V 元件。</span><span class="sxs-lookup"><span data-stu-id="8cec8-106">Typically, you can configure your electronic software distribution (ESD) system to uninstall the MED-V components by using a Windows-based Installer.</span></span> <span data-ttu-id="8cec8-107">或者，您也可以手動卸載全部或部分的 MED-V 元件。</span><span class="sxs-lookup"><span data-stu-id="8cec8-107">Alternately, you can uninstall all or some MED-V components manually.</span></span>

<span data-ttu-id="8cec8-108">**重要** 在您可以卸載 MED-V 主機代理程式之前，您必須先卸載任何已安裝的 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="8cec8-108">**Important** Before you can uninstall the MED-V Host Agent, you must first uninstall any installed MED-V workspace.</span></span>

 

<span data-ttu-id="8cec8-109">使用下列程式從您的企業卸載 MED-V 元件。</span><span class="sxs-lookup"><span data-stu-id="8cec8-109">Use the following procedures to uninstall the MED-V components from your enterprise.</span></span>

**<span data-ttu-id="8cec8-110">使用電子軟體發佈系統卸載 MED-V</span><span class="sxs-lookup"><span data-stu-id="8cec8-110">To uninstall MED-V using an electronic software distribution System</span></span>**

1.  <span data-ttu-id="8cec8-111">使用您的 ESD 系統發佈腳本來針對您要卸載的每個 MED-V 工作區，都叫用這個 uninstall.exe 的可執行程式。</span><span class="sxs-lookup"><span data-stu-id="8cec8-111">Use your ESD system to distribute a script that invokes the uninstall.exe executable program for every MED-V workspace that you want to uninstall.</span></span> <span data-ttu-id="8cec8-112">檔案位於 C:\\ProgramData\\Microsoft\\Medv\\Workspace。</span><span class="sxs-lookup"><span data-stu-id="8cec8-112">The file is located at C:\\ProgramData\\Microsoft\\Medv\\Workspace.</span></span> <span data-ttu-id="8cec8-113">您可以設定標誌來自動執行卸載可執行程式，讓使用者不知道卸載。</span><span class="sxs-lookup"><span data-stu-id="8cec8-113">You can set a flag to run the uninstall executable program silently so that end users are unaware of the uninstallation.</span></span>

2.  <span data-ttu-id="8cec8-114">建立套件，將 MED-V 主機代理程式安裝檔發佈到已卸載 MED-V 工作區的每一部電腦。</span><span class="sxs-lookup"><span data-stu-id="8cec8-114">Create a package to distribute the MED-V Host Agent installation file to each computer on which a MED-V workspace was uninstalled.</span></span> <span data-ttu-id="8cec8-115">將套件設定為在安靜模式下執行卸載。</span><span class="sxs-lookup"><span data-stu-id="8cec8-115">Configure the package to run the uninstallation in silent mode.</span></span>

<span data-ttu-id="8cec8-116">ESD 用戶端會辨識新套件何時可用，並開始根據定義和需求來卸載套件。</span><span class="sxs-lookup"><span data-stu-id="8cec8-116">The ESD client recognizes when the new packages are available and starts to uninstall the packages per the definition and requirements.</span></span>

**<span data-ttu-id="8cec8-117">若要手動卸載 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="8cec8-117">To manually uninstall a MED-V workspace</span></span>**

1.  <span data-ttu-id="8cec8-118">在主機電腦上，按一下 [**開始**]，按一下 [**控制台**]，然後按一下 [**程式和功能**]。</span><span class="sxs-lookup"><span data-stu-id="8cec8-118">On the host computer, click **Start**, click **Control Panel**, and then click **Programs and Features**.</span></span>

2.  <span data-ttu-id="8cec8-119">在 [**程式和功能**] 視窗中，選取您要移除的 med-v 工作區，然後按一下 [**卸載**]。</span><span class="sxs-lookup"><span data-stu-id="8cec8-119">In the **Programs and Features** window, select the MED-V workspace that you want to remove, and then click **Uninstall**.</span></span> <span data-ttu-id="8cec8-120">（MED-V 工作區命名為「MED-V-V 工作區- &lt;*工作區 \ _name* &gt; "）。</span><span class="sxs-lookup"><span data-stu-id="8cec8-120">(The MED-V workspace is named "MED-V Workspace - &lt;*workspace\_name*&gt;").</span></span> <span data-ttu-id="8cec8-121">&lt;隨即會開啟 [*工作區 \ _name* &gt; **設定] 嚮導**。</span><span class="sxs-lookup"><span data-stu-id="8cec8-121">The &lt;*workspace\_name*&gt; **Setup Wizard** opens.</span></span>

3.  <span data-ttu-id="8cec8-122">在 [**設定] 嚮導**中，按一下 **[下一步]**，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="8cec8-122">On the **Setup Wizard**, click **Next**, and then click **Remove**.</span></span>

4.  <span data-ttu-id="8cec8-123">如果您想要的話，請選取核取方塊以刪除由 MED-V 建立的主 VHD 磁片與差異磁片。</span><span class="sxs-lookup"><span data-stu-id="8cec8-123">If you prefer, select the check box to delete the master VHD disk and differencing disks created by MED-V.</span></span> <span data-ttu-id="8cec8-124">這不是必要的，但會在卸載完成後釋放磁碟空間。</span><span class="sxs-lookup"><span data-stu-id="8cec8-124">This is not required, but frees disk space after the uninstallation finishes.</span></span>

5.  <span data-ttu-id="8cec8-125">按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="8cec8-125">Click **Remove**.</span></span>

    <span data-ttu-id="8cec8-126">**記事** 如果 MED-V 目前正在執行，會出現一個對話方塊，詢問您是否要將它關閉。</span><span class="sxs-lookup"><span data-stu-id="8cec8-126">**Note** If MED-V is currently running, a dialog box appears and prompts you whether you want to shut it down.</span></span> <span data-ttu-id="8cec8-127">按一下 **[是]** 以繼續卸載。</span><span class="sxs-lookup"><span data-stu-id="8cec8-127">Click **Yes** to continue with the uninstallation.</span></span> <span data-ttu-id="8cec8-128">按一下 [**否**]，取消卸載。</span><span class="sxs-lookup"><span data-stu-id="8cec8-128">Click **No** to cancel the uninstallation.</span></span>

     

<span data-ttu-id="8cec8-129">或者，您也可以執行檔案 `uninstall.exe` （通常位於 C:\\ProgramData\\Microsoft\\Medv\\Workspace. 上）來移除 med-v 工作區</span><span class="sxs-lookup"><span data-stu-id="8cec8-129">Alternately, you can remove a MED-V workspace by running the `uninstall.exe` file, typically located at C:\\ProgramData\\Microsoft\\Medv\\Workspace.</span></span>

**<span data-ttu-id="8cec8-130">若要手動卸載 MED-V 主機代理程式</span><span class="sxs-lookup"><span data-stu-id="8cec8-130">To manually uninstall the MED-V Host Agent</span></span>**

1.  <span data-ttu-id="8cec8-131">在 Windows 7 主機電腦上，按一下 [**開始**]，按一下 [**控制台**]，然後按一下 [**程式和功能**]。</span><span class="sxs-lookup"><span data-stu-id="8cec8-131">On the Windows 7 host computer, click **Start**, click **Control Panel**, and then click **Programs and Features**.</span></span>

2.  <span data-ttu-id="8cec8-132">在 [**程式和功能**] 視窗中，選取 [ **Med-v 主機代理程式**]，然後按一下 [**卸載**]。</span><span class="sxs-lookup"><span data-stu-id="8cec8-132">In the **Programs and Features** window, select **MED-V Host Agent**, and then click **Uninstall**.</span></span>

    <span data-ttu-id="8cec8-133">Windows 安裝程式會移除 MED-V 主機代理程式。</span><span class="sxs-lookup"><span data-stu-id="8cec8-133">The Windows Installer removes the MED-V Host Agent.</span></span>

    <span data-ttu-id="8cec8-134">**記事** 如果您在卸載 MED-V 工作區之前嘗試卸載 MED-V 主機代理，會出現一個對話方塊，指出您必須先卸載 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="8cec8-134">**Note** If you try to uninstall the MED-V Host Agent before you uninstall the MED-V workspace, a dialog box appears that states that you must first uninstall the MED-V workspace.</span></span> <span data-ttu-id="8cec8-135">按一下**確定**繼續。</span><span class="sxs-lookup"><span data-stu-id="8cec8-135">Click **OK** to continue.</span></span>

     

**<span data-ttu-id="8cec8-136">若要手動卸載 MED-V 工作區包裝程式</span><span class="sxs-lookup"><span data-stu-id="8cec8-136">To manually uninstall the MED-V Workspace Packager</span></span>**

1.  <span data-ttu-id="8cec8-137">在主機電腦上，按一下 [**開始**]，按一下 [**控制台**]，然後按一下 [**程式和功能**]。</span><span class="sxs-lookup"><span data-stu-id="8cec8-137">On the host computer, click **Start**, click **Control Panel**, and then click **Programs and Features**.</span></span>

2.  <span data-ttu-id="8cec8-138">在 [**程式和功能**] 視窗中，選取 [ **Med-v-V 工作區包裝程式**]，然後按一下 [**卸載**]。</span><span class="sxs-lookup"><span data-stu-id="8cec8-138">In the **Programs and Features** window, select **MED-V Workspace Packager**, and then click **Uninstall**.</span></span>

    <span data-ttu-id="8cec8-139">Windows 安裝程式會移除 MED-V-V 工作區包裝程式。</span><span class="sxs-lookup"><span data-stu-id="8cec8-139">The Windows Installer removes the MED-V Workspace Packager.</span></span>

    <span data-ttu-id="8cec8-140">**記事** 您可以隨時卸載 MED-V 工作區包裝程式，而不會影響任何已部署的 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="8cec8-140">**Note** You can uninstall the MED-V Workspace Packager at any time without affecting any deployed MED-V workspaces.</span></span>

     

## <span data-ttu-id="8cec8-141">相關主題</span><span class="sxs-lookup"><span data-stu-id="8cec8-141">Related topics</span></span>


[<span data-ttu-id="8cec8-142">部署 MED-V 元件</span><span class="sxs-lookup"><span data-stu-id="8cec8-142">Deploy the MED-V Components</span></span>](deploy-the-med-v-components.md)

 

 





