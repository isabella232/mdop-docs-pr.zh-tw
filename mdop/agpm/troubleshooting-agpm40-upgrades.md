---
title: 疑難排解 AGPM 升級
description: 疑難排解 AGPM 升級
author: dansimp
ms.assetid: 1abbf0c1-fd32-46a8-a3ba-c005f066523d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2089eac51803dca60da51f61ebdb112fbf0bda08
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801741"
---
# <span data-ttu-id="8ddb9-103">疑難排解 AGPM 升級</span><span class="sxs-lookup"><span data-stu-id="8ddb9-103">Troubleshooting AGPM Upgrades</span></span>

<span data-ttu-id="8ddb9-104">本節列出當您將高級群組原則管理（AGPM）伺服器升級至較新版本（例如，AGPM 4.0 至 AGPM 4.3）時可能會遇到的常見問題。</span><span class="sxs-lookup"><span data-stu-id="8ddb9-104">This section lists common issues that you may encounter when you upgrade your Advanced Group Policy Management (AGPM) server to a newer version (e.g. AGPM 4.0 to AGPM 4.3).</span></span> <span data-ttu-id="8ddb9-105">若要診斷此處未列出的問題，請查看[疑難排解 AGPM](troubleshooting-agpm-agpm40.md)或 AGPM 系統管理員（完全控制），以使用記錄和追蹤功能。</span><span class="sxs-lookup"><span data-stu-id="8ddb9-105">To diagnose issues not listed here, it may be helpful to view the [Troubleshooting AGPM](troubleshooting-agpm-agpm40.md) or for an AGPM Administrator (Full Control) to use logging and tracing.</span></span> <span data-ttu-id="8ddb9-106">如需詳細資訊，請參閱[設定記錄和追蹤](configure-logging-and-tracing-agpm40.md)。</span><span class="sxs-lookup"><span data-stu-id="8ddb9-106">For more information, see [Configure Logging and Tracing](configure-logging-and-tracing-agpm40.md).</span></span>

## <span data-ttu-id="8ddb9-107">您遇到什麼問題？</span><span class="sxs-lookup"><span data-stu-id="8ddb9-107">What problems are you having?</span></span>

