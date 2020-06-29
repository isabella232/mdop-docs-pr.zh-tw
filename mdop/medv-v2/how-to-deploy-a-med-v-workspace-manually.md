---
title: 如何手動部署 MED-V 工作區
description: 如何手動部署 MED-V 工作區
author: dansimp
ms.assetid: 94bfb209-2230-49b6-bb40-9c6ab088dbf4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3f13d06e2232681f87df7a71b9a3ef3269b4f9ce
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812260"
---
# <span data-ttu-id="306fe-103">如何手動部署 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="306fe-103">How to Deploy a MED-V Workspace Manually</span></span>


<span data-ttu-id="306fe-104">在某些情況下，您可能會想手動部署 MED-V 工作區，例如，如果您的公司不使用電子軟體發佈系統來部署應用程式。</span><span class="sxs-lookup"><span data-stu-id="306fe-104">In some instances, you might want to deploy your MED-V workspace manually, for example, if your company does not use an electronic software distribution system to deploy applications.</span></span>

<span data-ttu-id="306fe-105">本節說明如何手動部署 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="306fe-105">This section provides instruction about how to manually deploy a MED-V workspace.</span></span>

**<span data-ttu-id="306fe-106">若要手動部署 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="306fe-106">To deploy a MED-V workspace manually</span></span>**

