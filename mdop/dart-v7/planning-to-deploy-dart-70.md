---
title: 規劃部署 DaRT 7.0
description: 規劃部署 DaRT 7.0
author: dansimp
ms.assetid: 05e97cdb-a8c2-46e4-9c75-a7d12fe26fe8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 09725e994a95f4f93ae655402e7577e137e33f18
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10808684"
---
# <span data-ttu-id="df17d-103">規劃部署 DaRT 7.0</span><span class="sxs-lookup"><span data-stu-id="df17d-103">Planning to Deploy DaRT 7.0</span></span>


<span data-ttu-id="df17d-104">您必須先考慮幾個不同的部署設定和先決條件，才能建立您的部署規劃。</span><span class="sxs-lookup"><span data-stu-id="df17d-104">There are a number of different deployment configurations and prerequisites that you must consider before you create your deployment plan.</span></span> <span data-ttu-id="df17d-105">本節包含可協助您收集資訊的資訊，這些資訊可協助您收集最符合您的業務需求的部署方案。</span><span class="sxs-lookup"><span data-stu-id="df17d-105">This section includes information that can help you gather the information that you must have to formulate a deployment plan that best meets your business requirements.</span></span>

<span data-ttu-id="df17d-106">規劃 Microsoft Diagnostics 與修復工具組（DaRT）7安裝時，請考慮下列事項：</span><span class="sxs-lookup"><span data-stu-id="df17d-106">Consider the following when you plan your Microsoft Diagnostics and Recovery Toolset (DaRT)7 installation:</span></span>

-   <span data-ttu-id="df17d-107">當您安裝 DaRT 時，您可以在 IT 系統管理員電腦上安裝所有與執行 DaRT 相關聯之工作的功能。</span><span class="sxs-lookup"><span data-stu-id="df17d-107">When you install DaRT, you can either install all functionality on an IT administrator computer where you will perform all the tasks associated with running DaRT.</span></span> <span data-ttu-id="df17d-108">或者，您只能安裝在 IT 系統管理員電腦上建立復原影像的 DaRT 功能。</span><span class="sxs-lookup"><span data-stu-id="df17d-108">Or you can install only the DaRT functionality that creates the recovery image on the IT administrator computer.</span></span> <span data-ttu-id="df17d-109">然後，在技術支援人員的電腦上安裝 DaRT （例如**DaRT 遠端連線檢視器**和損**毀分析**程式）所用的功能。</span><span class="sxs-lookup"><span data-stu-id="df17d-109">Then, install the functionality used to run DaRT, such as the **DaRT Remote Connection Viewer** and **Crash Analyzer**, on a helpdesk agent computer.</span></span>

-   <span data-ttu-id="df17d-110">若要能夠遠端執行 DaRT，請確認 [服務台代理電腦] 和您在遠端進行疑難排解的所有電腦都在相同的網路上。</span><span class="sxs-lookup"><span data-stu-id="df17d-110">To be able to run DaRT remotely, make sure that the helpdesk agent computer and all computers that you might be troubleshooting remotely are on the same network.</span></span>

-   <span data-ttu-id="df17d-111">在您將 DaRT 推出到生產環境之前，您可以先組建實驗環境以進行測試。</span><span class="sxs-lookup"><span data-stu-id="df17d-111">Before you roll out DaRT into production, you can first build a lab environment for testing.</span></span> <span data-ttu-id="df17d-112">測試實驗室至少應包含兩台電腦，其中一個是作為 IT 系統管理員/支援者代理電腦，另一個則充當最終使用者電腦。</span><span class="sxs-lookup"><span data-stu-id="df17d-112">A test lab should include a minimum of two computers, one to act as the IT administrator/helpdesk agent computer and one to act as an end-user computer.</span></span> <span data-ttu-id="df17d-113">或者，如果您想要將 IT 系統管理員的職責與技術支援人員的責任區分開來，您可以在實驗室中使用三台電腦。</span><span class="sxs-lookup"><span data-stu-id="df17d-113">Or, you can use three computers in your lab if you want to separate the IT administrator responsibilities from those of the helpdesk agent.</span></span>

## <span data-ttu-id="df17d-114">查看支援的設定</span><span class="sxs-lookup"><span data-stu-id="df17d-114">Review the supported configurations</span></span>


<span data-ttu-id="df17d-115">您應該查看 Microsoft Diagnostics 與復原工具集（DaRT）7支援的設定資訊，以確認您針對用戶端或功能安裝所選取的電腦符合最低硬體與作業系統需求。</span><span class="sxs-lookup"><span data-stu-id="df17d-115">You should review the Microsoft Diagnostics and Recovery Toolset (DaRT)7 Supported Configurations information to confirm that the computers you have selected for client or feature installation meet the minimum hardware and operating system requirements.</span></span>

