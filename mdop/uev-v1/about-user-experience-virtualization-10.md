---
title: 關於 User Experience Virtualization 1.0
description: 關於 User Experience Virtualization 1.0
author: dansimp
ms.assetid: 3758b100-35a8-4e10-ac08-f583fb8ddbd9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6010f9c4ebc260eec0324fb880dc2c92fd675130
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809519"
---
# <span data-ttu-id="c17c0-103">關於 User Experience Virtualization 1.0</span><span class="sxs-lookup"><span data-stu-id="c17c0-103">About User Experience Virtualization 1.0</span></span>


<span data-ttu-id="c17c0-104">Microsoft 使用者體驗虛擬化（UE-V）會監視使用者對應用程式設定和 Windows 作業系統設定所做的變更。</span><span class="sxs-lookup"><span data-stu-id="c17c0-104">Microsoft User Experience Virtualization (UE-V) monitors the changes that are made by users to application settings and Windows operating system settings.</span></span> <span data-ttu-id="c17c0-105">系統會捕獲使用者設定並將其集中到設定儲存位置。</span><span class="sxs-lookup"><span data-stu-id="c17c0-105">The user settings are captured and centralized to a settings storage location.</span></span> <span data-ttu-id="c17c0-106">然後，這些設定可以套用到使用者所存取的不同電腦，包括桌上型電腦、膝上型電腦和虛擬桌面基礎結構（VDI）會話。</span><span class="sxs-lookup"><span data-stu-id="c17c0-106">These settings can then be applied to the different computers that are accessed by the user, including desktop computers, laptop computers, and virtual desktop infrastructure (VDI) sessions.</span></span>

<span data-ttu-id="c17c0-107">使用者體驗虛擬化使用設定位置範本來指定使用者電腦上的哪些應用程式和 Windows 設定受到監視及集中式。</span><span class="sxs-lookup"><span data-stu-id="c17c0-107">User Experience Virtualization uses settings location templates to specify what applications and Windows settings on the user computers are monitored and centralized.</span></span> <span data-ttu-id="c17c0-108">[設定位置] 範本是一個 XML 檔案，可指定哪些檔案和登錄位置與每個應用程式或作業系統設定相關聯。</span><span class="sxs-lookup"><span data-stu-id="c17c0-108">The settings location template is an XML file that specifies which file and registry locations are associated with each application or operating system setting.</span></span> <span data-ttu-id="c17c0-109">範本不包含設定的值;它只包含要監控之設定的位置。</span><span class="sxs-lookup"><span data-stu-id="c17c0-109">The template does not contain values for the settings; it contains only the locations of the settings that are to be monitored.</span></span>

<span data-ttu-id="c17c0-110">當使用者在電腦上工作時，就會透過 UE-V 監控應用程式設定和 Windows 設定。</span><span class="sxs-lookup"><span data-stu-id="c17c0-110">The application settings and Windows settings are monitored by UE-V when users are working on their computers.</span></span> <span data-ttu-id="c17c0-111">當使用者關閉應用程式時，應用程式設定的值會儲存在 [設定] 儲存伺服器上。</span><span class="sxs-lookup"><span data-stu-id="c17c0-111">The values for the application settings are stored on the settings storage server when the user closes the application.</span></span> <span data-ttu-id="c17c0-112">Windows 設定的值會在使用者登出、電腦被鎖定時，或當其從電腦遠端中斷連線時儲存。</span><span class="sxs-lookup"><span data-stu-id="c17c0-112">The values for the Windows settings are stored when the user logs off, when the computer is locked, or when they disconnect remotely from a computer.</span></span>

<span data-ttu-id="c17c0-113">系統管理員可以建立 UE-V 設定位置範本，以指定要漫遊的企業應用程式設定。</span><span class="sxs-lookup"><span data-stu-id="c17c0-113">An administrator can create a UE-V settings location template to specify which enterprise application settings will roam.</span></span> <span data-ttu-id="c17c0-114">UE-V 包含一些 Microsoft 應用程式和 Windows 設定的設定位置樣板集合。</span><span class="sxs-lookup"><span data-stu-id="c17c0-114">UE-V includes a set of settings location templates for some Microsoft applications and Windows settings.</span></span> <span data-ttu-id="c17c0-115">如需 UE-V 中預設應用程式和設定的清單，請參閱[規劃要與 ue-v 1.0 同步處理哪些應用程式](planning-which-applications-to-synchronize-with-ue-v-10.md)。</span><span class="sxs-lookup"><span data-stu-id="c17c0-115">For a list of default applications and settings in UE-V, see [Planning Which Applications to Synchronize with UE-V 1.0](planning-which-applications-to-synchronize-with-ue-v-10.md).</span></span>

## <span data-ttu-id="c17c0-116">UEV 1.0 版本資訊</span><span class="sxs-lookup"><span data-stu-id="c17c0-116">UEV 1.0 Release Notes</span></span>


<span data-ttu-id="c17c0-117">如需詳細資訊，以及未在檔中使用的最新消息，請參閱[Microsoft 使用者體驗虛擬化（ue-v）1.0 版本](microsoft-user-experience-virtualization--ue-v--10-release-notes.md)資訊。</span><span class="sxs-lookup"><span data-stu-id="c17c0-117">For more information, and for late-breaking news that did not make it into the documentation, see [Microsoft User Experience Virtualization (UE-V) 1.0 Release Notes](microsoft-user-experience-virtualization--ue-v--10-release-notes.md).</span></span>

## <span data-ttu-id="c17c0-118">相關主題</span><span class="sxs-lookup"><span data-stu-id="c17c0-118">Related topics</span></span>


[<span data-ttu-id="c17c0-119">開始使用 User Experience Virtualization 1.0</span><span class="sxs-lookup"><span data-stu-id="c17c0-119">Getting Started With User Experience Virtualization 1.0</span></span>](getting-started-with-user-experience-virtualization-10.md)

[<span data-ttu-id="c17c0-120">Microsoft User Experience Virtualization (UE-V) 1.0</span><span class="sxs-lookup"><span data-stu-id="c17c0-120">Microsoft User Experience Virtualization (UE-V) 1.0</span></span>](index.md)

[<span data-ttu-id="c17c0-121">UE-V 1.0 的高階架構</span><span class="sxs-lookup"><span data-stu-id="c17c0-121">High-Level Architecture for UE-V 1.0</span></span>](high-level-architecture-for-ue-v-10.md)

 

 





