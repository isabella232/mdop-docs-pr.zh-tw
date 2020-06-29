---
title: 管理 UE-V 2。
description: 管理 UE-V 2。
author: dansimp
ms.assetid: 996e4797-8383-4627-b714-24a84c907798
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2674f6ace80672c1e89bb4f9c765b56f260c3bc0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811295"
---
# <span data-ttu-id="d22a9-103">管理 UE-V 2。</span><span class="sxs-lookup"><span data-stu-id="d22a9-103">Administering UE-V 2.x</span></span>


<span data-ttu-id="d22a9-104">部署 Microsoft 使用者體驗虛擬化（UE-V）2.0、2.1 或 2.1 SP1 之後，您必須能夠執行各種日常管理工作，例如管理 UE-V Agent 的設定，以及復原遺失的設定。</span><span class="sxs-lookup"><span data-stu-id="d22a9-104">After you have deployed Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, or 2.1 SP1, you must be able to perform various ongoing administrative tasks, such as managing the configuration of the UE-V Agent and recovering lost settings.</span></span> <span data-ttu-id="d22a9-105">下列各節將說明這些安裝後的工作。</span><span class="sxs-lookup"><span data-stu-id="d22a9-105">These post-installation tasks are described in the following sections.</span></span>

## <span data-ttu-id="d22a9-106">管理 UE-V 2. x 設定</span><span class="sxs-lookup"><span data-stu-id="d22a9-106">Managing UE-V 2.x configurations</span></span>


<span data-ttu-id="d22a9-107">在 UE-V 的生命週期期間，您必須管理 UE-V Agent 的設定，以及管理資源的儲存位置（例如設定套件檔案）。</span><span class="sxs-lookup"><span data-stu-id="d22a9-107">In the course of the UE-V lifecycle, you have to manage the configuration of the UE-V Agent and also manage storage locations for resources such as settings package files.</span></span>

[<span data-ttu-id="d22a9-108">管理 UE-V 2.x 的設定</span><span class="sxs-lookup"><span data-stu-id="d22a9-108">Manage Configurations for UE-V 2.x</span></span>](manage-configurations-for-ue-v-2x-new-uevv2.md)

## <span data-ttu-id="d22a9-109">使用自訂 UE-V 範本與 UE-V 2. x 發生器</span><span class="sxs-lookup"><span data-stu-id="d22a9-109">Working with custom UE-V templates and the UE-V 2.x Generator</span></span>


<span data-ttu-id="d22a9-110">本主題提供如何使用 UE-V 發生器及管理自訂設定位置範本的指示。</span><span class="sxs-lookup"><span data-stu-id="d22a9-110">This topic provides instructions for how to use the UE-V Generator and manage custom settings location templates.</span></span>

[<span data-ttu-id="d22a9-111">使用自訂的 UE-V 2. x 範本和 UE-V 2. x 發電機</span><span class="sxs-lookup"><span data-stu-id="d22a9-111">Working with Custom UE-V 2.x Templates and the UE-V 2.x Generator</span></span>](working-with-custom-ue-v-2x-templates-and-the-ue-v-2x-generator-new-uevv2.md)

## <span data-ttu-id="d22a9-112">備份與還原與 UE-V 2 同步處理的應用程式和 Windows 設定。</span><span class="sxs-lookup"><span data-stu-id="d22a9-112">Backup and restore application and Windows settings that are synchronized with UE-V 2.x</span></span>


<span data-ttu-id="d22a9-113">UE-V 的 windows 管理工具（WMI）和 Windows PowerShell 功能提供還原設定套件的功能。</span><span class="sxs-lookup"><span data-stu-id="d22a9-113">Windows Management Instrumentation (WMI) and Windows PowerShell features of UE-V provide the ability to restore settings packages.</span></span> <span data-ttu-id="d22a9-114">透過使用 WMI 和 Windows PowerShell 命令，您可以將應用程式和 Windows 設定還原至其原始狀態，並在使用者採用新的裝置時還原其他設定。</span><span class="sxs-lookup"><span data-stu-id="d22a9-114">By using WMI and Windows PowerShell commands, you can restore application and Windows settings to their original state and restore additional settings when a user adopts a new device.</span></span>

[<span data-ttu-id="d22a9-115">管理由 UE-V 2. x 的系統管理備份和還原</span><span class="sxs-lookup"><span data-stu-id="d22a9-115">Manage Administrative Backup and Restore in UE-V 2.x</span></span>](manage-administrative-backup-and-restore-in-ue-v-2x-new-topic-for-21.md)

