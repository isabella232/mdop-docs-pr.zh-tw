---
title: 如何使用 PowerShell 來套用部署設定檔案
description: 如何使用 PowerShell 來套用部署設定檔案
author: dansimp
ms.assetid: 5df5d5bc-6c72-4087-8b93-d6d4b502a1f4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b6764f07dfe8cff1fb30c354937a405202468428
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800595"
---
# <span data-ttu-id="161ad-103">如何使用 PowerShell 來套用部署設定檔案</span><span class="sxs-lookup"><span data-stu-id="161ad-103">How to Apply the Deployment Configuration File by Using PowerShell</span></span>


<span data-ttu-id="161ad-104">在已發佈套件之前，當您在執行 App-v 5.0 用戶端的電腦上新增或設定套件時，就會套用動態部署設定檔。</span><span class="sxs-lookup"><span data-stu-id="161ad-104">The dynamic deployment configuration file is applied when a package is added or set to a computer running the App-V 5.0 client before the package has been published.</span></span> <span data-ttu-id="161ad-105">此檔案會針對執行 App-v 5.0 用戶端的電腦上的所有使用者，設定封裝的預設設定。</span><span class="sxs-lookup"><span data-stu-id="161ad-105">The file configures the default settings for package for all users on the computer running the App-V 5.0 client.</span></span> <span data-ttu-id="161ad-106">本節說明使用部署設定檔的步驟。</span><span class="sxs-lookup"><span data-stu-id="161ad-106">This section describes the steps used to use a deployment configuration file.</span></span> <span data-ttu-id="161ad-107">程式會根據下列範例進行，並假設電腦上存在下列套件和設定檔：</span><span class="sxs-lookup"><span data-stu-id="161ad-107">The procedure is based on the following example and assumes the following package and configuration files exist on a computer:</span></span>

**<span data-ttu-id="161ad-108">c:\\Packages\\Contoso\\MyApp.appv</span><span class="sxs-lookup"><span data-stu-id="161ad-108">c:\\Packages\\Contoso\\MyApp.appv</span></span>**

**<span data-ttu-id="161ad-109">c:\\Packages\\Contoso\\DynamicConfigurations\\deploymentconfig.xml</span><span class="sxs-lookup"><span data-stu-id="161ad-109">c:\\Packages\\Contoso\\DynamicConfigurations\\deploymentconfig.xml</span></span>**

**<span data-ttu-id="161ad-110">使用 PowerShell 來套用部署設定檔</span><span class="sxs-lookup"><span data-stu-id="161ad-110">To Apply the Deployment Configuration File Using PowerShell</span></span>**

-   <span data-ttu-id="161ad-111">若要針對將在特定電腦上執行套件的所有使用者指定一組新的預設設定，請輸入下列專案：</span><span class="sxs-lookup"><span data-stu-id="161ad-111">To specify a new default set of configurations for all users who will run the package on a specific computer, using a PowerShell console type the following:</span></span>

    **<span data-ttu-id="161ad-112">AppVClientPackage – Path c:\\Packages\\Contoso\\MyApp.appv-DynamicDeploymentConfiguration c:\\Packages\\Contoso\\DynamicConfigurations\\deploymentconfig.xml</span><span class="sxs-lookup"><span data-stu-id="161ad-112">Add-AppVClientPackage –Path c:\\Packages\\Contoso\\MyApp.appv -DynamicDeploymentConfiguration c:\\Packages\\Contoso\\DynamicConfigurations\\deploymentconfig.xml</span></span>**

    **<span data-ttu-id="161ad-113">注意</span><span class="sxs-lookup"><span data-stu-id="161ad-113">Note</span></span>**  
    <span data-ttu-id="161ad-114">這個命令會將產生的物件捕獲到 $pkg 中。</span><span class="sxs-lookup"><span data-stu-id="161ad-114">This command captures the resulting object into $pkg.</span></span> <span data-ttu-id="161ad-115">如果套件已存在於電腦上，可以使用 AppVclientPackage Cmdlet 來套用部署**設定**檔：</span><span class="sxs-lookup"><span data-stu-id="161ad-115">If the package is already present on the computer, the **Set-AppVclientPackage** cmdlet can be used to apply the deployment configuration document:</span></span>

    **<span data-ttu-id="161ad-116">AppVClientPackage – Name Myapp-Path c:\\Packages\\Contoso\\MyApp.appv-DynamicDeploymentConfiguration c:\\Packages\\Contoso\\DynamicConfigurations\\deploymentconfig.xml</span><span class="sxs-lookup"><span data-stu-id="161ad-116">Set-AppVClientPackage –Name Myapp –Path c:\\Packages\\Contoso\\MyApp.appv -DynamicDeploymentConfiguration c:\\Packages\\Contoso\\DynamicConfigurations\\deploymentconfig.xml</span></span>**



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## <span data-ttu-id="161ad-117">相關主題</span><span class="sxs-lookup"><span data-stu-id="161ad-117">Related topics</span></span>


[<span data-ttu-id="161ad-118">App-V 5.0 作業</span><span class="sxs-lookup"><span data-stu-id="161ad-118">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)