[<span data-ttu-id="df17d-116">DaRT 7.0 支援的組態</span><span class="sxs-lookup"><span data-stu-id="df17d-116">DaRT 7.0 Supported Configurations</span></span>](dart-70-supported-configurations-dart-7.md)

## <span data-ttu-id="df17d-117">規劃建立 DaRT 恢復影像</span><span class="sxs-lookup"><span data-stu-id="df17d-117">Plan for creating the DaRT recovery image</span></span>


<span data-ttu-id="df17d-118">當您建立 DaRT 復原影像時，必須決定要在影像中包含哪些工具。</span><span class="sxs-lookup"><span data-stu-id="df17d-118">When you create the DaRT recovery image, you have to decide which tools to include on the image.</span></span> <span data-ttu-id="df17d-119">當您作出決定時，請記住，最終使用者可能會偶爾存取各種 DaRT 工具。</span><span class="sxs-lookup"><span data-stu-id="df17d-119">When you make that decision, remember that end users might have access occasionally to the various DaRT tools.</span></span> <span data-ttu-id="df17d-120">當您建立恢復影像時，您也會指定是否要包含其他驅動程式或檔案。</span><span class="sxs-lookup"><span data-stu-id="df17d-120">When you create the recovery image, you will also specify whether you want to include additional drivers or files.</span></span> <span data-ttu-id="df17d-121">決定您想要包含在 DaRT 復原影像中的任何其他驅動程式或檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="df17d-121">Determine the locations of any additional drivers or files that you want to include on the DaRT recovery image.</span></span>

<span data-ttu-id="df17d-122">您應該注意到建立 DaRT 復原影像的先決條件及其他額外規劃建議。</span><span class="sxs-lookup"><span data-stu-id="df17d-122">You should be aware of the prerequisites and other additional planning recommendations for creating the DaRT recovery image.</span></span>

[<span data-ttu-id="df17d-123">規劃建立 DaRT 7.0 復原映像</span><span class="sxs-lookup"><span data-stu-id="df17d-123">Planning to Create the DaRT 7.0 Recovery Image</span></span>](planning-to-create-the-dart-70-recovery-image.md)

## <span data-ttu-id="df17d-124">規劃儲存及部署 DaRT 恢復影像</span><span class="sxs-lookup"><span data-stu-id="df17d-124">Plan for saving and deploying the DaRT recovery image</span></span>


<span data-ttu-id="df17d-125">您可以使用數種方法儲存和部署 DaRT 恢復影像。</span><span class="sxs-lookup"><span data-stu-id="df17d-125">Several methods can be used to save and deploy the DaRT recovery image.</span></span> <span data-ttu-id="df17d-126">當您決定要使用的方法時，請考慮每個方法的優點與缺點。</span><span class="sxs-lookup"><span data-stu-id="df17d-126">When you are determining the method that you will use, consider the advantages and disadvantages of each.</span></span> <span data-ttu-id="df17d-127">此外，請考慮您想要在企業中使用 DaRT 的方式。</span><span class="sxs-lookup"><span data-stu-id="df17d-127">Also, consider how you want to use DaRT in your enterprise.</span></span>

<span data-ttu-id="df17d-128">**記事** 您可能會想要在您的組織中使用一個以上的方法。</span><span class="sxs-lookup"><span data-stu-id="df17d-128">**Note** You might want to use more than one method in your organization.</span></span> <span data-ttu-id="df17d-129">例如，在大多數情況下，您可以從遠端分區引導至 DaRT，並在使用者電腦無法連線到網路時，有可用的 USB 快閃記憶體磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="df17d-129">For example, you can boot into DaRT from a remote partition for most situations and have a USB flash drive available in case the end-user computer cannot connect to the network.</span></span>

 

[<span data-ttu-id="df17d-130">規劃如何儲存和部署 DaRT 7.0 復原映像</span><span class="sxs-lookup"><span data-stu-id="df17d-130">Planning How to Save and Deploy the DaRT 7.0 Recovery Image</span></span>](planning-how-to-save-and-deploy-the-dart-70-recovery-image.md)

## <span data-ttu-id="df17d-131">規劃部署 DaRT 的其他資源</span><span class="sxs-lookup"><span data-stu-id="df17d-131">Other resources for Planning to Deploy DaRT</span></span>


[<span data-ttu-id="df17d-132">規劃 DaRT 7.0</span><span class="sxs-lookup"><span data-stu-id="df17d-132">Planning for DaRT 7.0</span></span>](planning-for-dart-70-new-ia.md)

 

 





