---
title: 使用 DaRT 10 復原電腦
description: 使用 DaRT 10 復原電腦
author: dansimp
ms.assetid: 2ad7fab0-c22d-4171-8b5a-b2b7d7c0ad2d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2031d55427e24638e41dfc6ed7b0ef437922e9c4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809668"
---
# <span data-ttu-id="adc36-103">使用 DaRT 10 復原電腦</span><span class="sxs-lookup"><span data-stu-id="adc36-103">Recovering Computers Using DaRT 10</span></span>


<span data-ttu-id="adc36-104">部署 Microsoft Diagnostics 和復原工具集（DaRT）10復原影像之後，您可以使用 DaRT 10 來復原電腦。</span><span class="sxs-lookup"><span data-stu-id="adc36-104">After deploying the Microsoft Diagnostics and Recovery Toolset (DaRT) 10 recovery image, you can use DaRT 10 to recover computers.</span></span> <span data-ttu-id="adc36-105">本節中的資訊說明您可以執行的復原工作。</span><span class="sxs-lookup"><span data-stu-id="adc36-105">The information in this section describes the recovery tasks that you can perform.</span></span>

<span data-ttu-id="adc36-106">根據您部署 DaRT 復原影像的方式，您有數種不同的方法可供您選擇來引導至 DaRT。</span><span class="sxs-lookup"><span data-stu-id="adc36-106">You have several different methods to choose from to boot into DaRT, depending on how you deploy the DaRT recovery image.</span></span>

-   <span data-ttu-id="adc36-107">在有問題的電腦中插入 DaRT 復原影像 CD、DVD 或 USB 快閃磁碟機，並使用它來引導至電腦。</span><span class="sxs-lookup"><span data-stu-id="adc36-107">Insert a DaRT recovery image CD, DVD, or USB flash drive into the problem computer and use it to boot into the computer.</span></span>

-   <span data-ttu-id="adc36-108">從問題電腦上的 [恢復] 分區引導至 DaRT。</span><span class="sxs-lookup"><span data-stu-id="adc36-108">Boot into DaRT from a recovery partition on the problem computer.</span></span>

-   <span data-ttu-id="adc36-109">從網路上的遠端分區引導至 DaRT。</span><span class="sxs-lookup"><span data-stu-id="adc36-109">Boot into DaRT from a remote partition on the network.</span></span>

<span data-ttu-id="adc36-110">如需每個方法的優點與缺點的詳細資訊，請參閱[規劃如何儲存及部署 DaRT 10 復原影像](planning-how-to-save-and-deploy-the-dart-10-recovery-image.md)。</span><span class="sxs-lookup"><span data-stu-id="adc36-110">For information about the advantages and disadvantages of each method, see [Planning How to Save and Deploy the DaRT 10 Recovery Image](planning-how-to-save-and-deploy-the-dart-10-recovery-image.md).</span></span>

<span data-ttu-id="adc36-111">無論您使用何種方法引導至 DaRT，您都必須在 BIOS 中啟用啟動裝置，以找到您要讓使用者使用的引導選項或選項。</span><span class="sxs-lookup"><span data-stu-id="adc36-111">Whichever method that you use to boot into DaRT, you must enable the boot device in the BIOS for the boot option or options that you want to make available to the end user.</span></span>

<span data-ttu-id="adc36-112">**記事** 根據您組織中使用的硬碟、網路介面卡及其他硬體的類型，設定 BIOS 是唯一的。</span><span class="sxs-lookup"><span data-stu-id="adc36-112">**Note** Configuring the BIOS is unique, depending on the kind of hard disk drive, network adapters, and other hardware that is used in your organization.</span></span>

 

## <span data-ttu-id="adc36-113">使用 DaRT 恢復影像復原本機電腦</span><span class="sxs-lookup"><span data-stu-id="adc36-113">Recover a local computer by using the DaRT recovery image</span></span>


<span data-ttu-id="adc36-114">若要使用 DaRT 復原本機電腦，您必須在遇到需要 DaRT 之問題的使用者電腦上實際出現。</span><span class="sxs-lookup"><span data-stu-id="adc36-114">To recover a local computer by using DaRT, you must be physically present at the end-user computer that is experiencing problems that require DaRT.</span></span>

[<span data-ttu-id="adc36-115">如何使用 DaRT 復原映像來復原本機電腦</span><span class="sxs-lookup"><span data-stu-id="adc36-115">How to Recover Local Computers by Using the DaRT Recovery Image</span></span>](how-to-recover-local-computers-by-using-the-dart-recovery-image-dart-10.md)

