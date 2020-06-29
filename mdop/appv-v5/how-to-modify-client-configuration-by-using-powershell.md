---
title: 如何使用 PowerShell 來修改用戶端組態
description: 如何使用 PowerShell 來修改用戶端組態
author: dansimp
ms.assetid: 53ccb2cf-ef81-4310-a853-efcb395f006e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b5d3173944abfe2c2b3d30aa9654dae81f204a32
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800441"
---
# <span data-ttu-id="2839c-103">如何使用 PowerShell 來修改用戶端組態</span><span class="sxs-lookup"><span data-stu-id="2839c-103">How to Modify Client Configuration by Using PowerShell</span></span>


<span data-ttu-id="2839c-104">使用下列程式來設定 App-v 5.0 用戶端配置。</span><span class="sxs-lookup"><span data-stu-id="2839c-104">Use the following procedure to configure the App-V 5.0 client configuration.</span></span>

**<span data-ttu-id="2839c-105">使用 PowerShell 修改 App-v 5.0 用戶端設定</span><span class="sxs-lookup"><span data-stu-id="2839c-105">To modify App-V 5.0 client configuration using PowerShell</span></span>**

1.  <span data-ttu-id="2839c-106">若要使用 PowerShell 設定用戶端設定，請使用**AppvClientConfiguration** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2839c-106">To configure the client settings using PowerShell, use the **Set-AppvClientConfiguration** cmdlet.</span></span>

2.  <span data-ttu-id="2839c-107">若要修改用戶端設定，請開啟 PowerShell 命令提示字元，並執行下列 Cmdlet **AppvClientConfiguration** ，並使用任何必要的參數。</span><span class="sxs-lookup"><span data-stu-id="2839c-107">To modify the client configuration, open a PowerShell Command prompt and run the following cmdlet **Set-AppvClientConfiguration** with any required parameters.</span></span> <span data-ttu-id="2839c-108">例如：</span><span class="sxs-lookup"><span data-stu-id="2839c-108">For example:</span></span>

    `$config = Get-AppvClientConfiguration`

    `Set-AppvClientConfiguration $config`

    `Set-AppvClientConfiguration –AutoLoad 2`

    <span data-ttu-id="2839c-109">您**有應用程式-V 的建議**嗎？</span><span class="sxs-lookup"><span data-stu-id="2839c-109">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="2839c-110">在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="2839c-110">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="2839c-111">有應用程式-V 問題嗎？</span><span class="sxs-lookup"><span data-stu-id="2839c-111">Got an App-V issue?</span></span>** <span data-ttu-id="2839c-112">使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="2839c-112">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="2839c-113">相關主題</span><span class="sxs-lookup"><span data-stu-id="2839c-113">Related topics</span></span>


[<span data-ttu-id="2839c-114">App-V 5.0 作業</span><span class="sxs-lookup"><span data-stu-id="2839c-114">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

 

 