1.  <span data-ttu-id="306fe-107">將所有必備應用程式和 MED-V 工作區套件檔案複製到共用的磁片磁碟機或 DVD 中。</span><span class="sxs-lookup"><span data-stu-id="306fe-107">Copy all prerequisite applications and the MED-V workspace package files to a shared drive or to a DVD.</span></span> <span data-ttu-id="306fe-108">下列是所需的應用程式和檔案清單。</span><span class="sxs-lookup"><span data-stu-id="306fe-108">The following is a list of the required applications and files.</span></span>

    -   <span data-ttu-id="306fe-109">**Windows 虛擬電腦**。</span><span class="sxs-lookup"><span data-stu-id="306fe-109">**Windows Virtual PC**.</span></span> <span data-ttu-id="306fe-110">如需詳細資訊，請參閱[設定安裝必備元件](configure-installation-prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="306fe-110">For more information, see [Configure Installation Prerequisites](configure-installation-prerequisites.md).</span></span>

    -   <span data-ttu-id="306fe-111">**Windows 虛擬電腦新增和更新**。</span><span class="sxs-lookup"><span data-stu-id="306fe-111">**Windows Virtual PC Additions and Updates**.</span></span> <span data-ttu-id="306fe-112">如需詳細資訊，請參閱[設定安裝必備元件](configure-installation-prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="306fe-112">For more information, see [Configure Installation Prerequisites](configure-installation-prerequisites.md).</span></span>

    -   <span data-ttu-id="306fe-113">**Med-v 主機代理安裝**檔案–安裝主機代理程式（med-v \ _HostAgent \ _Setup 安裝檔案）。</span><span class="sxs-lookup"><span data-stu-id="306fe-113">**MED-V Host Agent Installation File** – installs the Host Agent (MED-V\_HostAgent\_Setup installation file).</span></span>

        **<span data-ttu-id="306fe-114">警告</span><span class="sxs-lookup"><span data-stu-id="306fe-114">Warning</span></span>**  
        <span data-ttu-id="306fe-115">在安裝 MED-V 主機代理程式前關閉 Internet Explorer，否則可能會在 URL 重新導向之後發生衝突。</span><span class="sxs-lookup"><span data-stu-id="306fe-115">Close Internet Explorer before you install the MED-V Host Agent, otherwise conflicts can occur later with URL redirection.</span></span> <span data-ttu-id="306fe-116">您也可以在發佈期間指定電腦重新開機來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="306fe-116">You can also do this by specifying a computer restart during a distribution.</span></span>



~~~
-   **MED-V Workspace Installer, VHD, and Setup Executable** – created with the **MED-V Workspace Packager**. For more information, see [Create a MED-V Workspace Package](create-a-med-v-workspace-package.md).

    **Important**  
    The compressed VHD file (.medv) and the Setup executable program (setup.exe) must be in the same folder as the MED-V workspace installer.
~~~



2. <span data-ttu-id="306fe-117">依所列順序安裝下列。</span><span class="sxs-lookup"><span data-stu-id="306fe-117">Install the following in the order listed.</span></span> <span data-ttu-id="306fe-118">最終使用者可以手動執行此工作，也可以建立腳本來安裝下列專案：</span><span class="sxs-lookup"><span data-stu-id="306fe-118">The end user can perform this task manually or you can create a script to install the following:</span></span>

   -   <span data-ttu-id="306fe-119">Windows 虛擬電腦和 Windows 虛擬電腦的新增和更新。</span><span class="sxs-lookup"><span data-stu-id="306fe-119">Windows Virtual PC and the Windows Virtual PC additions and updates.</span></span> <span data-ttu-id="306fe-120">需要重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="306fe-120">A computer restart is required.</span></span>

   -   <span data-ttu-id="306fe-121">MED-V 主機代理程式。</span><span class="sxs-lookup"><span data-stu-id="306fe-121">The MED-V Host Agent.</span></span>

       **<span data-ttu-id="306fe-122">注意</span><span class="sxs-lookup"><span data-stu-id="306fe-122">Note</span></span>**  
       <span data-ttu-id="306fe-123">如果它正在執行，則必須重新開機 Internet Explorer，才能安裝 MED-V 主機代理程式。</span><span class="sxs-lookup"><span data-stu-id="306fe-123">If it is running, Internet Explorer must be restarted before the installation of the MED-V Host Agent can finish.</span></span>



~~~
-   The MED-V workspace package.

    Install the MED-V workspace by running the setup.exe program that is included in the MED-V workspace package files.
~~~

3. <span data-ttu-id="306fe-124">第一次完成設定。</span><span class="sxs-lookup"><span data-stu-id="306fe-124">Complete first time setup.</span></span>

   <span data-ttu-id="306fe-125">安裝 MED-V 工作區之後，您可以選擇啟動 MED-V。</span><span class="sxs-lookup"><span data-stu-id="306fe-125">After the MED-V workspace is installed, you have the option of starting MED-V.</span></span> <span data-ttu-id="306fe-126">這會啟動 MED-V 主機代理程式。</span><span class="sxs-lookup"><span data-stu-id="306fe-126">This starts the MED-V Host Agent.</span></span> <span data-ttu-id="306fe-127">您可以在該時間啟動 MED-V，或稍後啟動 MED-V 主機代理程式，以完成第一次設定。</span><span class="sxs-lookup"><span data-stu-id="306fe-127">You can either start MED-V at that time, or start the MED-V Host Agent later to complete first time setup.</span></span>

   <span data-ttu-id="306fe-128">若要啟動 MED-V 主機代理程式，請按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft 企業版桌面虛擬化**]，然後按一下 [ **med-v 主機代理程式**]。</span><span class="sxs-lookup"><span data-stu-id="306fe-128">To start the MED-V Host Agent, click **Start**, click **All Programs**, click **Microsoft Enterprise Desktop Virtualization**, and then click **MED-V Host Agent**.</span></span>

## <span data-ttu-id="306fe-129">相關主題</span><span class="sxs-lookup"><span data-stu-id="306fe-129">Related topics</span></span>


[<span data-ttu-id="306fe-130">如何透過電子軟體發佈系統來部署 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="306fe-130">How to Deploy a MED-V Workspace Through an Electronic Software Distribution System</span></span>](how-to-deploy-a-med-v-workspace-through-an-electronic-software-distribution-system.md)

[<span data-ttu-id="306fe-131">如何在 Windows 7 映像中部署 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="306fe-131">How to Deploy a MED-V Workspace in a Windows 7 Image</span></span>](how-to-deploy-a-med-v-workspace-in-a-windows-7-image.md)

[<span data-ttu-id="306fe-132">部署 MED-V 工作區套件</span><span class="sxs-lookup"><span data-stu-id="306fe-132">Deploying the MED-V Workspace Package</span></span>](deploying-the-med-v-workspace-package.md)