-   [<span data-ttu-id="8ddb9-108">無法產生 HTML GPO 差異報告（錯誤碼80004003）</span><span class="sxs-lookup"><span data-stu-id="8ddb9-108">Failed to generate a HTML GPO difference report (Error code 80004003)</span></span>](#bkmk-error-80004003)

### <a href="" id="bkmk-error-80004003"></a><span data-ttu-id="8ddb9-109">無法產生 HTML GPO 差異報告（錯誤碼80004003）</span><span class="sxs-lookup"><span data-stu-id="8ddb9-109">Failed to generate a HTML GPO difference report (Error code 80004003)</span></span>

-   <span data-ttu-id="8ddb9-110">**原因**：您已使用錯誤的帳戶安裝 AGPM 升級套件。</span><span class="sxs-lookup"><span data-stu-id="8ddb9-110">**Cause**: You have installed the AGPM upgrade package with an incorrect account.</span></span>

-   <span data-ttu-id="8ddb9-111">**解決方案**：您必須是 AGPM 系統管理員才能修正這個問題。</span><span class="sxs-lookup"><span data-stu-id="8ddb9-111">**Solution**: You will need to be an AGPM administrator in order to fix this issue.</span></span>
    
    -   <span data-ttu-id="8ddb9-112">確定您知道**AGPM 服務帳戶**的使用者名稱 & 密碼。</span><span class="sxs-lookup"><span data-stu-id="8ddb9-112">Ensure you know the username & password of your **AGPM service account**.</span></span>

    -   <span data-ttu-id="8ddb9-113">以您的 AGPM 服務帳戶的形式，以互動方式登入您的 AGPM 服務器。</span><span class="sxs-lookup"><span data-stu-id="8ddb9-113">Log onto your AGPM server interactively as your AGPM service account.</span></span>
        
        -   <span data-ttu-id="8ddb9-114">這極其重要，因為如果您使用不同的帳戶，安裝將會失敗。</span><span class="sxs-lookup"><span data-stu-id="8ddb9-114">This is critically important, as the install will fail if you use a different account.</span></span>

    -   <span data-ttu-id="8ddb9-115">關閉 AGPM 服務。</span><span class="sxs-lookup"><span data-stu-id="8ddb9-115">Shutdown the AGPM service.</span></span>
    
    -   <span data-ttu-id="8ddb9-116">安裝必要的修復程式。</span><span class="sxs-lookup"><span data-stu-id="8ddb9-116">Install the required hotfix.</span></span>
    
    -   <span data-ttu-id="8ddb9-117">使用 AGPM 用戶端連線至 AGPM，以測試您的差異報告現已正常運作。</span><span class="sxs-lookup"><span data-stu-id="8ddb9-117">Connect to AGPM using an AGPM client to test that your difference reports are now functioning.</span></span>
    
## <span data-ttu-id="8ddb9-118">安裝 Microsoft 高級群組原則管理 4.0 SP3 的修補程式套件1</span><span class="sxs-lookup"><span data-stu-id="8ddb9-118">Install Hotfix Package 1 for Microsoft Advanced Group Policy Management 4.0 SP3</span></span>
    
<span data-ttu-id="8ddb9-119">**此修復程式中修正的問題**：當您控制或管理新的群組原則物件（gpo）時，AGPM 無法產生差異報告。</span><span class="sxs-lookup"><span data-stu-id="8ddb9-119">**Issue fixed in this hotfix**: AGPM can't generate difference reports when it controls or manages new Group Policy Objects (GPOs).</span></span>

<span data-ttu-id="8ddb9-120">**如何取得此更新**：安裝最新版本的 Microsoft 桌面優化套件（[2017 年3月服務版本](https://www.microsoft.com/download/details.aspx?id=54967)）。</span><span class="sxs-lookup"><span data-stu-id="8ddb9-120">**How to get this update**: Install the latest version of Microsoft Desktop Optimization Pack ([March 2017 Servicing Release](https://www.microsoft.com/download/details.aspx?id=54967)).</span></span> <span data-ttu-id="8ddb9-121">如需詳細資訊，請參閱[KB 4014009](https://support.microsoft.com/help/4014009/) 。</span><span class="sxs-lookup"><span data-stu-id="8ddb9-121">See [KB 4014009](https://support.microsoft.com/help/4014009/) for more information.</span></span>

<span data-ttu-id="8ddb9-122">更明確地說，您可以選擇只下載第一個檔案， `AGPM4.0SP1_Server_X64_KB4014009.exe` 從按下 [下載] 按鈕之後所顯示的清單中。</span><span class="sxs-lookup"><span data-stu-id="8ddb9-122">More specifically, you can choose to download only the first file, `AGPM4.0SP1_Server_X64_KB4014009.exe`, from the list presented after pressing the download button.</span></span>
      
<span data-ttu-id="8ddb9-123">您可以在[這裡](https://www.microsoft.com/download/details.aspx?id=54967)找到 Microsoft 桌面優化套件（2017年3月服務發行）的下載連結。</span><span class="sxs-lookup"><span data-stu-id="8ddb9-123">The download link to the Microsoft Desktop Optimization Pack (March 2017 Servicing Release) can be found [here](https://www.microsoft.com/download/details.aspx?id=54967).</span></span>
      
      
## <span data-ttu-id="8ddb9-124">參照連結</span><span class="sxs-lookup"><span data-stu-id="8ddb9-124">Reference link</span></span>
https://support.microsoft.com/help/3127165/hotfix-package-1-for-microsoft-advanced-group-policy-management-4-0-sp
      