## <span data-ttu-id="d22a9-116">變更 UE-V 2. x 排程任務的頻率</span><span class="sxs-lookup"><span data-stu-id="d22a9-116">Changing the frequency of UE-V 2.x scheduled tasks</span></span>


<span data-ttu-id="d22a9-117">您可以設定在 UE-V 檢查是否有新的或更新的設定，或設定範本目錄中更新的自訂設定位置範本時所管理的排程任務。</span><span class="sxs-lookup"><span data-stu-id="d22a9-117">You can configure the scheduled tasks that manage when UE-V checks for new or updated settings or for updated custom settings location templates in the settings template catalog.</span></span>

[<span data-ttu-id="d22a9-118">變更 UE-V 2. x 排程任務的頻率</span><span class="sxs-lookup"><span data-stu-id="d22a9-118">Changing the Frequency of UE-V 2.x Scheduled Tasks</span></span>](changing-the-frequency-of-ue-v-2x-scheduled-tasks-both-uevv2.md)

## <span data-ttu-id="d22a9-119">遷移 UE-V a.x 設定套件</span><span class="sxs-lookup"><span data-stu-id="d22a9-119">Migrating UE-V 2.x settings packages</span></span>


<span data-ttu-id="d22a9-120">當使用者的設定套件遷移至新的伺服器或用於備份時，您可以將它們重新置放。</span><span class="sxs-lookup"><span data-stu-id="d22a9-120">You can relocate the user settings packages either when they migrate to a new server or for backup purposes.</span></span>

[<span data-ttu-id="d22a9-121">遷移 UE-V a.x 設定套件</span><span class="sxs-lookup"><span data-stu-id="d22a9-121">Migrating UE-V 2.x Settings Packages</span></span>](migrating-ue-v-2x-settings-packages-both-uevv2.md)

## <span data-ttu-id="d22a9-122">使用 UE-V 2. x 與應用程式虛擬化應用程式</span><span class="sxs-lookup"><span data-stu-id="d22a9-122">Using UE-V 2.x with Application Virtualization applications</span></span>


<span data-ttu-id="d22a9-123">您可以使用 UE-V 與 Microsoft Application Virtualization （App-v），在多部電腦上共用虛擬應用程式與已安裝應用程式之間的設定。</span><span class="sxs-lookup"><span data-stu-id="d22a9-123">You can use UE-V with Microsoft Application Virtualization (App-V) to share settings between virtual applications and installed applications across multiple computers.</span></span>

[<span data-ttu-id="d22a9-124">使用 UE-V 2. x 與應用程式虛擬化應用程式</span><span class="sxs-lookup"><span data-stu-id="d22a9-124">Using UE-V 2.x with Application Virtualization Applications</span></span>](using-ue-v-2x-with-application-virtualization-applications-both-uevv2.md)

## <span data-ttu-id="d22a9-125">此產品的其他資源</span><span class="sxs-lookup"><span data-stu-id="d22a9-125">Other resources for this product</span></span>


-   [<span data-ttu-id="d22a9-126">Microsoft 使用者體驗虛擬化（UE-V） 2. x</span><span class="sxs-lookup"><span data-stu-id="d22a9-126">Microsoft User Experience Virtualization (UE-V) 2.x</span></span>](index.md)

-   [<span data-ttu-id="d22a9-127">UE-V 2.x 入門</span><span class="sxs-lookup"><span data-stu-id="d22a9-127">Get Started with UE-V 2.x</span></span>](get-started-with-ue-v-2x-new-uevv2.md)

-   [<span data-ttu-id="d22a9-128">準備 UE-V a.x 部署</span><span class="sxs-lookup"><span data-stu-id="d22a9-128">Prepare a UE-V 2.x Deployment</span></span>](prepare-a-ue-v-2x-deployment-new-uevv2.md)

-   [<span data-ttu-id="d22a9-129">疑難排解 UE-V 2. x</span><span class="sxs-lookup"><span data-stu-id="d22a9-129">Troubleshooting UE-V 2.x</span></span>](troubleshooting-ue-v-2x-both-uevv2.md)

-   [<span data-ttu-id="d22a9-130">UE-V 2.x 技術參考</span><span class="sxs-lookup"><span data-stu-id="d22a9-130">Technical Reference for UE-V 2.x</span></span>](technical-reference-for-ue-v-2x-both-uevv2.md)






 

 





