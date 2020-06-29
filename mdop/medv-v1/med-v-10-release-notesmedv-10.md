---
title: MED-V 1.0 版本資訊
description: MED-V 1.0 版本資訊
author: dansimp
ms.assetid: 006a3537-5c5b-43b5-8df8-4bf6ddd3cd2f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 683056f768a3d547828996a9b191d58337c21ad6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811847"
---
# <span data-ttu-id="428d3-103">MED-V 1.0 版本資訊</span><span class="sxs-lookup"><span data-stu-id="428d3-103">MED-V 1.0 Release Notes</span></span>


## <span data-ttu-id="428d3-104">MED-V 的已知問題</span><span class="sxs-lookup"><span data-stu-id="428d3-104">Known Issues with MED-V</span></span>


<span data-ttu-id="428d3-105">本節提供有關 Microsoft 企業桌面虛擬化（MED-V）平臺一般問題的最新資訊。</span><span class="sxs-lookup"><span data-stu-id="428d3-105">This section provides the most up-to-date information about general issues with the Microsoft Enterprise Desktop Virtualization (MED-V) platform.</span></span> <span data-ttu-id="428d3-106">這些問題不會出現在產品檔中，某些情況下，可能會矛盾現有的產品檔。</span><span class="sxs-lookup"><span data-stu-id="428d3-106">These issues do not appear in the product documentation and in some cases might contradict existing product documentation.</span></span> <span data-ttu-id="428d3-107">只要有可能，這些問題就會在後續版本中解決。</span><span class="sxs-lookup"><span data-stu-id="428d3-107">Whenever possible, these issues will be addressed in later releases.</span></span>

### <span data-ttu-id="428d3-108">檔案下載不遵循 Web 重新導向規則</span><span class="sxs-lookup"><span data-stu-id="428d3-108">File downloads do not follow Web redirection rules</span></span>

<span data-ttu-id="428d3-109">檔案下載不遵循 MED-V 工作區原則中設定的 Web 重新導向規則。</span><span class="sxs-lookup"><span data-stu-id="428d3-109">File downloads do not follow Web redirection rules set in a MED-V workspace policy.</span></span>

### <span data-ttu-id="428d3-110">將主控台發佈的應用程式視窗展開到全螢幕時，它就會消失</span><span class="sxs-lookup"><span data-stu-id="428d3-110">When expanding a console-published application window to full screen, it disappears</span></span>

<span data-ttu-id="428d3-111">如果您將主控台發佈的應用程式（例如 cmd.exe）視窗展開至全螢幕（在 [無縫整合] 模式中設定的 MED-V 工作區中），應用程式視窗可能會消失或無法回應。</span><span class="sxs-lookup"><span data-stu-id="428d3-111">If you expand a console-published application (such as cmd.exe) window to full screen inside a MED-V workspace configured in seamless integration mode, the application window might disappear or not respond.</span></span>

### <span data-ttu-id="428d3-112">在完整桌面圖案中工作時，電腦上的圖示位置不會儲存</span><span class="sxs-lookup"><span data-stu-id="428d3-112">When working in full desktop mode, icon locations on the desktop are not saved</span></span>

<span data-ttu-id="428d3-113">在完整桌面圖案中工作時，桌面上圖示的手動位置變更不會儲存在 MED-V 工作區會話中。</span><span class="sxs-lookup"><span data-stu-id="428d3-113">When working in full desktop mode, manual location changes of icons on the desktop are not saved between MED-V workspace sessions.</span></span>

### <span data-ttu-id="428d3-114">同一個網域中不能有相同名稱的本機映射與測試影像</span><span class="sxs-lookup"><span data-stu-id="428d3-114">A local image and a test image with the same name cannot exist in the same domain</span></span>

<span data-ttu-id="428d3-115">如果本機映射已加入網域，且系統管理員使用與測試映射相同的電腦名稱稱來建立新版本的同一個影像，則在測試映射加入網域時，[加入網域] 動作失敗或成功，並從網域移除本機影像。</span><span class="sxs-lookup"><span data-stu-id="428d3-115">If a local image is joined to the domain and the administrator creates a new version of the same image with the same computer name as a test image, when the test image joins the domain, either the join domain action fails or it succeeds and the local image is removed from the domain.</span></span>

### <span data-ttu-id="428d3-116">MED-V 不支援 Windows Aero 功能</span><span class="sxs-lookup"><span data-stu-id="428d3-116">MED-V does not support Windows Aero features</span></span>

<span data-ttu-id="428d3-117">MED-V 不支援 Windows Aero 功能（例如 Aero 翻轉3D）。</span><span class="sxs-lookup"><span data-stu-id="428d3-117">MED-V does not support Windows Aero features (such as Aero Flip 3D).</span></span>

### <span data-ttu-id="428d3-118">每個電腦只有一個 Windows 使用者可以使用管理主控台</span><span class="sxs-lookup"><span data-stu-id="428d3-118">The management console can be used by only one Windows user per computer</span></span>

<span data-ttu-id="428d3-119">MED-V 管理主控台只能由管理員和安裝管理應用程式的 Windows 使用者使用。</span><span class="sxs-lookup"><span data-stu-id="428d3-119">The MED-V management console can be used only by administrators and the Windows user who installed the management application.</span></span>

### <span data-ttu-id="428d3-120">MED-V 伺服器設定實用程式會在使用者內容下測試 Microsoft SQL Server 連線，而不是在 MED-V 伺服器服務內容下進行</span><span class="sxs-lookup"><span data-stu-id="428d3-120">The MED-V Server configuration utility tests Microsoft SQL Server connectivity under user context rather than under MED-V Server service context</span></span>

<span data-ttu-id="428d3-121">MED-V 使用 MED-V 伺服器服務內容來收集來自 Microsoft SQL Server 報表資料庫的報表。</span><span class="sxs-lookup"><span data-stu-id="428d3-121">MED-V uses MED-V Server service context to collect reports from the Microsoft SQL Server reports database.</span></span> <span data-ttu-id="428d3-122">MED-V 伺服器設定實用程式會驗證資料庫並測試資料庫連線字串。</span><span class="sxs-lookup"><span data-stu-id="428d3-122">The MED-V Server configuration utility verifies the database and tests the database connection string.</span></span> <span data-ttu-id="428d3-123">它不會驗證 MED-V Server 服務對資料庫的存取權。</span><span class="sxs-lookup"><span data-stu-id="428d3-123">It does not validate the access of MED-V Server service to the database.</span></span>

 

 





