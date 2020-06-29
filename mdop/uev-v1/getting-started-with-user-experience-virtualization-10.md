---
title: 開始使用 User Experience Virtualization 1.0
description: 開始使用 User Experience Virtualization 1.0
author: dansimp
ms.assetid: 74a068dc-4f87-4cb4-b114-8ca2a37149f7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 010cefc42c8f2d65ac7f815eff51ec2df42df4d0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812164"
---
# <span data-ttu-id="6926a-103">開始使用 User Experience Virtualization 1.0</span><span class="sxs-lookup"><span data-stu-id="6926a-103">Getting Started With User Experience Virtualization 1.0</span></span>


<span data-ttu-id="6926a-104">Microsoft 使用者體驗虛擬化（UE-V）可捕獲並集中使用者的應用程式設定和 Windows 作業系統設定。</span><span class="sxs-lookup"><span data-stu-id="6926a-104">Microsoft User Experience Virtualization (UE-V) captures and centralizes application settings and Windows operating system settings for the user.</span></span> <span data-ttu-id="6926a-105">然後，這些設定會套用到使用者所存取的不同電腦，包括桌上型電腦、膝上型電腦和虛擬桌面基礎結構（VDI）會話。</span><span class="sxs-lookup"><span data-stu-id="6926a-105">These settings are then applied to the different computers that are accessed by the user, including desktop computers, laptop computers, and virtual desktop infrastructure (VDI) sessions.</span></span>

<span data-ttu-id="6926a-106">UE-V 提供常見 Microsoft 應用程式和 Windows 設定的 [設定同步處理]。</span><span class="sxs-lookup"><span data-stu-id="6926a-106">UE-V offers settings synchronization for common Microsoft applications and Windows settings.</span></span> <span data-ttu-id="6926a-107">它也可隨時將使用者設定提供給使用者在整個企業中運作的任何時間。</span><span class="sxs-lookup"><span data-stu-id="6926a-107">It also delivers user settings at any time to wherever users work throughout the enterprise.</span></span> <span data-ttu-id="6926a-108">UE-V 可讓系統管理員指定要漫遊的應用程式設定和 Windows 設定。</span><span class="sxs-lookup"><span data-stu-id="6926a-108">UE-V allows administrators to specify which application settings and Windows settings roam.</span></span> <span data-ttu-id="6926a-109">UE-V 可協助管理員針對企業中使用的協力廠商或行業應用程式建立自訂設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="6926a-109">UE-V helps administrators to create custom settings location templates for third-party or line-of-business applications that are used in the enterprise.</span></span>

<span data-ttu-id="6926a-110">使用者體驗虛擬化可提供增強的使用者狀態虛擬化體驗。</span><span class="sxs-lookup"><span data-stu-id="6926a-110">User Experience Virtualization delivers an enhanced user state virtualization experience.</span></span> <span data-ttu-id="6926a-111">在下列情況下，它可提供一致的使用者設定個人化功能：</span><span class="sxs-lookup"><span data-stu-id="6926a-111">It provides consistent personalization of the user’s settings in the following scenarios:</span></span>

-   <span data-ttu-id="6926a-112">電腦間的漫遊使用者應用程式和 Windows 設定。</span><span class="sxs-lookup"><span data-stu-id="6926a-112">Roaming user application and Windows settings between computers.</span></span>

-   <span data-ttu-id="6926a-113">在使用不同方法部署之應用程式的實例之間進行漫遊使用者設定：</span><span class="sxs-lookup"><span data-stu-id="6926a-113">Roaming user settings between the instances of an application that are deployed by using different methods:</span></span>

    -   <span data-ttu-id="6926a-114">已安裝的應用程式</span><span class="sxs-lookup"><span data-stu-id="6926a-114">Installed applications</span></span>

    -   <span data-ttu-id="6926a-115">應用程式虛擬化（App-v）已排序的應用程式</span><span class="sxs-lookup"><span data-stu-id="6926a-115">Application Virtualization (App-V) sequenced applications</span></span>

    -   <span data-ttu-id="6926a-116">RemoteApp （遠端桌面虛擬化）應用程式</span><span class="sxs-lookup"><span data-stu-id="6926a-116">RemoteApp (Remote Desktop Virtualization) applications</span></span>

-   <span data-ttu-id="6926a-117">在替換、硬體升級或重新鏡像之後，復原電腦的設定。</span><span class="sxs-lookup"><span data-stu-id="6926a-117">Recovering settings for a computer after replacement, hardware upgrade, or reimage.</span></span>

<span data-ttu-id="6926a-118">此產品需要進行完整規劃，才能部署或使用其功能。</span><span class="sxs-lookup"><span data-stu-id="6926a-118">This product requires thorough planning before you deploy it or use its features.</span></span> <span data-ttu-id="6926a-119">因為這個產品可能會影響貴組織中的每一部電腦，所以如果您不小心規劃您的部署，可能會中斷整個網路。</span><span class="sxs-lookup"><span data-stu-id="6926a-119">Because this product can affect every computer in your organization, you might disrupt your entire network if you do not plan your deployment carefully.</span></span> <span data-ttu-id="6926a-120">不過，如果您仔細規劃部署並加以管理，以符合您的業務需求，此產品可協助降低您的管理負荷及總擁有權成本。</span><span class="sxs-lookup"><span data-stu-id="6926a-120">However, if you plan your deployment carefully and manage it so that it meets your business needs, this product can help reduce your administrative overhead and total cost of ownership.</span></span>

