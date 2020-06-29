---
title: 如何在 Windows 7 映像中部署 MED-V 工作區
description: 如何在 Windows 7 映像中部署 MED-V 工作區
author: dansimp
ms.assetid: a83aba4e-8681-4906-9872-f431c0bb15f9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 49dd796d6f6af425b9000b595a0d828c3cb0035a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812261"
---
# <span data-ttu-id="98626-103">如何在 Windows 7 映像中部署 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="98626-103">How to Deploy a MED-V Workspace in a Windows 7 Image</span></span>


<span data-ttu-id="98626-104">您可以將所有的 MED-V 元件，安裝在您整個企業中發佈的 Windows 7 映射，就像您在安裝任何新的 Windows 7 中一樣。</span><span class="sxs-lookup"><span data-stu-id="98626-104">You can install all the MED-V components into a Windows 7 image that you distribute throughout your enterprise just as you would any new installation of Windows 7.</span></span> <span data-ttu-id="98626-105">然後，使用者按一下您設定以啟動 MED-V-V 的 [**開始**] 功能表快捷方式，即可完成 med-v 工作區的安裝。</span><span class="sxs-lookup"><span data-stu-id="98626-105">The end user then finishes the installation of the MED-V workspace by clicking a **Start** menu shortcut that you configure to start MED-V.</span></span> <span data-ttu-id="98626-106">第一次設定開始，而最終使用者遵循指示完成設定。</span><span class="sxs-lookup"><span data-stu-id="98626-106">First time setup starts and the end user follows the instructions to complete the configuration.</span></span>

<span data-ttu-id="98626-107">下列章節提供資訊與指示，協助您使用 Windows 7 影像在整個企業中部署 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="98626-107">The following section provides information and instructions to help you deploy the MED-V workspace throughout your enterprise by using a Windows 7 image.</span></span>

**<span data-ttu-id="98626-108">在 Windows 7 影像中部署 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="98626-108">To deploy a MED-V workspace in a Windows 7 image</span></span>**

