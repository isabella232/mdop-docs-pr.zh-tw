---
title: 如何手動安裝 MED-V 主機代理程式
description: 如何手動安裝 MED-V 主機代理程式
author: dansimp
ms.assetid: 4becc90b-6481-4e1f-a4d3-aec74c8821ec
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8a7fb44b23a390cf394af2331152955afc2d8eba
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800208"
---
# <span data-ttu-id="0341e-103">如何手動安裝 MED-V 主機代理程式</span><span class="sxs-lookup"><span data-stu-id="0341e-103">How to Manually Install the MED-V Host Agent</span></span>


<span data-ttu-id="0341e-104">Microsoft 企業版桌面虛擬化（MED-V）2.0 解決方案有兩個不同但相關的元件： MED-V 主機代理程式和來賓代理程式。</span><span class="sxs-lookup"><span data-stu-id="0341e-104">There are two separate but related components to the Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 solution: the MED-V Host Agent and Guest Agent.</span></span> <span data-ttu-id="0341e-105">主機代理程式位於主機電腦（執行 Windows 7 的使用者電腦）上，並提供通道來與 MED-V 來賓（在主機電腦中執行的 MED-V 虛擬機器）進行通訊。</span><span class="sxs-lookup"><span data-stu-id="0341e-105">The Host Agent resides on the host computer (a user’s computer that is running Windows 7) and provides a channel to communicate with the MED-V guest (the MED-V virtual machine running in the host computer).</span></span> <span data-ttu-id="0341e-106">它也會提供某些與 MED-V 相關的功能，例如應用程式發佈。</span><span class="sxs-lookup"><span data-stu-id="0341e-106">It also provides certain MED-V related functionality, such as application publishing.</span></span>

<span data-ttu-id="0341e-107">通常，您可以使用公司的喜好預配軟體方法來部署並安裝 MED-V 主機代理程式。</span><span class="sxs-lookup"><span data-stu-id="0341e-107">Typically, you deploy and install the MED-V Host Agent by using your company’s preferred method of provisioning software.</span></span> <span data-ttu-id="0341e-108">不過，在整個企業中部署 MED-V 之前，您可能比較想要在本機安裝主機代理程式來進行測試。</span><span class="sxs-lookup"><span data-stu-id="0341e-108">However, before deploying MED-V across your enterprise, you might prefer to install the Host Agent locally for testing.</span></span> <span data-ttu-id="0341e-109">本節提供手動安裝 MED-V 主機代理程式的逐步指示。</span><span class="sxs-lookup"><span data-stu-id="0341e-109">This section provides step-by-step instructions for manually installing the MED-V Host Agent.</span></span>

<span data-ttu-id="0341e-110">**記事** MED-V 來賓代理程式會在第一次設定期間自動安裝。</span><span class="sxs-lookup"><span data-stu-id="0341e-110">**Note** The MED-V Guest Agent is installed automatically during first time setup.</span></span>

 

<span data-ttu-id="0341e-111">**重要** 在安裝 MED-V 主機代理程式前關閉 Internet Explorer，否則可能會在 URL 重新導向之後發生衝突。</span><span class="sxs-lookup"><span data-stu-id="0341e-111">**Important** Close Internet Explorer before you install the MED-V Host Agent, otherwise conflicts can occur later with URL redirection.</span></span> <span data-ttu-id="0341e-112">您也可以在發佈期間指定電腦重新開機來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="0341e-112">You can also do this by specifying a computer restart during a distribution.</span></span>

 

**<span data-ttu-id="0341e-113">安裝 MED-V 主機代理程式</span><span class="sxs-lookup"><span data-stu-id="0341e-113">To install the MED-V Host Agent</span></span>**

1.  <span data-ttu-id="0341e-114">找出您在軟體下載中收到的 MED-V 安裝檔案。</span><span class="sxs-lookup"><span data-stu-id="0341e-114">Locate the MED-V installation files that you received as part of your software download.</span></span>

2.  <span data-ttu-id="0341e-115">按兩下 MED-V \ _HostAgent \ _Setup 安裝檔。</span><span class="sxs-lookup"><span data-stu-id="0341e-115">Double-click the MED-V\_HostAgent\_Setup installation file.</span></span>

    <span data-ttu-id="0341e-116">[ **Microsoft 企業桌面虛擬化（med-v）主機代理程式設定**] 嚮導隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="0341e-116">The **Microsoft Enterprise Desktop Virtualization (MED-V) Host Agent Setup** wizard opens.</span></span> <span data-ttu-id="0341e-117">按 \[**下一步**\] 繼續。</span><span class="sxs-lookup"><span data-stu-id="0341e-117">Click **Next** to continue.</span></span>

3.  <span data-ttu-id="0341e-118">接受 Microsoft 軟體授權條款，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="0341e-118">Accept the Microsoft Software License Terms, and then click **Next**.</span></span>

4.  <span data-ttu-id="0341e-119">選取要安裝 MED-V 主機代理程式的目的地資料夾。</span><span class="sxs-lookup"><span data-stu-id="0341e-119">Select the destination folder for installing the MED-V Host Agent.</span></span> <span data-ttu-id="0341e-120">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="0341e-120">Click **Next**.</span></span>

5.  <span data-ttu-id="0341e-121">若要開始安裝主機代理程式，請按一下 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="0341e-121">To begin the Host Agent installation, click **Install**.</span></span>

6.  <span data-ttu-id="0341e-122">成功完成安裝後，請按一下 **[完成**] 以關閉嚮導。</span><span class="sxs-lookup"><span data-stu-id="0341e-122">After the installation is completed successfully, click **Finish** to close the wizard.</span></span>

    <span data-ttu-id="0341e-123">若要確認主機代理程式已成功安裝，請按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft 企業版桌面虛擬化**]，然後按一下 [ **med-v 主機代理程式**]。</span><span class="sxs-lookup"><span data-stu-id="0341e-123">To verify that the installation of the Host Agent was successful, click **Start**, click **All Programs**, click **Microsoft Enterprise Desktop Virtualization**, and then click **MED-V Host Agent**.</span></span>

<span data-ttu-id="0341e-124">**記事** 除非已安裝 MED-V 工作區，否則 MED-V 主機代理程式可以啟動並執行，但不提供任何功能。</span><span class="sxs-lookup"><span data-stu-id="0341e-124">**Note** Until a MED-V workspace is installed, the MED-V Host Agent can be started and runs, but provides no functionality.</span></span>

 

## <span data-ttu-id="0341e-125">相關主題</span><span class="sxs-lookup"><span data-stu-id="0341e-125">Related topics</span></span>


[<span data-ttu-id="0341e-126">如何透過電子軟體發佈系統來部署 MED-V 元件</span><span class="sxs-lookup"><span data-stu-id="0341e-126">How to Deploy the MED-V Components Through an Electronic Software Distribution System</span></span>](how-to-deploy-the-med-v-components-through-an-electronic-software-distribution-system.md)

[<span data-ttu-id="0341e-127">如何安裝 MED-V 工作區封裝工具</span><span class="sxs-lookup"><span data-stu-id="0341e-127">How to Install the MED-V Workspace Packager</span></span>](how-to-install-the-med-v-workspace-packager.md)

[<span data-ttu-id="0341e-128">如何解除安裝 MED-V 元件</span><span class="sxs-lookup"><span data-stu-id="0341e-128">How to Uninstall the MED-V Components</span></span>](how-to-uninstall-the-med-v-components.md)

 

 





