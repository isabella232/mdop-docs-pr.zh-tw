---
title: 如何使用 PowerShell 來修改用戶端組態
description: 如何使用 PowerShell 來修改用戶端組態
author: dansimp
ms.assetid: c3a59592-bb0d-43b6-8f4e-44f3a2d5b7ea
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 368a0d12c12e10a623afad3f9040ae01cee6cb38
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800437"
---
# <span data-ttu-id="a8dd9-103">如何使用 PowerShell 來修改用戶端組態</span><span class="sxs-lookup"><span data-stu-id="a8dd9-103">How to Modify Client Configuration by Using PowerShell</span></span>


<span data-ttu-id="a8dd9-104">使用下列程式來設定 App-v 5.1 用戶端配置。</span><span class="sxs-lookup"><span data-stu-id="a8dd9-104">Use the following procedure to configure the App-V 5.1 client configuration.</span></span>

**<span data-ttu-id="a8dd9-105">使用 PowerShell 修改 App-v 5.1 用戶端設定</span><span class="sxs-lookup"><span data-stu-id="a8dd9-105">To modify App-V 5.1 client configuration using PowerShell</span></span>**

1.  <span data-ttu-id="a8dd9-106">若要使用 PowerShell 設定用戶端設定，請使用**AppvClientConfiguration** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a8dd9-106">To configure the client settings using PowerShell, use the **Set-AppvClientConfiguration** cmdlet.</span></span> <span data-ttu-id="a8dd9-107">如需安裝 PowerShell 及 Cmdlet 清單的詳細資訊，請參閱[如何載入 Powershell Cmdlet 及取得 Cmdlet 說明](how-to-load-the-powershell-cmdlets-and-get-cmdlet-help-51.md)。</span><span class="sxs-lookup"><span data-stu-id="a8dd9-107">For more information about installing PowerShell, and a list of cmdlets see, [How to Load the PowerShell Cmdlets and Get Cmdlet Help](how-to-load-the-powershell-cmdlets-and-get-cmdlet-help-51.md).</span></span>

2.  <span data-ttu-id="a8dd9-108">若要修改用戶端設定，請開啟 PowerShell 命令提示字元，並執行下列 Cmdlet **AppvClientConfiguration** ，並使用任何必要的參數。</span><span class="sxs-lookup"><span data-stu-id="a8dd9-108">To modify the client configuration, open a PowerShell Command prompt and run the following cmdlet **Set-AppvClientConfiguration** with any required parameters.</span></span> <span data-ttu-id="a8dd9-109">例如：</span><span class="sxs-lookup"><span data-stu-id="a8dd9-109">For example:</span></span>

    `$config = Get-AppvClientConfiguration`

    `Set-AppvClientConfiguration $config`

    `Set-AppvClientConfiguration –AutoLoad 2`

    <span data-ttu-id="a8dd9-110">您**有應用程式-V 的建議**嗎？</span><span class="sxs-lookup"><span data-stu-id="a8dd9-110">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="a8dd9-111">在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="a8dd9-111">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="a8dd9-112">有應用程式-V 問題嗎？</span><span class="sxs-lookup"><span data-stu-id="a8dd9-112">Got an App-V issue?</span></span>** <span data-ttu-id="a8dd9-113">使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="a8dd9-113">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="a8dd9-114">相關主題</span><span class="sxs-lookup"><span data-stu-id="a8dd9-114">Related topics</span></span>


[<span data-ttu-id="a8dd9-115">App-V 5.1 作業</span><span class="sxs-lookup"><span data-stu-id="a8dd9-115">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)

 

 