1.  <span data-ttu-id="98626-109">建立 Windows 7 的標準影像。</span><span class="sxs-lookup"><span data-stu-id="98626-109">Create a standard image of Windows 7.</span></span> <span data-ttu-id="98626-110">如需詳細資訊，請參閱[建立 Windows 7 的標準影像：逐步指南](https://go.microsoft.com/fwlink/?LinkId=204843)（ https://go.microsoft.com/fwlink/?LinkId=204843) 。</span><span class="sxs-lookup"><span data-stu-id="98626-110">For more information, see [Building a Standard Image of Windows 7: Step-by-Step Guide](https://go.microsoft.com/fwlink/?LinkId=204843) (https://go.microsoft.com/fwlink/?LinkId=204843).</span></span>

2.  <span data-ttu-id="98626-111">在 Windows 7 映射中，安裝 Windows 虛擬電腦和 Windows 虛擬電腦更新。</span><span class="sxs-lookup"><span data-stu-id="98626-111">In the Windows 7 image, install Windows Virtual PC and the Windows Virtual PC updates.</span></span> <span data-ttu-id="98626-112">如需詳細資訊，請參閱[設定安裝必備元件](configure-installation-prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="98626-112">For more information, see [Configure Installation Prerequisites](configure-installation-prerequisites.md).</span></span>

3.  <span data-ttu-id="98626-113">使用 MED-V \ _HostAgent \ _Setup 安裝檔來安裝 MED-V 主機代理程式。</span><span class="sxs-lookup"><span data-stu-id="98626-113">Install the MED-V Host Agent by using the MED-V\_HostAgent\_Setup installation file.</span></span> <span data-ttu-id="98626-114">如需詳細資訊，請參閱[如何手動安裝 Med-v 主機代理程式](how-to-manually-install-the-med-v-host-agent.md)。</span><span class="sxs-lookup"><span data-stu-id="98626-114">For more information, see [How to Manually Install the MED-V Host Agent](how-to-manually-install-the-med-v-host-agent.md).</span></span>

    <span data-ttu-id="98626-115">**警告** 您必須先關閉 Internet Explorer，才能安裝 MED-V 主機代理程式，否則可能會在 URL 重新導向後發生衝突。</span><span class="sxs-lookup"><span data-stu-id="98626-115">**Warning** Internet Explorer must be closed before you install the MED-V Host Agent, otherwise conflicts can occur later with URL redirection.</span></span> <span data-ttu-id="98626-116">您也可以在發佈期間指定電腦重新開機來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="98626-116">You can also do this by specifying a computer restart during a distribution.</span></span>

     

4.  <span data-ttu-id="98626-117">將 MED-V 工作區套件檔案複製到 Windows 7 影像。</span><span class="sxs-lookup"><span data-stu-id="98626-117">Copy the MED-V workspace package files to the Windows 7 image.</span></span> <span data-ttu-id="98626-118">MED-V 工作區套件檔案是 MED-V 的工作區安裝程式、medv 檔案，以及您使用**Med-v 工作區包裝**程式建立的 setup.exe 檔案。</span><span class="sxs-lookup"><span data-stu-id="98626-118">The MED-V workspace package files are the MED-V workspace installer, .medv file, and setup.exe file that you created by using the **MED-V Workspace Packager**.</span></span>

    <span data-ttu-id="98626-119">**重要** Medv 和 setup.exe 檔案必須與 MED-V 工作區安裝程式位於相同的資料夾中。</span><span class="sxs-lookup"><span data-stu-id="98626-119">**Important** The .medv and setup.exe file must be in the same folder as the MED-V workspace installer.</span></span> <span data-ttu-id="98626-120">然後，透過執行 setup.exe 來安裝 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="98626-120">Then, install the MED-V workspace by running setup.exe.</span></span>

     

5.  <span data-ttu-id="98626-121">在 [**開始**] 功能表上設定快速鍵，以開啟 med-v 工作區套件安裝。</span><span class="sxs-lookup"><span data-stu-id="98626-121">Configure a shortcut on the **Start** menu to open the MED-V workspace package installation.</span></span>

    <span data-ttu-id="98626-122">建立 [**開始**] 功能表的快捷方式至 setup.exe 檔案，讓最終使用者根據需要啟動 med-v 安裝。</span><span class="sxs-lookup"><span data-stu-id="98626-122">Create a **Start** menu shortcut to the setup.exe file that lets the end user start a MED-V installation as required.</span></span>

6.  <span data-ttu-id="98626-123">使用貴公司的標準影像部署程式，將 Windows 7 影像發佈到企業中需要 MED-V 的電腦。</span><span class="sxs-lookup"><span data-stu-id="98626-123">By using your company’s standard image deployment process, distribute the Windows 7 image to computers in your enterprise that require MED-V.</span></span>

<span data-ttu-id="98626-124">當使用者必須存取在 MED-V 工作區中發佈的應用程式時，他們可以按一下 [**開始**] 功能表的快捷方式來安裝 med-v 工作區。</span><span class="sxs-lookup"><span data-stu-id="98626-124">When the end user has to access an application published in the MED-V workspace, they can click the **Start** menu shortcut to install the MED-V workspace.</span></span> <span data-ttu-id="98626-125">這會在第一次設定開始時自動啟動，並完成 MED-V 的配置。</span><span class="sxs-lookup"><span data-stu-id="98626-125">This automatically starts first time setup and completes the configuration of MED-V.</span></span> <span data-ttu-id="98626-126">第一次完成設定之後，使用者就可以在 [**開始**] 功能表上存取 med-v 應用程式。</span><span class="sxs-lookup"><span data-stu-id="98626-126">After first time setup is complete, the end user can access the MED-V applications on the **Start** menu.</span></span>

## <span data-ttu-id="98626-127">相關主題</span><span class="sxs-lookup"><span data-stu-id="98626-127">Related topics</span></span>


[<span data-ttu-id="98626-128">MED-V 2.0 部署概觀</span><span class="sxs-lookup"><span data-stu-id="98626-128">MED-V 2.0 Deployment Overview</span></span>](med-v-20-deployment-overview.md)

[<span data-ttu-id="98626-129">如何透過電子軟體發佈系統來部署 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="98626-129">How to Deploy a MED-V Workspace Through an Electronic Software Distribution System</span></span>](how-to-deploy-a-med-v-workspace-through-an-electronic-software-distribution-system.md)

 

 





