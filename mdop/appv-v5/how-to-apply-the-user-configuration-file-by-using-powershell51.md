---
title: 如何使用 PowerShell 來套用使用者設定檔案
description: 如何使用 PowerShell 來套用使用者設定檔案
author: dansimp
ms.assetid: 986e638c-4a0c-4a7e-be73-f4615e8b8000
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 97b3db253993d6d855384ee5d9771a7f9ff5b64d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800591"
---
# <span data-ttu-id="f0021-103">如何使用 PowerShell 來套用使用者設定檔案</span><span class="sxs-lookup"><span data-stu-id="f0021-103">How to Apply the User Configuration File by Using PowerShell</span></span>


<span data-ttu-id="f0021-104">當套件發佈至特定使用者並決定套件的執行方式時，就會套用動態使用者設定檔。</span><span class="sxs-lookup"><span data-stu-id="f0021-104">The dynamic user configuration file is applied when a package is published to a specific user and determines how the package will run.</span></span>

<span data-ttu-id="f0021-105">使用下列程式來指定使用者專用的設定檔。</span><span class="sxs-lookup"><span data-stu-id="f0021-105">Use the following procedure to specify a user-specific configuration file.</span></span> <span data-ttu-id="f0021-106">下列程式是以範例為基礎：</span><span class="sxs-lookup"><span data-stu-id="f0021-106">The following procedure is based on the example:</span></span>

**<span data-ttu-id="f0021-107">c:\\Packages\\Contoso\\MyApp.appv</span><span class="sxs-lookup"><span data-stu-id="f0021-107">c:\\Packages\\Contoso\\MyApp.appv</span></span>**

**<span data-ttu-id="f0021-108">若要套用使用者設定檔</span><span class="sxs-lookup"><span data-stu-id="f0021-108">To apply a user Configuration file</span></span>**

1.  <span data-ttu-id="f0021-109">若要使用 PowerShell 主控台將套件新增到電腦，請輸入以下命令：</span><span class="sxs-lookup"><span data-stu-id="f0021-109">To add the package to the computer using the PowerShell console type the following command:</span></span>

    <span data-ttu-id="f0021-110">**AppVClientPackage c:\\Packages\\Contoso\\MyApp.appv**。</span><span class="sxs-lookup"><span data-stu-id="f0021-110">**Add-AppVClientPackage c:\\Packages\\Contoso\\MyApp.appv**.</span></span>

2.  <span data-ttu-id="f0021-111">使用下列命令將套件發佈給使用者，並指定更新的動態使用者設定檔案：</span><span class="sxs-lookup"><span data-stu-id="f0021-111">Use the following command to publish the package to the user and specify the updated the dynamic user configuration file:</span></span>

    **<span data-ttu-id="f0021-112">發佈-AppVClientPackage $pkg – DynamicUserConfigurationPath c:\\Packages\\Contoso\\config.xml</span><span class="sxs-lookup"><span data-stu-id="f0021-112">Publish-AppVClientPackage $pkg –DynamicUserConfigurationPath c:\\Packages\\Contoso\\config.xml</span></span>**

    <span data-ttu-id="f0021-113">您**有應用程式-V 的建議**嗎？</span><span class="sxs-lookup"><span data-stu-id="f0021-113">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="f0021-114">在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="f0021-114">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="f0021-115">有應用程式-V 問題嗎？</span><span class="sxs-lookup"><span data-stu-id="f0021-115">Got an App-V issue?</span></span>** <span data-ttu-id="f0021-116">使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="f0021-116">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="f0021-117">相關主題</span><span class="sxs-lookup"><span data-stu-id="f0021-117">Related topics</span></span>


[<span data-ttu-id="f0021-118">App-V 5.1 作業</span><span class="sxs-lookup"><span data-stu-id="f0021-118">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)

 

 





