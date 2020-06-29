---
title: 關於 DaRT 8.1
description: 關於 DaRT 8.1
author: dansimp
ms.assetid: dcaddc57-0111-4a9d-8be9-f5ada0eefa7d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 29c7522b4f5a5da3b451b23f2fd200db44bb9481
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10808649"
---
# <span data-ttu-id="22267-103">關於 DaRT 8.1</span><span class="sxs-lookup"><span data-stu-id="22267-103">About DaRT 8.1</span></span>


<span data-ttu-id="22267-104">Microsoft 診斷與修復工具組（DaRT）8.1 提供下列增強功能，如本主題所述。</span><span class="sxs-lookup"><span data-stu-id="22267-104">Microsoft Diagnostics and Recovery Toolset (DaRT) 8.1 provides the following enhancements, which are described in this topic.</span></span>

## <a href="" id="what-s-new"></a><span data-ttu-id="22267-105">新功能</span><span class="sxs-lookup"><span data-stu-id="22267-105">What’s new</span></span>


-   **<span data-ttu-id="22267-106">支援 WIMBoot</span><span class="sxs-lookup"><span data-stu-id="22267-106">Support for WIMBoot</span></span>**

    <span data-ttu-id="22267-107">如果符合下列條件，則診斷和修復工具組8.1 支援 Windows 映像檔啟動（WIMBoot）環境：</span><span class="sxs-lookup"><span data-stu-id="22267-107">Diagnostics and Recovery Toolset 8.1 supports the Windows image file boot (WIMBoot) environment if these conditions are met:</span></span>

    -   <span data-ttu-id="22267-108">WIMBoot 是以 Windows 8.1 Update 1 或更新版本為基礎。</span><span class="sxs-lookup"><span data-stu-id="22267-108">WIMBoot is based on Windows 8.1 Update 1 or later.</span></span>

    -   <span data-ttu-id="22267-109">DaRT 8.1 映射是在 Windows 8.1 更新1或更新版本上建立。</span><span class="sxs-lookup"><span data-stu-id="22267-109">The DaRT 8.1 image is built on Windows 8.1 Update 1 or later.</span></span>

    <span data-ttu-id="22267-110">如需 WIMBoot 的詳細資訊，請參閱[Windows 映像檔引導（WIMBoot）概述](https://go.microsoft.com/fwlink/?LinkId=517536)。</span><span class="sxs-lookup"><span data-stu-id="22267-110">For more information about WIMBoot, see [Windows Image File Boot (WIMBoot) Overview](https://go.microsoft.com/fwlink/?LinkId=517536).</span></span>

-   **<span data-ttu-id="22267-111">Windows Server 2012 R2 和 Windows 8.1 的支援</span><span class="sxs-lookup"><span data-stu-id="22267-111">Support for Windows Server 2012 R2 and Windows 8.1</span></span>**

    <span data-ttu-id="22267-112">您可以使用 Windows Server 2012 R2 或 Windows 8.1 來建立 DaRT 映射。</span><span class="sxs-lookup"><span data-stu-id="22267-112">You can create DaRT images by using Windows Server 2012 R2 or Windows 8.1.</span></span>

    **<span data-ttu-id="22267-113">注意</span><span class="sxs-lookup"><span data-stu-id="22267-113">Note</span></span>**  
    <span data-ttu-id="22267-114">針對舊版的 Windows Server 和 Windows 作業系統，請繼續使用舊版的 DaRT。</span><span class="sxs-lookup"><span data-stu-id="22267-114">For earlier versions of the Windows Server and Windows operating systems, continue to use the earlier versions of DaRT.</span></span>



-   **<span data-ttu-id="22267-115">客戶回函</span><span class="sxs-lookup"><span data-stu-id="22267-115">Customer feedback</span></span>**

    <span data-ttu-id="22267-116">DaRT 8.1 包含的更新會解決從 DaRT 8.0 SP1 發行以來發現的問題。</span><span class="sxs-lookup"><span data-stu-id="22267-116">DaRT 8.1 includes updates that address issues found since the DaRT 8.0 SP1 release.</span></span>

-   **<span data-ttu-id="22267-117">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="22267-117">Windows Defender</span></span>**

    <span data-ttu-id="22267-118">Windows 8.1 中的 windows Defender 包括改良的保護。</span><span class="sxs-lookup"><span data-stu-id="22267-118">Windows Defender in Windows 8.1 includes improved protection.</span></span> <span data-ttu-id="22267-119">變更不會影響您搭配 Windows Defender 使用 DaRT 的方式。</span><span class="sxs-lookup"><span data-stu-id="22267-119">The changes do not impact how you use DaRT with Windows Defender.</span></span>

## <span data-ttu-id="22267-120">需求</span><span class="sxs-lookup"><span data-stu-id="22267-120">Requirements</span></span>


-   **<span data-ttu-id="22267-121">Windows 評估與開發套件8。1</span><span class="sxs-lookup"><span data-stu-id="22267-121">Windows Assessment and Development Kit 8.1</span></span>**

    <span data-ttu-id="22267-122">Windows 評估與開發套件（ADK）8.1 是 DaRT 復原映射嚮導必要的先決條件。</span><span class="sxs-lookup"><span data-stu-id="22267-122">Windows Assessment and Development Kit (ADK) 8.1 is a required prerequisite for the DaRT Recovery Image Wizard.</span></span> <span data-ttu-id="22267-123">Windows ADK 8.1 包含用來自訂、部署及服務 Windows 影像的部署工具。</span><span class="sxs-lookup"><span data-stu-id="22267-123">Windows ADK 8.1 contains deployment tools that are used to customize, deploy, and service Windows images.</span></span> <span data-ttu-id="22267-124">它也包含 Windows 預先安裝環境（Windows PE）。</span><span class="sxs-lookup"><span data-stu-id="22267-124">It also contains the Windows Preinstallation Environment (Windows PE).</span></span>

    **<span data-ttu-id="22267-125">注意</span><span class="sxs-lookup"><span data-stu-id="22267-125">Note</span></span>**  
    <span data-ttu-id="22267-126">如果您只安裝遠端連線檢視器或故障分析程式，則不需要 Windows ADK 8.1。</span><span class="sxs-lookup"><span data-stu-id="22267-126">Windows ADK 8.1 is not required if you are installing only Remote Connection Viewer or Crash Analyzer.</span></span>



~~~
To download Windows ADK 8.1, see [Windows Assessment and Deployment Kit (Windows ADK) for Windows 8.1](https://www.microsoft.com/download/details.aspx?id=39982) in the Microsoft Download Center.
~~~

-   **<span data-ttu-id="22267-127">Microsoft .NET Framework 4.5。1</span><span class="sxs-lookup"><span data-stu-id="22267-127">Microsoft .NET Framework 4.5.1</span></span>**

    <span data-ttu-id="22267-128">DaRT 8.1 需要安裝 .NET Framework 4.5.1。</span><span class="sxs-lookup"><span data-stu-id="22267-128">DaRT 8.1 requires that .NET Framework 4.5.1 is installed.</span></span> <span data-ttu-id="22267-129">若要下載，請參閱 Microsoft 下載中心中的[Microsoft.NET Framework 4.5.1](https://go.microsoft.com/fwlink/?LinkId=329038) 。</span><span class="sxs-lookup"><span data-stu-id="22267-129">To download, see [Microsoft.NET Framework 4.5.1](https://go.microsoft.com/fwlink/?LinkId=329038) in the Microsoft Download Center.</span></span>

-   **<span data-ttu-id="22267-130">Windows 8.1 調試工具</span><span class="sxs-lookup"><span data-stu-id="22267-130">Windows 8.1 Debugging Tools</span></span>**

    <span data-ttu-id="22267-131">若要在 DaRT 8.1 中使用 [損毀分析工具]，您需要適用于 Windows 8.1 的軟體發展套件所需的調試工具。</span><span class="sxs-lookup"><span data-stu-id="22267-131">To use the Crash Analyzer tool in DaRT 8.1, you need the required debugging tools, which are available in the Software Development Kit for Windows 8.1.</span></span>

    <span data-ttu-id="22267-132">若要下載，請參閱 Microsoft 下載中心中[適用于 windows 8.1 的 Windows 軟體發展工具組（SDK）](https://msdn.microsoft.com/library/windows/desktop/bg162891.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="22267-132">To download, see [Windows Software Development Kit (SDK) for Windows 8.1](https://msdn.microsoft.com/library/windows/desktop/bg162891.aspx) in the Microsoft Download Center.</span></span>

## <span data-ttu-id="22267-133">語言可用性</span><span class="sxs-lookup"><span data-stu-id="22267-133">Language availability</span></span>


<span data-ttu-id="22267-134">DaRT 8.1 提供下列語言版本：</span><span class="sxs-lookup"><span data-stu-id="22267-134">DaRT 8.1 is available in the following languages:</span></span>

-   <span data-ttu-id="22267-135">英文（美國） en</span><span class="sxs-lookup"><span data-stu-id="22267-135">English (United States) en-US</span></span>

-   <span data-ttu-id="22267-136">法文（法國） fr-fr</span><span class="sxs-lookup"><span data-stu-id="22267-136">French (France) fr-FR</span></span>

-   <span data-ttu-id="22267-137">義大利文（義大利） it</span><span class="sxs-lookup"><span data-stu-id="22267-137">Italian (Italy) it-IT</span></span>

-   <span data-ttu-id="22267-138">德國（德國） de</span><span class="sxs-lookup"><span data-stu-id="22267-138">German (Germany) de-DE</span></span>

-   <span data-ttu-id="22267-139">西班牙文，國際排序（西班牙） es</span><span class="sxs-lookup"><span data-stu-id="22267-139">Spanish, International Sort (Spain) es-ES</span></span>

-   <span data-ttu-id="22267-140">韓文（韓國） ko-KR</span><span class="sxs-lookup"><span data-stu-id="22267-140">Korean (Korea) ko-KR</span></span>

-   <span data-ttu-id="22267-141">日文（日本） ja-jp</span><span class="sxs-lookup"><span data-stu-id="22267-141">Japanese (Japan) ja-JP</span></span>

-   <span data-ttu-id="22267-142">葡萄牙文（巴西） pt-BR</span><span class="sxs-lookup"><span data-stu-id="22267-142">Portuguese (Brazil) pt-BR</span></span>

-   <span data-ttu-id="22267-143">俄文（俄羅斯） ru-RU</span><span class="sxs-lookup"><span data-stu-id="22267-143">Russian (Russia) ru-RU</span></span>

-   <span data-ttu-id="22267-144">繁體中文 zh-cn&platform-幼圓</span><span class="sxs-lookup"><span data-stu-id="22267-144">Chinese Traditional zh-TW</span></span>

-   <span data-ttu-id="22267-145">簡體中文 zh-cn&platform-CN</span><span class="sxs-lookup"><span data-stu-id="22267-145">Chinese Simplified zh-CN</span></span>

## <span data-ttu-id="22267-146">如何取得 MDOP 技術</span><span class="sxs-lookup"><span data-stu-id="22267-146">How to Get MDOP Technologies</span></span>


<span data-ttu-id="22267-147">DaRT 8.1 是 Microsoft 桌面優化套件（MDOP）的一部分。</span><span class="sxs-lookup"><span data-stu-id="22267-147">DaRT 8.1 is a part of the Microsoft Desktop Optimization Pack (MDOP).</span></span> <span data-ttu-id="22267-148">MDOP 是 Microsoft 軟體保證的一部分。</span><span class="sxs-lookup"><span data-stu-id="22267-148">MDOP is part of Microsoft Software Assurance.</span></span> <span data-ttu-id="22267-149">如需 Microsoft 軟體保證及取得 MDOP 的詳細資訊，請參閱[如何取得 mdop](https://go.microsoft.com/fwlink/?LinkId=322049) （ https://go.microsoft.com/fwlink/?LinkId=322049) 。</span><span class="sxs-lookup"><span data-stu-id="22267-149">For more information about Microsoft Software Assurance and acquiring MDOP, see [How Do I Get MDOP](https://go.microsoft.com/fwlink/?LinkId=322049) (https://go.microsoft.com/fwlink/?LinkId=322049).</span></span>

## <span data-ttu-id="22267-150">相關主題</span><span class="sxs-lookup"><span data-stu-id="22267-150">Related topics</span></span>


[<span data-ttu-id="22267-151">DaRT 8.1 版本資訊</span><span class="sxs-lookup"><span data-stu-id="22267-151">Release Notes for DaRT 8.1</span></span>](release-notes-for-dart-81.md)