<span data-ttu-id="6926a-121">如果您是本產品的新使用者，建議您仔細閱讀檔。</span><span class="sxs-lookup"><span data-stu-id="6926a-121">If you are new to this product, we recommend that you read the documentation carefully.</span></span> <span data-ttu-id="6926a-122">在您將產品部署到生產環境之前，我們也建議您在測試網路環境中驗證您的部署規劃。</span><span class="sxs-lookup"><span data-stu-id="6926a-122">Before you deploy the product to a production environment, we also recommend that you validate your deployment plan in a test network environment.</span></span> <span data-ttu-id="6926a-123">您也可以考慮參與相關技術的課程。</span><span class="sxs-lookup"><span data-stu-id="6926a-123">You might also consider taking a class about relevant technologies.</span></span> <span data-ttu-id="6926a-124">如需 Microsoft 訓練商機的詳細資訊，請參閱 Microsoft 訓練概覽 <https://go.microsoft.com/fwlink/p/?LinkId=80347> 。</span><span class="sxs-lookup"><span data-stu-id="6926a-124">For more information about Microsoft training opportunities, see the Microsoft Training Overview at <https://go.microsoft.com/fwlink/p/?LinkId=80347>.</span></span>

<span data-ttu-id="6926a-125">**記事** 此系統管理員指南的可下載版本無法使用。</span><span class="sxs-lookup"><span data-stu-id="6926a-125">**Note** A downloadable version of this administrator’s guide is not available.</span></span> <span data-ttu-id="6926a-126">不過，您可以瞭解 TechNet 文件庫的特殊模式，讓您選取文章、將其群組在集合中，或在 <https://go.microsoft.com/fwlink/?LinkId=272497> （ https://go.microsoft.com/fwlink/?LinkId=272497) 。</span><span class="sxs-lookup"><span data-stu-id="6926a-126">However, you can learn about a special mode of the TechNet Library that allows you to select articles, group them in a collection, and print them or export them to a file at <https://go.microsoft.com/fwlink/?LinkId=272497> (https://go.microsoft.com/fwlink/?LinkId=272497).</span></span>

 

## <span data-ttu-id="6926a-127">Microsoft 使用者體驗虛擬化主題快速入門</span><span class="sxs-lookup"><span data-stu-id="6926a-127">Getting started with Microsoft User Experience Virtualization topics</span></span>


-   [<span data-ttu-id="6926a-128">關於 User Experience Virtualization 1.0</span><span class="sxs-lookup"><span data-stu-id="6926a-128">About User Experience Virtualization 1.0</span></span>](about-user-experience-virtualization-10.md)

    <span data-ttu-id="6926a-129">說明使用者體驗虛擬化的功能和功能。</span><span class="sxs-lookup"><span data-stu-id="6926a-129">Describes the functionality and features of User Experience Virtualization.</span></span>

-   [<span data-ttu-id="6926a-130">UE-V 1.0 的高階架構</span><span class="sxs-lookup"><span data-stu-id="6926a-130">High-Level Architecture for UE-V 1.0</span></span>](high-level-architecture-for-ue-v-10.md)

    <span data-ttu-id="6926a-131">說明使用者體驗虛擬化的功能。</span><span class="sxs-lookup"><span data-stu-id="6926a-131">Explains the features of User Experience Virtualization.</span></span>

-   [<span data-ttu-id="6926a-132">Microsoft User Experience Virtualization (UE-V) 1.0 版本資訊</span><span class="sxs-lookup"><span data-stu-id="6926a-132">Microsoft User Experience Virtualization (UE-V) 1.0 Release Notes</span></span>](microsoft-user-experience-virtualization--ue-v--10-release-notes.md)

    <span data-ttu-id="6926a-133">描述 UE-V 的已知問題。</span><span class="sxs-lookup"><span data-stu-id="6926a-133">Describes the known issues for UE-V.</span></span>

-   [<span data-ttu-id="6926a-134">UE-V 的協助工具</span><span class="sxs-lookup"><span data-stu-id="6926a-134">Accessibility for UE-V</span></span>](accessibility-for-ue-v.md)

    <span data-ttu-id="6926a-135">說明 UE-V 的鍵盤快速鍵和協助工具資訊。</span><span class="sxs-lookup"><span data-stu-id="6926a-135">Describes the keyboard shortcuts and accessibility information for UE-V.</span></span>

## <span data-ttu-id="6926a-136">此產品的其他資源</span><span class="sxs-lookup"><span data-stu-id="6926a-136">Other resources for this product</span></span>


-   [<span data-ttu-id="6926a-137">Microsoft User Experience Virtualization (UE-V) 1.0</span><span class="sxs-lookup"><span data-stu-id="6926a-137">Microsoft User Experience Virtualization (UE-V) 1.0</span></span>](index.md)

-   [<span data-ttu-id="6926a-138">為 UE-V 1.0 進行規劃</span><span class="sxs-lookup"><span data-stu-id="6926a-138">Planning for UE-V 1.0</span></span>](planning-for-ue-v-10.md)

-   [<span data-ttu-id="6926a-139">部署 UE-V 1.0</span><span class="sxs-lookup"><span data-stu-id="6926a-139">Deploying UE-V 1.0</span></span>](deploying-ue-v-10.md)

-   [<span data-ttu-id="6926a-140">UE-V 1.0 作業</span><span class="sxs-lookup"><span data-stu-id="6926a-140">Operations for UE-V 1.0</span></span>](operations-for-ue-v-10.md)

-   [<span data-ttu-id="6926a-141">疑難排解 UE-V 1.0</span><span class="sxs-lookup"><span data-stu-id="6926a-141">Troubleshooting UE-V 1.0</span></span>](troubleshooting-ue-v-10.md)

 

 





