---
title: 在 MBAM 2.5 SP1 上套用 Hotfix
description: 在 MBAM 2.5 SP1 上套用 Hotfix
ms.author: ppriya-msft
author: dansimp
ms.assetid: ''
ms.reviewer: ''
manager: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 8/30/2018
ms.openlocfilehash: 71f840ce4d57a0698289128f92b9d760ca14ddfc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810406"
---
# <span data-ttu-id="a0503-103">在 MBAM 2.5 SP1 上套用 Hotfix</span><span class="sxs-lookup"><span data-stu-id="a0503-103">Applying hotfixes on MBAM 2.5 SP1</span></span>
<span data-ttu-id="a0503-104">本主題描述針對 Microsoft BitLocker 管理和監控（MBAM） Server 2.5 SP1 應用修復程式的程式</span><span class="sxs-lookup"><span data-stu-id="a0503-104">This topic describes the process for applying the hotfixes for Microsoft BitLocker Administration and Monitoring (MBAM) Server 2.5 SP1</span></span>

### <span data-ttu-id="a0503-105">在開始之前，請先下載 Microsoft BitLocker 管理和監控（MBAM） Server 2.5 SP1 的最新修復程式</span><span class="sxs-lookup"><span data-stu-id="a0503-105">Before you begin, download the latest hotfix of Microsoft BitLocker Administration and Monitoring (MBAM) Server 2.5 SP1</span></span>
[<span data-ttu-id="a0503-106">桌面優化套件</span><span class="sxs-lookup"><span data-stu-id="a0503-106">Desktop Optimization Pack</span></span>](https://www.microsoft.com/download/details.aspx?id=57157)

> [!NOTE]
> <span data-ttu-id="a0503-107">如需有關修補程式版本的詳細資訊，請參閱[MBAM 版本圖表](https://docs.microsoft.com/archive/blogs/dubaisec/mbam-version-chart)。</span><span class="sxs-lookup"><span data-stu-id="a0503-107">For more information about the hotfix releases, see the [MBAM version chart](https://docs.microsoft.com/archive/blogs/dubaisec/mbam-version-chart).</span></span>

#### <span data-ttu-id="a0503-108">更新現有 MBAM 環境之 MBAM 伺服器的步驟</span><span class="sxs-lookup"><span data-stu-id="a0503-108">Steps to update the MBAM Server for existing MBAM environment</span></span> 
1. <span data-ttu-id="a0503-109">移除 MBAM server 功能（若要執行此動作，請開啟 [MBAM 伺服器設定] 工具，然後選取 [移除功能]）。</span><span class="sxs-lookup"><span data-stu-id="a0503-109">Remove MBAM server feature (do this by opening the MBAM Server Configuration Tool, then selecting Remove Features).</span></span>
2. <span data-ttu-id="a0503-110">從 [控制台] 中移除 [MDOP MBAM] |程式和功能。</span><span class="sxs-lookup"><span data-stu-id="a0503-110">Remove MDOP MBAM from Control Panel | Programs and Features.</span></span>
3. <span data-ttu-id="a0503-111">安裝 MBAM 2.5 SP1 RTM 伺服器元件。</span><span class="sxs-lookup"><span data-stu-id="a0503-111">Install MBAM 2.5 SP1 RTM server components.</span></span>
4. <span data-ttu-id="a0503-112">安裝 lastest MBAM 2.5 SP1 中的修補程式匯總。</span><span class="sxs-lookup"><span data-stu-id="a0503-112">Install lastest MBAM 2.5 SP1 hotfix rollup.</span></span>
5. <span data-ttu-id="a0503-113">使用 MBAM 伺服器配置器設定 MBAM 功能。</span><span class="sxs-lookup"><span data-stu-id="a0503-113">Configure MBAM features using MBAM Server Configurator.</span></span>

#### <span data-ttu-id="a0503-114">安裝新的 MBAM 2.5 SP1 server 修復程式的步驟</span><span class="sxs-lookup"><span data-stu-id="a0503-114">Steps to install the new MBAM 2.5 SP1 server hotfix</span></span>
<span data-ttu-id="a0503-115">請參閱檔以瞭解[新的伺服器安裝](deploying-the-mbam-25-server-infrastructure.md)。</span><span class="sxs-lookup"><span data-stu-id="a0503-115">Refer to the document for [new server installation](deploying-the-mbam-25-server-infrastructure.md).</span></span>