## <span data-ttu-id="adc36-116">使用 DaRT 恢復影像復原遠端電腦</span><span class="sxs-lookup"><span data-stu-id="adc36-116">Recover a remote computer by using the DaRT recovery image</span></span>


<span data-ttu-id="adc36-117">DaRT 中的遠端連線功能可讓 IT 系統管理員在最終使用者電腦上遠端執行 DaRT 工具。</span><span class="sxs-lookup"><span data-stu-id="adc36-117">The Remote Connection feature in DaRT lets an IT administrator run the DaRT tools remotely on an end-user computer.</span></span> <span data-ttu-id="adc36-118">當使用者（或由支援使用者電腦的技術支援人員）提供特定資訊之後，IT 系統管理員或技術支援人員就可以控制最終使用者的電腦，並以遠端方式執行必要的 DaRT 工具。</span><span class="sxs-lookup"><span data-stu-id="adc36-118">After certain information is provided by the end user (or by a help desk professional working on the end-user computer), the IT administrator or help desk worker can take control of the end user's computer and run the necessary DaRT tools remotely.</span></span>

<span data-ttu-id="adc36-119">**重要** 建立遠端連線的兩台電腦必須是相同網路的一部分。</span><span class="sxs-lookup"><span data-stu-id="adc36-119">**Important** The two computers establishing a remote connection must be part of the same network.</span></span>

 

<span data-ttu-id="adc36-120">[**診斷與修復工具集**] 視窗包含在使用者從系統管理員電腦遠端執行 DaRT 的選項。</span><span class="sxs-lookup"><span data-stu-id="adc36-120">The **Diagnostics and Recovery Toolset** window includes the option to run DaRT on an end-user computer remotely from an administrator computer.</span></span> <span data-ttu-id="adc36-121">使用者會在有問題的電腦上開啟 DaRT 工具，然後按一下 [**遠端**連線] 以啟動遠端會話。</span><span class="sxs-lookup"><span data-stu-id="adc36-121">The end user opens the DaRT tools on the problem computer and starts the remote session by clicking **Remote Connection**.</span></span>

<span data-ttu-id="adc36-122">最終使用者電腦上的 [遠端連線] 功能會建立下列連線資訊：票證號碼、埠，以及所有可用 IP 位址的清單。</span><span class="sxs-lookup"><span data-stu-id="adc36-122">The Remote Connection feature on the end-user computer creates the following connection information: a ticket number, a port, and a list of all available IP addresses.</span></span> <span data-ttu-id="adc36-123">票據編號與埠會隨機產生。</span><span class="sxs-lookup"><span data-stu-id="adc36-123">The ticket number and port are generated randomly.</span></span>

<span data-ttu-id="adc36-124">IT 系統管理員或技術支援人員會將此資訊輸入到**DaRT 遠端連線檢視器**，以與使用者電腦建立終端服務連線。</span><span class="sxs-lookup"><span data-stu-id="adc36-124">The IT administrator or help desk worker enters this information into the **DaRT Remote Connection Viewer** to establish the terminal services connection to the end-user computer.</span></span> <span data-ttu-id="adc36-125">建立的終端服務連線可讓 IT 系統管理員與端使用者電腦上的 DaRT 工具進行遠端互動。</span><span class="sxs-lookup"><span data-stu-id="adc36-125">The terminal services connection that is established lets an IT administrator remotely interact with the DaRT tools on the end-user computer.</span></span> <span data-ttu-id="adc36-126">最終使用者電腦接著會處理連線資訊、共用其螢幕，並回應來自 IT 系統管理員電腦的指示。</span><span class="sxs-lookup"><span data-stu-id="adc36-126">The end-user computer then processes the connection information, shares its screen, and responds to instructions from the IT administrator computer.</span></span>

[<span data-ttu-id="adc36-127">如何使用 DaRT 復原映像來復原遠端電腦</span><span class="sxs-lookup"><span data-stu-id="adc36-127">How to Recover Remote Computers by Using the DaRT Recovery Image</span></span>](how-to-recover-remote-computers-by-using-the-dart-recovery-image-dart-10.md)

## <span data-ttu-id="adc36-128">使用 DaRT 10 復原電腦的其他資源</span><span class="sxs-lookup"><span data-stu-id="adc36-128">Other resources for recovering computers using DaRT 10</span></span>


[<span data-ttu-id="adc36-129">適用於 DaRT 10 的操作</span><span class="sxs-lookup"><span data-stu-id="adc36-129">Operations for DaRT 10</span></span>](operations-for-dart-10.md)

 

 





