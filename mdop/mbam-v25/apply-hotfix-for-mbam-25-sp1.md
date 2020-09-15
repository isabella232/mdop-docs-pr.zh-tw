---
title: 在 MBAM 2.5 SP1 上套用 Hotfix
description: 在 MBAM 2.5 SP1 上套用 Hotfix
ms.author: dansimp
author: dansimp
ms.assetid: ''
ms.reviewer: ''
manager: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 8/30/2018
ms.openlocfilehash: ea564d93a3eec6a46ec7d4c1be0f794abba9c93e
ms.sourcegitcommit: 8ecbf818a6ff2ddafd80b93614c01256484737ad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/14/2020
ms.locfileid: "11014987"
---
# <span data-ttu-id="322e3-103">在 MBAM 2.5 SP1 上套用 Hotfix</span><span class="sxs-lookup"><span data-stu-id="322e3-103">Applying hotfixes on MBAM 2.5 SP1</span></span>
<span data-ttu-id="322e3-104">本主題描述在 MBAM) Server 2.5 SP1 中套用 Microsoft BitLocker 管理和監控 (的程式的處理常式</span><span class="sxs-lookup"><span data-stu-id="322e3-104">This topic describes the process for applying the hotfixes for Microsoft BitLocker Administration and Monitoring (MBAM) Server 2.5 SP1</span></span>

### <span data-ttu-id="322e3-105">在開始之前，請先在 MBAM) Server 2.5 SP1 中下載 Microsoft BitLocker 管理和監視 (的最新修復程式</span><span class="sxs-lookup"><span data-stu-id="322e3-105">Before you begin, download the latest hotfix of Microsoft BitLocker Administration and Monitoring (MBAM) Server 2.5 SP1</span></span>
[<span data-ttu-id="322e3-106">桌面優化套件</span><span class="sxs-lookup"><span data-stu-id="322e3-106">Desktop Optimization Pack</span></span>](https://www.microsoft.com/download/details.aspx?id=57157)

> [!NOTE]
> <span data-ttu-id="322e3-107">如需有關修補程式版本的詳細資訊，請參閱 [MBAM 版本圖表](https://docs.microsoft.com/archive/blogs/dubaisec/mbam-version-chart)。</span><span class="sxs-lookup"><span data-stu-id="322e3-107">For more information about the hotfix releases, see the [MBAM version chart](https://docs.microsoft.com/archive/blogs/dubaisec/mbam-version-chart).</span></span>

#### <span data-ttu-id="322e3-108">更新現有 MBAM 環境之 MBAM 伺服器的步驟</span><span class="sxs-lookup"><span data-stu-id="322e3-108">Steps to update the MBAM Server for existing MBAM environment</span></span> 
1. <span data-ttu-id="322e3-109">移除 MBAM server 功能 (執行此動作的方法是開啟 [MBAM 伺服器設定] 工具，然後選取 [移除功能]) 。</span><span class="sxs-lookup"><span data-stu-id="322e3-109">Remove MBAM server feature (do this by opening the MBAM Server Configuration Tool, then selecting Remove Features).</span></span>
2. <span data-ttu-id="322e3-110">從 [控制台] 中移除 [MDOP MBAM] |程式和功能。</span><span class="sxs-lookup"><span data-stu-id="322e3-110">Remove MDOP MBAM from Control Panel | Programs and Features.</span></span>
3. <span data-ttu-id="322e3-111">安裝 MBAM 2.5 SP1 RTM 伺服器元件。</span><span class="sxs-lookup"><span data-stu-id="322e3-111">Install MBAM 2.5 SP1 RTM server components.</span></span>
4. <span data-ttu-id="322e3-112">安裝 lastest MBAM 2.5 SP1 中的修補程式匯總。</span><span class="sxs-lookup"><span data-stu-id="322e3-112">Install lastest MBAM 2.5 SP1 hotfix rollup.</span></span>
5. <span data-ttu-id="322e3-113">使用 MBAM 伺服器配置器設定 MBAM 功能。</span><span class="sxs-lookup"><span data-stu-id="322e3-113">Configure MBAM features using MBAM Server Configurator.</span></span>

#### <span data-ttu-id="322e3-114">安裝新的 MBAM 2.5 SP1 server 修復程式的步驟</span><span class="sxs-lookup"><span data-stu-id="322e3-114">Steps to install the new MBAM 2.5 SP1 server hotfix</span></span>
<span data-ttu-id="322e3-115">請參閱檔以瞭解 [新的伺服器安裝](deploying-the-mbam-25-server-infrastructure.md)。</span><span class="sxs-lookup"><span data-stu-id="322e3-115">Refer to the document for [new server installation](deploying-the-mbam-25-server-infrastructure.md).</span></span>
